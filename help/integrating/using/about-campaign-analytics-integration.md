---
title: Campaign と Analytics の統合について
description: Adobe Campaign Standardから KPI データを収集することで、キャンペーンデータをAdobe Analyticsと共有して、Adobe Campaignからの電子メールマーケティング指標を測定できるようになりました。
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

Adobe CampaignのAdobe Analytics統合により、Adobe Analyticsで直接 E メール配信の成功を追跡できるようになりました。

Adobe Campaign StandardとAdobe Analyticsの統合により、次のことが可能になります。

* Adobe Campaign StandardからAdobe Analyticsに KPI（主要業績評価指標）データを共有します。
* Adobe Analyticsのパラメーターを使用してトラッキング式を強化します。

これは、最初にAdobe Analyticsにリンクされた外部アカウントを作成することで機能します。 テクニカルワークフローが自動的に起動し、デフォルトでは 15 分ごとに自動実行されます。 KPI データが Analytics にプッシュされます。

この統合は、E メール配信でのみ使用できます。

Adobe Analyticsのコアサービスの統合 **トリガー** Adobe Campaignも利用できます。 Web サイト上でAdobe Analyticsによってトラッキングされている特定の行動に対する反応として、パーソナライズされた E メールを顧客に送信できます（15 分以内）。

**関連トピック：**

* [Analytics とCampaign Standardの統合の概要](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html)
* [Campaign Standard統合の設定](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html)
* [Analytics での Campaign のディメンションと指標](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
