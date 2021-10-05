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
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# モバイルアプリケーションデータに基づくプロファイル情報の作成と更新

## 概要

このページでは、モバイルアプリケーションが PII 収集データをスケジュールに従って送信した後に、プロファイルデータを作成/更新するワークフローを開発する手順について説明します。

* **** PII は、「個人を特定できる情報」の略です。例えば、Analytics for Mobile [ 目標地点 ](../../integrating/using/about-campaign-points-of-interest-data-integration.md) など、Campaign データベースのプロファイルテーブルに表示されない情報を含め、あらゆるデータを指定できます。 PII は、モバイルアプリ開発者（通常はマーケター）が定義します。
* **PII を収** 集は、モバイルアプリからAdobe Campaign Standardの Rest API に対する HTTPPOST操作です。

この使用例の目的は、モバイルアプリケーションから返される PII データにプロファイル関連のデータが含まれる場合に、Campaign Standardプロファイルを作成または更新することです。

## 前提条件

モバイルアプリのサブスクリプションデータに基づいてプロファイルを作成または更新する前に、Campaign Standardでプッシュ通知を有効にするには、いくつかの設定手順を実行します。

1. [モバイルアプリケーションの作成](../../administration/using/configuring-a-mobile-application.md)
1. [AdobeMobile SDK をモバイルアプリケーションと統合します](../../administration/using/supported-mobile-use-cases.md)。
1. [プッシュ通知を送信するようにAdobe Campaignを設定します](../../administration/using/configuring-a-mobile-application.md)。

## 手順 1 — プッシュ通知/購読のプロファイルリソースの拡張

PII データを使用してプロファイルリソースを作成または更新するには、まず目的のフィールドを使用してプロファイルリソースを拡張する必要があります。 手順は次のとおりです。

* モバイルアプリケーションから送信される PII フィールドを特定します。
* PII データとプロファイルデータを関連付けるための紐付けに使用するフィールドを特定します。

![](assets/update_profile1.png)

この例の **[!UICONTROL Fields]** セクションは、モバイルアプリケーションから送信された PII データを反映しています。 **[!UICONTROL Link to profiles]** セクションは、PII とプロファイルデータの関連付けに使用するフィールドを示します。ここで **cusEmail** は **@email** にマッピングされます。

**[!UICONTROL Subscriptions to an Application]** リソースを拡張する際のプロファイルデータのマッピングは読み取り専用です。 紐付けに使用されます。 プロファイルと PII データを紐付けるには、必要なデータを使用してプロファイルをシステムに入力する必要があります。 この場合、紐付けをおこなうには、プロファイルの電子メールアドレスが Collect PII の電子メールと一致する必要があります。

* Collect PII は、名が「Jane」、姓が「Doe」、電子メールアドレスがjanedoe@doe.comのユーザーに対して、モバイルアプリから受け取られます。
* プロファイルの電子メールアドレスがjanedoe@doe.comの場合は、プロファイルデータが存在する必要があります（例えば、データは手動で入力するか、既に他のリソースから取得している必要があります）。

**関連トピック：**

