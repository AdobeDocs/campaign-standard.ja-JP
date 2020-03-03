---
title: Campaign-Experience Manager統合の設定
description: Adobe Experience Managerの統合により、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37b1c17234a300b092db3c810a32de3600bb8f2f

---


# Campaign-Experience Manager統合の設定 {#configuration-aem}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

この使用例では、Adobe Experience Managerで電子メールコンテンツを作成および管理し、電子メールをAdobe Campaign Standardにインポートしてマーケティングキャンペーンに使用する方法を学びます。

## 前提条件 {#prerequisites}

前もって次の要素があることを確認してください。

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Adobe Campaignインスタンス

## Adobe Campaign Standardでの設定 {#config-acs}

2 つのソリューションを同時に使用するには、相互接続を設定する必要があります。Adobe Campaign を設定するには：

1. 最初に、> >で外部アカウン **[!UICONTROL Adobe Experience Manager instance]** トを設定する **[!UICONTROL Administration]** 必要があ **[!UICONTROL Application settings]** ります **[!UICONTROL External accounts menu]**。

1. Adobe Experience Managerタイプの外部アカウントを **[!UICONTROL Server]** URLで設定し、およびを使用 **[!UICONTROL Account]** しま **[!UICONTROL Password]**&#x200B;す。

   ![](assets/aem_1.png)

1. このオプションが正し **[!UICONTROL AEMResourceTypeFilter]** く設定されていることを確認します。 //メニュー **[!UICONTROL Options]** の下のメニ **[!UICONTROL Administration]** ューにア **[!UICONTROL Application settings]** クセス **[!UICONTROL Options]** します。

1. このフィールド **[!UICONTROL Value (text)]** で、次の構文が正しいことを確認します。

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 次に、/の下の詳細メニューで、既存のテ **[!UICONTROL Resources]** ンプレ **[!UICONTROL Templates]** ート **[!UICONTROL Delivery templates]**&#x200B;の1つを複製し、Adobe Experience Manager専用の電子メールテンプレートを作成します。

   ![](assets/aem_3.png)

1. アイコンをクリッ **[!UICONTROL Edit properties]** クします。

   ![](assets/aem_4.png)

1. ドロップダ **[!UICONTROL Content]** ウンの下で、フィー **[!UICONTROL Adobe Experience Manager]** ルド内を選択 **[!UICONTROL Content source]** し、前にで作成した外部アカウントを選択しま **[!UICONTROL Adobe Experience Manager account]**&#x200B;す。

これで、Adobe Experience Managerで統合を設定する必要があります。

## Configuration in Adobe Experience Manager {#config-aem}

Adobe Experience ManagerをAdobe Campaign Standardと共に設定するには、次の手順に従う必要があります。

1. まず、Adobe Experience Managerのオーサリングインスタンスとパブリッシュインスタンス間のレプリケーションを設定する必要があります。 この[節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)を参照してください。

1. Then, connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**. この[節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)を参照してください。

1. これで、作成者インスタンス上のAdobe Experience Managerで外部化機能を設定する必要があります。 この[節](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)を参照してください。

