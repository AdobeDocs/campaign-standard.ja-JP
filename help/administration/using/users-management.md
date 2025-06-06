---
title: ユーザー管理
description: Adobe Campaign ユーザーには、特定の役割が割り当てられます。主なユーザータイプについて説明します。
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 6605203e-78f8-4ebd-b256-a621a3a9d638
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 81%

---

# ユーザー管理{#users-management}

## ユーザーについて {#about-users}

Adobe Campaign では、ユーザーに一連の役割を割り当てて、ユーザーがアクセスできるインターフェイス領域を定義できます。

特定の役割とそれに対応する認証については、[役割の概要](../../administration/using/list-of-roles.md)の節および[認証](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=ja)の節で詳しく説明します。

管理者は、Admin Consoleからユーザーを管理できます。 ユーザーは、Adobe Campaign と自動的に同期されるようになります。詳しくは、[Admin Console](https://helpx.adobe.com/jp/enterprise/using/users.html) ドキュメントを参照してください。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

Adobe Campaignでユーザーを表示するには、左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、「**&#x200B;[!UICONTROL Administration > Users & Security > Users]&#x200B;**」を選択します。**

Adobe Campaign からユーザー管理インターフェイスにアクセスするには、**[!UICONTROL User administration]** をクリックします。

![](assets/user_management_5.png)

**関連トピック：**

* [ユーザー権限の管理](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html?lang=ja)（ビデオ）
* [役割のリスト](../../administration/using/list-of-roles.md)
* [認証のリスト](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=ja)

## ユーザーのタイプ {#type-of-users}

このユーザーセグメント化は必須ではなく、Adobe Campaign の最も一般的な使用方法の 1 つに過ぎません。

この節では、Adobe Campaign ユーザーの主なタイプを理解するのに役立ちます。 ユーザーが保持できる特定の役割（配信の開始、書き出し、配信の準備など）について詳しくは、[ 役割のリスト ](../../administration/using/list-of-roles.md) および [ グループとユーザーの管理 ](../../administration/using/managing-groups-and-users.md) ページを参照してください。

この節では、Adobe Campaign 内の様々なタスクを 3 つの主なユーザータイプに分けて説明します。

* [機能管理者](#functional-administrators)：組織のすべてのユーザーの中で、技術面での最高責任者となるユーザーです。
* [ 上級ユーザー ](#advanced-users)：マーケターが配信を送信および監視するために必要なすべての要素を設定します。
* [基本ユーザー](#basic-users)：キャンペーンをパーソナライズ、配信、および監視するマーケターです。

>[!NOTE]
>
>機能管理者は、アドビの技術管理者とは異なります。アドビの技術管理者は、お客様には割り当てられないアドビ内部の役割を持っており、インスタンスのプロビジョニング、ホスティング、インフラストラクチャの監視および監督、技術的なトラブルシューティングを管理します。

### 職務管理者 {#functional-administrators}

機能管理者は、インターフェイスの技術面において最高レベルのアクセス権限を持つユーザーです。機能管理者は **[!UICONTROL Administration]** の役割を持ち、マーケターがキャンペーンの配信に専念できるように、プラットフォームのあらゆる設定を確認します。

>[!IMPORTANT]
>
>**[!UICONTROL Administration]** の役割と **すべて** ユニットへのアクセス権を持つ機能管理者のみが、送信ログ、メッセージログ、トラッキングログ、除外ログ、提案ログおよびサブスクリプションログにアクセスできます。 管理者以外のユーザーは、これらのログをターゲットにすることができますが、これはリンクされたテーブル（プロファイル、配信）から開始します。

Adobe Campaign インターフェイスで **[!UICONTROL Administration]** メニューにアクセスできるのは、機能管理者のみです。これらのユーザーは技術リソースにアクセスする必要があるので、標準の役割（**[!UICONTROL Administration]** および **[!UICONTROL Datamodel]**）など、より高度な役割を割り当てる必要があります。これらの役割は、標準の **[!UICONTROL Administrators]** セキュリティグループで組み合わされます。詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [ユーザーと権限の管理](../../administration/using/about-access-management.md)：プラットフォーム（ユーザー、役割、セキュリティグループ、単位）へのアクセスを管理します。
* [様々なチャネルの設定](../../administration/using/about-channel-configuration.md)：様々なプラットフォームチャネル、タイポロジおよび強制隔離管理を設定します。
* [一般的なアプリケーション設定](../../administration/using/external-accounts.md)：様々なアプリケーション要素（外部アカウント、オプション、テクニカルワークフロー）を設定します。
* [標準機能を強化する新機能の開発](../../developing/using/data-model-concepts.md)：カスタムリソースを管理し、診断ツールにアクセスします。
* [インスタンスパラメーターの設定](../../administration/using/branding.md)：様々なブランドを定義し、設定（ロゴ、トラッキングの管理、ランディングページにアクセスするための URL ドメインなど）を指定します。
* [データパッケージのエクスポートとインポート](../../automating/using/managing-packages.md)：構造化 XML ファイルを使用して、異なる Adobe Campaign インスタンス間でリソースを交換します。
* [ログの書き出し](../../automating/using/exporting-logs.md)と[インポートテンプレートの定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

### 上級ユーザー {#advanced-users}

上級ユーザーとは、Adobe Campaign における技術的な操作について最高レベルの権限を持つマーケティングユーザーです。上級ユーザーは、マーケターが配信を送信および監視するために使用するすべての要素の事前設定をおこないます。

このタイプのユーザーは、機能管理者よりも多くの一般的な役割が必要ですが、技術的な操作を実行できる必要があります。そのためには、**[!UICONTROL Export]** や **[!UICONTROL Generic import]**、**[!UICONTROL Workflow]** などの標準の役割を割り当てる必要があります。詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [複雑なデータ管理ワークフローの作成と実行](../../automating/using/about-data-management-activities.md)：データのインポート、エンリッチメントおよび変換によってデータベースへのデータ取り込みをおこない、外部ファイルで必要なデータを書き出して独自のツールで処理します。
* [テンプレートの管理](../../start/using/marketing-activity-templates.md)：テンプレートを管理し、必要に応じてマーケティングアクティビティの特定のパラメーターを事前設定します。
* [クエリの作成](../../automating/using/editing-queries.md#about-query-editor)と[オーディエンスの管理](../../audiences/using/about-audiences.md)：クエリを使用してオーディエンスを手動で作成するか、専用ワークフローを使用してオーディエンスを自動で作成します。
* [高度な式編集の実行](../../automating/using/editing-queries.md#about-query-editor)：高度な関数を使用して、日付、文字列、数値フィールド、並べ替えなどの特定のクエリを実行するための値を操作します。
* [リストの書き出し](../../automating/using/exporting-lists.md)、および[既存のインポートテンプレートを使用したデータのインポート](../../automating/using/importing-data-with-import-templates.md)。

### 基本ユーザー {#basic-users}

機能管理者や上級ユーザーのサポートにより、マーケターは、技術的な設定に煩わされることなくキャンペーンのパーソナライズ、配信、監視に専念できます。そのためには、**[!UICONTROL Prepare deliveries]** や **[!UICONTROL Workflow]**、**[!UICONTROL Start deliveries]** などの標準の役割を割り当てる必要があります。これらの役割は、標準の **[!UICONTROL Standard Users]** セキュリティグループで組み合わされます。詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

実行できる主なタスクは次のとおりです。

* [プログラムとキャンペーンの管理](../../start/using/programs-and-campaigns.md)：様々な種類のアクティビティ（メール、SMS メッセージ、プッシュ通知、ワークフロー、ランディングページ）を含むマーケティングキャンペーンを作成します。
* [プロファイル](../../audiences/using/about-profiles.md)および[テストプロファイル](../../audiences/using/managing-test-profiles.md)の管理：配信のターゲットとなる特定の受信者およびテスト受信者を管理します。姓名、連絡先情報、購読、メールなどの情報を追加します。
* [メッセージの作成と送信](../../sending/using/confirming-the-send.md)：メッセージの作成、オーディエンスの選択、メッセージの内容とパーソナライゼーション要素の定義、配達確認の送信、オーディエンスへの最終メッセージの送信をおこないます。
* [ランディングページの作成と公開](../../channels/using/getting-started-with-landing-pages.md)：購読フォームや購読解除フォームなど、クライアントにオファーする一連のサービスを作成および管理します。
* [キャンペーンワークフローの作成と実行](../../automating/using/building-a-workflow.md)：ワークフローを使用してキャンペーンプロセスを自動化します。
* [使用可能なレポート](../../reporting/using/defining-the-report-period.md)を使用してマーケティングアクティビティを監視します。

## ユーザーの作成 {#creating-a-user}

インスタンスにユーザーを追加するには、まずAdmin Consoleでユーザーを作成してから、Adobe Campaign Standardで管理する必要があります。

1. 詳細メニューから **[!UICONTROL Administration > Users & Security > Users]** を選択し、**[!UICONTROL User administration]** をクリックして Admin Console にアクセスします。

   ![](assets/user_management_5.png)

1. **[!UICONTROL Admin Console]** で「**[!UICONTROL Users]**」タブをクリックします。

1. 「**[!UICONTROL Add User]**」をクリックします。

   ![](assets/create_user_2.png)

1. 「**[!UICONTROL User details]**」タブで、メールアドレスや姓名などのユーザーの詳細情報を入力します。

   ![](assets/create_user_3.png)

1. 「**[!UICONTROL Assign products]**」タブで、1 つ以上のセキュリティグループをユーザーに割り当てます。 セキュリティグループについて詳しくは、この[ページ](../../administration/using/managing-groups-and-users.md)を参照してください。

   設定が完了したら、「**[!UICONTROL Save]**」をクリックします。

   ![](assets/create_user_4.png)

ユーザーが作成されます。ユーザーはメールを受け取り、下のウィンドウにリダイレクトされます。このウィンドウでは、ユーザーはパスワードを設定して利用規約に同意する必要があります。これで、ユーザーは Adobe Campaign Standard インスタンスに接続できるようになります。

![](assets/create_user_5.png)

インスタンスに署名すると、このユーザーはAdobe Campaign Standardに同期されます。

その後、ユーザーが Adobe Campaign と正しく同期されているかどうかを確認できます。

1. 詳細設定メニューの **[!UICONTROL Administration > Users & Security > Users]** から、以前に作成したユーザーを選択します。

1. 必要に応じて、**[!UICONTROL Mobile]**、**[!UICONTROL Time zone]**、または **[!UICONTROL Regional settings]** を更新します。

1. ユーザーのセキュリティグループを確認します。ここでは、ユーザーに **[!UICONTROL Administrators]** セキュリティグループが割り当てられていることを確認できます。

   >[!NOTE]
   >
   >セキュリティグループの削除または追加は、Admin Console でのみおこなうことができます。

   ![](assets/create_user_6.png)

1. このユーザーを無効にするには、「**[!UICONTROL Account disabled]**」を選択します。

1. 「**[!UICONTROL Authorized connection zone]**」フィールドでは、ユーザーがこのインスタンスに接続する方法（内部ネットワーク、VPN など）を選択します。

1. 「**[!UICONTROL Save]**」をクリックします。

これで、Adobe Campaign Standard を使用する準備が整いました。

## チュートリアルビデオ {#video}

このビデオでは、ユーザーのアクセス権を管理する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/36085?quality=12&captions=jpn)

その他のCampaign Standardチュートリアルビデオについては、[ こちら ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。
