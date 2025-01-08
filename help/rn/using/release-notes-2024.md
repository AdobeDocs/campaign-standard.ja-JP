---
title: リリースノート 2024
description: このページでは、Adobe Campaign Standard の 2024年の全リリースを紹介します。
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
source-git-commit: 85f3a3d8fe9e41eaa78fac955bc2d0f3f3d2c35e
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 98%

---

# リリースノート 2024 {#release-notes-2024}


## リリース 24.2 - 2024年夏リリース（LA） {#summer-24}

### 改善点 {#summer-24-rn-improvements}

**OAuth サーバー間の資格情報への移行**

このバージョン以降、サービスアカウント（JWT）資格情報はアドビによって廃止され、アドビのソリューションおよびアプリとの Campaign アウトバウンド統合は OAuth サーバー間の資格情報に依存するようになりました。アドビでは、Campaign と Analytics 統合や Experience Cloud トリガー統合などのアウトバウンド統合に対して、JWT から OAuth への移行を実行します。

Campaign とのインバウンド統合を実装していて、[Campaign API](../../api/using/get-started-apis.md) を使用している場合は、[このドキュメント](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}の説明に従って、テクニカルアカウントを移行する必要があります。既存のサービスアカウント（JWT）資格情報は、**2025年1月27日（PT）**&#x200B;に機能しなくなります。

### 修正点 {#summer-24-rn-fixes}

* ワークフロースケジューラーがスケジュールされた時間より前に開始される問題を修正しました。（CAMP-55412）
* トランザクションプッシュ通知でカスタムフィールドを複製する際にエラーが発生する問題を修正しました。（CAMP-54459）
* アプリ内メッセージングの日時スケジューラーの使いやすさに影響を与える問題を修正しました。（CAMP-54495）
* カスタムトラッキングエイリアス機能を使用し、リンク全体が動的な場合に、トラッキングが機能しない問題を修正しました。（CAMP-56044）
* 検索を使用して特定のテンプレートを検索する際に、表示されるテンプレートの数が制限される問題を修正しました。（CAMP-55273）
* 優先言語ドロップダウンリストに en_kz（英語 - カザフスタン）および en_ua（英語 - ウクライナ）を追加しました。（CAMP-55336）
* スケジューラー設定で時間調整ボタンが機能しない問題を修正しました。（CAMP-53602）
* スケジューラー設定の時間調整バーに関するいくつかのユーザーインターフェイスの問題を修正しました。（CAMP-55291）


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
