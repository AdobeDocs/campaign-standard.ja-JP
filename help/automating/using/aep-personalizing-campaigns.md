---
title: Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ
description: Adobe Experience Platform属性を使用してキャンペーンをパーソナライズする方法を説明します。
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 アドビカスタマーケアにお問い合わせの際は、アドビカスタマーケアにご連絡ください。
>
>**Adobe Experience** Platformのコンテキストデータを使用したパーソナライゼーションでは **、プッシュ** チャネルとアプリ内プラットフォームはまだ使用できません。

ワークフローが [Adobe Experience Platformオーディエンスを使用して設定されたら](../../audiences/using/aep-about-audience-destinations-service.md)、Experience Data Model(XDM)専用のプロファイル属性を使用してメッセージをパーソナライズできます。

これを行うには、次の属性を **[!UICONTROL Read audience]** アクティビティに追加する必要があります。

1. Open the **[!UICONTROL Read audience]** activity. タブで、 **[!UICONTROL Additional data]** ボタンをクリックし **[!UICONTROL Create element]** ます。

   この **[!UICONTROL Additional data]** タブは、Adobe Experience Platformオーディエンスを選択した後でのみ使用できます。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >この機能では、配列とマップのデータ型はサポートされていません。 また、和集合スキーマのデータのみがピッカーに表示されます。

1. リストから目的のXDMフィールドを選択し、をクリックし **[!UICONTROL Confirm]**&#x200B;ます。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. ボタンをクリックし **[!UICONTROL Add]** て、追加データのリストに追加します。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. ワークフローに追加するすべてのXDMフィールドに対して、この手順を繰り返します。

   >[!NOTE]
   >
   >1つの **[!UICONTROL Read audience]** アクティビティに追加できるXDMフィールドの数は最大20個です。

1. すべてのフィールドを追加したら、 **[!UICONTROL Confirm]** ボタンをクリックして変更を保存します。 これで、配信をパーソナライズできるようになります。

配信を作成およびパーソナライズする方法について詳しくは、Campaign Standardのドキュメントを参照してください。

* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
* [配信のパーソナライゼーション](../../designing/using/personalization.md)
