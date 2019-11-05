---
title: ユーザー管理
description: 'Adobe Campaignユーザーは特定の役割を持ちます。 メインユーザータイプを検出します。 '
page-status-flag: 非活性化の
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: ユーザーとセキュリティ
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ユーザー管理{#users-management}

## ユーザーについて {#about-users}

Adobe Campaignでは、ユーザーに一連のロールを割り当てて、ユーザーがアクセスできるインターフェイスの部分を定義できます。

具体的な役割と対応する承認について、以下の節で詳しく説明します。役割 [と承認](../../administration/using/list-of-roles.md)[](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

管理者は、管理コンソールからユーザーを管理できます。 その後、ユーザーは自動的にAdobe Campaignと同期されます。 For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

Adobe Campaignでユーザーを表示するには、左上隅 **[!UICONTROL Adobe Campaign]** にあるロゴをクリックし、を選択します **[!UICONTROL Administration > Users & Security > Users]**。

Adobe Campaignからユーザー管理インターフェイスにアクセスするには、をクリックしま **[!UICONTROL User administration]**&#x200B;す。

![](assets/user_management_5.png)

**関連トピック：**

* [ユーザ権限の管理](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) （ビデオ）
* [役割のリスト](../../administration/using/list-of-roles.md)
* [承認のリスト](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## ユーザーのタイプ {#type-of-users}

このユーザーセグメントは必須ではなく、Adobe Campaignの最も一般的な使用方法を表したものに過ぎません。

この節では、Adobe Campaignの主なユーザータイプを理解する際に役立ちます。 ここでは、ユーザーが保持できる特定の役割（配信の開始、エクスポート、配信の準備など）については説明しません。 ロールの詳細については、「ロールのリスト」お [よび](../../administration/using/list-of-roles.md) 「グループとユ [ーザーの管理」ページを参照してください](../../administration/using/managing-groups-and-users.md) 。

Adobe Campaignの様々なタスクを3つのメインユーザータイプに分割する方法に焦点を当てます。

* [機能管理者](#functional-administrators):組織のすべてのユーザーの中で、最も技術的なユーザーです。
* [上級ユーザ](#advanced-users):マーケターが配信を送信および監視するために必要なすべての要素を設定します。
* [基本ユーザ](#basic-users):キャンペーンをパーソナライズ、提供、監視するマーケターです。

>[!NOTE]
>
>機能管理者は、アドビの技術管理者とは異なります。 アドビの技術管理者は、アドビの内部的な役割を担っており、お客様はこの役割を利用できません。 インスタンスのプロビジョニング、ホスティング、インフラストラクチャの監視、技術的なトラブルシューティングを管理します。

### 機能管理者 {#functional-administrators}

機能管理者は、インターフェイスの最も技術的な部分にアクセスできるユーザーです。 この役割を持ち、マ **[!UICONTROL Administration]** ーケティング担当者がキャンペーンの配信に集中するだけで済むように、プラットフォームがすべて設定されていることを確認します。

機能管理者は、Adobe Campaignインターフェイスでメニューにア **[!UICONTROL Administration]** クセスできる唯一のユーザーです。 これらのユーザーは技術リソースにアクセスする必要があるので、あらかじめ用意されているロールやロールなど、より高度な **[!UICONTROL Administration]** ロールを **[!UICONTROL Datamodel]** 割り当てる必要があります。 これらの役割は、あらかじめ用意さ **[!UICONTROL Administrators]** れているセキュリティグループ内で組み合わされます。 詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [ユーザーと権限の管理](../../administration/using/about-access-management.md):プラットフォーム（ユーザー、役割、セキュリティグループ、ユニット）へのアクセスを管理します。
* [様々なチャネルを設定します](../../administration/using/about-channel-configuration.md)。様々なプラットフォームチャネル、タイポロジ、検疫管理を設定します。
* [一般的なアプリケーション設定を設定します](../../administration/using/external-accounts.md)。様々なアプリケーション要素（外部アカウント、オプション、技術ワークフロー）を設定します。
* [すぐに使える機能を強化する新機能を開発します](../../developing/using/data-model-concepts.md)。カスタムリソースを管理し、診断ツールにアクセスします。
* [インスタンスパラメーターの設定](../../administration/using/branding.md):様々なブランドを定義し、その設定（ロゴ、トラッキングの管理、ランディングページにアクセスするためのURLドメインなど）を行います。
* [データパッケージの書き出しと読み込み](../../automating/using/managing-packages.md):構造化XMLファイルを使用して、様々なAdobe Campaignインスタンス間でリソースを交換します。
* [ログを書き出し](../../automating/using/exporting-logs.md) 、インポ [ートテンプレートを定義しま](../../automating/using/defining-import-templates.md)す。

### 上級ユーザー {#advanced-users}

上級ユーザーとは、Adobe Campaignで最も技術的な使用例を実行するマーケティングユーザーです。 マーケターが配信の送信や監視に使用するすべての要素を事前設定します。

このタイプのユーザーには、機能管理者よりも一般的な役割が必要ですが、一部の技術的な操作を実行できる必要があります。 そのためには、（、など）既製のロールを割り **[!UICONTROL Export]**&#x200B;当て **[!UICONTROL Generic import]** る **[!UICONTROL Workflow]** 必要があります。 詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [複雑なデータ管理ワークフローの作成と実行](../../automating/using/about-data-management-activities.md):データの読み込み、拡張、変換を行ってデータベースにデータを埋め込んだり、必要なデータを外部ファイルに書き出して独自のツールで処理したりします。
* [テンプレートの管理](../../start/using/about-templates.md):テンプレートを管理し、必要に応じてマーケティングアクティビティの特定のパラメーターを事前設定します。
* [クエリの作成](../../automating/using/editing-queries.md#about-query-editor) 、オ [ーディエンスの管理](../../audiences/using/about-audiences.md):クエリを使用してオーディエンスを手動で作成するか、専用のワークフローを使用して自動的にオーディエンスを作成します。
* [式の高度な編集を実行します](../../automating/using/editing-queries.md#about-query-editor)。高度な関数を使用して、日付、文字列、数値フィールド、並べ替えなどの特定のクエリを実行する際に使用する値を操作します。
* [既存のインポートテンプレートを使用して](../../automating/using/exporting-lists.md) 、リスト [をエクスポートし、データをインポートします](../../automating/using/importing-data-with-import-templates.md)。

### 基本ユーザ {#basic-users}

機能管理者や上級ユーザーのおかげで、マーケティング担当者は、技術的な設定を気にすることなく、キャンペーンをパーソナライズ、配信、監視できます。 そのためには、ロール、ロールなど、あらかじめ用意され **[!UICONTROL Prepare deliveries]**&#x200B;てい **[!UICONTROL Workflow]** るロ **[!UICONTROL Start deliveries]** ールを割り当てる必要があります。 これらの役割は、あらかじめ用意さ **[!UICONTROL Standard Users]** れているセキュリティグループ内で組み合わされます。 詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [プログラムとキャンペーンの管理](../../start/using/programs-and-campaigns.md):様々なタイプのアクティビティ（電子メール、SMSメッセージ、プッシュ通知、ワークフロー、ランディングページ）を含むマーケティングキャンペーンを作成します。
* プロファ [イル](../../audiences/using/about-profiles.md) /テ [ストプロファイル](../../sending/using/managing-test-profiles-and-sending-proofs.md):配信によってターゲット設定される、特定された受信者およびテスト受信者を管理します。 名、姓、連絡先情報、購読、電子メールなどの情報を追加します。
* [メッセージの作成と送信](../../sending/using/confirming-the-send.md):メッセージの作成、オーディエンスの選択、メッセージのコンテンツとパーソナライゼーション要素の定義、校正の送信、オーディエンスへの最終的なメッセージの送信を行います。
* [ランディングページの作成と発行](../../channels/using/about-landing-pages.md):購読フォームや購読解除フォームなど、クライアントに提供する一連のサービスを作成し、管理します。
* [キャンペーンワークフローの作成と実行](../../automating/using/building-a-workflow.md):ワークフローを使用してキャンペーンプロセスを自動化します。
* 使用可能なレポートを使用してマーケティングア [クティビティを監視](../../reporting/using/defining-the-report-period.md)。

## ユーザーの作成 {#creating-a-user}

インスタンスにユーザーを追加するには、まず管理コンソールで作成してから、Adobe Campaign Standardで管理する必要があります。

1. 詳細メニューで、を選択し、をクリ **[!UICONTROL Administration > Users & Security > Users]** ックして管理 **[!UICONTROL User administration]** コンソールにアクセスします。

   ![](assets/user_management_5.png)

1. で、タブ **[!UICONTROL Admin Console]**&#x200B;をクリックし **[!UICONTROL Users]** ます。

1. Click **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. タブで、 **[!UICONTROL User details]** 電子メールアドレス、名前、姓などのユーザーの詳細を入力します。

   ![](assets/create_user_3.png)

1. タブから、1 **[!UICONTROL Assign products]** つ以上のセキュリティグループをユーザーに割り当てます。 For more information on security groups, refer to this [page](../../administration/using/managing-groups-and-users.md).

   設定が完了 **[!UICONTROL Save]** したら、をクリックします。

   ![](assets/create_user_4.png)

これでユーザーが作成され、次のウィンドウにリダイレクトする電子メールが届きます。このウィンドウで、ユーザーはパスワードを設定し、使用条件に同意する必要があります。 これで、このユーザーはAdobe Campaign Standardインスタンスに接続できるようになります。

![](assets/create_user_5.png)

ユーザーは、インスタンスにサインインするとすぐにAdobe Campaign Standardと同期されます。

その後、ユーザーがAdobe Campaignと正しく同期されているかどうかを確認できます。

1. アドバンスメニューから、以 **[!UICONTROL Administration > Users & Security > Users]** 前に作成したユーザを選択します。

1. または必要に応じ **[!UICONTROL Mobile]**&#x200B;て、を **[!UICONTROL Time zone]** 更新 **[!UICONTROL Regional settings]** してください。

1. ユーザーのセキュリティグループを確認します。 ここでは、ユーザーにセキュリティ・グループが割り当てられているこ **[!UICONTROL Administrators]** とを示します。

   >[!N注]
   >
   >セキュリティグループは、管理コンソールでのみ削除またはユーザーに追加できます。

   ![](assets/create_user_6.png)

1. このユー **[!UICONTROL Account disabled]** ザーを非アクティブ化するかどうかを選択します。

1. このフィ **[!UICONTROL Authorized connection zone]** ールドで、ユーザがこのインスタンスに接続する方法（例：内部ネットワーク、VPN）を選択します。

1. Click **[!UICONTROL Save]**.

これで、ユーザーはAdobe Campaign Standardを使用する準備が整いました。
