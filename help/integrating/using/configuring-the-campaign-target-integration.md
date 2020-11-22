---
solution: Campaign Standard
product: campaign
title: Campaign と Target の統合の設定
description: Adobe Campaignの動的コンテンツを使用して、開始へのAdobe Target統合を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 13%

---


# Campaign と Target の統合の設定{#configuring-the-campaign-target-integration}

Adobe CampaignとAdobe Targetの統合により、配信に動的なコンテンツを挿入できます。

設定は、まずAdobe Targetとの統合機能を使用するAdobe Campaignで必要となり、機能管理者が管理する必要があります。

この手順では、次の要素が必要です。

* Adobe Experience Cloudの住人
* Adobe Targetの住人
* Adobe Campaign との接続を確立するために指定された Adobe Target ローボックス

1. 詳細設定メニューの左上隅にあるAdobe Campaignロゴで、 **[!UICONTROL Administration]** / **[!UICONTROL Application settings]** /を選択し **[!UICONTROL Options]**&#x200B;ます。
1. Adobe Targetのサーバーとテナントのオプションを構成するには、それに応じて次のフィールドに入力します。

   * **[!UICONTROL TNT_TenantName]**:adobe targetの住人の名前。 This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**:統合に使用されるAdobe Targetサーバ。 このオプションは既定では既に提供されています。 この値は、Adobe Targetに対応し **[!UICONTROL Server Domain]**、その後に **/m2** 値が続きます。 例：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

これで、ユーザはAdobe Targetとの配信に動的な画像を追加できます。
