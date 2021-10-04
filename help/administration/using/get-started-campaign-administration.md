---
title: Campaign Standard 管理の基本を学ぶ要
description: ユーザーと権限の管理、監視のガイドライン、チャネル固有の設定およびアプリケーション設定のガイドラインを確認します。
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 15%

---

# Campaign Standard 管理の基本を学ぶ要 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理メニュー</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">ユーザーとセキュリティ</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">チャネルの設定</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">アプリケーション設定</a></p></td></tr>
</table>

クラウドベースのソリューションであるAdobe Campaignでは、管理者が様々な方法でアプリケーションを設定できます。 インフラストラクチャの設定はAdobeが実行しますが、機能管理者は、以下に説明する様々な設定操作を実行できます。

>[!NOTE]
>
>実装と設定に関する質問やリクエストがある場合は、担当のAdobeアカウント担当者にお問い合わせください。

管理者ユーザーは、CampaignCampaign コントロールパネルを利用して、各インスタンスの設定を管理し、使用状況を追跡することもできます。 詳しくは、[該当するドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)を参照してください。

## 管理メニュー {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

様々なAdobe Campaign管理操作は、左上隅のAdobe Campaignロゴをクリックするとアクセスできる **[!UICONTROL Administration]** メニューを使用して実行されます。 インターフェイスのこの部分には、プラットフォームの機能管理者のみがアクセスできます。

次のメニューを使用できます。

* [ユーザーとセキュリティ](../../administration/using/about-access-management.md):このメニューを使用すると、プラットフォーム（ユーザー、役割、セキュリティグループ、単位）へのアクセスを管理できます。
* [チャネル](../../administration/using/about-channel-configuration.md):このメニューは、様々なプラットフォームチャネル（E メール、モバイル）、タイポロジおよび強制隔離の管理にリンクされた技術パラメーターを再グループ化します。
* [アプリケーション設定](../../administration/using/external-accounts.md):このメニューを使用すると、様々なアプリケーション要素（外部アカウント、オプション、テクニカルワークフロー）を設定できます。
* [開発](../../developing/using/data-model-concepts.md):このメニューを使用すると、カスタムリソースを管理し、診断ツールにアクセスできます。
* [インスタンス設定](../../administration/using/branding.md):このメニューでは、様々なブランドを定義し、その設定（ロゴ、トラッキングの管理、ランディングページにアクセスするための URL ドメインなど）を指定します。
* [導入](../../automating/using/managing-packages.md):このメニューは、パッケージのインポートおよびエクスポートオプションを再グループ化します。
* [顧客指標](../../audiences/using/active-profiles.md):Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。このレポートは情報が得られるだけで、請求に直接影響はありません。
* [プライバシーツール](../../start/using/privacy-management.md):このメニューを使用すると、GDPR のアクセス要求および削除要求を作成し、その推移を追跡できます。

## ユーザーとセキュリティ {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

ユーザーをアプリケーションにアクセスするよう招待し、**セキュリティグループ** を管理します。セキュリティグループとは、組織内で同じ役割と権限を共有するユーザーのセットです。 Adobe Campaignには、ユーザーとユーザーグループに割り当てる単一の認証を定義できる **役割** のセットがデフォルトで用意されています。 **組織単位** と組み合わせると、役割によってユーザーはインターフェイスのフィルタ表示が可能になり、様々な機能へのアクセスが定義されます。

また、Campaign Standard では、セキュリティ関連の情報を監視できます。 ユーザーが実行したデータのエクスポートに関する情報を **[!UICONTROL Export audits]** 画面から取得し、**[!UICONTROL Licenses]** 画面を使用して、組織内にインストールされている Campaign ライセンスのほか、ビルド番号、リリースバージョン、契約条件などの様々な情報を監視できます。

詳しくは、以下を参照してください。

* [ユーザー管理](../../administration/using/users-management.md)
* [組織単位](../../administration/using/organizational-units.md)
* [役割のリスト](../../administration/using/list-of-roles.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)
* [エクスポートログの監査](../../administration/using/auditing-export-logs.md)
* [ライセンス](../../administration/using/licenses.md)

## チャネルの設定 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaignのすべての通信チャネルは、メッセージを効果的に送信できるように正しく設定されている必要があります。**[!UICONTROL Channel]**

様々な **email** パラメーターを設定します。バウンス、強制隔離、E メールのプロパティおよびルーティングパラメーター（通常はルール）の処理ルール **SMS** チャネルのルーティング設定とプロパティ、および SMS のエンコードと形式を定義します。

Adobe Experience Platform SDK を使用してアプリ内メッセージとプッシュ通知を送信できるように、**モバイルアプリケーション** を設定します。

詳しくは、以下を参照してください。

* [チャネル設定について](../../administration/using/about-channel-configuration.md)
* [E メールチャネルの設定](../../administration/using/configuring-email-channel.md)
* [SMS チャネルの設定](../../administration/using/configuring-sms-channel.md)
* [モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)

## アプリケーション設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standardには、ニーズに合わせて設定できる様々なアプリケーション要素が付属しています。

**外部アカウント** を設定します。外部アカウントは、Adobe Campaignを外部サーバーに接続するのに使用します。 Campaign Standardターゲットマッピングにアクセスし、**テクニカルワークフロー** を使用してプラットフォームを監視します。

組織の 1 つまたは複数の **ブランド** を定義し、重要なシステムアクティビティの場合は、アプリケーション内で **リアルタイム通知** の送信を設定します。

詳しくは、以下を参照してください。

* [Adobe Campaign Standard 設定について](../../administration/using/about-campaign-standard-settings.md)
* [外部アカウント](../../administration/using/external-accounts.md)
* [Campaign でのターゲットマッピング](../../administration/using/target-mappings-in-campaign.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [ブランディング](../../administration/using/branding.md)
* [内部通知の送信](../../administration/using/sending-internal-notifications.md)
