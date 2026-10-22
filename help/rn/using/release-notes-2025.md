---
title: リリースノート 2025
description: このページでは、Adobe Campaign Standardの2025年リリースの一覧を示します
feature: Overview
role: User
level: Beginner
exl-id: 9046db34-f610-4721-b6eb-92334149366d
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e8d937ec-9046-41b5-834b-d22a624e0d37
    internal-label: Campaign overview
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 94%
---
# リリースノート 2025 {#release-notes-2025}

## リリース 25.2 - 2025年夏リリース {#summer-25}

### セキュリティ関連の修正 {#summer-25-security}

* このリリースでは、セキュリティ上の問題が修正されています。
* このリリースには、次のセキュリティアップグレードが含まれています。PostgreSQL 14.18、Azure インスタンスの CentOS から Rocky への移行。

### その他の修正点 {#summer-25-fixes}

* シーケンス枯渇の処理を改善し、システムの信頼性を向上しました。 （CAMP-57281）
* 一般的な製品の安定化に関するアップデートを行いました。 （CAMP-57339）
* 動的レポートを改善し、堅牢性を向上し、データの不一致を削減しました。 （CAMP-58157）
* ドロップダウンメニューでテキストが正しく折り返されない問題を修正しました。 （CAMP-57360）
* ユーザーが 2 年以上前のデータのクエリを実行できないようにレポート機能を更新しました。 （CAMP-59262）

## リリース 25.1.2 {#25.1.2}

### セキュリティ関連の修正 {#25.1.2-security}

* このリリースでは、セキュリティ上の問題が修正されています。
* このリリースには、次のセキュリティアップグレードが含まれています。Apache Tomcat が v10.1.36 にアップグレードされました。

### その他の修正点 {#25.1.2-fixes}

* ユーザーが IMS 経由でログインできない可能性があったトークン解析の問題を修正しました。 （CAMP-57337）
* 自動シーケンス ID 生成メカニズムを改善し、システムの信頼性を向上しました。 （CAMP-57281）

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
