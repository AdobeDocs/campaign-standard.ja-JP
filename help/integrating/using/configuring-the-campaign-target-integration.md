---
solution: Campaign Standard
product: campaign
title: Campaign と Target の統合の設定
description: Adobe Campaignの動的コンテンツを使用して、開始へのAdobe Target統合を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: トリガー
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 13%

---


# Campaign と Target の統合の設定{#configuring-the-campaign-target-integration}

Adobe CampaignとAdobe Targetの統合により、配信に動的なコンテンツを挿入できます。

設定は、まずAdobe Targetとの統合機能を使用するAdobe Campaignで必要となり、機能管理者が管理する必要があります。

この手順では、次の要素が必要です。

* Adobe Experience Cloudの住人
* Adobe Targetの住人
* Adobe Campaign との接続を確立するために指定された Adobe Target ローボックス

1. 詳細設定メニューの左上隅にあるAdobe Campaignロゴから、**[!UICONTROL Administration]**/**[!UICONTROL Application settings]**/**[!UICONTROL Options]**&#x200B;を選択します。
1. Adobe Targetのサーバーとテナントのオプションを構成するには、それに応じて次のフィールドに入力します。

   * **[!UICONTROL TNT_TenantName]**:Adobe Targetの住人の名前。この値は、Adobe Target **[!UICONTROL Client]**&#x200B;の名前に対応します。
   * **[!UICONTROL TNT_EdgeServer]**:統合に使用されるAdobe Targetサーバ。このオプションは既定では既に提供されています。 この値は、Adobe Target **[!UICONTROL Server Domain]**&#x200B;に続く&#x200B;**/m2**&#x200B;値に対応します。 例：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

これで、ユーザはAdobe Targetとの配信に動的な画像を追加できます。