* [アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [既存のリソースの作成または拡張](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

## 手順 2 — ワークフローの作成

ワークフローをCampaign Standardで使用すると、管理者は、AppSubscription（購読者）データと、プロファイルまたは受信者データとの間でデータを一意に識別し、同期できます。 ワークフローベースの更新では、プロファイルデータはリアルタイムで同期されませんが、データベースの過度のロックやオーバーヘッドが発生することはありません。

ワークフローを作成する主な手順は次のとおりです。

1. **[!UICONTROL Query]** または **[!UICONTROL Incremental query]** アクティビティを使用して、最新の購読のリストを取得します。
1. **[!UICONTROL Reconciliation]** アクティビティを使用して、PII データをプロファイルにマッピングします。
1. 検証プロセスを追加します。
1. **[!UICONTROL Update data]** を使用して、PII データを使用してプロファイルを更新または作成します。

このワークフローでは、次の要件が想定されます。

* 拡張されたすべてのフィールドを使用して、プロファイルテーブルを作成または更新できる必要があります。
* プロファイルテーブルを拡張して、ネイティブサポートされないフィールド（T シャツサイズなど）をサポートできます。
* AppSubscription テーブルの空白のフィールドは、プロファイルテーブルで更新しないでください。
* AppSubscription テーブルで更新されたレコードは、次回のワークフロー実行に含める必要があります。

ワークフローを作成するには、次のアクティビティをワークスペースにドラッグ&amp;ドロップし、リンクします。**[!UICONTROL Start]**、**[!UICONTROL Scheduler]**、**[!UICONTROL Incremental query]**、**[!UICONTROL Update data]**。

![](assets/update_profile0.png)

次に、以下の手順に従って各アクティビティを設定します。

### **[!UICONTROL Scheduler]** アクティビティの設定

**[!UICONTROL General]** タブで、**[!UICONTROL Execution frequency]**（例：「日別」）、**[!UICONTROL Time]**（例：「1:00: 午前 0 時」）、**[!UICONTROL Start]**（例：今日の日付）を設定します。

![](assets/update_profile2.png)

### **[!UICONTROL Incremental query]** アクティビティを設定します。

1. 「**[!UICONTROL Properties]**」タブで、「**[!UICONTROL Resource]**」フィールドの **[!UICONTROL Select an element]** アイコンをクリックし、**[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 要素を選択します。

   ![](assets/update_profile3.png)

1. 「**[!UICONTROL Target]**」タブで、**[!UICONTROL Mobile application]** フィルターをドラッグし、モバイルアプリ名を選択します。

   ![](assets/update_profile4.png)

1. 「**[!UICONTROL Processed data]**」タブで「**[!UICONTROL Use a date field]**」を選択し、「**[!UICONTROL Last modified (lastModified)]**」フィールドに「**[!UICONTROL Path to the date field]**」と入力します。

   ![](assets/update_profile5.png)

### **[!UICONTROL Update data]** アクティビティを設定します。

1. 「**[!UICONTROL Identification]**」タブで、「**[!UICONTROL Dimension to update]**」フィールドが「Profiles (profile)」に設定されていることを確認し、「**[!UICONTROL Create element]**」ボタンをクリックして、フィールドを紐付け条件として追加します。

   ![](assets/update_profile_createelement.png)

1. **[!UICONTROL Source]** フィールドで、appSubscriptionRcp テーブルからフィールドを紐付けフィールドとして選択します。 プロファイルの電子メール、crmId、marketingCloudId などがあります。 この例では、「Email (cusEmail)」フィールドを使用します。

1. 「 **[!UICONTROL Destination]** 」フィールドで、プロファイルテーブルからフィールドを選択し、 appSubscriptionRcp テーブルからのデータを紐付けします。 プロファイルの電子メール、または crmId、marketingCloudId などの拡張フィールドを指定できます。 この例では、「Email (email)」フィールドを選択して、appSubscriptionRcp テーブルの「Email (cusEmail)」フィールドにマッピングする必要があります。

   ![](assets/update_profile7.png)

1. 「**[!UICONTROL Fields to update]**」タブで「**[!UICONTROL Create element]**」ボタンをクリックし、appSubscriptionRcp テーブル（**[!UICONTROL Source]** フィールド）のフィールドを、「プロファイル」テーブル（**[!UICONTROL Destination]** フィールド）の更新するフィールドにマッピングします。

1. 「 **[!UICONTROL Enabled if]** 」フィールドに式を追加して、ソースフィールドに値が含まれている場合にのみ、Profile テーブル内の対応するフィールドが更新されるようにします。 これをおこなうには、リストからフィールドを選択し、「!=&quot;&quot;式（式エディタで「ソース」フィールドが `[target/@cusEmail]` の場合は、必ず `[target/@cusEmail] != ''"` と入力してください）

   ![](assets/update_profile8.png)

>[!NOTE]
>
>この場合、ワークフローは UPSERT を実行しますが、**[!UICONTROL Incremental query]** データに基づいているので、挿入されるのはデータのみです。 クエリを変更すると、挿入または更新するデータに影響する場合があります。
>また、「更新するフィールド」タブの設定によって、特定の条件下で挿入または更新されるフィールドが決まります。 これらの設定は、アプリケーションまたは顧客ごとに一意に指定できます。
>appSubscriptionRcp データに基づいてプロファイルのレコードを更新すると、検証されずにユーザーの個人情報を変更する可能性があるので、これらの設定を行う際は意図しない結果が生じる可能性があるので、注意が必要です。

プロファイルに挿入/更新するすべてのフィールドを追加したら、「**[!UICONTROL Confirm]**」をクリックします。

![](assets/update_profile9.png)

ワークフローを保存し、「**[!UICONTROL Start]**」をクリックしてワークフローを実行します。

![](assets/update_profile10.png)
