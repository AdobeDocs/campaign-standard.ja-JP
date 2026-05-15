---
title: Campaign Standard 管理の基本を学ぶ要
description: ユーザーと権限の管理、監視のガイドライン、チャネル固有の設定およびアプリケーション設定のガイドラインについて学ぶ
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
TQID: https://experienceleague.adobe.com/FKO2q2Cn5rO8aKh0d88eaFi7p1Xa608fOmEZiCRazBc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: b4ecd69f-2adf-4219-bc47-c9cd9a53c118
  - id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 647
ht-degree: 16%

---

# Campaign Standard 管理の基本を学ぶ要 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理メニュー</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">ユーザーとセキュリティ</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">チャネル設定</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">アプリケーション設定</a></p></td></tr>
</table>

Adobe Campaignは、クラウドベースのソリューションとして、管理者がアプリケーションを設定するための様々な方法を提供します。 インフラストラクチャの設定はAdobeで行われますが、機能管理者は次に説明する様々な設定操作を実行できます。

>[!NOTE]
>
>導入と設定に関するご質問やご質問は、Adobeの担当者までお問い合わせください。

管理者ユーザーは、Campaign Campaign コントロールパネルを活用して、各インスタンスの設定を管理したり、使用状況を追跡したりすることもできます。 詳しくは、[該当するドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)を参照してください。

## 管理メニュー {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

左上隅のAdobe Campaign ロゴをクリックすると、アクセス可能な&#x200B;**[!UICONTROL Administration]** メニューを介して、さまざまなAdobe Campaign管理操作が実行されます。 インターフェイスのこの部分には、プラットフォームの機能管理者のみがアクセスできます。

利用可能な様々なメニューは次のとおりです。

* [&#x200B; ユーザーとセキュリティ &#x200B;](../../administration/using/about-access-management.md)：このメニューを使用すると、プラットフォーム（ユーザー、役割、セキュリティグループ、ユニット）へのアクセスを管理できます。
* [&#x200B; チャネル &#x200B;](../../administration/using/about-channel-configuration.md)：このメニューは、様々なプラットフォームチャネル（電子メール、モバイル）にリンクされている技術的なパラメーターと、タイポロジおよび強制隔離の管理を再グループ化します。
* [&#x200B; アプリケーション設定](../../administration/using/external-accounts.md)：このメニューでは、様々なアプリケーション要素（外部アカウント、オプション、技術ワークフロー）を設定できます。
* [開発](../../developing/using/data-model-concepts.md)：このメニューを使用すると、カスタムリソースを管理したり、診断ツールにアクセスしたりできます。
* [&#x200B; インスタンス設定](../../administration/using/branding.md)：このメニューでは、様々なブランドを定義し、その設定（ロゴ、トラッキングの管理、ランディングページにアクセスするためのURL ドメインなど）を設定します。
* [&#x200B; デプロイメント &#x200B;](../../automating/using/managing-packages.md)：このメニューは、パッケージのインポートとエクスポートのオプションを再グループ化します。
* [顧客指標](../../audiences/using/active-profiles.md): Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。 このレポートは情報提供に過ぎず、請求に直接影響を与えません。
* [&#x200B; プライバシーツール &#x200B;](../../start/using/privacy-management.md)：このメニューを使用すると、GDPR アクセス要求と削除要求を作成し、その進化を追跡できます。

## ユーザーとセキュリティ {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

ユーザーを招待してアプリケーションにアクセスし、組織内で同じ役割と権限を共有するユーザーのセットである&#x200B;**セキュリティグループ**&#x200B;を管理します。 デフォルトでは、Adobe Campaignには&#x200B;**役割**&#x200B;のセットが用意されており、ユーザーとユーザーグループに割り当てられた単一の承認を定義できます。 **組織単位**&#x200B;と組み合わせることで、ユーザーはインターフェイスのフィルタリングされたビューを使用し、様々な機能へのアクセスを定義できます。

また、Campaign Standardでは、セキュリティ関連の情報を監視することもできます。 ユーザーが実行したデータ書き出しに関する情報を&#x200B;**[!UICONTROL Export audits]**&#x200B;画面から取得し、**[!UICONTROL Licenses]**&#x200B;画面を活用して、組織内にインストールされているすべてのCampaign ライセンスを監視します。また、ビルド番号、リリースバージョン、契約条件などの様々な情報も監視できます。

詳しくは、以下を参照してください。

* [ユーザー管理](../../administration/using/users-management.md)
* [組織単位](../../administration/using/organizational-units.md)
* [役割のリスト](../../administration/using/list-of-roles.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)
* [エクスポートログの監査](../../administration/using/auditing-export-logs.md)
* [ライセンス](../../administration/using/licenses.md)

## チャネル設定 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaignのすべてのコミュニケーション チャネルは、メッセージを効果的に送信できるように正しく設定されている必要があります。**[!UICONTROL Channel]** メニューでは、異なるチャネルにリンクされた技術的なパラメーターを管理できます。

様々な&#x200B;**電子メール** パラメーターを設定します。バウンス、強制隔離、電子メールプロパティ、ルーティングパラメーターの処理ルール、タイプルールです。 **SMS** チャネルのルーティング設定とプロパティ、およびSMS エンコーディングと形式を定義します。

Adobe Experience Platform SDKを使用してアプリ内メッセージとプッシュ通知を送信できるようにするには、**モバイルアプリケーション**&#x200B;を設定します。

詳しくは、以下を参照してください。

* [チャネル設定について](../../administration/using/about-channel-configuration.md)
* [メールチャネルの設定](../../administration/using/configuring-email-channel.md)
* [SMS チャネルの設定](../../administration/using/configuring-sms-channel.md)
* [モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)

## アプリケーション設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standardには、ニーズに合わせて設定できるさまざまなアプリケーション要素が用意されています。

Adobe Campaignを外部サーバーに接続するために使用する&#x200B;**外部アカウント**&#x200B;を設定します。 **テクニカルワークフロー**&#x200B;を使用して、Campaign Standard ターゲットマッピングにアクセスし、プラットフォームをモニタリングします。

組織用に1つまたは複数の&#x200B;**ブランド**&#x200B;を定義し、重要なシステムアクティビティの場合にアプリケーション内で&#x200B;**リアルタイム通知**&#x200B;の送信を設定します。

詳しくは、以下を参照してください。

* [Adobe Campaign Standard 設定について](../../administration/using/about-campaign-standard-settings.md)
* [外部アカウント](../../administration/using/external-accounts.md)
* [Campaign でのターゲットマッピング](../../administration/using/target-mappings-in-campaign.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [ブランディング](../../administration/using/branding.md)
* [内部通知の送信](../../administration/using/sending-internal-notifications.md)
