---
title: 最新リリース
description: このページでは、Adobe Campaign Standard の最新リリースを紹介します。
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 9291eb06c35b1d06c0a992fa64a460215477f57e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# 最新リリース{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## リリース 24.1 - 2024年冬リリース {#winter-24}

### 改善点 {#e-rn-improvements}

* **Android プッシュ通知** - Adobe Campaign Standard 24.1 では、今後の FCM の変更との互換性を確保するために、HTTP v1 API を使用して Android プッシュ通知メッセージを送信します。 詳しくは、[このテクニカルノート](../../administration/using/push-technote.md)を参照してください。

* **iOSのプッシュ通知** - Adobe Campaign Standard 24.1 で、iOS プッシュ通知用の p8 認証証明書がサポートされるようになりました。 これらの変更をアクティブ化するには、実装を調整する必要があります。詳しくは、[このテクニカルノート](../../administration/using/push-technote.md)を参照してください。

**ワンクリックリスト – 登録解除** - 2024 年 6 月 1 日以降、Googleと Yahoo! ワンクリックでの List-Unsubscribe への準拠を送信者に義務付ける予定です。Campaign では、この機能を標準でサポートするようになりました。詳しくは、[こちら](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters)を参照してください。

* **インフラストラクチャ** - Postgres データベースをバージョン 11.22 からバージョン 12.17 にアップグレードしました。

* **CTA トラッキング** - ユーザーがパーソナライズされた URL を開いてクリックした場合、コード化されたパーソナライズされた URL ではなく、解決されたパーソナライズされた URL がトラッキングされるようになりました。 この変更は、デフォルトでは有効になっていません。 Campaign インスタンスで有効にするには、Adobe担当者にお問い合わせください。

* **パーソナライゼーションフィールドのドロップダウン** - Adobe Experience Managerでトランザクションメールメッセージテンプレートを作成する際に、ドロップダウンリストからパーソナライゼーションフィールドを選択できるようになりました。 この変更は、デフォルトでは有効になっていません。 Campaign インスタンスで有効にするには、Adobe担当者にお問い合わせください。

### 修正点 {#e-rn-fixes}

* バウンスされたメールアドレスが 30 日後に強制隔離から削除されない問題を修正しました。（CAMP-52977）
* `division by zero` のエラーで配信アラートワークフローが停止する問題を修正しました。（CAMP-49786）

