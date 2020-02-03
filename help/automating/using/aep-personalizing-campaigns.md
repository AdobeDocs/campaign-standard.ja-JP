---
title: Adobe Experience Platform属性を使用したキャンペーンのパーソナライズ
description: Adobe Experience Platform属性を使用してキャンペーンをパーソナライズする方法について説明します。
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
source-git-commit: 4b18f3b93394101eb569799bcfe362b4daf8f250

---


# Adobe Experience Platform属性を使用したキャンペーンのパーソナライズ {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。
>
>**Adobe Experience Platformのコ** ンテキストデータを使用したパーソナライゼーションでは **** 、プッシュチャネルとアプリ内チャネルはまだ利用できません。

ワークフローが [Adobe Experience Platformオーディエンスを使用して設定されると](../../audiences/using/aep-about-audience-destinations-service.md)、エクスペリエンスデータモデル(XDM)にのみ存在するプロファイル属性を使用してメッセージをパーソナライズできます。

これを行うには、次の属性をアクティビティに追加する必要があ **[!UICONTROL Read audience]**ります。

1. Open the **[!UICONTROL Read audience]**activity. タブで、ボ**[!UICONTROL Additional data]** タンをクリックし **[!UICONTROL Create element]**ます。

   このタブは、Adobe Experience Platform **[!UICONTROL Additional data]**オーディエンスが選択された後でのみ使用できます。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >この機能では、配列とマップのデータ型はサポートされていません。 また、ユニオンスキーマのデータのみがピッカーに表示されます。

1. リストから目的のXDMフィールドを選択し、をクリックしま **[!UICONTROL Confirm]**す。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. ボタンをク **[!UICONTROL Add]**リックして、追加データのリストに追加します。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. ワークフローに追加するすべてのXDMフィールドに対して、この手順を繰り返します。

   >[!NOTE]
   >
   >アクティビティに追加できるXDMフィールドの数は最大20個 **[!UICONTROL Read audience]**です。

1. すべてのフィールドを追加したら、ボタンをクリック **[!UICONTROL Confirm]**して変更を保存します。 これで、配信をパーソナライズできるようになります。

配信を作成およびパーソナライズする方法について詳しくは、キャンペーン標準のドキュメントを参照してください。

* [通信チャネルの検出](../../channels/using/discovering-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
* [配信のパーソナライゼーション](../../designing/using/personalization.md)
