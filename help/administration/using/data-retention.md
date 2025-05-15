---
title: データ保持
description: 標準テーブルの既定の保有値について説明します
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2bc6ce04d2580b561bfdaafe29985353fd116a42
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# データ保持{#data-retention}

>[!NOTE]
>
>データレポートは過去 2 年間のみ使用できます。 データ保持期間について詳しくは、Adobe コンサルタントまたは技術管理者にお問い合わせください。

Campaign の標準ログテーブルには、システムの過負荷を回避するために、データストレージ期間を制限する保持期間が事前に設定されています。

データ保持の設定は、実装時にAdobeの技術管理者が指定します。値は顧客の要件に基づくため、実装ごとに異なる場合があります。

お使いの環境に適した保存期間の詳細やカスタム保存期間の設定については、Adobeのコンサルタントまたは技術管理者にお問い合わせください。

標準のワークフロー機能を使用すると、任意のカスタムテーブルに保持期間を設定できます。

標準テーブルのデフォルトの保存期間は次のとおりです。 Adobeでは、可能な限り、データ使用状況に応じて、Campaign インスタンスのパフォーマンスを向上させるために、推奨される保持期間に移行することをお勧めします。

* **統合されたトラッキング**:6 か月（推奨：1 か月）
* **配信ログ**:6 か月（推奨：1 か月）
* **トラッキングログ**:6 か月（推奨：1 か月）
* **イベント**：1 ヶ月
* **イベント処理の統計**:6 か月（推奨：1 か月）
* **アーカイブしたイベント**:6 か月（推奨：1 か月）
* **臨時の事業者**：7 日間
* **無視されたパイプラインイベント**：1 ヶ月
* **配信アラート**：1 ヶ月
* **書き出しの監査**:6 か月（推奨：1 か月）
* **配信**:2 年

## 配信の保持期間 {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

2025 年 6 月 1 日（PT）より、過去 2 年間の配信のみがシステムで引き続き使用できるようになります。 詳しくは、以下を参照してください。

* 2 年以上経過した配信は完全に削除され、アクセスできなくなります。
* このクリーンアップには、送信された配信と失敗した配信のみが含まれます。繰り返し配信、ドラフト配信およびテンプレートは影響を受けません。
* 配信を削除すると、リンクされたトラッキング情報や送信情報も完全に削除されます。
* マーケティングテンプレートまたはトランザクション配信テンプレートは削除されません。
* 繰り返し配信の場合、集計期間が月または年に設定された子配信は削除されません。

**[!UICONTROL Copy headers from delivery templates]** ワークフローなどのプロセスを高速化したい場合は、配信保持期間を短くすることができます。 詳しくは、Adobe担当者にお問い合わせください。

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


