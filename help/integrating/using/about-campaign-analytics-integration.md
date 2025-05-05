---
title: Campaign と Analytics の統合について
description: Adobe Campaign Standardから KPI データを収集することで、キャンペーンデータをAdobe Analyticsと共有して、Adobe Campaignからメールマーケティング指標を測定できるようになりました。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---

# Campaign と Analytics の統合について{#about-campaign-analytics-integration}

Adobe CampaignのAdobe Analytics統合により、メール配信の成功をAdobe Analyticsで直接トラッキングできるようになりました。

Adobe Campaign StandardとAdobe Analyticsの統合により、次のことが可能になります。

* KPI （主要業績評価指標）データをAdobe Campaign StandardからAdobe Analyticsに共有します。
* Adobe Analytics パラメーターを使用してトラッキング式を強化します。

この操作を行うには、まず、Adobe Analyticsにリンクされた外部アカウントを作成します。 その後、テクニカルワークフローが自動的に起動し、デフォルトでは 15 分ごとに自動実行されます。 その後、KPI データが Analytics にプッシュされます。

この統合は、メール配信でのみ使用できます。

Adobe Analyticsのコアサービス **トリガー** とAdobe Campaignの統合も利用できます。 これにより、Adobe Analyticsが web サイト上で追跡する特定の行動に対する反応として、パーソナライズされたメールを顧客に送信できます（15 分以内）。

**関連トピック：**

* [Analytics 統合のCampaign Standardの概要 ](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html?lang=ja)
* [Campaign Standard統合の設定 ](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html?lang=ja)
* [Analytics での Campaign のディメンションと指標](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
