---
title: モバイルアプリケーションデータに基づいたプロファイル情報の作成および更新
seo-title: モバイルアプリケーションデータに基づいたプロファイル情報の作成および更新
description: モバイルアプリケーションデータに基づいたプロファイル情報の作成および更新
seo-description: モバイルアプリケーションデータに基づいてプロファイル情報を作成および更新する方法について説明します。
page-status-flag: 決して活性化されていない
uuid: 8cf74CAD- b1ba-4aad-83bd-7289cb2d5f4
contentOwner: レモン
products: SG_キャンペーン/標準
audience: チャンネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: dc944c85-2059-46df- b396-676fe3617dd1
context-tags: 配信， MobileAppContent，背面
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 64c7de127285ca56b6af398b0a0c3f1470756fe4

---


# モバイルアプリケーションデータに基づいたプロファイル情報の作成および更新

## 概要

このページでは、モバイルアプリケーションがPIIデータを収集してスケジュールベースで収集するワークフローを開発する手順について説明します。

* **PII** は「個人識別情報」の略である。たとえば、モバイル [ポイントの分析など、CampaignデータベースのProfileテーブルに表示されない情報など、任意のデータを使用](../../integrating/using/about-campaign-points-of-interest-data-integration.md)できます。PIIはモバイルアプリ開発者によって定義され、通常はマーケティング担当者によって定義されます。
* **PIIの収集** は、モバイルアプリからのAdobe Campaign StandardのRest APIへのHTTP- POST操作です。

このユースケースの目的は、モバイルアプリケーションから返されるPIIデータにプロファイル関連のデータが含まれている場合に、キャンペーン標準プロファイルを作成または更新することです。

## 前提条件

Mobile Appサブスクリプションデータに基づいてプロファイルを作成または更新する前に、Campaign Standardでプッシュ通知を有効にするために、いくつかの構成手順があります。

1. [モバイルアプリケーションの作成](../../administration/using/configuring-a-mobile-application.md)
1. [モバイルアプリケーションとAdobe Mobile SDKを統合](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)します。
1. [プッシュ通知を送信するようにAdobe Campaignを構成](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)します。

## ステップ1-プッシュ通知/サブスクリプションのプロファイルリソースを拡張する

PIIデータを使用してプロファイルリソースを作成または更新できるようにするには、まず、必要なフィールドでプロファイルリソースを拡張する必要があります。これを行うには:

* モバイルアプリケーションによって送信されるPIIフィールドを識別します。
* 調整に使用するフィールドを指定して、PIIデータをプロファイルデータに関連付けます。

![](assets/update_profile1.png)

この例では、セクション **[!UICONTROL Fields]** はモバイルアプリケーションから送信されたPIIデータを反映します。**[!UICONTROL Link to profiles]** このセクションは、PIIをプロファイルデータに関連付けるために使用するフィールドを示します。ここで **、CustEmail** は **@ emailにマップ**&#x200B;されます。

**[!UICONTROL Subscriptions to an Application]** リソースの拡張中にプロファイルデータのマッピングは読み取り専用です。調整に使用されます。プロファイルをPIIデータと照合するために必要なデータをシステムに入力する必要があります。この場合、調整を実行するには、プロファイルの電子メールアドレスがPII収集の電子メールと一致する必要があります。

* PIIを収集するには、Mobile Appから"Jane， Last Name is"Doe"および"Email address isjanedoe@doe.com"と入力します。
* プロファイルの電子メールアドレスはjanedoe@doe.comである必要があります（たとえば、データは手動で入力する必要があります）。また、プロファイルの電子メールアドレスがである必要があります。

**関連トピック:**

* [アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)。
* [既存のリソース](../../developing/using/key-steps-to-add-a-resource.md)の作成または拡張

## 手順2-ワークフローを作成する

Campaign Standardでワークフローを使用すると、管理者はAppSubscription（サブスクライバー）データとプロファイルデータまたは受信者データ間のデータを一意に識別および同期できます。ワークフローベースの更新では、プロファイルデータはリアルタイムで同期されませんが、過度のデータベースロックやオーバーヘッドは発生しません。

ワークフローを構築する主な手順は次のとおりです。

1. 最新のサブスクリプションの一覧を取得するには、また **[!UICONTROL Query]** は **[!UICONTROL Incremental query]** アクティビティを使用します。
1. **[!UICONTROL Reconciliation]** アクティビティを使用して、PIIデータをプロファイルにマップします。
1. 検証プロセスを追加します。
1. を **[!UICONTROL Update data]** 使用して、PIIデータでプロファイルを更新または作成します。

