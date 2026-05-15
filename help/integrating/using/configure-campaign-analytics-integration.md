---
title: Campaign と Analytics の統合の設定
description: Adobe Analyticsとの連携を設定して、メール配信の成果を測定する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
TQID: https://experienceleague.adobe.com/bt1FQbafwhEuRao-YFhynO-ecg5EaiUDskSFvxuFv-k
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 10%

---

# Campaign と Analytics の統合の設定{#configure-campaign-analytics-integration}

この統合により、Adobe CampaignからAdobe Analytics StandardまたはPremiumに、主要業績評価指標データを直接共有できます。

Adobe Campaign StandardとAdobe Analyticsの統合を開始するには、まずAdobe Analyticsにリンクされた外部アカウントを設定する必要があります。

外部アカウントとテクニカルワークフローは、プラットフォームの機能管理者のみが管理できます。

1. 詳細設定メニューから、Adobe Campaign ロゴを使用して、**[!UICONTROL Administration > Application settings > External accounts]**&#x200B;を選択します。
1. **[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;外部アカウントを選択します。

   ![](assets/analytics_2.png)

1. **[!UICONTROL Connection]** フィールドに&#x200B;**[!UICONTROL Web services user name]**&#x200B;と&#x200B;**[!UICONTROL Web services share secret]**&#x200B;を指定します。

   これらのパラメーターは、**[!UICONTROL Admin > Company settings > Web services]**&#x200B;を選択してAnalyticsで見つけることができます。

   ![](assets/analytics_1.png)

1. 「**[!UICONTROL Refresh report suites]**」ボタンをクリックします。
1. Adobe Campaign データでエンリッチするAdobe Analytics レポートスイートを&#x200B;**[!UICONTROL Analytics default report suite]** ドロップダウンで選択します。

   これで、外部アカウントの準備が整い、Adobe Analyticsにリンクされました。 **[!UICONTROL Enabled]** ボックスをオンにすれば、いつでも無効にできます。

   ![](assets/analytics.png)

**[!UICONTROL Share KPIs with Adobe Analytics]** テクニカルワークフローが自動的に起動し、**[!UICONTROL Administration > Application settings > Workflow]**&#x200B;を選択して詳細メニューから表示できるようになります。 このテクニカルワークフローでは、最大6か月経過したブロードログを保持できます。 このワークフローは増分であり、前日のデータをプッシュすることに注意してください。

![](assets/analytics_3.png)

これで、Adobe Analyticsでデータを利用できるようになります。

**関連トピック：**

* [外部アカウント](../../administration/using/external-accounts.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [統合キャンペーンレポート用のKPIの共有](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html)動画
