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
source-wordcount: '341'
ht-degree: 12%

---


# Campaign と Experience Manager の統合の設定 {#configuration-aem}

このAdobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

この使用例では、Adobe Experience Managerで電子メールコンテンツを作成および管理し、電子メールをAdobe Campaign Standardにインポートしてマーケティングキャンペーンに使用する方法を学びます。

## 前提条件 {#prerequisites}

前もって次の要素を用意しておく必要があります。

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Adobe Campaignインスタンス

## Adobe Campaign Standardの設定 {#config-acs}

2 つのソリューションを同時に使用するには、相互接続を設定する必要があります。Adobe Campaign を設定するには：

1. まず、> >の下で **[!UICONTROL Adobe Experience Manager instance]** 外部アカウントを設定する必要があり **[!UICONTROL Administration]****[!UICONTROL Application settings]****[!UICONTROL External accounts menu]**&#x200B;ます。

1. Adobe Experience Managerタイプ外部アカウントを **[!UICONTROL Server]** URLで設定し、 **[!UICONTROL Account]** と **[!UICONTROL Password]**&#x200B;を使用します。

   ![](assets/aem_1.png)

1. この **[!UICONTROL AEMResourceTypeFilter]** オプションが正しく設定されていることを確認します。 //メニューの下の **[!UICONTROL Options]** メニューにアクセスし **[!UICONTROL Administration]** ま **[!UICONTROL Application settings]** す **[!UICONTROL Options]** 。

1. フィールドで、次の構文が正しいことを確認し **[!UICONTROL Value (text)]** ます。

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 次に、 > **[!UICONTROL Resources]** >のアドバンスメニューで、既存のテンプレートの1つを重複して、Adobe Experience Manager向けの電子メールテンプレートを作成し **[!UICONTROL Templates]****[!UICONTROL Delivery templates]**&#x200B;ます。

   ![](assets/aem_3.png)

1. アイコンをクリックし **[!UICONTROL Edit properties]** ます。

   ![](assets/aem_4.png)

1. ドロップダウンの下で、 **[!UICONTROL Content]** フィールド **[!UICONTROL Adobe Experience Manager]** 内を選択し、前に作成した外部アカウントを **[!UICONTROL Content source]****[!UICONTROL Adobe Experience Manager account]**&#x200B;内で選択します。

次に、Adobe Experience Managerで統合を設定する必要があります。

## Configuration in Adobe Experience Manager {#config-aem}

Adobe Campaign StandardとAdobe Experience Managerを設定するには、次の手順に従う必要があります。

1. まず、Adobe Experience Managerのオーサリングインスタンスとパブリッシングインスタンスの間のレプリケーションを設定する必要があります。 [こちら](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)を参照してください。

1. Then, connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**. [こちら](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)を参照してください。

1. これで、作成者インスタンスのAdobe Experience Managerで外部化子を設定する必要があります。 [こちら](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)を参照してください。

