---
title: ユーザー管理
seo-title: ユーザー管理
description: ユーザー管理
seo-description: 'Adobe Campaignユーザーは特定の役割を保持します。メインユーザーのタイプを見つけます。 '
page-status-flag: 常にアクティブ化されていない
uuid: 8c4cc74a-815f-4815- af66- a7c21bc754f1
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: ユーザーおよびセキュリティ
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Users management{#users-management}

## About users {#about-users}

Adobe Campaignでは、ユーザーにロールのセットを割り当てて、アクセスできるインターフェイスの一部を定義できます。

The specific roles and the corresponding authorizations are detailed in the following sections: [understanding roles](../../administration/using/list-of-roles.md) and [authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

管理者は管理コンソールからユーザーを管理できます。ユーザーは自動的にAdobe Campaignと同期されます。For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

To view the users in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Users]**.

To access the user management interface from Adobe Campaign, click **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**関連トピック:**

* [ユーザー権限](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) のビデオの管理
* [ロールのリスト](../../administration/using/list-of-roles.md)
* [承認のリスト](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Type of users {#type-of-users}

このユーザーセグメントは必須ではありません。Adobe Campaignの最も一般的な使用方法が示されています。

ここでは、Adobe Campaignユーザーの主なタイプについて説明します。ここでは、ユーザーが保持できる特定の役割（配信を開始、エクスポート、配信準備など）には移動しません。For more information on roles, refer to [List of roles](../../administration/using/list-of-roles.md) and [Managing groups and users](../../administration/using/managing-groups-and-users.md) pages.

Adobe Campaignの様々なタスクが、3つの主なユーザータイプ間でどのように分割されているかについて、以下に説明します。

* [機能管理者](../../administration/using/users-management.md#functional-administrators):をすべての組織のユーザーにとって、最も技術的な作業です。
* [上級ユーザー](../../administration/using/users-management.md#advanced-users):マーケティング担当者が配信を送信し監視する必要があるすべての要素をセットアップします。
* [基本ユーザー](../../administration/using/users-management.md#basic-users):これらは、キャンペーンをカスタマイズ、配信、監視するマーケティング担当者です。

>[!NOTE]
>
>機能管理者は、アドビのテクニカル管理者とは異なります。アドビのテクニカル管理者は、ユーザーが使用できるアドビ内部の役割を持っています。これらは、インスタンスプロビジョニング、ホスティング、インフラストラクチャ監視および監視、技術的トラブルシューティングを管理します。

### Functional administrators {#functional-administrators}

機能管理者は、インターフェイスの最も技術的な部分にアクセスできるユーザーです。**[!UICONTROL Administration]** ロールを保持して、プラットフォームがすべて設定されていることを確認し、マーケティング担当者がキャンペーンの配信に集中できるようにします。

Functional administrators are the only users who can access the **[!UICONTROL Administration]** menu, in the Adobe Campaign interface. Since these users need to access technical resources, more advanced roles should be assigned to them, such as the **[!UICONTROL Administration]** and **[!UICONTROL Datamodel]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Administrators]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

実行できる主要なタスクは次のとおりです。

* [ユーザーと権限](../../administration/using/about-access-management.md)の管理:プラットフォーム（ユーザー、役割、セキュリティグループ、数量）へのアクセスを管理します。
* [様々なチャネル](../../administration/using/about-channel-configuration.md)の設定:プラットフォームチャネルと、タイポロジおよび強制管理を設定します。
* [一般的なアプリケーション設定](../../administration/using/external-accounts.md)を設定します。異なるアプリケーション要素（外部アカウント、オプション、テクニカルワークフロー）を設定します。
* [新機能を強化し、次の機能](../../developing/using/data-model-concepts.md)を強化しました。カスタムリソースを管理し、診断ツールにアクセスします。
* [インスタンスパラメーター](../../administration/using/branding.md)を設定します。異なるブランドを定義し、その設定（ロゴ、トラッキングの管理、ランディングページにアクセスするためのURLドメインなど）を設定します。
* [データパッケージの書き出しと読み込み](../../automating/using/managing-packages.md):を使用して、様々なAdobe Campaignインスタンス間のリソースを構造化XMLファイルに交換できます。
* [ログをエクスポート](../../automating/using/exporting-logs.md) し [、インポートテンプレート](../../automating/using/defining-import-templates.md)を定義します。

### Advanced users {#advanced-users}

上級ユーザーとは、Adobe Campaignの最も技術的な使用例を実行するマーケティングユーザーです。マーケティング担当者は、配信の送信および監視に使用するすべての要素を事前設定します。

このタイプのユーザーは、機能管理者よりも一般的な役割を必要としますが、技術的な操作を実行することができます。To do so, they should be assigned, for example, the **[!UICONTROL Export]**, **[!UICONTROL Generic import]** or **[!UICONTROL Workflow]** out-of-the-box roles. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

実行できる主要なタスクは次のとおりです。

* [複雑なデータ管理ワークフロー](../../automating/using/about-data-management-activities.md)の作成と実行:インポート、エンリッチメントおよび変換データを取り込み、データベースをフィードするか、外部ファイルで必要なデータをエクスポートして、独自のツールで処理します。
* [テンプレートの管理](../../start/using/about-templates.md):テンプレートを管理して、ニーズに応じてマーケティングアクティビティの特定のパラメーターを事前設定します。
* [クエリ](../../automating/using/editing-queries.md#about-query-editor) を作成し、 [オーディエンス](../../audiences/using/about-audiences.md)を管理します。クエリを手動で作成するか、専用ワークフローを使用して自動的にオーディエンスを作成します。
* [高度なエクスプレッション編集](../../automating/using/editing-queries.md#about-query-editor)の実行:高度な関数を使用して、日付、文字列、数値フィールド、並べ替えなどの特定のクエリを実行するために使用する値を操作します。
* [既存のインポートテンプレートを使用して、リスト](../../automating/using/exporting-lists.md) の書き出しと [データの読み込み](../../automating/using/importing-data-with-import-templates.md)を行います。

### Basic users {#basic-users}

機能管理者および上級ユーザーは、技術的な設定に気を遣うことなく、キャンペーンをカスタマイズ、配信、監視することができます。To do so, they should be assigned, for example, the **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** and **[!UICONTROL Start deliveries]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Standard Users]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

実行できる主要なタスクは次のとおりです。

* [プログラムとキャンペーン](../../start/using/programs-and-campaigns.md)の管理:様々なタイプのアクティビティ（電子メール、SMSメッセージ、プッシュ通知、ワークフロー、ランディングページ）を含むマーケティングキャンペーンを作成できます。
* [プロファイル](../../audiences/using/about-profiles.md) と [テストプロファイル](../../sending/using/managing-test-profiles-and-sending-proofs.md)の管理:配信によってターゲット設定される特定の受信者およびテストの受信者を管理します。名、姓、連絡先情報、購読、電子メールなどの情報を追加します。
* [メッセージ](../../sending/using/confirming-the-send.md)の作成と送信:メッセージを作成し、オーディエンスを選択して、メッセージコンテンツとそのパーソナライゼーションエレメントを定義し、配達確認を送信して、最終的なメッセージをオーディエンスに送信します。
* [ランディングページの作成と公開](../../channels/using/about-landing-pages.md):購読または購読解除のフォームなど、クライアントに提供する一連のサービスを作成および管理します。
* [キャンペーンワークフロー](../../automating/using/building-a-workflow.md)の作成と実行:ワークフローを使用してキャンペーンプロセスを自動化します。
* [利用可能なレポートを通してマーケティング活動を監視](../../reporting/using/defining-the-report-period.md)します。

## Creating a user {#creating-a-user}

ユーザーをインスタンスに追加するには、まず管理コンソールで作成してから、Adobe Campaign Standardで管理する必要があります。

1. From the advanced menu, select **[!UICONTROL Administration > Users & Security > Users]** and click **[!UICONTROL User administration]** to access the admin console.

   ![](assets/user_management_5.png)

1. In the **[!UICONTROL Admin Console]**, click on the **[!UICONTROL Users]** tab.

1. **[!UICONTROL Add User]**&#x200B;をクリックします。

   ![](assets/create_user_2.png)

1. **[!UICONTROL User details]** タブから、電子メールアドレス、名前、姓などのユーザーの詳細を入力します。

   ![](assets/create_user_3.png)

1. **[!UICONTROL Assign products]** タブから、1つまたは複数のセキュリティグループをユーザーに割り当てます。For more information on security groups, refer to this [page](../../administration/using/managing-groups-and-users.md).

   Click **[!UICONTROL Save]** when done configuring.

   ![](assets/create_user_4.png)

ユーザーが作成され、ユーザーがパスワードを設定する必要がある次のウィンドウに電子メールをリダイレクトして、使用条件に同意する必要があります。このユーザーは、Adobe Campaign Standardインスタンスに接続できます。

![](assets/create_user_5.png)

ユーザーがインスタンスにサインインすると、すぐにAdobe Campaign Standardと同期されます。

ユーザーがAdobe Campaignと正しく同期されているかどうかを確認できます。

1. From the advanced menu **[!UICONTROL Administration > Users & Security > Users]** select your previously created user.

1. Update the **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** or **[!UICONTROL Regional settings]** if needed.

1. ユーザーのセキュリティグループを確認します。Here, you can see that the user has been assigned the **[!UICONTROL Administrators]** security group.

   >[!Ntoo]
   >
   >セキュリティグループは、管理コンソールのユーザーにのみ削除することも、追加することもできます。

   ![](assets/create_user_6.png)

1. Check **[!UICONTROL Account disabled]** if you want to deactivate this user.

1. **[!UICONTROL Authorized connection zone]** フィールドで、ユーザーがこのインスタンスに接続する方法（内部ネットワークやVPNなど）を選択します。

1. **[!UICONTROL Save]**&#x200B;をクリックします。
