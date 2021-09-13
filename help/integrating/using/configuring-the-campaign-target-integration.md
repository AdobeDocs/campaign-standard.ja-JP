---
title: Campaign と Target の統合の設定
description: Adobe Campaignで動的コンテンツを使用するようにAdobe Target統合を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 13%

---

# Campaign と Target の統合の設定{#configuring-the-campaign-target-integration}

Adobe CampaignとAdobe Targetの統合により、配信に動的コンテンツを挿入できます。

設定は、まずAdobe CampaignでAdobe Targetとの統合機能を使用するために必要で、機能管理者が管理する必要があります。

この手順では、次の要素が必要です。

* Adobe Experience Cloudテナント
* Adobe Targetテナント
* Adobe Campaign との接続を確立するために指定された Adobe Target ローボックス

1. 詳細設定メニューの左上隅にあるAdobe Campaignロゴから、**[!UICONTROL Administration]** / **[!UICONTROL Application settings]** / **[!UICONTROL Options]**&#x200B;を選択します。
1. Adobe Targetのサーバーおよびテナントオプションを設定するには、それに応じて次のフィールドに入力します。

   * **[!UICONTROL TNT_TenantName]**:Adobe Targetテナントの名前。この値は、Adobe Targetの&#x200B;**[!UICONTROL Client]**&#x200B;名に対応します。
   * **[!UICONTROL TNT_EdgeServer]**:Adobe Targetサーバーを統合に使用。このオプションは既にデフォルトで提供されています。 この値はAdobe Targetの&#x200B;**[!UICONTROL Server Domain]**&#x200B;に続く&#x200B;**/m2**&#x200B;値に対応します。 例：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

ユーザーは、Adobe Targetを使用した配信に動的画像を追加できるようになりました。
