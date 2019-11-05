---
title: モバイルアプリケーションデータに基づくプロファイル情報の作成と更新
description: モバイルアプリケーションデータに基づいてプロファイル情報を作成および更新する方法について説明します。
page-status-flag: 非活性化の
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: レメイト
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# モバイルアプリケーションデータに基づくプロファイル情報の作成と更新

## 概要

このページでは、モバイルアプリケーションがPIIデータの収集をスケジュールに基づいて送信した後にプロファイルデータを作成/更新するワークフローを作成する手順について説明します。

* **PIIは** 、「個人を特定できる情報」の略です。 例えば、モバイル目標地点の分析など、Campaignデータベースからプロファイルテーブルに表示されない情報を含む、任意のデ [ータを指定できます](../../integrating/using/about-campaign-points-of-interest-data-integration.md)。 PIIは、モバイルアプリの開発者（通常はマーケティング担当者）が定義します。
* **PIIの収集は** 、モバイルアプリからAdobe Campaign StandardのRest APIに対するHTTP-POST操作です。

この使用例の目標は、モバイルアプリケーションから返されるPIIデータにプロファイル関連のデータが含まれる場合に、キャンペーン標準プロファイルを作成または更新することです。

## 前提条件

モバイルアプリの購読データに基づいてプロファイルを作成または更新する前に、Campaign Standardでプッシュ通知を有効にするために従う必要がある設定手順はいくつかあります。

