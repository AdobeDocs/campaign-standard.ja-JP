---
title: データ保持
description: 標準テーブルのデフォルトの保持値について説明します
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
TQID: https://experienceleague.adobe.com/MKbmxOV4o1R-x8HwnWdd1ewflrckuahOmO36Fu1lhfQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 9%

---

# データ保持{#data-retention}

>[!NOTE]
>
>データレポートは、過去2年間のみ利用できます。 データ保持期間について詳しくは、アドビコンサルタントまたは技術管理者にお問い合わせください。

Campaignの標準ログテーブルには、システムの過負荷を避けるために、データストレージ期間を制限するプリセットの保持期間が設定されています。

データ保持の設定は、導入時にAdobeの技術管理者が行い、お客様の要件に応じて実装ごとに値が異なる場合があります。

お客様の環境に適用される保持期間の詳細やカスタム保持期間の設定については、Adobeのコンサルタントまたは技術管理者にお問い合わせください。

標準ワークフロー機能を使用すると、任意のカスタムテーブルに保持期間を設定できます。

標準テーブルのデフォルトの保持期間を以下に示します。 可能な限り、データの使用状況に応じて、Adobeでは、Campaign インスタンスのパフォーマンスを向上させるために、推奨される保持期間に移行することをお勧めします。

* **統合トラッキング**: 6か月（推奨：1か月）
* **配信ログ**: 6か月（推奨：1か月）
* **トラッキングログ**: 6か月（推奨：1か月）
* **イベント**：1 ヶ月
* **イベント処理の統計**: 6か月（推奨：1か月）
* **アーカイブ済みイベント**: 6か月（推奨：1か月）
* **臨時の事業者**：7 日間
* **無視されたパイプラインイベント**：1 ヶ月
* **配信アラート**：1 ヶ月
* **監査の書き出し**: 6か月（推奨：1か月）
* **配信**: 2年

## 配信の保持期間 {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

2025年6月1日より、過去2年間の配信のみがシステムで引き続き利用可能になります。 詳細は以下をご覧ください。

* 2年以上経過した配信は完全に削除され、アクセスできなくなります。
* このクリーンアップには、送信された配信と失敗した配信のみが含まれます。定期的な配信、ドラフト配信およびテンプレートは影響を受けません。
* 配信が削除されると、リンクされたトラッキングまたは送信情報も完全に削除されます。
* マーケティングまたはトランザクションの配信テンプレートは削除されません。
* 定期的な配信の場合、集計期間が月または年に設定されている子配信は削除されません。

**[!UICONTROL Copy headers from delivery templates]** ワークフローなどのプロセスを高速化する場合は、配信保持期間を短縮できます。 こちらから、Adobeの担当者にお問い合わせください。

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


