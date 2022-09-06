---
title: 最新リリース
description: このページでは、Adobe Campaign Standard の最新リリースを紹介します。
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 20%

---


# 最新リリース{#latest-release}

![コントロールパネル](assets/do-not-localize/cp-icon.png) **新しいコントロールパネルのリリース**。[詳細情報](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=ja){target=&quot;_blank&quot;}。


## リリース 22.3 - 2022 年秋/冬 {#sept-22}

### 改善点{#rn-improvements}

**アクセシビリティ**

Campaign Standard22.3 には、ユーザーがAdobe Campaignを最大限に活用し、操作しやすくなるアクセシビリティの修正と改善が含まれています。

これらの機能は、限定提供でリリースされ、一連のお客様にのみロールアウトされます。 これらの改善を Campaign 環境で有効にするには、Adobe担当者にお問い合わせください。

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### セキュリティの更新{#rn-security}

このリリースには、次のセキュリティアップグレードが含まれています。Apache Tomcat が v7.0 から v8.0 にアップグレードされました。

### 修正点{#e-rn-fixes}

* スケジュールされたタイミングの 1 時間前にトリガーされた予定レポートの問題を修正しました。 （CAMP-51502）
* 配信ダッシュボードの配信指標が送信ログ (nms:broadLogRcp) と一致しなかった問題を修正しました。 （CAMP-51127）
* ACS コネクタ (Prime Offering) でカスタムリソースを拡張できない問題を修正しました。 （CAMP-51033）
* 遅延を避けるために、プライバシーリクエスト応答の公開プロセスを改善しました。 （CAMP-50613）

