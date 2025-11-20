---
title: 最新のリリースノート
description: このページでは、Adobe Campaign Standard の最新リリースを紹介します。
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1f64589578c144a9b8eb879684f27834efaf8d8
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 100%

---


# 最新のリリースノート {#latest-release}

<!--
## Release notes {#e-new-release}


This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).

-->

## リリース 25.2 - 2025年夏リリース {#summer-25}

### セキュリティ関連の修正 {#summer-25-security}

* このリリースでは、セキュリティ上の問題が修正されています。
* このリリースには、次のセキュリティアップグレードが含まれています。PostgreSQL 14.18、Azure インスタンスの CentOS から Rocky への移行。

### その他の修正点 {#summer-25-fixes}

* シーケンス枯渇の処理を改善し、システムの信頼性を向上しました。（CAMP-57281）
* 一般的な製品の安定化に関するアップデートを行いました。（CAMP-57339）
* 動的レポートを改善し、堅牢性を向上し、データの不一致を削減しました。（CAMP-58157）
* ドロップダウンメニューでテキストが正しく折り返されない問題を修正しました。（CAMP-57360）
* ユーザーが 2 年以上前のデータのクエリを実行できないようにレポート機能を更新しました。（CAMP-59262）

## リリース 25.1.2 {#25.1.2}

### セキュリティ関連の修正 {#25.1.2-security}

* このリリースでは、セキュリティ上の問題が修正されています。
* このリリースには、次のセキュリティアップグレードが含まれています。Apache Tomcat が v10.1.36 にアップグレードされました。

### その他の修正点 {#25.1.2-fixes}

* ユーザーが IMS 経由でログインできない可能性があったトークン解析の問題を修正しました。（CAMP-57337）
* 自動シーケンス ID 生成メカニズムを改善し、システムの信頼性を向上しました。（CAMP-57281）

## リリース 25.1 - 2025年冬リリース {#winter-25}

### セキュリティ関連の修正 {#winter-25-security}

* このリリースでは、セキュリティ上の問題が修正されています。
* このリリースには、次のセキュリティアップグレードが含まれています。Apache Tomcat が v10.1.33 にアップグレードされました。

### その他の修正点 {#winter-25-fixes}


* 購読の概要画面の「データスキーマ」URLを修正しました（CAMP-56168、CAMP-56296）
* 「**メッセージをすぐに送信**」オプションを使用する際に、疲労ルールがバイパスされる問題を修正しました（CAMP-56866、CAMP-57033）
* テンプレートでの重複の問題を修正しました（CAMP-56340）
* Adobe Experience Manager テンプレートで動的 URL が使用された際のトラッキングリグレッションを修正しました（CAMP-51932）
* 請求プロセスのパフォーマンスの問題を修正しました（CAMP-56796）
* JSSP web ページの `>` 文字の HTML エンコーディングの問題を修正しました（CAMP-56497）
* 「**選択した行に表示**」オプションを使用する際の動的レポートの問題を修正しました（CAMP-55895）

