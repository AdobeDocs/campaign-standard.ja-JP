---
title: データ保持
seo-title: データ保持
description: データ保持
seo-description: null
page-status-flag: 常にアクティブ化されていない
uuid: d90852b4- e9f3-4187- bbea- e748d16d1590
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: アプリケーション設定
discoiquuid: b791562b-6c51-447d-9e5b- bb77136f3dd8
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Data retention{#data-retention}

キャンペーンの標準ログテーブルでは保持期間が事前設定されており、通常はデータストレージを6ヶ月未満に制限しています。

標準テーブルの定着値は次のとおりです。保持設定は、実装時にアドビのテクニカル管理者が設定するものであり、顧客の要件に基づいて、実装ごとに異なることがあります。

* **統合トラッキング**:6months
* **配信ログ**:6months
* **トラッキングログ**:6months
* **イベント**:1month
* **イベント処理の統計**:6months
* **アーカイブされたイベント**:6months
* **一時エンティティ**:7日
* **無視されるパイプラインイベント**:1month
* **配信アラート**:1month
* **監査の書き出し**:6months

標準ワークフロー機能を使用すると、カスタムテーブルの保持期間を設定できます。

リテンションについて詳しく説明するか、カスタムテーブルのリテンションを設定する必要があるかについては、アドビコンサルタントまたは技術者にお問い合わせください。
