---
title: Campaign- Target統合の設定
seo-title: Campaign- Target統合の設定
description: Campaign- Target統合の設定
seo-description: Adobe Target統合を設定して、Adobe Campaignで動的コンテンツを使用する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 0df5701c- dc26-4c30-9af9- ebf92815d90c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- target
discoiquuid: f7fb2084- dd6f-4aa2-940f- e48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring the Campaign-Target integration{#configuring-the-campaign-target-integration}

Adobe CampaignとAdobe Targetの統合により、動的コンテンツを配信に挿入できます。

Adobe Campaignでは、Adobe Targetの統合機能を使用するために設定が最初に必要であり、機能管理者が管理する必要があります。

この手順には、次の要素が必要です。

* Adobe Experience Cloudテナント
* Adobe Targetテナント
* Adobe Campaignとの接続を確立するために指定されたAdobe Target rawbox

1. From the advanced menu, via the Adobe Campaign logo in the top left corner, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. Adobe Targetのサーバーおよびテナントオプションを設定するには、次のフィールドに適切な情報を入力します。

   * **[!UICONTROL TNT_TenantName]**:Adobe Targetテナントの名前。This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**:統合に使用されるAdobe Targetサーバー。このオプションはデフォルトで提供されています。This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. For example: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Adobe Targetを使用して、動的な画像を配信に追加できるようになりました。
