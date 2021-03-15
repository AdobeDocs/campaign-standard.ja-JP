---
solution: Campaign Standard
product: campaign
title: モバイルアプリケーションデータに基づくプロファイル情報の作成と更新
description: モバイルアプリケーションデータに基づいてプロファイル情報を作成および更新する方法について説明します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: プッシュ
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 4%

---


# モバイルアプリケーションデータに基づくプロファイル情報の作成と更新

## 概要

このページでは、モバイルアプリケーションがPIIデータを収集した後にスケジュールに基づいてプロファイルデータを作成/更新するワークフローを開発する手順について説明します。

* **PIIは「** 個人が特定できる情報」を表します。例えば、Analytics for Mobile [目標地点](../../integrating/using/about-campaign-points-of-interest-data-integration.md)のように、キャンペーンデータベースのプロファイルテーブルに表示されない情報を含め、任意のデータを指定できます。 PIIは、モバイルアプリ開発者（通常はマーケティング担当者）が定義します。
* **モバイルアプリから** PIIを収集するは、Adobe Campaign StandardのRest APIへのHTTPPOST操作です。

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

この例では、**[!UICONTROL Fields]**&#x200B;セクションにはモバイルアプリケーションから送信されるPIIデータが反映されています。 **[!UICONTROL Link to profiles]**&#x200B;セクションは、PIIとプロファイルデータの関連付けに使用するフィールドを示します。**cusEmail**&#x200B;は&#x200B;**@email**&#x200B;に対応付けられます。

**[!UICONTROL Subscriptions to an Application]**&#x200B;リソースを拡張する際のプロファイルデータのマッピングは読み取り専用です。 それは和解に使われる。 プロファイルとPIIデータを調整するには、プロファイルを必要なデータと共にシステムに入力する必要があります。 この場合、調整を行うには、プロファイルの電子メールアドレスがCollect PIIからの電子メールと一致する必要があります。

* PIIをモバイルアプリから受け取ったユーザーの名は「Jane」、姓は「Doe」、電子メールアドレスは「janedoe@doe.com」です。
* 別に、プロファイルの電子メールアドレスがjanedoe@doe.comであるプロファイルデータが存在する必要があります（例えば、データを手動で入力する必要がある場合や、既に他のリソースから取得している場合）。

**関連トピック：**

