---
title: ユーザー管理
description: 'Adobe Campaignユーザーは特定の役割を持ちます。 メインユーザータイプを見つけます。 '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 3%

---


# ユーザー管理{#users-management}

## ユーザーについて {#about-users}

Adobe Campaignを使用すると、ユーザーに一連のロールを割り当てて、ユーザーがアクセスできるインターフェイスの部分を定義できます。

特定の役割と対応する承認については、以下の節で詳しく説明します。 [ロール](../../administration/using/list-of-roles.md) と [承認の理解](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

管理者は管理コンソールからユーザーを管理できます。 ユーザーは、Adobe Campaignと自動的に同期されます。 For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

Adobe Campaignでユーザーを表示するには、左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、を選択し **[!UICONTROL Administration > Users & Security > Users]**&#x200B;ます。

Adobe Campaignからユーザー管理インターフェイスにアクセスするには、をクリックし **[!UICONTROL User administration]**&#x200B;ます。

![](assets/user_management_5.png)

**関連トピック：**

* [ユーザ権限の管理](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html) （ビデオ）
* [役割のリスト](../../administration/using/list-of-roles.md)
* [承認のリスト](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## ユーザーのタイプ {#type-of-users}

このユーザーセグメントは必須ではなく、Adobe Campaignの最も一般的な使用方法を表したものに過ぎません。

この節では、Adobe Campaignユーザーの主なタイプを理解する際に役立ちます。 ここでは、ユーザーが保持できる特定の役割(開始配信、エクスポート、配信の準備など)のすべては行いません。 ロールの詳細については、「ロールの [リスト](../../administration/using/list-of-roles.md) 」および「グループとユーザー [」ページの](../../administration/using/managing-groups-and-users.md) 管理を参照してください。

Adobe Campaign内の異なるタスクが3つの主なユーザータイプ間でどのように分割されるかに焦点を当てます。

* [機能管理者](#functional-administrators): 組織のすべてのユーザーの中で、最も技術的なユーザーです。
* [上級ユーザー](#advanced-users): マーケティング担当者が配信を送信および監視するために必要なすべての要素を設定します。
* [基本ユーザー](#basic-users): キャンペーンをパーソナライズ、提供、監視するマーケターです。

>[!NOTE]
>
>機能管理者は、アドビの技術管理者とは異なります。 アドビの技術管理者は、アドビの内部的な役割を持っており、お客様はこの役割を利用できません。 インスタンスのプロビジョニング、ホスティング、インフラストラクチャの監視および監視、技術的なトラブルシューティングを管理します。

### 機能管理者 {#functional-administrators}

機能管理者は、インターフェイスの最も技術的な部分にアクセスできるユーザーです。 彼らはその役割を持ち、マーケティング担当者がキャンペーンの配信に集中できるように、プラットフォームがすべて設定されていることを確認します。 **[!UICONTROL Administration]**

Adobe Campaignインターフェイスでメニューにアクセスできるのは、機能管理者のみ **[!UICONTROL Administration]** です。 これらのユーザーは技術リソースにアクセスする必要があるので、既製のロールやなど、より高度なロールを割り当て **[!UICONTROL Administration]** る必要があり **[!UICONTROL Datamodel]** ます。 これらのロールは、あらかじめ用意され **[!UICONTROL Administrators]** ているセキュリティグループで組み合わされます。 詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [ユーザーと権限の管理](../../administration/using/about-access-management.md): プラットフォーム（ユーザー、役割、セキュリティグループ、ユニット）へのアクセスを管理します。
* [様々なチャネルの設定](../../administration/using/about-channel-configuration.md): 様々なプラットフォームチャネル、並びにタイポロジーおよび強制隔離管理を設定します。
* [一般的なアプリケーション設定を構成します](../../administration/using/external-accounts.md)。 様々なアプリ要素(外部アカウント、オプション、テクニカルワークフロー)を設定します。
* [標準搭載の機能を強化する新機能を開発します](../../developing/using/data-model-concepts.md)。 カスタムリソースを管理し、診断ツールにアクセスします。
* [インスタンスパラメーターの設定](../../administration/using/branding.md): 様々なブランドを定義し、設定(ロゴ、トラッキングの管理、ランディングページにアクセスするためのURLドメインなど)を指定します。
* [データパッケージの書き出しと読み込み](../../automating/using/managing-packages.md): 構造化XMLファイルを使用して、異なるAdobe Campaignインスタンス間でリソースを交換する。
* [ログの書き出し](../../automating/using/exporting-logs.md) 、インポートテンプレートの [定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

### 上級ユーザー {#advanced-users}

上級ユーザーとは、Adobe Campaignで最も技術的な使用例を実行するマーケティングユーザーです。 マーケティング担当者は、配信の送信や監視に使用するすべての要素を事前設定します。

このタイプのユーザーには、機能管理者よりも多くの一般的な役割が必要ですが、技術的な操作を実行できる必要があります。 そのためには、ロール（、など）やロール（すぐに使用できるロール） **[!UICONTROL Export]**&#x200B;を割り当て **[!UICONTROL Generic import]** る必要があ **[!UICONTROL Workflow]** ります。 詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [複雑なデータ管理ワークフローの作成と実行](../../automating/using/about-data-management-activities.md): データの読み込み、エンリッチおよび変換を行ってデータベースをフィードしたり、外部ファイルで必要なデータを書き出して独自のツールで処理したりします。
* [テンプレートの管理](../../start/using/marketing-activity-templates.md): テンプレートを管理し、必要に応じてマーケティングアクティビティの特定のパラメーターを事前設定します。
* [クエリの作成](../../automating/using/editing-queries.md#about-query-editor) 、オーディエンスの [管理](../../audiences/using/about-audiences.md): クエリを使用して手動でオーディエンスを作成するか、専用ワークフローを自動的に使用して作成します。
* [高度な式編集を実行します](../../automating/using/editing-queries.md#about-query-editor)。 高度な関数を使用して、日付、文字列、数値フィールド、並べ替えなどの特定のクエリを実行するための値を操作します。
* [リスト](../../automating/using/exporting-lists.md) を書き出し、既存のインポートテンプレートを使用して [データを読み込みます](../../automating/using/importing-data-with-import-templates.md)。

### 基本ユーザー {#basic-users}

機能的な管理者や上級ユーザーのおかげで、マーケティング担当者は、技術的な設定を気にすることなく、キャンペーンをパーソナライズ、配信、監視できます。 そのためには、ロール、ロールなど、あらかじめ用意され **[!UICONTROL Prepare deliveries]**&#x200B;ているロールを割り当て **[!UICONTROL Workflow]** る必要があ **[!UICONTROL Start deliveries]** ります。 これらのロールは、あらかじめ用意され **[!UICONTROL Standard Users]** ているセキュリティグループで組み合わされます。 詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [プログラムとキャンペーンの管理](../../start/using/programs-and-campaigns.md): 様々な種類のアクティビティ(電子メール、SMSメッセージ、プッシュ通知、ワークフロー、ランディングページ)を含むマーケティングキャンペーンを作成できます。
* [プロファイル](../../audiences/using/about-profiles.md) および [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md): 配信がターゲットにする、特定およびテスト受信者を管理します。 名追加、姓、連絡先情報、購読、電子メールなどの情報
* [メッセージの作成と送信](../../sending/using/confirming-the-send.md): メッセージの作成、オーディエンスの選択、メッセージの内容とパーソナライズ要素の定義、配達確認の送信、最終オーディエンスの送信を行います。
* [ランディングページの作成と公開](../../channels/using/getting-started-with-landing-pages.md): 購読フォームや購読解除フォームなど、クライアントのオファーを行う一連のサービスを作成および管理します。
* [キャンペーンワークフローの作成と実行](../../automating/using/building-a-workflow.md): ワークフローを使用してキャンペーンプロセスを自動化します。
* [使用可能なレポートを使用してマーケティングアクティビティを監視します](../../reporting/using/defining-the-report-period.md)。

## ユーザーの作成 {#creating-a-user}

ユーザーをインスタンスに追加するには、まず管理コンソールでユーザーを作成してから、Adobe Campaign標準で管理する必要があります。

1. 詳細設定メニューからを選択し、をクリック **[!UICONTROL Administration > Users & Security > Users]** して管理コンソール **[!UICONTROL User administration]** にアクセスします。

   ![](assets/user_management_5.png)

1. で、 **[!UICONTROL Admin Console]**&#x200B;タブのをクリックし **[!UICONTROL Users]** ます。

1. クリック **[!UICONTROL Add User]** .

   ![](assets/create_user_2.png)

1. 「 **[!UICONTROL User details]** 」タブで、電子メールアドレス、名前、姓など、ユーザーの詳細を入力します。

   ![](assets/create_user_3.png)

1. タブから、1つまたは複数のセキュリティグループをユーザーに割り当て **[!UICONTROL Assign products]** ます。 For more information on security groups, refer to this [page](../../administration/using/managing-groups-and-users.md).

   設定が完了 **[!UICONTROL Save]** したら、をクリックします。

   ![](assets/create_user_4.png)

ユーザーが作成され、次のウィンドウにリダイレクトされる電子メールを受け取ります。このウィンドウでは、ユーザーはパスワードを設定してから使用条件に同意する必要があります。 これで、このユーザはAdobe Campaign標準インスタンスに接続できます。

![](assets/create_user_5.png)

ユーザーは、インスタンスにサインインするとすぐにAdobe Campaign標準と同期されます。

その後、ユーザーがAdobe Campaignと正しく同期されているかどうかを確認できます。

1. 詳細メニューから、以前に作成したユーザを **[!UICONTROL Administration > Users & Security > Users]** 選択します。

1. または **[!UICONTROL Mobile]**&#x200B;必要に応じて、を更新 **[!UICONTROL Time zone]****[!UICONTROL Regional settings]** します。

1. ユーザーのセキュリティグループを確認します。 ここでは、ユーザーに **[!UICONTROL Administrators]** セキュリティ・グループが割り当てられていることを確認できます。

   >[!N注意]
   >
   >セキュリティグループの削除または追加は、管理コンソールでのみ行うことができます。

   ![](assets/create_user_6.png)

1. このユーザー **[!UICONTROL Account disabled]** を非アクティブ化するかどうかを選択します。

1. このフィールドでは、ユーザーがこのインスタンスに接続する方法（内部ネットワーク、VPNなど）を選択します。 **[!UICONTROL Authorized connection zone]**

1. クリック **[!UICONTROL Save]** .

これで、Adobe Campaign標準を使用する準備が整いました。
