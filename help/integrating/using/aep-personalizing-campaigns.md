---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ
description: Adobeエクスペリエンスプラットフォーム属性を使用してキャンペーンをパーソナライズする方法を説明します。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---


# Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。
>
>**** Pushチャネルと **In-** Appchannelsは、Adobe Experience Platformのコンテキストデータを使用したパーソナライゼーションではまだ利用できません。

[Adobe Experience Platformオーディエンス](../../integrating/using/aep-about-audience-destinations-service.md)を使用してワークフローを設定すると、エクスペリエンスデータモデル(XDM)専用のプロファイル属性を使用してメッセージをパーソナライズできます。

これを行うには、次の属性を&#x200B;**[!UICONTROL Read audience]**&#x200B;アクティビティに追加する必要があります。

1. **[!UICONTROL Read audience]**&#x200B;アクティビティを開きます。 「**[!UICONTROL Additional data]**」タブで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   「**[!UICONTROL Additional data]**」タブは、Adobe Experience Platformオーディエンスを選択した後にのみ使用できます。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >この機能では、配列とマップのデータ型はサポートされていません。 また、和集合スキーマのデータのみがピッカーに表示されます。

1. リストから目的のXDMフィールドを選択し、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. **[!UICONTROL Add]**&#x200B;ボタンをクリックして、追加データのリストに追加します。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. ワークフローに追加するすべてのXDMフィールドに対して、この手順を繰り返します。

   >[!NOTE]
   >
   >**[!UICONTROL Read audience]**&#x200B;アクティビティには、最大20個のXDMフィールドを追加できます。

1. すべてのフィールドを追加したら、**[!UICONTROL Confirm]**&#x200B;ボタンをクリックして変更を保存します。 これで、配信をパーソナライズできるようになります。

配信を作成およびパーソナライズする方法について詳しくは、Campaign Standardのドキュメントを参照してください。

* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
* [配信のパーソナライゼーション](../../designing/using/personalization.md)
