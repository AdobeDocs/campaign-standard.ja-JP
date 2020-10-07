---
title: モバイルアプリケーションデータに基づくプロファイル情報の作成と更新
description: モバイルアプリケーションデータに基づいてプロファイル情報を作成および更新する方法について説明します。
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 4%

---


# モバイルアプリケーションデータに基づくプロファイル情報の作成と更新

## 概要

このページでは、モバイルアプリケーションがPIIデータを収集した後にスケジュールに基づいてプロファイルデータを作成/更新するワークフローを開発する手順について説明します。

* **PIIは** 、「個人を特定できる情報」の略です。 例えば、モバイル [目標地点分析など、キャンペーンデータベースからプロファイルテーブルに表示されない情報を含む、任意のデータを指定できます](../../integrating/using/about-campaign-points-of-interest-data-integration.md)。 PIIは、モバイルアプリ開発者（通常はマーケティング担当者）が定義します。
* **PIIの収集** (PII)は、Adobe Campaign StandardのREST APIに対するモバイルアプリからのHTTPPOST操作です。

この使用例の目標は、モバイルアプリケーションから返されるPIIデータにプロファイル関連のデータが含まれる場合に、Campaign Standardプロファイルを作成または更新することです。

## 前提条件

モバイルアプリの購読データに基づいてプロファイルを作成または更新する前に、Campaign Standardでプッシュ通知を有効にするには、いくつかの設定手順に従う必要があります。

