---
title: Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ
description: Experience Platform属性を使用してキャンペーンをパーソナライズするAdobeについて説明します。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---

# Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。
>
>**** プッシュチャネルとア **プ** リ内チャネルは、Adobe Experience Platformのコンテキストデータを使用したパーソナライゼーションには、まだ使用できません。

ワークフローに[Adobe Experience Platformオーディエンス](../../integrating/using/aep-about-audience-destinations-service.md)が設定されたら、エクスペリエンスデータモデル(XDM)のみに存在するプロファイル属性を使用してメッセージをパーソナライズできます。

これをおこなうには、次の属性を&#x200B;**[!UICONTROL Read audience]**&#x200B;アクティビティに追加する必要があります。

1. **[!UICONTROL Read audience]**&#x200B;アクティビティを開きます。 「**[!UICONTROL Additional data]**」タブで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   「 **[!UICONTROL Additional data]** 」タブは、Adobe Experience Platformオーディエンスが選択された後でのみ使用できます。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >この機能では、配列とマップのデータ型はサポートされていません。 また、和集合スキーマのデータのみがピッカーに表示されます。

1. リストから目的のXDMフィールドを選択し、「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. **[!UICONTROL Add]**&#x200B;ボタンをクリックして、追加データのリストに追加します。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. ワークフローに追加するすべてのXDMフィールドに対して、これらの手順を繰り返します。

   >[!NOTE]
   >
   >1つの&#x200B;**[!UICONTROL Read audience]**&#x200B;アクティビティに追加できるXDMフィールドは最大20個です。

1. すべてのフィールドを追加したら、「**[!UICONTROL Confirm]**」ボタンをクリックして変更を保存します。 これで、配信をパーソナライズできるようになります。

配信の作成とパーソナライズの方法について詳しくは、次のCampaign Standardドキュメントを参照してください。

* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
* [配信のパーソナライゼーション](../../designing/using/personalization.md)
