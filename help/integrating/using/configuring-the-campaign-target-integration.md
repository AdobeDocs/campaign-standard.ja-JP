---
title: Campaign と Target の統合の設定
description: Adobe Campaignで動的コンテンツの使用を開始するようにAdobe Target統合を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
TQID: https://experienceleague.adobe.com/trfuEp6pEd2jFADsK6NMw6tx8ASi86ZFur56AjwnpWQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 14%

---

# Campaign と Target の統合の設定{#configuring-the-campaign-target-integration}

Adobe CampaignとAdobe Targetの連携により、コンテンツを動的に配信できます。

Adobe Targetとの統合機能を使用するには、Adobe Campaignで最初に設定が必要です。設定は、機能管理者が管理する必要があります。

この手順には、次の要素が必要です。

* Adobe Experience Cloud テナント
* Adobe Target テナント
* Adobe Campaign との接続を確立するために指定された Adobe Target ローボックス

1. 詳細設定メニューの左上隅にあるAdobe Campaign ロゴから、**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;を選択します。
1. Adobe Targetのサーバーオプションとテナントオプションを設定するには、次のフィールドに入力します。

   * **[!UICONTROL TNT_TenantName]**: Adobe Target テナントの名前。 この値は、Adobe Target **[!UICONTROL Client]**&#x200B;の名前に対応します。
   * **[!UICONTROL TNT_EdgeServer]**：統合に使用されるAdobe Target サーバー。 このオプションは既にデフォルトで提供されています。 この値はAdobe Target **[!UICONTROL Server Domain]**&#x200B;に対応し、その後に&#x200B;**/m2**&#x200B;値が続きます。 例：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

Adobe Targetを使用して、配信内に動的画像を追加できるようになりました。
