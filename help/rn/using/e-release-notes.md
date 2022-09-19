---
title: 早期リリースノート
description: 早期リリースノート
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 20a59e064afeb93a2a6260439b09790692971071
workflow-type: ht
source-wordcount: '130'
ht-degree: 100%

---


# 早期リリースノート {#e-new-release}

このページでは、次回の Campaign Standard リリースに含まれる改善点および修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 22.3 - 2022年秋／冬 {#e-rn-2022}

<!--
### Improvement{#e-rn-improvements}


**Accessibility**

Campaign Standard 22.3 comes with accessibility fixes and improvements which facilitate users to navigate and get the most out of Adobe Campaign.

These capabilities are released in Limited Availability and rolled out to a set of customers only. To have these improvements enabled on your Campaign environment(s), contact your Adobe representative.
-->

### セキュリティアップデート{#e-rn-security}

このリリースには、次のセキュリティアップグレードが含まれています。Apache Tomcat が v7.0 から v8.0 にアップグレードされました。

### 修正点{#e-rn-fixes}

* スケジュールされたタイミングの 1 時間前にトリガーされた予定レポートの問題を修正しました。 （CAMP-51502）
* 配信ダッシュボードの配信指標が送信ログ（nms:broadLogRcp）と一致しなかった問題を修正しました。 （CAMP-51127）
* ACS コネクタ（プライムオファー）でカスタムリソースを拡張できない問題を修正しました。 （CAMP-51033）
* 遅延を避けるために、プライバシーリクエスト応答の公開プロセスを改善しました。 （CAMP-50613）