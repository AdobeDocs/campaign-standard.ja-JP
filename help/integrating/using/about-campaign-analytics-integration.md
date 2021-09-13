---
title: Campaign と Analytics の統合について
description: Adobe Campaign StandardからKPIデータを収集することで、キャンペーンデータをAdobe Analyticsと共有して、Adobe Campaignの電子メールマーケティング指標を測定できるようになりました。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 6%

---

# Campaign と Analytics の統合について{#about-campaign-analytics-integration}

Adobe CampaignのAdobe Analytics統合により、Eメール配信の成功をAdobe Analyticsで直接トラッキングできるようになりました。

Adobe Campaign StandardとAdobe Analyticsのこの統合により、次のことが可能になります。

* Adobe Campaign StandardからAdobe AnalyticsにKPI（主要業績評価指標）データを共有します。
* Adobe Analyticsのパラメーターを使用して、トラッキング式を強化する。

これは、最初にAdobe Analyticsにリンクされた外部アカウントを作成することで機能します。 テクニカルワークフローが自動的に起動し、デフォルトでは、15分ごとに自動実行されます。 次に、KPIデータがAnalyticsにプッシュされます。

この統合は、Eメール配信でのみ使用できます。

Adobe Analyticsのコアサービス&#x200B;**トリガー**&#x200B;とAdobe Campaignの統合も可能です。 Webサイト上でAdobe Analyticsによって追跡される特定の動作に対する反応として、パーソナライズされたEメールを顧客に送信できます（15分以内）。

**関連トピック：**

* [AnalyticsとCampaign Standardの統合の概要](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html)
* [Campaign Standard統合の設定](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html)
* [Analytics での Campaign のディメンションと指標](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
