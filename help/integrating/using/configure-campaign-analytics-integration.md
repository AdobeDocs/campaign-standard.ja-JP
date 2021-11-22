---
title: Campaign と Analytics の統合の設定
description: Adobe Analytics統合を設定して、E メール配信の成功の測定を開始する方法について説明します。
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

この統合により、主要業績評価指標のデータをAdobe CampaignからAdobe Analytics Standardまたは Premium に直接共有できます。

Adobe Campaign StandardとAdobe Analyticsの統合を開始するには、まずAdobe Analyticsにリンクされた外部アカウントを設定する必要があります。

外部アカウントとテクニカルワークフローは、プラットフォームの機能管理者のみが管理できます。

1. 詳細設定メニューのAdobe Campaignロゴから、を選択します。 **[!UICONTROL Administration > Application settings > External accounts]**.
1. を選択します。 **[!UICONTROL Share KPIs with Adobe Analytics]** 外部アカウント。

   ![](assets/analytics_2.png)

1. 次を指定： **[!UICONTROL Web services user name]** および **[!UICONTROL Web services share secret]** 内 **[!UICONTROL Connection]** フィールドに入力します。

   これらのパラメーターは、Analytics で **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. 「**[!UICONTROL Refresh report suites]**」ボタンをクリックします。
1. を **[!UICONTROL Analytics default report suite]** Adobe CampaignデータのエンリッチメントをおこなうAdobe Analyticsレポートスイートのドロップダウン。

   これで、外部アカウントが準備でき、Adobe Analyticsにリンクされました。 これは、 **[!UICONTROL Enabled]** ボックス

   ![](assets/analytics.png)

この **[!UICONTROL Share KPIs with Adobe Analytics]** テクニカルワークフローが自動的に起動し、詳細設定メニューから「 **[!UICONTROL Administration > Application settings > Workflow]**. このテクニカルワークフローは、15 分ごとに自動的に実行され、最大 6 か月前のデータをAdobe Analyticsにプッシュします。

![](assets/analytics_3.png)

これで、データがAdobe Analyticsで使用できるようになりました。

**関連トピック：**

* [外部アカウント](../../administration/using/external-accounts.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [統合キャンペーンレポートの KPI を共有](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) ビデオ
