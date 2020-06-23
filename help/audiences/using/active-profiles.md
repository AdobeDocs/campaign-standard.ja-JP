---
title: アクティブなプロファイル
description: 顧客指標に関する専用レポートにアクセスし、キャンペーンデータベースでアクティブなプロファイルを視覚化できます。
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 19%

---


# アクティブなプロファイル{#active-profiles}

Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。 このレポートは情報を提供するだけで、請求に直接影響しません。 このレポートにアクセスできるのは、管理者のみです。 **[!UICONTROL Administration > Customer metrics]**

![](assets/audience_active_profiles1.png)

テクニカル **[!UICONTROL Billing]** ワークフローは、毎月、過去12か月の周期中にターゲットにされたアクティブなプロファイルの数を含むレポートを生成します。

配信の準備中に（タイポロジルール、強制隔離によって）除外されたプロファイルは、考慮されません。プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。レポートの下部には、各ターゲティングディメンションのアクティブなプロファイルのリストが表示されます。

![](assets/audience_active_profiles2.png)

AWSでホストし、ビルド10368のCampaign Standardを使用している場合は、コントロールパネルから直接、インスタンスで使用されるアクティブなプロファイルの数を監視することもできます。 For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
