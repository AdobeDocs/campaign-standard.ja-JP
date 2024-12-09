---
title: リリースノート 2024
description: このページでは、Adobe Campaign Standard の 2024年の全リリースを紹介します。
feature: Overview
role: User
level: Beginner
source-git-commit: c70e3058f75ba2b11a8311628198e5c02d489964
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 97%

---

# リリースノート 2024 {#release-notes-2024}

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

