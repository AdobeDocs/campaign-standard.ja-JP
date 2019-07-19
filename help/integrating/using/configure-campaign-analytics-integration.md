---
title: Campaign- Analytics統合の設定
seo-title: Campaign- Analytics統合の設定
description: Campaign- Analytics統合の設定
seo-description: Adobe Analytics統合を設定して、電子メール配信の成功の測定を開始する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: bda00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- analytics
discoiquuid: 92b9004c- cba0-41fd- a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configure Campaign-Analytics integration{#configure-campaign-analytics-integration}

この統合により、主要業績評価指標データをAdobe CampaignからAdobe Analytics StandardまたはPremiumに直接共有できます。

Adobe Campaign StandardとAdobe Analyticsの統合を開始するには、まずAdobe Analyticsにリンクされている外部アカウントを設定する必要があります。

外部アカウントおよび技術ワークフローは、プラットフォームの機能管理者のみが管理できます。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. **[!UICONTROL Share KPIs with Adobe Analytics]** 外部アカウントを選択します。

   ![](assets/analytics_2.png)

1. Specify your **[!UICONTROL Web services user name]** and **[!UICONTROL Web services share secret]** in the **[!UICONTROL Connection]** field.

   These parameters can be found in Analytics by selecting **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Select in the **[!UICONTROL Analytics default report suite]** drop-down the Adobe Analytics report suite you want to enrich with Adobe Campaign data.

   外部アカウントが準備され、Adobe Analyticsとリンクされました。**[!UICONTROL Enabled]** チェックボックスをオンにすると、いつでも無効にできます。

   ![](assets/analytics.png)

**[!UICONTROL Share KPIs with Adobe Analytics]** 技術ワークフローが自動的に起動し、詳細メニューから選択 **[!UICONTROL Administration > Application settings > Workflow]**&#x200B;して表示できます。この技術ワークフローは、15分ごとに自動的に実行され、Adobe Analyticsで6か月前のデータにプッシュされます。

![](assets/analytics_3.png)

データがAdobe Analyticsで使用できるようになりました。

**関連トピック:**

* [外部アカウント](../../administration/using/external-accounts.md)
* [技術ワークフロー](../../administration/using/technical-workflows.md)
* [統合キャンペーンレポート](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) ビデオのKPIの共有

