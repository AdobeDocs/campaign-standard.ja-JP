---
title: Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ
description: Experience Platform 属性を使用してキャンペーンをパーソナライズするAdobeについて説明します。
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
>Audience Destinations サービスは現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。
>
>**プッシュ** および **アプリ内** Adobe Experience Platformのコンテキストデータを使用したパーソナライゼーションでは、チャネルはまだ使用できません。

ワークフローが [Adobe Experience Platformオーディエンス](../../integrating/using/aep-about-audience-destinations-service.md)に設定すると、エクスペリエンスデータモデル (XDM) にのみ存在するプロファイル属性を使用してメッセージをパーソナライズできます。

これをおこなうには、次の属性を **[!UICONTROL Read audience]** アクティビティ：

1. を開きます。 **[!UICONTROL Read audience]** アクティビティ。 内 **[!UICONTROL Additional data]** タブで、 **[!UICONTROL Create element]** 」ボタンをクリックします。

   なお、 **[!UICONTROL Additional data]** 「 」タブは、Adobe Experience Platformオーディエンスが選択された場合にのみ使用できます。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >この機能では、配列とマップのデータタイプはサポートされていません。 また、和集合スキーマのデータのみがピッカーに表示されます。

1. リストから目的の XDM フィールドを選択し、「 **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 次をクリック： **[!UICONTROL Add]** ボタンをクリックして、追加データのリストに追加します。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. ワークフローに追加するすべての XDM フィールドに対して、これらの手順を繰り返します。

   >[!NOTE]
   >
   >1 つに追加できる XDM フィールドは最大 20 個です **[!UICONTROL Read audience]** アクティビティ。

1. すべてのフィールドを追加したら、 **[!UICONTROL Confirm]** ボタンをクリックして、変更を保存します。 これで、配信をパーソナライズできるようになります。

配信を作成およびパーソナライズする方法について詳しくは、次のCampaign Standardドキュメントを参照してください。

* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
* [配信のパーソナライゼーション](../../designing/using/personalization.md)
