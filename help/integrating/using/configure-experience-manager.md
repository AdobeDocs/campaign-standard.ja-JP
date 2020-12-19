---
solution: Campaign Standard
product: campaign
title: Campaign と Experience Manager の統合の設定
description: Adobe Experience Manager統合では、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Campaign と Experience Manager の統合の設定 {#configuration-aem}

このAdobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

この使用例では、Adobe Experience Managerで電子メールコンテンツを作成および管理し、電子メールをAdobe Campaign Standardにインポートしてマーケティングキャンペーンに使用する方法を学びます。

## 前提条件 {#prerequisites}

前もって次の要素を用意しておく必要があります。

* Adobe Experience Manager **オーサリング**&#x200B;インスタンス
* Adobe Experience Manager **発行**&#x200B;インスタンス
* Adobe Campaignインスタンス

## Adobe Campaign Standard{#config-acs}の設定

2 つのソリューションを同時に使用するには、相互接続を設定する必要があります。Adobe Campaign を設定するには：

1. まず、**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**&#x200B;の下に&#x200B;**[!UICONTROL Adobe Experience Manager instance]**&#x200B;外部アカウントを設定する必要があります。

1. **[!UICONTROL Server]** URL、**[!UICONTROL Account]**、**[!UICONTROL Password]**&#x200B;を使用して、Adobe Experience Managerタイプ外部アカウントを設定します。

   ![](assets/aem_1.png)

1. **[!UICONTROL AEMResourceTypeFilter]**&#x200B;オプションが正しく設定されていることを確認します。 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;メニューの下の&#x200B;**[!UICONTROL Options]**&#x200B;メニューにアクセスします。

1. **[!UICONTROL Value (text)]**&#x200B;フィールドで、次の構文が正しいことを確認します。

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 次に、**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;の下の詳細メニューで、既存のテンプレートの1つを重複し、Adobe Experience Manager専用の電子メールテンプレートを作成します。

   ![](assets/aem_3.png)

1. **[!UICONTROL Edit properties]**&#x200B;アイコンをクリックします。

   ![](assets/aem_4.png)

1. **[!UICONTROL Content]**&#x200B;ドロップダウンで、**[!UICONTROL Content source]**&#x200B;フィールドの&#x200B;**[!UICONTROL Adobe Experience Manager]**&#x200B;を選択し、**[!UICONTROL Adobe Experience Manager account]**&#x200B;に以前に作成した外部アカウントを選択します。

次に、Adobe Experience Managerで統合を設定する必要があります。

## Adobe Experience Manager{#config-aem}の設定

Adobe Campaign StandardとAdobe Experience Managerを設定するには、次の手順に従う必要があります。

1. まず、Adobe Experience Managerのオーサリングインスタンスとパブリッシングインスタンスの間のレプリケーションを設定する必要があります。 [こちら](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)を参照してください。

1. 次に、専用の&#x200B;**[!UICONTROL Cloud Service]**&#x200B;を設定して、Adobe Experience ManagerをAdobe Campaignに接続します。 [こちら](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)を参照してください。

1. これで、作成者インスタンスのAdobe Experience Managerで外部化子を設定する必要があります。 [こちら](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)を参照してください。

