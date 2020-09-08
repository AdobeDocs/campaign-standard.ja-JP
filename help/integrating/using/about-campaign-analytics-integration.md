---
title: Campaign と Analytics の統合について
description: Adobe Campaign StandardからKPIデータを収集することで、キャンペーンデータをAdobe Analyticsと共有して、Adobe Campaignからの電子メールマーケティング指標を測定できるようになりました。
page-status-flag: never-activated
uuid: 7a351e1d-50cb-4ec5-8b66-318b797af77f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 2ea51543-fe4d-462b-b47e-9ccaa1d68dfa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3534fb2cf9f77168eb3ca0021f4121a44a57916d
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 6%

---


# Campaign と Analytics の統合について{#about-campaign-analytics-integration}

Adobe CampaignでのAdobe Analyticsの統合により、Adobe Analyticsで電子メール配信の成功を直接追跡できるようになりました。

このAdobe Campaign StandardとAdobe Analyticsの統合により、次のことが可能になります。

* Adobe Campaign StandardからAdobe AnalyticsまでKPI（主要業績評価指標）データを共有します。
* Adobe Analyticsのパラメーターを使用して、トラッキング式を拡張します。

これは、最初にAdobe Analyticsにリンクされた外部アカウントを作成することで機能します。 技術的なワークフローが自動的に起動し、デフォルトでは、15分ごとに自動実行されます。 次に、KPIデータがAnalyticsにプッシュされます。

この統合は、電子メール配信のみで使用できます。

Adobe Analyticsのコアサービス **Triggers** とAdobe Campaignの統合も可能です。 これにより、Adobe AnalyticsがWebサイトで追跡する特定の行動に対する反応として、顧客に対してパーソナライズされた電子メールを送信できます（15分以内）。

**関連トピック：**

* [AnalyticsとのCampaign Standardの概要](https://docs.adobe.com/content/help/en/analytics/integration/adobe-campaign.html)
* [Campaign Standard統合の設定](https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html)
* [Analytics での Campaign のディメンションと指標](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
