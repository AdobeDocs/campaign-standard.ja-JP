---
title: モバイルアプリケーションデータに基づくプロファイル情報の作成と更新
description: モバイルアプリケーションデータに基づいてプロファイル情報を作成および更新する方法について説明します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 1b48456e-9aae-485c-a7c4-7e3e2f53cbca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 4%

---

# モバイルアプリケーションデータに基づくプロファイル情報の作成と更新

## 概要

このページでは、モバイルアプリケーションがPII収集データをスケジュールに従って送信した後にプロファイルデータを作成/更新するワークフローを開発する手順について説明します。

* **** PIIは、「個人を特定できる情報」を表します。例えば、Analytics for Mobile [目標地点](../../integrating/using/about-campaign-points-of-interest-data-integration.md)など、Campaignデータベースのプロファイルテーブルに表示されない情報を含め、あらゆるデータを指定できます。 PIIは、モバイルアプリ開発者（通常はマーケター）が定義します。
* **PIIを収** 集は、モバイルアプリからAdobe Campaign StandardのRest APIに対するHTTPPOST操作です。

この使用例の目的は、モバイルアプリケーションから返されるPIIデータにプロファイル関連のデータが含まれる場合に、Campaign Standardプロファイルを作成または更新することです。

## 前提条件

モバイルアプリのサブスクリプションデータに基づいてプロファイルを作成または更新する前に、Campaign Standardでプッシュ通知を有効にするには、いくつかの設定手順を実行する必要があります。

