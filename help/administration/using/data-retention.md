---
solution: Campaign Standard
product: campaign
title: データ保持
audience: administration
content-type: reference
topic-tags: application-settings
feature: インスタンス設定
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 71%

---

# データ保持{#data-retention}

Campaignの標準ログテーブルには、事前に設定された保存期間があり、通常、データのストレージは6か月以下に制限されます。

標準テーブルのデフォルトのリテンション期間を以下に示します。リテンションは実装時にアドビの技術管理者が設定します。値は顧客の要件に基づくため、実装環境によって異なる場合があります。

* **統合されたトラッキング**：6 か月
* **配信ログ**：6 か月
* **トラッキングログ**：6 か月
* **イベント**：1 ヶ月
* **イベント処理の統計**：6 か月
* **アーカイブしたイベント**：6 か月
* **臨時の事業者**：7 日間
* **無視されたパイプラインイベント**：1 ヶ月
* **配信アラート**：1 ヶ月
* **書き出しの監査**：6 か月

標準のワークフロー機能を使用して、任意のカスタムテーブルのリテンション期間を設定できます。

リテンションの詳細について知りたい場合、またはカスタムテーブルの設定が必要な場合は、アドビのコンサルタントまたは技術管理者にお問い合わせください。
