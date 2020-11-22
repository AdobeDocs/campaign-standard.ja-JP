---
solution: Campaign Standard
product: campaign
title: データリテンション
description: null
audience: administration
content-type: reference
topic-tags: application-settings
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 70%

---


# データリテンション{#data-retention}

キャンペーンの標準ログ・テーブルには、事前に設定された保存期間が含まれ、通常、データのストレージは6か月以下に制限されます。

標準テーブルのデフォルトのリテンション期間を以下に示します。リテンションは実装時にアドビの技術管理者が設定します。値は顧客の要件に基づくため、実装ごとに異なる場合があります。

* **統合されたトラッキング**：6 ヶ月
* **配信ログ**：6 ヶ月
* **トラッキングログ**：6 ヶ月
* **イベント**：1 ヶ月
* **イベント処理の統計**：6 ヶ月
* **アーカイブしたイベント**：6 ヶ月
* **一時エンティティ**:7日
* **無視されたパイプラインイベント**：1 ヶ月
* **配信アラート**：1 ヶ月
* **書き出しの監査**：6 ヶ月

標準的なワークフロー機能を使用して、任意のカスタムテーブルに対して保持期間を設定できます。

リテンションの詳細について知りたい場合、またはカスタムテーブルの設定が必要な場合は、アドビのコンサルタントまたは技術管理者にお問い合わせください。