1. [モバイルアプリの作成](../../administration/using/configuring-a-mobile-application.md)
1. [Adobe Mobile SDKをモバイルアプリケーションと統合します](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)。
1. [プッシュ通知を送信するようにAdobe Campaignを設定します](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

## 手順1 — プッシュ通知/購読用のプロファイルリソースを拡張する

PIIデータを使用してプロファイルリソースを作成または更新するには、まず目的のフィールドを使用してプロファイルリソースを拡張する必要があります。 手順は次のとおりです。

* モバイルアプリケーションから送信されるPIIフィールドを識別します。
* PIIデータをプロファイルデータに関連付けるために調整に使用するフィールドを指定します。

![](assets/update_profile1.png)

この例では、この節はモバ **[!UICONTROL Fields]** イルアプリケーションから送信されるPIIデータを反映しています。 このセ **[!UICONTROL Link to profiles]** クションは、PIIをプロファイルデータに関連付けるために使用されるフィールドを示します。ここで、 **cusEmail** は@emailにマッ **プされます**。

リソースの拡張中のプロファイルデータのマ **[!UICONTROL Subscriptions to an Application]** ッピングは読み取り専用です。 和解に使用されます。 プロファイルとPIIデータを調整するには、必要なデータを使用してプロファイルをシステムに入力する必要があります。 この場合、調整を行うには、プロファイルの電子メールアドレスがCollect PIIからの電子メールと一致する必要があります。

* モバイルアプリから受け取ったPIIの収集(姓は「Jane」、姓は「Doe」、電子メールアドレスは「janedoe@doe.com」)を持つユーザー用です。
* 別に、プロファイルの電子メールアドレスがjanedoe@doe.comである場合は、プロファイルデータが存在する必要があります（例えば、データを手動で入力するか、既に他のリソースから入手している必要があります）。

**関連トピック：**

* [アプリケーションリソースへの購読の拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [既存のリソースを作成または拡張します](../../developing/using/key-steps-to-add-a-resource.md)。

## 手順2 — ワークフローを作成する

Campaign Standardのワークフローを使用すると、管理者はAppSubscription（購読者）データとプロファイルデータまたは受信者データの間でデータを一意に識別し、同期できます。 ワークフローベースの更新では、プロファイルデータがリアルタイムで同期されませんが、データベースの過度なロックやオーバーヘッドが発生することはありません。

ワークフローを構築する主な手順は次のとおりです。

1. またはアクテ **[!UICONTROL Query]** ィビテ **[!UICONTROL Incremental query]** ィを使用して、最新の購読のリストを取得します。
1. アクティビティ **[!UICONTROL Reconciliation]** を使用して、PIIデータをプロファイルにマッピングします。
1. 検証プロセスを追加します。
1. PIIデータを使 **[!UICONTROL Update data]** 用してプロファイルを更新または作成するには、を使用します。

このワークフローでは、次の要件を前提としています。

* 拡張されたすべてのフィールドを使用して、プロファイルテーブルを作成または更新できる必要があります。
* プロファイルテーブルを拡張して、ネイティブでサポートされていないフィールド（例えば、Tシャツのサイズ）をサポートすることができます。
* AppSubscriptionテーブルの空白のフィールドは、プロファイルテーブルで更新しないでください。
* AppSubscriptionテーブルで更新されたレコードは、ワークフローの次回の実行に含める必要があります。

ワークフローを構築するには、以下の手順に従います。

1. 次のアクティビティをワークスペースにドラッグ&amp;ドロップし、リンクします。
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. Configure the **[!UICONTROL Scheduler]** activity. タブ **[!UICONTROL General]** で、 **[!UICONTROL Execution frequency]** （例：「日別」）、 **[!UICONTROL Time]** （例：「1:00:00 AM」）および **[!UICONTROL Start]** （例：「今日の日付」）を設定します。

   ![](assets/update_profile2.png)

1. Configure the **[!UICONTROL Incremental query]** activity.
   1. タブで、 **[!UICONTROL Properties]** フィールドのア **[!UICONTROL Select an element]** イコンをク **[!UICONTROL Resource]** リックし、要素を選択し **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** ます。

      ![](assets/update_profile3.png)

   1. タブで、フ **[!UICONTROL Target]** ィルターをドラッグ **[!UICONTROL Mobile application]** し、モバイルアプリ名を選択します。

      ![](assets/update_profile4.png)

   1. タブで、 **[!UICONTROL Processed data]** を選択し、 **[!UICONTROL Use a date field]**&#x200B;フィールドを次のように **[!UICONTROL Last modified (lastModified)]** 追加しま **[!UICONTROL Path to the date field]**&#x200B;す。

      ![](assets/update_profile5.png)

1. Configure the **[!UICONTROL Update data]** activity.
   1. タブで、フ **[!UICONTROL Identification]** ィールドが「Profiles (profile)」に設定されていることを確認し、ボタンをクリックして、フィ **[!UICONTROL Dimension to update]****[!UICONTROL Create element]** ールドを調整条件として追加します。

      ![](assets/update_profile_createelement.png)

   1. フィールド **[!UICONTROL Source]** で、appSubscriptionRcpテーブルからフィールドを調整フィールドとして選択します。 プロファイルの電子メール、crmId、marketingCloudIdなどを指定できます。 この例では、「電子メール(cusEmail)」フィールドを使用します。
   1. フィールド **[!UICONTROL Destination]** で、プロファイルテーブルからフィールドを選択し、appSubscriptionRcpテーブルのデータを調整します。 プロファイルの電子メール、またはcrmId、marketingCloudIdなどの拡張フィールドを指定できます。 この例では、「電子メール（電子メール）」フィールドを選択して、appSubscriptionRcpテーブルの「電子メール(cusEmail)」フィールドにマッピングする必要があります。

      ![](assets/update_profile7.png)

   1. タブでボ **[!UICONTROL Fields to update]** タンをクリ **[!UICONTROL Create element]** ックし、appSubscriptionRcpテーブル（フィールド）から取得するフィールドを、プロファイルテーブル（フィールド）で更新するフィールドにマッピング&#x200B;**[!UICONTROL Source]****[!UICONTROL Destination]** します。
   1. フィールド **[!UICONTROL Enabled if]** に式を追加し、ソースフィールドに値が含まれている場合にのみ、Profileテーブルの対応するフィールドが更新されるようにします。 これを行うには、リストからフィールドを選択し、「!="" expression(Sourceフィールドが式エディターにあ `[target/@cusEmail]` る場合は、必ず入力してくだ `[target/@cusEmail] != ''"`さい)。

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >この場合、ワークフローはUPSERTを実行しますが、インクリメンタルクエリデータに基づいているので、挿入されるのは挿入だけです。 クエリーを変更すると、挿入または更新するデータに影響を与える場合があります。
      >さらに、「更新するフィールド」タブの設定によって、特定の条件で挿入または更新するフィールドが決まります。 これらの設定は、アプリケーションごとまたは顧客ごとに一意に指定できます。 appSubscriptionRcpデータに基づいてプロファイルのレコードを更新すると、ユーザーの個人情報が検証なしに変更される可能性があるので、これらの設定を行う場合は意図しない結果が生じる可能性があるので注意が必要です。

   1. プロファイルに挿入/更新するすべてのフィールドが追加されたら、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。

      ![](assets/update_profile9.png)

1. ワークフローを保存し、「開始」をクリックしてワークフロープロセスを開始します。

   ![](assets/update_profile10.png)
