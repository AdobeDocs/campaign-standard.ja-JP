---
title: モバイルアプリケーションデータに基づくプロファイル情報の作成と更新
description: モバイルアプリケーションデータに基づいてプロファイル情報を作成および更新する方法を説明します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 1b48456e-9aae-485c-a7c4-7e3e2f53cbca
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 2%

---

# モバイルアプリケーションデータに基づくプロファイル情報の作成と更新

## 概要

このページでは、モバイルアプリケーションがスケジュールに従って収集 PII データを送信した後にプロファイルデータを作成/更新するワークフローを開発する手順について説明します。

* **PII** は、「個人を特定できる情報」を表します。 Analytics for Mobile [ 目標地点 ](../../integrating/using/about-campaign-points-of-interest-data-integration.md) など、Campaign データベースからプロファイルテーブルに表示されない情報を含む、任意のデータを指定できます。 PII は、モバイルアプリ開発者が（通常はマーケターと）定義します。
* **PII を収集** は、モバイルアプリからAdobe Campaign Standardの Rest API に対する HTTPPOST操作です。

このユースケースの目的は、モバイルアプリケーションから返される PII データにプロファイル関連のデータが含まれている場合、Campaign Standardプロファイルを作成または更新することです。

## 前提条件

モバイルアプリ購読データに基づいてプロファイルを作成または更新する前に、Campaign Standardでプッシュ通知を有効にするために従うべき設定手順がいくつかあります。

1. [モバイルアプリケーションの作成](../../administration/using/configuring-a-mobile-application.md)
1. [Adobe Mobile SDKをモバイルアプリケーションと統合します ](../../administration/using/supported-mobile-use-cases.md)。
1. [ プッシュ通知を送信するようにAdobe Campaignを設定する ](../../administration/using/configuring-a-mobile-application.md)。

## 手順 1 - プッシュ通知/購読用のプロファイルリソースを拡張

PII データを使用してプロファイルリソースを作成または更新できるようにするには、まず目的のフィールドでプロファイルリソースを拡張する必要があります。 手順は次のとおりです。

* モバイルアプリケーションから送信される PII フィールドを識別します。
* PII データとプロファイルデータを関連付けるために紐付けに使用するフィールドを識別します。

![](assets/update_profile1.png)

この例では、「**[!UICONTROL Fields]**」セクションにモバイルアプリケーションから送信された PII データが反映されます。 **[!UICONTROL Link to profiles]** のセクションは、PII とプロファイルデータを関連付けるために使用されるフィールドを示します。ここで、**cusEmail** は **@email** にマッピングされます。

**[!UICONTROL Subscriptions to an Application]** リソースの拡張時のプロファイルデータのマッピングは読み取り専用です。 紐付けに使用されます。 プロファイルを PII データと紐付けするために必要なデータを使用して、プロファイルをシステムに入力する必要があります。 この場合、紐付けが発生するには、プロファイルのメールアドレスが Collect PII のメールと一致する必要があります。

* Collect PII は、ユーザーの名が「Jane」、姓が「Doe」、メールアドレスがjanedoe@doe.comの場合にモバイルアプリから受信されます。
* 別に、プロファイルデータが存在する必要があります（例えば、データを手動で入力する必要や、他のリソースから既に取得する必要があります）。この場合、プロファイルのメールアドレスはjanedoe@doe.comです。

**関連トピック：**

* [ アプリケーションリソースの購読の拡張 ](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)。
* [ 既存のリソースの作成または拡張 ](../../developing/using/key-steps-to-add-a-resource.md)。

## 手順 2 - ワークフローの作成

Campaign Standardでワークフローを使用すると、管理者は AppSubscription （サブスクライバー）データとプロファイルまたは受信者データの間で、データを一意に識別および同期できます。 ワークフローベースの更新ではプロファイルデータはリアルタイムで同期されませんが、不要なデータベースロックやオーバーヘッドが発生することはありません。

ワークフローを作成するための主な手順は次のとおりです。

1. **[!UICONTROL Query]** または **[!UICONTROL Incremental query]** アクティビティを使用して、最新の購読のリストを取得します。
1. **[!UICONTROL Reconciliation]** アクティビティを使用して、PII データをプロファイルにマッピングします。
1. 検証プロセスを追加します。
1. **[!UICONTROL Update data]** を使用して、PII データでプロファイルを更新または作成します。

このワークフローでは、次の要件が想定されています。

* 拡張されたすべてのフィールドを使用して、プロファイルテーブルを作成または更新できます。
* プロファイルテーブルは、ネイティブにサポートされていないフィールド（T シャツサイズなど）をサポートするように拡張できます。
* AppSubscription テーブルの空白のフィールドは、プロファイル テーブルで更新しないでください。
* AppSubscription テーブルで更新されたレコードは、次回のワークフロー実行に含める必要があります。

