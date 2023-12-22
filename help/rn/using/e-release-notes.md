---
title: 早期リリースノート
description: 早期リリースノート
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 602aca18af81625b9756a8f2020b5bc636199b96
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 68%

---


# 早期リリースノート {#e-new-release}

このページでは、次回の Campaign Standard リリースに含まれる改善点および修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 24.1 - 2024年冬リリース {#winter-24}

>[!AVAILABILITY]
>
>このリリースは、一連の組織のみが使用できます（限定提供）。詳しくは、アドビ担当者にお問い合わせください。

### 改善点 {#e-rn-improvements}

Adobe Campaign Standard 24.1 は、HTTP v1 API を使用して Android プッシュ通知メッセージを送信し、今後の FCM の変更との互換性を確保します。 詳しくは、[このテクニカルノート](../../administration/using/push-technote.md)を参照してください。


### 修正点 {#e-rn-fixes}

* 次のエラーで配信アラートワークフローが停止する問題を修正しました。 `division by zero`. （CAMP-49786）
