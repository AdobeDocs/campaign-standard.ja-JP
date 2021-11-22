---
title: Campaign と Target の統合の設定
description: Adobe Campaignで動的コンテンツを使用し始めるようにAdobe Target統合を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 13%

---

# Campaign と Target の統合の設定{#configuring-the-campaign-target-integration}

Adobe CampaignとAdobe Targetの統合により、配信に動的コンテンツを挿入できます。

設定は、まずAdobe CampaignでAdobe Targetとの統合機能を使用するために必要で、機能管理者が管理する必要があります。

この手順では、次の要素が必要です。

* Adobe Experience Cloudテナント
* Adobe Targetテナント
* Adobe Campaign との接続を確立するために指定された Adobe Target ローボックス

1. 詳細設定メニューの左上隅にあるAdobe Campaignロゴから、 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Adobe Targetのサーバーおよびテナントオプションを設定するには、それに応じて次のフィールドに入力します。

   * **[!UICONTROL TNT_TenantName]**:Adobe Targetテナントの名前。 この値は、Adobe Targetの名前に対応します **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**:統合に使用するAdobe Targetサーバー。 このオプションは、デフォルトで既に提供されています。 この値は、Adobe Target **[!UICONTROL Server Domain]**、その後に **/m2** の値です。 例：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

ユーザーは、Adobe Targetを使用した配信に動的画像を追加できるようになりました。
