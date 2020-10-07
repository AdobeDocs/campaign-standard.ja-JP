---
title: Campaign と Analytics の統合の設定
description: 電子メール配信の成功度を測定する開始に、Adobe Analytics統合を設定する方法を説明します。
page-status-flag: never-activated
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---


# Campaign と Analytics の統合の設定{#configure-campaign-analytics-integration}

この統合により、主要業績評価指標データをAdobe CampaignからAdobe Analytics Standardまたはプレミアムに直接共有できます。

Adobe Campaign StandardとAdobe Analyticsの統合を開始するには、まずAdobe Analyticsにリンクされた外部アカウントを設定する必要があります。

外部アカウントとテクニカルワークフローは、プラットフォームの機能管理者のみが管理できます。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. フィールドに **[!UICONTROL Web services user name]** および **[!UICONTROL Web services share secret]** を指定し **[!UICONTROL Connection]** ます。

   これらのパラメーターは、Analyticsでを選択すると表示でき **[!UICONTROL Admin > Company settings > Web services]**&#x200B;ます。

   ![](assets/analytics_1.png)

1. 「**[!UICONTROL Refresh report suites]**」ボタンをクリックします。
1. Adobe Campaignデータの拡充を行うAdobe Analyticsレポートスイートの **[!UICONTROL Analytics default report suite]** ドロップダウンリストから選択します。

   これで外部アカウントはAdobe Analyticsとリンクされました。 この設定は、 **[!UICONTROL Enabled]** ボックスをオンにするといつでも無効にできます。

   ![](assets/analytics.png)

これで、 **[!UICONTROL Share KPIs with Adobe Analytics]** 技術ワークフローが自動的に起動し、を選択してアドバンスメニューから表示できるようにな **[!UICONTROL Administration > Application settings > Workflow]**&#x200B;ります。 この技術ワークフローは、15分ごとに自動的に実行され、6か月前までのデータがAdobe Analyticsにプッシュされます。

![](assets/analytics_3.png)

データがAdobe Analyticsで入手できるようになりました。

**関連トピック：**

* [外部アカウント](../../administration/using/external-accounts.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [統合キャンペーンレポート](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) ・ビデオのKPIを共有