1. [モバイルアプリの作成](../../administration/using/configuring-a-mobile-application.md)
1. [AdobeMobile SDKをモバイルアプリケーションと統合します](https://helpx.adobe.com/jp/campaign/kb/integrate-mobile-sdk.html)。
1. [プッシュ通知を送信するようにAdobe Campaignを設定します](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html)。

## 手順1 — プッシュ通知/サブスクリプションのプロファイルリソースの拡張

PIIデータを使用してプロファイルリソースを作成または更新するには、まず目的のフィールドを使用してプロファイルリソースを拡張する必要があります。 手順は次のとおりです。

* モバイルアプリケーションから送信されるPIIフィールドを特定します。
* PIIデータとプロファイルデータを関連付けるための紐付けに使用するフィールドを特定します。

![](assets/update_profile1.png)

この例の&#x200B;**[!UICONTROL Fields]**&#x200B;セクションは、モバイルアプリケーションから送信されたPIIデータを反映しています。 **[!UICONTROL Link to profiles]**&#x200B;セクションは、PIIをプロファイルデータに関連付けるために使用するフィールドを示します。**cusEmail**&#x200B;は&#x200B;**@email**&#x200B;にマッピングされます。

**[!UICONTROL Subscriptions to an Application]**&#x200B;リソースを拡張する際のプロファイルデータのマッピングは読み取り専用です。 紐付けに使用されます。 プロファイルとPIIデータを紐付けるには、必要なデータを使用してプロファイルをシステムに入力する必要があります。 この場合、紐付けをおこなうには、プロファイルの電子メールアドレスがCollect PIIの電子メールと一致する必要があります。

* Collect PIIは、ユーザーの名が「Jane」、姓が「Doe」、電子メールアドレスがjanedoe@doe.comのモバイルアプリから受け取ります。
* プロファイルの電子メールアドレスがjanedoe@doe.comの場合は、プロファイルデータが存在する必要があります（例えば、データは手動で入力するか、既に他のリソースから取得している必要があります）。

**関連トピック：**

* [アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [既存のリソースの作成または拡張](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

## 手順2 — ワークフローの作成

ワークフローをCampaign Standardで使用すると、管理者は、AppSubscription（購読者）データと、プロファイルまたは受信者データとの間でデータを一意に識別し、同期できます。 ワークフローベースの更新では、プロファイルデータはリアルタイムで同期されませんが、データベースの過度のロックやオーバーヘッドを引き起こすことはありません。

ワークフローを作成する主な手順は次のとおりです。

1. **[!UICONTROL Query]**&#x200B;または&#x200B;**[!UICONTROL Incremental query]**&#x200B;アクティビティを使用して、最新の購読のリストを取得します。
1. **[!UICONTROL Reconciliation]**&#x200B;アクティビティを使用して、PIIデータをプロファイルにマッピングします。
1. 検証プロセスを追加します。
1. **[!UICONTROL Update data]**&#x200B;を使用して、PIIデータを使用してプロファイルを更新または作成します。

このワークフローでは、次の要件を前提としています。

* 拡張されたすべてのフィールドを使用して、プロファイルテーブルを作成/更新できる必要があります。
* プロファイルテーブルを拡張して、ネイティブサポートされていないフィールド（Tシャツのサイズなど）をサポートできます。
* AppSubscriptionテーブルの空白のフィールドは、プロファイルテーブルでは更新されません。
* AppSubscriptionテーブルで更新されたレコードは、次回のワークフロー実行に含める必要があります。

ワークフローを構築するには、次のアクティビティをワークスペースにドラッグ&amp;ドロップし、リンクします。**[!UICONTROL Start]**、**[!UICONTROL Scheduler]**、**[!UICONTROL Incremental query]**、**[!UICONTROL Update data]**。

![](assets/update_profile0.png)

次に、以下の手順に従って各アクティビティを設定します。

### **[!UICONTROL Scheduler]**&#x200B;アクティビティを設定します

**[!UICONTROL General]**&#x200B;タブで、**[!UICONTROL Execution frequency]**（例：「日別」）、**[!UICONTROL Time]**（例：「1:00:午前0時」）、**[!UICONTROL Start]**（例：今日の日付）を設定します。

![](assets/update_profile2.png)

### **[!UICONTROL Incremental query]**&#x200B;アクティビティを設定します。

1. 「**[!UICONTROL Properties]**」タブで、「**[!UICONTROL Resource]**」フィールドの&#x200B;**[!UICONTROL Select an element]**&#x200B;アイコンをクリックし、**[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]**&#x200B;要素を選択します。

   ![](assets/update_profile3.png)

1. 「**[!UICONTROL Target]**」タブで、**[!UICONTROL Mobile application]**&#x200B;フィルターをドラッグし、モバイルアプリ名を選択します。

   ![](assets/update_profile4.png)

1. 「**[!UICONTROL Processed data]**」タブで「**[!UICONTROL Use a date field]**」を選択し、「**[!UICONTROL Last modified (lastModified)]**」フィールドに「**[!UICONTROL Path to the date field]**」を追加します。

   ![](assets/update_profile5.png)

### **[!UICONTROL Update data]**&#x200B;アクティビティを設定します。

1. 「**[!UICONTROL Identification]**」タブで、「**[!UICONTROL Dimension to update]**」フィールドが「Profiles (profile)」に設定されていることを確認し、「**[!UICONTROL Create element]**」ボタンをクリックして、フィールドを紐付け条件として追加します。

   ![](assets/update_profile_createelement.png)

1. **[!UICONTROL Source]**&#x200B;フィールドで、appSubscriptionRcpテーブルからフィールドを紐付けフィールドとして選択します。 プロファイルの電子メール、crmId、marketingCloudIdなどがあります。 この例では、「Eメール(cusEmail)」フィールドを使用します。

1. 「 **[!UICONTROL Destination]** 」フィールドで、プロファイルテーブルからフィールドを選択し、 appSubscriptionRcpテーブルからのデータを紐付けします。 プロファイルの電子メール、またはcrmId、marketingCloudIdなどの拡張フィールドを使用できます。 この例では、「Email (email)」フィールドを選択して、appSubscriptionRcpテーブルの「Email (cusEmail)」フィールドにマッピングする必要があります。

   ![](assets/update_profile7.png)

1. 「**[!UICONTROL Fields to update]**」タブで「**[!UICONTROL Create element]**」ボタンをクリックし、appSubscriptionRcpテーブル（**[!UICONTROL Source]**&#x200B;フィールド）から取得したフィールドを、プロファイルテーブル（**[!UICONTROL Destination]**&#x200B;フィールド）で更新するフィールドにマッピングします。

1. 「 **[!UICONTROL Enabled if]** 」フィールドに式を追加して、ソースフィールドに値が含まれている場合にのみProfileテーブル内の対応するフィールドが更新されるようにします。 これをおこなうには、リストからフィールドを選択し、「!=&quot;&quot;式（式エディターで「ソース」フィールドが`[target/@cusEmail]`の場合は、必ず`[target/@cusEmail] != ''"`と入力してください）

   ![](assets/update_profile8.png)

>[!NOTE]
>
>この場合、ワークフローはUPSERTを実行しますが、**[!UICONTROL Incremental query]**データに基づいているため、挿入されるのみです。 クエリを変更すると、挿入または更新されるデータに影響する場合があります。
>また、「更新するフィールド」タブの設定によって、特定の条件下で挿入または更新されるフィールドが決まります。 これらの設定は、アプリケーションまたは顧客ごとに一意に指定できます。
>appSubscriptionRcpデータに基づいてプロファイルのレコードを更新すると、検証されることなくユーザーの個人情報を変更する可能性があるので、これらの設定を行う際は意図しない結果が生じる可能性があるので注意が必要です。

プロファイルに挿入/更新するすべてのフィールドを追加したら、「**[!UICONTROL Confirm]**」をクリックします。

![](assets/update_profile9.png)

ワークフローを保存し、「**[!UICONTROL Start]**」をクリックしてワークフローを実行します。

![](assets/update_profile10.png)