1. [モバイルアプリの作成](../../administration/using/configuring-a-mobile-application.md)
1. [AdobeモバイルSDKをモバイルアプリケーションと統合し](https://helpx.adobe.com/jp/campaign/kb/integrate-mobile-sdk.html)ます。
1. [プッシュ通知を送信するAdobe Campaignを設定します](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.translate.html)。

## 手順1 — プッシュ通知/購読用のプロファイルリソースを拡張する

PIIデータを使用してプロファイルリソースを作成または更新するには、まず目的のフィールドを使用してプロファイルリソースを拡張する必要があります。 手順は次のとおりです。

* モバイルアプリケーションから送信されるPIIフィールドを識別します。
* PIIデータとプロファイルデータを関連付けるための調整に使用するフィールドを指定します。

![](assets/update_profile1.png)

この例では、この **[!UICONTROL Fields]** 節はモバイルアプリケーションから送信されるPIIデータを反映しています。 この **[!UICONTROL Link to profiles]** セクションは、PIIとプロファイルデータの関連付けに使用されるフィールドを示します。ここで、 **cusEmail** は@emailにマッピングされ ****&#x200B;ます。

プロファイルを拡張する際のリソースデータのマッピングは、 **[!UICONTROL Subscriptions to an Application]** 読み取り専用です。 それは和解に使われる。 プロファイルとPIIデータを調整するには、プロファイルを必要なデータと共にシステムに入力する必要があります。 この場合、調整を行うには、プロファイルの電子メールアドレスがCollect PIIからの電子メールと一致する必要があります。

* PIIをモバイルアプリから受け取ったユーザーの名は「Jane」、姓は「Doe」、電子メールアドレスは「janedoe@doe.com」です。
* 別に、プロファイルの電子メールアドレスがjanedoe@doe.comであるプロファイルデータが存在する必要があります（例えば、データを手動で入力する必要がある場合や、既に他のリソースから取得している場合）。

**関連トピック：**

* [アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [既存のリソースを作成または拡張します](../../developing/using/key-steps-to-add-a-resource.md)。

## 手順2 — ワークフローを作成する

Campaign Standardでワークフローを使用すると、管理者はAppSubscription（購読者）データとプロファイルまたは受信者データの間でデータを一意に識別し、同期できます。 ワークフローベースの更新では、プロファイルデータがリアルタイムで同期されませんが、データベースのロックやオーバーヘッドが不必要になることはありません。

ワークフローを構築する主な手順は次のとおりです。

1. または **[!UICONTROL Query]****[!UICONTROL Incremental query]** アクティビティを使用して、最新購読のリストを取得します。
1. アクティビティを使用して、PIIデータをプロファイルにマッピングします。 **[!UICONTROL Reconciliation]**
1. 追加検証プロセス。
1. PIIデータを使用し **[!UICONTROL Update data]** てプロファイルを更新または作成します。

このワークフローでは、次の要件を前提としています。

* 拡張された任意の/すべてのフィールドを使用して、プロファイルテーブルを作成/更新できる必要があります。
* ネイティブでサポートされていないフィールド（例えば、Tシャツのサイズ）をサポートするようにプロファイルテーブルを拡張できます。
* AppSubscriptionテーブルの空白のフィールドは、プロファイルテーブルで更新しないでください。
* AppSubscriptionテーブルで更新されたレコードは、ワークフローの次回の実行に含める必要があります。

ワークフローを構築するには、次のアクティビティをワークスペースにドラッグ&amp;ドロップし、それらをリンクします。 **[!UICONTROL Start]**、 **[!UICONTROL Scheduler]**、 **[!UICONTROL Incremental query]**、 **[!UICONTROL Update data]**。

![](assets/update_profile0.png)

次に、次の手順に従って各アクティビティを設定します。

### **[!UICONTROL Scheduler]** アクティビティの設定

「 **[!UICONTROL General]** 」タブで、 **[!UICONTROL Execution frequency]** （例：「日別」）、（例：「午前1:00:00」） **[!UICONTROL Time]** および（例：「今日の日付」） **[!UICONTROL Start]** を設定します。

![](assets/update_profile2.png)

### **[!UICONTROL Incremental query]** アクティビティを設定します

1. タブで、フ **[!UICONTROL Properties]** ィールドの **[!UICONTROL Select an element]** アイコンをクリックし、 **[!UICONTROL Resource]****[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 要素を選択します。

   ![](assets/update_profile3.png)

1. タブで、 **[!UICONTROL Target]****[!UICONTROL Mobile application]** フィルターをドラッグし、モバイルアプリ名を選択します。

   ![](assets/update_profile4.png)

1. タブでを選択し、 **[!UICONTROL Processed data]** フィールドをに追加し **[!UICONTROL Use a date field]****[!UICONTROL Last modified (lastModified)]****[!UICONTROL Path to the date field]**&#x200B;ます。

   ![](assets/update_profile5.png)

### **[!UICONTROL Update data]** アクティビティを設定します

1. タブで、 **[!UICONTROL Identification]** フィールドが「プロファイル(プロファイル)」に設定されていることを確認し、 **[!UICONTROL Dimension to update]****[!UICONTROL Create element]** ボタンをクリックしてフィールドを調整条件として追加します。

   ![](assets/update_profile_createelement.png)

1. この **[!UICONTROL Source]** フィールドで、appSubscriptionRcpテーブルからフィールドを調整フィールドとして選択します。 プロファイルの電子メール、crmId、marketingCloudIdなどがあります。 この例では、「電子メール(cusEmail)」フィールドを使用します。

1. この **[!UICONTROL Destination]** フィールドで、プロファイルテーブルからフィールドを選択して、appSubscriptionRcpテーブルのデータを調整します。 プロファイルの電子メール、またはcrmId、marketingCloudIdなどの拡張フィールドを使用できます。 この例では、「電子メール（電子メール）」フィールドを選択して、appSubscriptionRcpテーブルの「電子メール(cusEmail)」フィールドにマッピングする必要があります。

   ![](assets/update_profile7.png)

1. タブで **[!UICONTROL Fields to update]** ボタンをクリックし、appSubscriptionRcpテーブル( **[!UICONTROL Create element]** フィールド)から取得されるフィールドを、プロファイルテーブル（フィールド）内の更新するフィールドにマッピングし&#x200B;**[!UICONTROL Source]****[!UICONTROL Destination]** ます。

1. フィールドに式を追加し、プロファイルテーブル内の対応するフィールドが更新されるのは、ソースフィールドに値が含まれている場合のみにします。 **[!UICONTROL Enabled if]** これを行うには、リストからフィールドを選択し、=&quot;&quot;式(「ソース」フィールドが式エディタ `[target/@cusEmail]` にある場合は、必ず入力してく `[target/@cusEmail] != ''"`ださい)。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>この場合、ワークフローはUPSERTを実行しますが、データに基づくものなので、挿入される **[!UICONTROL Incremental query]** だけです。 クエリを変更すると、挿入または更新するデータに影響を与える場合があります。
>また、「更新するフィールド」タブの設定により、特定の条件下で挿入または更新するフィールドが決まります。 これらの設定は、アプリケーションや顧客ごとに一意に指定できます。
>appSubscriptionRcpデータに基づいてプロファイルのレコードを更新すると、ユーザーの個人情報が検証なしに変更される可能性があるので、意図しない結果が生じる可能性があるので、これらの設定を行う場合は注意が必要です。

プロファイルに挿入または更新するすべてのフィールドが追加されたら、をクリックし **[!UICONTROL Confirm]**&#x200B;ます。

![](assets/update_profile9.png)

ワークフローを保存し、をクリックしてワークフロー **[!UICONTROL Start]** を実行します。

![](assets/update_profile10.png)