* [アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [既存のリソースを作成または拡張します](../../developing/using/key-steps-to-add-a-resource.md)。

## 手順2 — ワークフローを作成する

Campaign Standardでワークフローを使用すると、管理者はAppSubscription（購読者）データとプロファイルまたは受信者データの間でデータを一意に識別し、同期できます。 ワークフローベースの更新では、プロファイルデータがリアルタイムで同期されませんが、データベースのロックやオーバーヘッドが不必要になることはありません。

ワークフローを構築する主な手順は次のとおりです。

1. **[!UICONTROL Query]**&#x200B;または&#x200B;**[!UICONTROL Incremental query]**&#x200B;アクティビティを使用して、最新購読のリストを取得します。
1. **[!UICONTROL Reconciliation]**&#x200B;アクティビティを使用して、PIIデータをプロファイルにマッピングします。
1. 追加検証プロセス。
1. **[!UICONTROL Update data]**&#x200B;を使用して、PIIデータを使用してプロファイルを更新または作成します。

このワークフローでは、次の要件を前提としています。

* 拡張された任意の/すべてのフィールドを使用して、プロファイルテーブルを作成/更新できる必要があります。
* ネイティブでサポートされていないフィールド（例えば、Tシャツのサイズ）をサポートするようにプロファイルテーブルを拡張できます。
* AppSubscriptionテーブルの空白のフィールドは、プロファイルテーブルで更新しないでください。
* AppSubscriptionテーブルで更新されたレコードは、ワークフローの次回の実行に含める必要があります。

ワークフローを構築するには、次のアクティビティをワークスペースにドラッグ&amp;ドロップし、それらをリンクします。**[!UICONTROL Start]**、**[!UICONTROL Scheduler]**、**[!UICONTROL Incremental query]**、**[!UICONTROL Update data]**。

![](assets/update_profile0.png)

次に、次の手順に従って各アクティビティを設定します。

### **[!UICONTROL Scheduler]**&#x200B;アクティビティを設定

**[!UICONTROL General]**&#x200B;タブで、**[!UICONTROL Execution frequency]**（例：「毎日」）、**[!UICONTROL Time]**（例：「1:00:00 AM」）、**[!UICONTROL Start]**（例：今日の日付）を設定します。

![](assets/update_profile2.png)

### **[!UICONTROL Incremental query]**&#x200B;アクティビティを設定します。

1. 「**[!UICONTROL Properties]**」タブで、**[!UICONTROL Resource]**&#x200B;フィールドの&#x200B;**[!UICONTROL Select an element]**&#x200B;アイコンをクリックし、**[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]**&#x200B;要素を選択します。

   ![](assets/update_profile3.png)

1. 「**[!UICONTROL Target]**」タブで、**[!UICONTROL Mobile application]**&#x200B;フィルターをドラッグし、モバイルアプリ名を選択します。

   ![](assets/update_profile4.png)

1. 「**[!UICONTROL Processed data]**」タブで「**[!UICONTROL Use a date field]**」を選択し、**[!UICONTROL Last modified (lastModified)]**&#x200B;フィールドを&#x200B;**[!UICONTROL Path to the date field]**&#x200B;として追加します。

   ![](assets/update_profile5.png)

### **[!UICONTROL Update data]**&#x200B;アクティビティを設定します。

1. 「**[!UICONTROL Identification]**」タブで、**[!UICONTROL Dimension to update]**&#x200B;フィールドが「プロファイル(プロファイル)」に設定されていることを確認し、「**[!UICONTROL Create element]**」ボタンをクリックして、フィールドを調整条件として追加します。

   ![](assets/update_profile_createelement.png)

1. 「**[!UICONTROL Source]**」フィールドで、appSubscriptionRcpテーブルからフィールドを調整フィールドとして選択します。 プロファイルの電子メール、crmId、marketingCloudIdなどがあります。 この例では、「電子メール(cusEmail)」フィールドを使用します。

1. 「**[!UICONTROL Destination]**」フィールドで、プロファイルテーブルからフィールドを選択し、appSubscriptionRcpテーブルのデータを調整します。 プロファイルの電子メール、またはcrmId、marketingCloudIdなどの拡張フィールドを使用できます。 この例では、「電子メール（電子メール）」フィールドを選択して、appSubscriptionRcpテーブルの「電子メール(cusEmail)」フィールドにマッピングする必要があります。

   ![](assets/update_profile7.png)

1. 「**[!UICONTROL Fields to update]**」タブで「**[!UICONTROL Create element]**」ボタンをクリックし、appSubscriptionRcpテーブル（**[!UICONTROL Source]**&#x200B;フィールド）から取得されるフィールドを、プロファイルテーブル（**[!UICONTROL Destination]**&#x200B;フィールド）内の更新するフィールドにマッピングします。

1. **[!UICONTROL Enabled if]**&#x200B;フィールドに式を追加し、ソースフィールドに値が含まれている場合にのみ、プロファイルテーブルの対応するフィールドが更新されるようにします。 これを行うには、リストからフィールドを選択し、=&quot;&quot;式(式エディタのソースフィールドが`[target/@cusEmail]`の場合は、`[target/@cusEmail] != ''"`と入力してください)。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>この場合、ワークフローはUPSERTを実行しますが、**[!UICONTROL Incremental query]**データに基づいているため、挿入されるのは挿入だけです。 クエリを変更すると、挿入または更新するデータに影響を与える場合があります。
>また、「更新するフィールド」タブの設定により、特定の条件下で挿入または更新するフィールドが決まります。 これらの設定は、アプリケーションや顧客ごとに一意に指定できます。
>appSubscriptionRcpデータに基づいてプロファイルのレコードを更新すると、ユーザーの個人情報が検証なしに変更される可能性があるので、意図しない結果が生じる可能性があるので、これらの設定を行う場合は注意が必要です。

プロファイル内に挿入/更新するすべてのフィールドが追加されたら、**[!UICONTROL Confirm]**&#x200B;をクリックします。

![](assets/update_profile9.png)

ワークフローを保存し、**[!UICONTROL Start]**&#x200B;をクリックしてワークフローを実行します。

![](assets/update_profile10.png)
