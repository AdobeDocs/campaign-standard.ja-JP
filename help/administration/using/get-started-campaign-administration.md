---
solution: Campaign Standard
product: campaign
title: Campaign Standard の管理の概要
description: ユーザーと権限の管理、監視のガイドライン、チャネル固有の設定およびアプリケーション設定のガイドラインを確認します。
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
feature: アクセス管理
role: 管理者
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 16%

---


# Campaign Standard の管理の概要 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理メニュー</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">ユーザーとセキュリティ</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">チャネル設定</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">アプリケーション設定</a></p></td></tr>
</table>

クラウドベースのソリューションでは、Adobe Campaignオファー管理者は様々な方法でアプリを設定します。 インフラストラクチャの設定はAdobeが実行しますが、機能の管理者は、以下に説明する様々な設定操作を実行できます。

>[!NOTE]
>
>導入と設定に関する質問やリクエストがある場合は、Adobeのアカウント担当者にお問い合わせください。

管理者ユーザーは、キャンペーンCampaign コントロールパネルを利用して設定を管理し、各インスタンスの使用を追跡することもできます。 詳しくは、[該当するドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)を参照してください。

## [管理]メニュー{#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

様々なAdobe Campaign管理操作は、左上隅のAdobe Campaignロゴをクリックするとアクセス可能な&#x200B;**[!UICONTROL Administration]**&#x200B;メニューを介して実行されます。 インターフェイスのこの部分にアクセスできるのは、プラットフォームの機能管理者のみです。

使用できるメニューは次のとおりです。

* [ユーザーとセキュリティ](../../administration/using/about-access-management.md):このメニューを使用すると、プラットフォーム（ユーザー、役割、セキュリティグループ、ユニット）へのアクセスを管理できます。
* [チャネル](../../administration/using/about-channel-configuration.md):このメニューでは、様々なプラットフォームチャネル（電子メール、モバイル）にリンクされている技術パラメーター、およびタイポロジーと強制隔離管理を再グループ化します。
* [アプリケーション設定](../../administration/using/external-accounts.md):このメニューを使用すると、様々なアプリ要素(外部アカウント、オプション、テクニカルワークフロー)を設定できます。
* [開発](../../developing/using/data-model-concepts.md):このメニューを使用すると、カスタムリソースを管理し、診断ツールにアクセスできます。
* [インスタンス設定](../../administration/using/branding.md):このメニューでは、様々なブランドを定義し、設定(ロゴ、追跡の管理、ランディングページにアクセスするためのURLドメインなど)を指定します。
* [導入](../../automating/using/managing-packages.md):このメニューは、パッケージの読み込みと書き出しのオプションを再グループ化します。
* [顧客指標](../../audiences/using/active-profiles.md):Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。このレポートは情報を提供するだけで、請求に直接影響しません。
* [プライバシーツール](../../start/using/privacy-management.md):このメニューを使用すると、GDPRへのアクセスとリクエストの削除を作成し、その進化を追跡できます。

## ユーザーとセキュリティ{#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

ユーザーを招待してアプリケーションにアクセスし、**セキュリティグループ**&#x200B;を管理します。これは、組織内で同じ役割と権限を共有するユーザーのセットです。 デフォルトでは、Adobe Campaignオファーは&#x200B;**ロール**&#x200B;のセットを使用して、ユーザーおよびユーザーグループに割り当てられた一元認証を定義できます。 **組織単位**&#x200B;と組み合わせて、役割を使用すると、ユーザーはインターフェイスのフィルタされた表示を提供し、様々な機能へのアクセスを定義できます。

キャンペーン標準では、セキュリティ関連の情報を監視することもできます。 **[!UICONTROL Export audits]**&#x200B;画面を通して、ユーザーが実行したデータのエクスポートに関する情報を取得できます。**[!UICONTROL Licenses]**&#x200B;画面を使用して、組織内にインストールされているキャンペーンライセンスのすべてと、ビルド番号、リリースバージョン、契約条件などの様々な情報を監視します。

詳しくは、以下を参照してください。

* [ユーザー管理](../../administration/using/users-management.md)
* [組織単位](../../administration/using/organizational-units.md)
* [役割のリスト](../../administration/using/list-of-roles.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)
* [エクスポートログの監査](../../administration/using/auditing-export-logs.md)
* [ライセンス](../../administration/using/licenses.md)

## チャネル構成{#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaign内のすべての通信チャネルは、メッセージを効果的に送信できるように正しく構成する必要があります。**[!UICONTROL Channel]**&#x200B;メニューを使うと、異なるチャネルにリンクされた技術的なパラメータを管理できます。

様々な&#x200B;**email**&#x200B;パラメーターを設定します。バウンス、強制隔離、電子メールのプロパティ、ルーティングパラメーター（通常はルール）の処理ルール。 **SMS**&#x200B;チャネルのルーティング構成とプロパティ、およびSMSのエンコードと形式を定義します。

**モバイルアプリ**&#x200B;を設定して、Adobe Experience PlatformSDKを使用してアプリ内メッセージとプッシュ通知を送信できるようにします。

詳しくは、以下を参照してください。

* [チャネル設定について](../../administration/using/about-channel-configuration.md)
* [E メールチャネルの設定](../../administration/using/configuring-email-channel.md)
* [SMS チャネルの設定](../../administration/using/configuring-sms-channel.md)
* [モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)

## アプリケーション設定{#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standardには、ニーズに合わせて設定できる様々なアプリケーション要素が付属しています。

**外部アカウント**&#x200B;を設定します。これは、Adobe Campaignを外部サーバーに接続するために使用します。 Campaign Standardターゲットマッピングにアクセスし、**テクニカルワークフロー**&#x200B;を使用してプラットフォームを監視します。

組織に対して1つまたは複数の&#x200B;**ブランド**&#x200B;を定義し、重要なシステムアクティビティの場合は、アプリケーション内で&#x200B;**リアルタイム通知**&#x200B;を送信するように設定します。

詳しくは、以下を参照してください。

* [Adobe Campaign Standard 設定について](../../administration/using/about-campaign-standard-settings.md)
* [外部アカウント](../../administration/using/external-accounts.md)
* [Campaign での Target マッピング](../../administration/using/target-mappings-in-campaign.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [ブランディング](../../administration/using/branding.md)
* [内部通知の送信](../../administration/using/sending-internal-notifications.md)
