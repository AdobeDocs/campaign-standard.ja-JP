---
title: Campaign と Analytics の統合の設定
description: Adobe Analytics統合を設定して、Eメール配信の成功の測定を開始する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---

# Campaign と Analytics の統合の設定{#configure-campaign-analytics-integration}

この統合により、主要業績評価指標のデータをAdobe CampaignからAdobe Analytics StandardまたはPremiumに直接共有できます。

Adobe Campaign StandardとAdobe Analyticsの統合を開始するには、まずAdobe Analyticsにリンクされた外部アカウントを設定する必要があります。

外部アカウントとテクニカルワークフローは、プラットフォームの機能管理者のみが管理できます。

1. 詳細設定メニューのAdobe Campaignロゴから、**[!UICONTROL Administration > Application settings > External accounts]**&#x200B;を選択します。
1. **[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;外部アカウントを選択します。

   ![](assets/analytics_2.png)

1. **[!UICONTROL Connection]**&#x200B;フィールドに&#x200B;**[!UICONTROL Web services user name]**&#x200B;と&#x200B;**[!UICONTROL Web services share secret]**&#x200B;を指定します。

   これらのパラメーターは、**[!UICONTROL Admin > Company settings > Web services]**&#x200B;を選択するとAnalyticsで見つかります。

   ![](assets/analytics_1.png)

1. 「**[!UICONTROL Refresh report suites]**」ボタンをクリックします。
1. Adobe CampaignデータをエンリッチメントするAdobe Analyticsレポートスイートの「 **[!UICONTROL Analytics default report suite]** 」ドロップダウンでを選択します。

   これで、外部アカウントの準備が整い、Adobe Analyticsにリンクされました。 **[!UICONTROL Enabled]**&#x200B;ボックスをオンにすれば、いつでも無効にできます。

   ![](assets/analytics.png)

**[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;テクニカルワークフローが自動的に起動し、**[!UICONTROL Administration > Application settings > Workflow]**&#x200B;を選択して詳細設定メニューから表示できるようになりました。 このテクニカルワークフローは、15分ごとに自動的に実行され、最大6ヶ月の古いデータをAdobe Analyticsにプッシュします。

![](assets/analytics_3.png)

これで、データがAdobe Analyticsで使用できるようになりました。

**関連トピック：**

* [外部アカウント](../../administration/using/external-accounts.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [統合キャンペーンレポートのKPIを](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) 共有（ビデオ）
