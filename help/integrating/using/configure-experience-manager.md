---
title: Campaign と Experience Manager の統合の設定
description: Adobe Experience Manager統合を使用すると、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用することができます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 8%

---

# Campaign と Experience Manager の統合の設定 {#configuration-aem}

Adobe Campaign StandardとAdobe Experience Managerのこの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaign E メールで使用できます。

この使用例では、Adobe Experience Managerで E メールコンテンツを作成および管理し、E メールでAdobe Campaign Standardにインポートしてマーケティングキャンペーンで使用する方法を学びます。

## 前提条件 {#prerequisites}

事前に次の要素を用意しておく必要があります。

* Adobe Experience Manager **authoring** インスタンス
* Adobe Experience Manager **公開** インスタンス
* Adobe Campaignインスタンス

## Adobe Campaign Standardでの設定 {#config-acs}

これら 2 つのソリューションを同時に使用するには、相互に接続するように設定する必要があります。
Adobe Campaign を設定するには：

1. 最初に、 **[!UICONTROL Adobe Experience Manager instance]** 下の外部アカウント **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Adobe Experience Managerタイプの外部アカウントを **[!UICONTROL Server]** URL, **[!UICONTROL Account]** および **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. 以下を確認します。 **[!UICONTROL AEMResourceTypeFilter]** 」オプションが正しく設定されていることを確認します。 次にアクセス： **[!UICONTROL Options]** 下のメニュー **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** メニュー。

1. Adobe Analytics の **[!UICONTROL Value (text)]** フィールドで、次の構文が正しいことを確認します。

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. 次に、 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**、既存のテンプレートの 1 つを複製して、Adobe Experience Manager専用の E メールテンプレートを作成します。

   ![](assets/aem_3.png)

1. 次をクリック： **[!UICONTROL Edit properties]** アイコン。

   ![](assets/aem_4.png)

1. の下 **[!UICONTROL Content]** ドロップダウンで、「 **[!UICONTROL Adobe Experience Manager]** （内） **[!UICONTROL Content source]** フィールドに入力し、以前に作成した外部アカウントを **[!UICONTROL Adobe Experience Manager account]**.

次に、Adobe Experience Managerで統合を設定する必要があります。

## Adobe Experience Managerでの設定 {#config-aem}

Adobe Campaign StandardでAdobe Experience Managerを設定するには、次の手順に従う必要があります。

1. 最初に、Adobe Experience Managerオーサリングインスタンスとパブリッシュインスタンスの間のレプリケーションを設定する必要があります。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager)を参照してください。

1. 次に、専用の **[!UICONTROL Cloud Service]**. [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign)を参照してください。

1. 次に、オーサーインスタンス上のAdobe Experience Managerで Externalizer を設定する必要があります。 [こちら](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer)を参照してください。
