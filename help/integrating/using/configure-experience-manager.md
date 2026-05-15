---
title: Campaign と Experience Manager の統合の設定
description: Adobe Experience Managerとの連携により、AEMで直接コンテンツを制作し、後のAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
TQID: https://experienceleague.adobe.com/LluSzpCdzqvBNFz9HmI4MCLj8hhXO0Wp-kefaoNLB5U
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 12%

---

# Campaign と Experience Manager の統合の設定 {#configuration-aem}

Adobe Campaign StandardとAdobe Experience Managerの連携により、Adobe Experience Managerで作成したコンテンツをAdobe Campaignの電子メールで使用できるようになります。

このユースケースでは、Adobe Experience Managerでメールコンテンツを作成および管理し、メールでAdobe Campaign Standardに読み込むことでマーケティングキャンペーンに使用する方法を説明します。

## 前提条件 {#prerequisites}

事前に次の要素を確認する必要があります。

* Adobe Experience Manager **オーサリング** インスタンス
* Adobe Experience Manager **パブリッシング** インスタンス
* Adobe Campaign インスタンス

## Adobe Campaign Standardの設定 {#config-acs}

2 つのソリューションを同時に使用するには、相互接続を設定する必要があります。
Adobe Campaign を設定するには：

1. 最初に、**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**&#x200B;の下の&#x200B;**[!UICONTROL Adobe Experience Manager instance]**&#x200B;外部アカウントを設定する必要があります。

1. **[!UICONTROL Server]** URL、**[!UICONTROL Account]**&#x200B;および&#x200B;**[!UICONTROL Password]**&#x200B;を使用して、Adobe Experience Manager タイプの外部アカウントを設定します。

   ![](assets/aem_1.png)

1. **[!UICONTROL AEMResourceTypeFilter]** オプションが正しく設定されていることを確認してください。 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** メニューの下の&#x200B;**[!UICONTROL Options]** メニューにアクセスします。

1. **[!UICONTROL Value (text)]** フィールドで、次の構文が正しいことを確認します。

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 次に、**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;の詳細メニューで、既存のテンプレートのいずれかを複製して、Adobe Experience Managerに固有のメールテンプレートを作成します。

   ![](assets/aem_3.png)

1. **[!UICONTROL Edit properties]** アイコンをクリックします。

   ![](assets/aem_4.png)

1. **[!UICONTROL Content]** ドロップダウンで、**[!UICONTROL Content source]** フィールドの&#x200B;**[!UICONTROL Adobe Experience Manager]**&#x200B;を選択し、次に&#x200B;**[!UICONTROL Adobe Experience Manager account]**&#x200B;で以前に作成した外部アカウントを選択します。

次に、Adobe Experience Managerで統合を設定する必要があります。

## Adobe Experience Managerの設定 {#config-aem}

Adobe Campaign StandardでAdobe Experience Managerを設定するには、次の手順に従う必要があります。

1. まず、Adobe Experience Manager オーサリングインスタンスとパブリッシングインスタンス間のレプリケーションを設定する必要があります。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)を参照してください。

1. 次に、専用の&#x200B;**[!UICONTROL Cloud Service]**&#x200B;を設定して、Adobe Experience ManagerをAdobe Campaignに接続します。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)を参照してください。

1. 次に、オーサーインスタンスでAdobe Experience Managerのexternalizerを設定する必要があります。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)を参照してください。
