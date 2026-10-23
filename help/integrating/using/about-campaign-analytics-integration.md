---
title: Campaign と Analytics の統合について
description: Adobe Adobe Campaign StandardでKPI データを収集し、そのキャンペーンデータをAdobe Adobe Analyticsと共有することで、Adobe Adobe Campaignの電子メールマーケティング指標を測定できるようになります。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
TQID: 'https://experienceleague.adobe.com/xTX1m0UTCuDt2YMByv8L6vyJG1W0dRme5ETBJuFG-J4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 7%
---
# Campaign と Analytics の統合について{#about-campaign-analytics-integration}

Adobe CampaignとAdobe Analyticsの連携により、電子メールの配信状況をAdobe Analyticsで直接追跡できるようになりました。

Adobe Campaign StandardとAdobe Analyticsの連携により、次のことが可能になります。

* Adobe Adobe Campaign StandardからAdobe AnalyticsにKPI （主要業績評価指標）データを共有する。
* Adobe Analytics パラメーターを使用してトラッキング式を充実させます。

これは、最初にAdobe Analyticsにリンクされた外部アカウントを作成することで機能します。 テクニカルワークフローは自動的に起動し、デフォルトでは15分ごとに自動実行されます。 KPI データはAdobe Analyticsにプッシュされます。

この統合は、メール配信でのみ使用できます。

Adobe Analyticsのコアサービス **トリガー**&#x200B;とAdobe Campaignの統合も利用できます。 これにより、Adobe Analyticsがweb サイトで追跡している特定の行動に対する反応として、パーソナライズされた電子メールを顧客に送信できます（15分以内）。

**関連トピック：**

* [Campaign StandardとAnalyticsの統合の概要](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html?lang=ja)
* [Campaign Standard統合の設定](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html?lang=ja)
* [Analytics での Campaign のディメンションと指標](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
