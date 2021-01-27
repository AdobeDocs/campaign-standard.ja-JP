---
solution: Campaign Standard
product: campaign
title: Campaign と Analytics の統合の設定
description: 電子メール配信の成功度を測定する開始に、Adobe Analytics統合を設定する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---


# Campaign と Analytics の統合の設定{#configure-campaign-analytics-integration}

この統合により、主要業績評価指標データをAdobe CampaignからAdobe Analytics Standardまたはプレミアムに直接共有できます。

Adobe Campaign StandardとAdobe Analyticsの統合を開始するには、まずAdobe Analyticsにリンクされた外部アカウントを設定する必要があります。

外部アカウントとテクニカルワークフローは、プラットフォームの機能管理者のみが管理できます。

1. 詳細設定メニューのAdobe Campaignロゴで&#x200B;**[!UICONTROL Administration > Application settings > External accounts]**&#x200B;を選択します。
1. **[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;外部アカウントを選択します。

   ![](assets/analytics_2.png)

1. **[!UICONTROL Web services user name]**&#x200B;と&#x200B;**[!UICONTROL Web services share secret]**&#x200B;を&#x200B;**[!UICONTROL Connection]**&#x200B;フィールドに指定します。

   これらのパラメーターは、Analyticsで&#x200B;**[!UICONTROL Admin > Company settings > Web services]**&#x200B;を選択すると確認できます。

   ![](assets/analytics_1.png)

1. 「**[!UICONTROL Refresh report suites]**」ボタンをクリックします。
1. **[!UICONTROL Analytics default report suite]**&#x200B;ドロップダウンで、Adobe Campaignデータの拡充に使用するAdobe Analyticsレポートスイートを選択します。

   これで外部アカウントはAdobe Analyticsとリンクされました。 **[!UICONTROL Enabled]**&#x200B;ボックスをチェックすると、いつでも無効にできます。

   ![](assets/analytics.png)

**[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;テクニカルワークフローが自動的に起動し、**[!UICONTROL Administration > Application settings > Workflow]**&#x200B;を選択してアドバンスメニューから表示できるようになりました。 この技術ワークフローは、15分ごとに自動的に実行され、6か月前までのデータがAdobe Analyticsにプッシュされます。

![](assets/analytics_3.png)

データがAdobe Analyticsで入手できるようになりました。

**関連トピック：**

* [外部アカウント](../../administration/using/external-accounts.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [統合キャンペーンレポートビデオのKPIを共有](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) します

