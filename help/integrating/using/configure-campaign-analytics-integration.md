---
title: Campaign と Analytics の統合の設定
description: 電子メール配信の成功の測定を開始するためのAdobe Analytics統合の設定方法について説明します。
page-status-flag: 非活性化の
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンと分析の連携
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Campaign と Analytics の統合の設定{#configure-campaign-analytics-integration}

この統合により、主要業績評価指標データをAdobe CampaignからAdobe Analytics StandardまたはPremiumに直接共有できます。

Adobe Campaign StandardとAdobe Analyticsの統合を開始するには、まずAdobe Analyticsにリンクされた外部アカウントを設定する必要があります。

外部アカウントと技術ワークフローは、プラットフォームの機能管理者のみが管理できます。

1. アドバンスメニューで、Adobe Campaignロゴを使用してを選択しま **[!UICONTROL Administration > Application settings > External accounts]**&#x200B;す。
1. 外部アカウント **[!UICONTROL Share KPIs with Adobe Analytics]** を選択します。

   ![](assets/analytics_2.png)

1. フィールド **[!UICONTROL Web services user name]** でと **[!UICONTROL Web services share secret]** を指定し **[!UICONTROL Connection]** ます。

   これらのパラメーターは、を選択することで、Analyticsで確認できま **[!UICONTROL Admin > Company settings > Web services]**&#x200B;す。

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Adobe Campaignデータを **[!UICONTROL Analytics default report suite]** 有効にするAdobe Analyticsレポートスイートをドロップダウンリストで選択します。

   これで、外部アカウントの準備が整い、Adobe Analyticsにリンクされました。 この設定は、チェックボックスをオンにするといつでも無効にで **[!UICONTROL Enabled]** きます。

   ![](assets/analytics.png)

テクニカ **[!UICONTROL Share KPIs with Adobe Analytics]** ルワークフローが自動的に起動し、を選択してアドバンスメニューから表示できるようになりま **[!UICONTROL Administration > Application settings > Workflow]**&#x200B;す。 この技術ワークフローは15分ごとに自動的に実行され、Adobe Analyticsで最大6か月の古いデータがプッシュされます。

![](assets/analytics_3.png)

これで、データがAdobe Analyticsで使用できるようになります。

**関連トピック：**

* [外部アカウント](../../administration/using/external-accounts.md)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [統合キャンペーンレポートビデオのKPIを共有](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) （英語）

