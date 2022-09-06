---
title: 早期リリースノート
description: 早期リリースノート
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 19%

---


# 早期リリースノート {#e-new-release}

このページでは、次のリリースに含まれる機能強化および修正点についてCampaign Standardします。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 22.3 - 2022 年秋/冬 {#e-rn-2022}

### 改善点{#e-rn-improvements}

**アクセシビリティ**

Campaign Standard22.3 には、ユーザーがAdobe Campaignを最大限に活用し、操作しやすくなるアクセシビリティの修正と改善が含まれています。

これらの機能は、限定提供でリリースされ、一連のお客様にのみロールアウトされます。 これらの改善を Campaign 環境で有効にするには、Adobe担当者にお問い合わせください。

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### セキュリティの更新{#e-rn-security}

このリリースには、次のセキュリティアップグレードが含まれています。Apache Tomcat が v7.0 から v8.0 にアップグレードされました。

### 修正点{#e-rn-fixes}

* スケジュールされたタイミングの 1 時間前にトリガーされた予定レポートの問題を修正しました。 （CAMP-51502）
* 配信ダッシュボードの配信指標が送信ログ (nms:broadLogRcp) と一致しなかった問題を修正しました。 （CAMP-51127）
* ACS コネクタ (Prime Offering) でカスタムリソースを拡張できない問題を修正しました。 （CAMP-51033）
* 遅延を避けるために、プライバシーリクエスト応答の公開プロセスを改善しました。 （CAMP-50613）