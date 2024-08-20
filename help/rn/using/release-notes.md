---
title: 最新のリリースノート
description: このページでは、Adobe Campaign Standard の最新リリースを紹介します。
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 0beb4934d1412c3f64d28106f9243673907629f3
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 73%

---


# 最新のリリースノート {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

<!--
## Early release notes {#e-new-release}

This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).
-->

## リリース 24.2 - 2024年夏リリース {#summer-24}

**リリース日**：2024年8月（限定提供） - [詳細情報](../../rn/using/release-planning.md)。

### 改善 {#summer-24-rn-improvements}

**OAuth サーバー間の資格情報への移行**

このバージョン以降、サービスアカウント（JWT）資格情報はアドビによって廃止され、アドビのソリューションおよびアプリとの Campaign アウトバウンド統合は OAuth サーバー間の資格情報に依存するようになりました。アドビでは、Campaign と Analytics 統合や Experience Cloud トリガー統合などのアウトバウンド統合に対して、JWT から OAuth への移行を実行します。

Campaign とのインバウンド統合を実装していて、[Campaign API](../../api/using/get-started-apis.md) を使用している場合は、[このドキュメント](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}の説明に従って、テクニカルアカウントを移行する必要があります。既存のサービスアカウント（JWT）資格情報は、**2025年1月27日（PT）**&#x200B;に機能しなくなります。

### 修正点 {#summer-24-rn-fixes}

* スケジュールされた時間より前にワークフロースケジューラーが開始する問題を修正しました。 （CAMP-55412）
* トランザクションプッシュ通知でカスタムフィールドを複製するとエラーが発生する問題を修正しました。 （CAMP-54459）
* アプリ内メッセージの時間と日付のスケジューラーの使いやすさに影響を与えていた問題を修正しました。 （CAMP-54495）
* カスタムトラッキングエイリアス機能を利用し、リンク全体が動的な場合に、トラッキングが機能しない問題を修正しました。 （CAMP-56044）
* 検索を使用して特定のテンプレートを検索する際に、表示されるテンプレートの数が制限される問題を修正しました。 （CAMP-55273）
* 優先言語ドロップダウンリストに次の言語を追加しました：en_kz （英語 – カザフスタン）および en_ua （英語 – ウクライナ）。 （CAMP-55336）
* スケジューラー設定で時間調整ボタンが機能しない問題を修正しました。 （CAMP-53602）
* スケジューラー設定の時間調整バーに関するいくつかのユーザーインターフェイスの問題を修正しました。 （CAMP-55291）

## リリース 24.1 - 2024年冬リリース {#winter-24}

### 改善点 {#e-rn-improvements}

* **Android プッシュ通知** - Adobe Campaign Standard 24.1 では、HTTP v1 API を使用して Android プッシュ通知メッセージを送信し、今後の FCM 変更との互換性を確保します。詳しくは、[このテクニカルノート](../../administration/using/push-technote.md)を参照してください。

* **iOS プッシュ通知** - Adobe Campaign Standard 24.1 では、iOS プッシュ通知の p8 認証証明書をサポートするようになりました。これらの変更をアクティブ化するには、実装を調整する必要があります。詳しくは、[このテクニカルノート](../../administration/using/push-technote.md)を参照してください。

* **ワンクリックでのリストの購読解除** - 2024年6月1日（PT）以降、Google と Yahoo! は、ワンクリックでの List-Unsubscribe への準拠を送信者に義務付ける予定です。Campaign では、この機能を標準でサポートするようになりました。詳しくは、[こちら](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters)を参照してください。

* **インフラストラクチャ** - Postgres データベースがバージョン 11.22 からバージョン 12.17 にアップグレードされました。

* **CTA トラッキング** - ユーザーがパーソナライズされた URL を開いてクリックすると、コード化されたパーソナライズされた URL の代わりに、解決されたパーソナライズされた URL がトラッキングされるようになりました。この変更はデフォルトでは有効になっていません。Campaign インスタンスで有効にするには、アドビ担当者にお問い合わせください。

* **パーソナライゼーションフィールドのドロップダウン** - Adobe Experience Manager でトランザクションメールメッセージテンプレートを作成する際に、ドロップダウンリストからパーソナライゼーション フィールドを選択できるようになりました。この変更はデフォルトでは有効になっていません。Campaign インスタンスで有効にするには、アドビ担当者にお問い合わせください。

### 修正点 {#e-rn-fixes}

* バウンスされたメールアドレスが 30 日後に強制隔離から削除されない問題を修正しました。（CAMP-52977）
* `division by zero` のエラーで配信アラートワークフローが停止する問題を修正しました。（CAMP-49786）