ワークフローを作成するには、**[!UICONTROL Start]**、**[!UICONTROL Scheduler]**、**[!UICONTROL Incremental query]**、**[!UICONTROL Update data]** のアクティビティをワークスペースにドラッグ&amp;ドロップし、リンクします。

![](assets/update_profile0.png)

次に、次の手順に従って各アクティビティを設定します。

### **[!UICONTROL Scheduler]** アクティビティの設定

「**[!UICONTROL General]**」タブで、**[!UICONTROL Execution frequency]** （「毎日」など）、**[!UICONTROL Time]** （「午前 1:00:00 分」など）および **[!UICONTROL Start]** （「今日の日付」など）を設定します。

![](assets/update_profile2.png)

### **[!UICONTROL Incremental query]** アクティビティを設定します。

1. 「**[!UICONTROL Properties]**」タブで、「**[!UICONTROL Resource]**」フィールドの「**[!UICONTROL Select an element]**」アイコンをクリックし、**[!UICONTROL Subscriptions to an application (`nms:appSubscriptionRcp:appSubscriptionRcpDetail`）]** 要素を選択します。

   ![](assets/update_profile3.png)

1. 「**[!UICONTROL Target]**」タブで「**[!UICONTROL Mobile application]**」フィルターをドラッグして、モバイルアプリケーション名を選択します。

   ![](assets/update_profile4.png)

1. 「**[!UICONTROL Processed data]**」タブで「**[!UICONTROL Use a date field]**」を選択し、「**[!UICONTROL Last modified (lastModified)]**」フィールドを **[!UICONTROL Path to the date field]** のように追加します。

   ![](assets/update_profile5.png)

### **[!UICONTROL Update data]** アクティビティを設定します。

1. 「**[!UICONTROL Identification]**」タブで、「**[!UICONTROL Dimension to update]**」フィールドが「プロファイル （プロファイル）」に設定されていることを確認し、「**[!UICONTROL Create element]**」ボタンをクリックしてフィールドを紐付け条件として追加します。

   ![](assets/update_profile_createelement.png)

1. 「**[!UICONTROL Source]**」フィールドで、appSubscrsiptionRcp テーブルから紐付けフィールドとしてフィールドを選択します。 プロファイルのメールアドレス、crmId、marketingCloudId などがあります。 この例では、「Email （cusEmail）」フィールドを使用します。

1. 「**[!UICONTROL Destination]**」フィールドで、プロファイルテーブルからフィールドを選択して、appSubscriptionRcp テーブルからのデータを紐付けます。 これは、プロファイルのメールか、任意の拡張フィールド （crmId、marketingCloudId など）です。 この例では、「Email （email）」フィールドを選択し、appSubscriptionRcp テーブルの「Email （cusEmail）」フィールドにマッピングする必要があります。

   ![](assets/update_profile7.png)

1. 「**[!UICONTROL Fields to update]**」タブで「**[!UICONTROL Create element]**」ボタンをクリックし、appSubscriptionRcp テーブル（**[!UICONTROL Source]** フィールド）から取得したフィールドを、プロファイルテーブル（**[!UICONTROL Destination]** フィールド）の更新するフィールドにマッピングします。

1. **[!UICONTROL Enabled if]** フィールドに式を追加して、ソーステーブルの対応するフィールドが、ソースフィールドに値が含まれている場合にのみ更新されるようにします。 それには、リストからフィールドを選択し、「!=&quot;&quot;式（式エディターで「Source」フィールドが `[target/@cusEmail]` の場合は、必ず「`[target/@cusEmail] != ''"`」と入力します）。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>この場合、ワークフローは UPSERT を実行しますが、**[!UICONTROL Incremental query]** データに基づいているので、挿入されるだけです。 クエリを変更すると、挿入または更新されるデータに影響を与える可能性があります。
>さらに、「更新するフィールド」タブの設定によって、特定の条件下で挿入または更新するフィールドが決まります。 これらの設定は、アプリケーションまたは顧客ごとに一意にすることができます。
>appSubscriptionRcp データに基づいてプロファイルのレコードを更新すると、検証なしでユーザーの個人情報が変更される可能性があるので、これらの設定を設定する際は、意図しない結果が生じる可能性があるので注意が必要です。

プロファイルに挿入/更新するフィールドをすべて追加したら、「**[!UICONTROL Confirm]**」をクリックします。

![](assets/update_profile9.png)

ワークフローを保存し、「**[!UICONTROL Start]**」をクリックしてワークフローを実行します。

![](assets/update_profile10.png)
