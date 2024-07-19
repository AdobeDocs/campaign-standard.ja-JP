---
title: Campaign と Target の統合の設定
description: Adobe Campaignで動的コンテンツの使用を開始するようにAdobe Target統合を設定する方法を説明します。
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

まず、Adobe Targetとの統合機能を使用するための設定がAdobe Campaignで必要であり、機能管理者が管理する必要があります。

この手順では、以下の要素が必要です。

* Adobe Experience Cloud テナント
* Adobe Target テナント
* Adobe Campaign との接続を確立するために指定された Adobe Target ローボックス

1. 左上隅のAdobe Campaign ロゴを使用し、詳細メニューで **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** を選択します。
1. Adobe Targetのサーバーオプションとテナントオプションを設定するには、次のフィールドを適宜入力します。

   * **[!UICONTROL TNT_TenantName]**: Adobe Target テナントの名前。 この値はAdobe Target **[!UICONTROL Client]** の名前に対応します。
   * **[!UICONTROL TNT_EdgeServer]**：統合に使用されるAdobe Target サーバー。 このオプションはデフォルトで既に指定されています。 この値はAdobe Target **[!UICONTROL Server Domain]** に対応し、その後に **/m2** 値が続きます。 例：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

ユーザーは、Adobe Targetの配信に動的画像を追加できるようになりました。