このワークフローでは、次の要件が想定されます。

* 拡張されたすべてのフィールドは、プロファイルテーブルの作成/更新に使用できます。
* プロファイルテーブルは、ネイティブでサポートされていないフィールド（Tシャツサイズなど）をサポートするように拡張できます。
* AppSubscriptionテーブルの任意のフィールドは、プロファイルテーブルでは更新しないでください。
* AppSubscriptionテーブルで更新されたレコードはすべて、ワークフローの次の実行に含める必要があります。

ワークフローを構築するには、次の手順に従います。

1. 次のアクティビティをワークスペースにドラッグアンドドロップし、一緒にリンクします。
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. **[!UICONTROL Scheduler]** アクティビティを構成します。**[!UICONTROL General]** タブで、（ **[!UICONTROL Execution frequency]** 例:"Daily"）、（ **[!UICONTROL Time]** 例:"1:00:00AM»）、および（???«今日の日付&#x200B;**[!UICONTROL Start]**

   ![](assets/update_profile2.png)

1. **[!UICONTROL Incremental query]** アクティビティを構成します。
   1. **[!UICONTROL Properties]** タブで、フィールドの **[!UICONTROL Select an element]** アイコン **[!UICONTROL Resource]** をクリックし、 **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 要素を選択します。

      ![](assets/update_profile3.png)

   1. **[!UICONTROL Target]** タブで **[!UICONTROL Mobile application]** フィルタをドラッグし、モバイルアプリケーション名を選択します。

      ![](assets/update_profile4.png)

   1. **[!UICONTROL Processed data]** タブで、を選択 **[!UICONTROL Use a date field]**&#x200B;し、フィールドをとして追加 **[!UICONTROL Last modified (lastModified)]****[!UICONTROL Path to the date field]**&#x200B;します。

      ![](assets/update_profile5.png)

1. **[!UICONTROL Update data]** アクティビティを構成します。
   1. **[!UICONTROL Identification]** タブで、フィールド **[!UICONTROL Dimension to update]** が「プロファイル（プロファイル）」に設定されていることを確認し、ボタン **[!UICONTROL Create element]** をクリックして調整条件としてフィールドを追加します。

      ![](assets/update_profile_createelement.png)

   1. **[!UICONTROL Source]** フィールドで、AppSubScrsitionRCPテーブルから調整フィールドとしてフィールドを選択します。プロファイルの電子メール、CrmID、MarketingCloudIDなどになります。この例では、"Email（cusEmail）」フィールドを使用します。
   1. **[!UICONTROL Destination]** フィールド内で、AppSubscriptionrCPテーブルからデータを調整するために、プロファイルテーブルからフィールドを選択します。プロファイルの電子メール、またはCRMid、MarketingCloudIDなどの拡張フィールドを使用できます。この例では、"Email（email）」フィールドを選択して、AppSubscriptionrCPテーブルから"Email（cusEmail）」フィールドにマッピングする必要があります。

      ![](assets/update_profile7.png)

   1. **[!UICONTROL Fields to update]** タブで **[!UICONTROL Create element]** ボタンをクリックし、AppSubscriptionrCPテーブル（フィールド&#x200B;**[!UICONTROL Source]** ）からのフィールドをProfileテーブル（**[!UICONTROL Destination]** フィールド）で更新するフィールドにマップします。
   1. **[!UICONTROL Enabled if]** フィールドで、「プロファイル」（Profile）テーブルの対応するフィールドが値を含んでいる場合にのみ更新されるように、式を追加します。これを行うには、リストからフィールドを選択し、「」を追加します。=「」 expression（Sourceフィールドが `[target/@cusEmail]` Expressionエディタにある場合は、必ず入力 `[target/@cusEmail] != ''"`します）。

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >この場合、ワークフローはUPERTを実行しますが、増分クエリデータは挿入されます。クエリを変更すると、挿入または更新されるデータに影響することがあります。
      >また、「更新するフィールド」タブの設定によって、特定の条件下で挿入または更新されるフィールドが決まります。これらの設定は、アプリケーションまたは顧客ごとに一意です。AppSubscriptionrCPデータに基づいてプロファイル内のレコードを更新すると、検証が行われずに個人情報を変更できるので、これらの設定を構成する際には注意してください。

   1. プロファイルに挿入/更新するすべてのフィールドを追加したら、をクリック **[!UICONTROL Confirm]**&#x200B;します。

      ![](assets/update_profile9.png)

1. ワークフローを保存し、「開始」をクリックしてワークフロープロセスを開始します。

   ![](assets/update_profile10.png)
