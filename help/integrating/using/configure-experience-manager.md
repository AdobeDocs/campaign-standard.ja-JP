---
solution: Campaign Standard
product: campaign
title: Campaign と Experience Manager の統合の設定
description: Adobe Experience Manager統合を使用すると、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: トリガー
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 12%

---

# Campaign と Experience Manager の統合の設定 {#configuration-aem}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe CampaignのEメールで使用できます。

この使用例では、Adobe Experience ManagerでEメールコンテンツを作成および管理し、EメールでAdobe Campaign Standardにインポートしてマーケティングキャンペーンで使用する方法を学習します。

## 前提条件 {#prerequisites}

事前に、次の要素を用意しておく必要があります。

* Adobe Experience Manager **オーサリング**&#x200B;インスタンス
* Adobe Experience Manager **パブリッシュ**&#x200B;インスタンス
* Adobe Campaignインスタンス

## Adobe Campaign Standardの設定{#config-acs}

2 つのソリューションを同時に使用するには、相互接続を設定する必要があります。Adobe Campaign を設定するには：

1. 最初に、**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**&#x200B;の下に&#x200B;**[!UICONTROL Adobe Experience Manager instance]**&#x200B;外部アカウントを設定する必要があります。

1. **[!UICONTROL Server]** URL、**[!UICONTROL Account]**&#x200B;および&#x200B;**[!UICONTROL Password]**&#x200B;を使用して、Adobe Experience Managerタイプの外部アカウントを設定します。

   ![](assets/aem_1.png)

1. **[!UICONTROL AEMResourceTypeFilter]**&#x200B;オプションが正しく設定されていることを確認します。 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;メニューの下の&#x200B;**[!UICONTROL Options]**&#x200B;メニューにアクセスします。

1. **[!UICONTROL Value (text)]**&#x200B;フィールドで、次の構文が正しいことを確認します。

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 次に、**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;の詳細設定メニューで、既存のテンプレートの1つを複製して、Adobe Experience Manager専用のEメールテンプレートを作成します。

   ![](assets/aem_3.png)

1. **[!UICONTROL Edit properties]**&#x200B;アイコンをクリックします。

   ![](assets/aem_4.png)

1. **[!UICONTROL Content]**&#x200B;ドロップダウンで、「**[!UICONTROL Content source]**」フィールドで「**[!UICONTROL Adobe Experience Manager]**」を選択し、以前に作成した外部アカウントを「**[!UICONTROL Adobe Experience Manager account]**」で選択します。

次に、Adobe Experience Managerで統合を設定する必要があります。

## Adobe Experience Managerの設定{#config-aem}

Adobe Campaign StandardでAdobe Experience Managerを設定するには、次の手順に従う必要があります。

1. 最初に、Adobe Experience Managerオーサリングインスタンスとパブリッシュインスタンスの間のレプリケーションを設定する必要があります。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)を参照してください。

1. 次に、専用の&#x200B;**[!UICONTROL Cloud Service]**&#x200B;を設定してAdobe Experience ManagerをAdobe Campaignに接続します。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)を参照してください。

1. 次に、オーサーインスタンス上のAdobe Experience ManagerでExternalizerを設定する必要があります。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)を参照してください。
