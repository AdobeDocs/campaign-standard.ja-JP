---
title: Campaign Standard の管理の概要
description: Discoverのユーザーと権限の管理、監視のガイドライン、チャネル固有の設定およびアプリケーション設定のガイドライン。
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 14%

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

## 管理メニュー {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

様々なAdobe Campaign管理操作は、左上隅のAdobe Campaignロゴをクリックすると **[!UICONTROL Administration]** メニューにアクセスできるようになります。 インターフェイスのこの部分にアクセスできるのは、プラットフォームの機能管理者のみです。

使用できるメニューは次のとおりです。

* [ユーザーとセキュリティ](../../administration/using/about-access-management.md):このメニューを使用すると、プラットフォーム（ユーザー、役割、セキュリティグループ、ユニット）へのアクセスを管理できます。
* [チャネル](../../administration/using/about-channel-configuration.md):このメニューでは、様々なプラットフォームチャネル（電子メール、モバイル）にリンクされている技術パラメーター、およびタイポロジーと強制隔離管理を再グループ化します。
* [アプリケーション設定](../../administration/using/external-accounts.md):このメニューを使用すると、様々なアプリ要素(外部アカウント、オプション、テクニカルワークフロー)を設定できます。
* [開発](../../developing/using/data-model-concepts.md):このメニューを使用すると、カスタムリソースを管理し、診断ツールにアクセスできます。
* [インスタンス設定](../../administration/using/branding.md):このメニューでは、様々なブランドを定義し、設定(ロゴ、追跡の管理、ランディングページにアクセスするためのURLドメインなど)を指定します。
* [導入](../../automating/using/managing-packages.md):このメニューは、パッケージの読み込みと書き出しのオプションを再グループ化します。
* [顧客指標](../../audiences/using/active-profiles.md):Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。 このレポートは情報を提供するだけで、請求に直接影響しません。
* [プライバシーツール](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy.html):このメニューを使用すると、GDPRへのアクセスとリクエストの削除を作成し、その進化を追跡できます。

## ユーザーとセキュリティ{#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

ユーザーを招待してアプリケーションにアクセスし、 **セキュリティグループを管理します**。セキュリティグループは、組織内で同じ役割と権限を共有するユーザーのセットです。 By default, Adobe Campaign offers a set of **roles** which allows you to define unitary authorizations assigned to users and user groups. Combined with **organizational units**, roles give users a filtered view of the interface and define their access to the different features.

キャンペーン標準では、セキュリティ関連の情報を監視することもできます。 ユーザーが実行したデータのエクスポートに関する情報を **[!UICONTROL Export audits]****[!UICONTROL Licenses]** 画面から取得でき、この画面を使用して、組織内にインストールされているキャンペーンライセンスのすべてと、ビルド番号、リリースバージョン、契約条件などの異なる情報を監視できます。

詳しくは、以下を参照してください。

* [ユーザー管理](../../administration/using/users-management.md)
* [組織単位](../../administration/using/organizational-units.md)
* [役割のリスト](../../administration/using/list-of-roles.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)
* [エクスポートログの監査](../../administration/using/auditing-export-logs.md)
* [ライセンス](../../administration/using/licenses.md)

## チャネル設定 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaign内のすべての通信チャネルは、メッセージを効果的に送信できるように正しく構成する必要があります。 **[!UICONTROL Channel]** メニューを使用すると、異なるチャネルにリンクされた技術的なパラメータを管理できます。

様々な **電子メール** パラメーターを設定します。バウンス、強制隔離、電子メールのプロパティ、ルーティングパラメーター（通常はルール）の処理ルール。 SMS **** チャネルのルーティング構成とプロパティ、およびSMSのエンコードと形式を定義します。

Adobe Experience PlatformSDKを使用してアプリ内メッセージとプッシュ通知を送信できるように **モバイルアプリを設定し** 、イベントを作成して設定することで **トランザクションメッセージを設定します** 。

詳しくは、以下を参照してください。

* [チャネル設定について](../../administration/using/about-channel-configuration.md)
* [E メールチャネルの設定](../../administration/using/configuring-email-channel.md)
* [SMS チャネルの設定](../../administration/using/configuring-sms-channel.md)
* [モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)
* [トランザクションメッセージの設定](../../administration/using/configuring-transactional-messaging.md)

## アプリケーション設定{#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standardには、ニーズに合わせて設定できる様々なアプリケーション要素が付属しています。

Adobe Campaignを外部サーバーに接続するために使用する **外部アカウント**&#x200B;を設定します。 Campaign Standardターゲットマッピングにアクセスし、 **テクニカルワークフローを使用してプラットフォームを監視します**。

組織に1つまたは複数の **ブランドを定義し** 、重要なシステムアクティビティの場合にアプリケーション内で **** リアルタイム通知の送信を設定します。

詳しくは、以下を参照してください。

* [Adobe Campaign Standard 設定について](../../administration/using/about-campaign-standard-settings.md)
* [外部アカウント](../../administration/using/external-accounts.md)
* [Campaign での Target マッピング](../../administration/using/target-mappings-in-campaign.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [ブランディング](../../administration/using/branding.md)
* [内部通知の送信](../../administration/using/sending-internal-notifications.md)

## その他のリソース

* [ユーザアクセス権の管理（ビデオ）](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [コントロールパネルのドキュメント](https://docs.adobe.com/content/help/ja-JP/control-panel/using/control-panel-home.html)
