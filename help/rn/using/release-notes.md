---
title: 最新リリース
description: このページでは、Adobe Campaign Standard の最新リリースを紹介します。
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: d6421cda301eed85fddf2df7b2d6fc2cf1db96b3
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 100%

---


# 最新リリース{#latest-release}

![コントロールパネル](assets/do-not-localize/cp-icon.png) **新しいコントロールパネルのリリース**。[詳細情報](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=ja){target="_blank"}.

## リリース 24.1 - 2024年冬リリース {#winter-24}

### 改善点 {#e-rn-improvements}

Adobe Campaign Standard 24.1 では、HTTP v1 API を使用して Android プッシュ通知メッセージを送信し、今後の FCM 変更との互換性を確保します。詳しくは、[このテクニカルノート](../../administration/using/push-technote.md)を参照してください。

Adobe Campaign Standard 24.1 では、iOS プッシュ通知の p8 認証証明書をサポートするようになりました。これらの変更をアクティブ化するには、実装を調整する必要があります。詳しくは、[このテクニカルノート](../../administration/using/push-technote.md)を参照してください。


### 修正点 {#e-rn-fixes}

* バウンスされたメールアドレスが 30 日後に強制隔離から削除されない問題を修正しました。（CAMP-52977）
* `division by zero` のエラーで配信アラートワークフローが停止する問題を修正しました。（CAMP-49786）

