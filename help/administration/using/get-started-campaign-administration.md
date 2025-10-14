---
title: Campaign Standard 管理の基本を学ぶ要
description: ユーザーと権限の管理、監視のガイドライン、チャネル固有の設定およびアプリケーション設定のガイドラインについて学ぶ
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 13%

---

# Campaign Standard 管理の基本を学ぶ要 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理メニュー</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">ユーザーとセキュリティ</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">チャネル設定</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">アプリケーション設定</a></p></td></tr>
</table>

Adobe Campaignは、クラウドベースのソリューションとして、管理者にアプリケーションを設定するための様々な方法を提供します。 インフラストラクチャの設定は管理者が行いますが、Adobe管理者は、以下に説明する様々な設定操作を実行できます。

>[!NOTE]
>
>実装や設定に関するご質問やご要望については、Adobeアカウント担当者にお問い合わせください。

また、管理者ユーザーは、Campaign Campaign コントロールパネルを利用して設定を管理し、各インスタンスの使用状況をトラッキングすることもできます。 詳しくは、[該当するドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)を参照してください。

## 管理メニュー {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

様々なAdobe Campaign管理操作は、左上隅のAdobe Campaign ロゴをクリックするとアクセスできる **[!UICONTROL Administration]** メニューから実行されます。 インターフェイスのこの部分には、プラットフォームの機能管理者のみがアクセスできます。

使用できる様々なメニューを次に示します。

* [&#x200B; ユーザーとセキュリティ &#x200B;](../../administration/using/about-access-management.md)：このメニューを使用すると、プラットフォーム（ユーザー、役割、セキュリティグループ、ユニット）へのアクセスを管理できます。
* [&#x200B; チャネル &#x200B;](../../administration/using/about-channel-configuration.md)：このメニューは、様々なプラットフォームチャネル（メール、モバイル）にリンクされた技術的なパラメーターのほか、タイポロジおよび強制隔離管理を再グループ化します。
* [&#x200B; アプリケーション設定 &#x200B;](../../administration/using/external-accounts.md)：このメニューを使用すると、様々なアプリケーション要素（外部アカウント、オプション、テクニカルワークフロー）を設定できます。
* [&#x200B; 開発 &#x200B;](../../developing/using/data-model-concepts.md)：このメニューを使用すると、カスタムリソースを管理し、診断ツールにアクセスできます。
* [&#x200B; インスタンス設定 &#x200B;](../../administration/using/branding.md)：このメニューでは、様々なブランドを定義し、その設定（ロゴ、トラッキングの管理、ランディングページにアクセスするための URL ドメインなど）を設定できます。
* [&#x200B; デプロイメント &#x200B;](../../automating/using/managing-packages.md)：このメニューは、パッケージのインポートおよびエクスポートオプションを再グループ化します。
* [&#x200B; 顧客指標 &#x200B;](../../audiences/using/active-profiles.md):Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。 このレポートは情報提供だけを目的としており、請求に直接影響を与えるものではありません。
* [&#x200B; プライバシーツール &#x200B;](../../start/using/privacy-management.md)：このメニューを使用すると、GDPR のアクセスリクエストと削除リクエストを作成し、それらの進化を追跡できます。

## ユーザーとセキュリティ {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

ユーザーを招待してアプリケーションにアクセスさせ、**セキュリティグループ** を管理させます。セキュリティグループは、組織内で同じ役割と権限を共有するユーザーの集まりです。 デフォルトでは、Adobe Campaignには一連の **ロール** が用意されています。これを使用すると、ユーザーやユーザーグループに割り当てる単一権限を定義できます。 役割を **組織単位** と組み合わせることで、ユーザーはインターフェイスのフィルター表示を使用し、様々な機能へのアクセス権を定義できます。

また、Campaign standard では、セキュリティ関連の情報を監視することもできます。 ユーザーが実行したデータエクスポートに関する情報を **[!UICONTROL Export audits]** 画面から取得できます。**[!UICONTROL Licenses]** 画面を利用すると、組織内にインストールされているすべての Campaign ライセンスのほか、ビルド番号、リリースバージョン、契約条件などの様々な情報を監視できます。

詳しくは、以下を参照してください。

* [ユーザー管理](../../administration/using/users-management.md)
* [組織単位](../../administration/using/organizational-units.md)
* [役割のリスト](../../administration/using/list-of-roles.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)
* [エクスポートログの監査](../../administration/using/auditing-export-logs.md)
* [ライセンス](../../administration/using/licenses.md)

## チャネル設定 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

メッセージを効率的に送信するには、Adobe Campaignのすべての通信チャネルが正しく設定されている必要があります。**[!UICONTROL Channel]** のメニューを使用すると、様々なチャネルにリンクされた技術的なパラメーターを管理できます。

様々な **メール** パラメーターの設定：バウンス、強制隔離、メールプロパティとルーティングパラメーターの処理ルール、タイポリルール。 **SMS** チャネルのルーティング設定とプロパティ、および SMS エンコーディングと SMS 形式を定義します。

Adobe Experience Platform SDK を使用してアプリ内メッセージおよびプッシュ通知を送信できるようにするには、**モバイルアプリケーション** を設定します。

詳しくは、以下を参照してください。

* [チャネル設定について](../../administration/using/about-channel-configuration.md)
* [メールチャネルの設定](../../administration/using/configuring-email-channel.md)
* [SMS チャネルの設定](../../administration/using/configuring-sms-channel.md)
* [モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)

## アプリケーション設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standardには、ニーズに合わせて設定できる様々なアプリケーション要素が用意されています。

Adobe Campaignを外部サーバーに接続するために使用する **外部アカウント** を設定します。 Campaign Standardのターゲットマッピングにアクセスし、**テクニカルワークフロー** を使用してプラットフォームを監視します。

組織の 1 つまたは複数の **ブランド** を定義し、重要なシステムアクティビティの場合にアプリケーション内で **リアルタイム通知** の送信を設定します。

詳しくは、以下を参照してください。

* [Adobe Campaign Standard 設定について](../../administration/using/about-campaign-standard-settings.md)
* [外部アカウント](../../administration/using/external-accounts.md)
* [Campaign でのターゲットマッピング](../../administration/using/target-mappings-in-campaign.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [ブランディング](../../administration/using/branding.md)
* [内部通知の送信](../../administration/using/sending-internal-notifications.md)
