---
title: Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ
description: Adobe Experience Platform 属性を使用してキャンペーンをパーソナライズする方法について説明します。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 6%

---

# Adobe Experience Platform 属性を使用したキャンペーンのパーソナライズ {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Audience Destinations サービスは現在ベータ版です。予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様を Azure でホストする必要があります（現在は北米向けのベータ版のみ）。 へのアクセスを希望する場合は、Adobe カスタマーケアにお問い合わせください。
>
>**プッシュ** チャネルと **アプリ内** チャネルは、Adobe Experience Platformのコンテキストデータを使用したパーソナライゼーションではまだ使用できません。

ワークフローに [Adobe Experience Platform オーディエンス ](../../integrating/using/aep-about-audience-destinations-service.md) が設定されたら、エクスペリエンスデータモデル（XDM）にのみ存在するプロファイル属性を使用してメッセージをパーソナライズできます。

これを行うには、次の属性を **[!UICONTROL Read audience]** アクティビティに追加する必要があります。

1. **[!UICONTROL Read audience]** アクティビティを開きます。 「**[!UICONTROL Additional data]**」タブで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   「**[!UICONTROL Additional data]**」タブは、Adobe Experience Platform オーディエンスが選択された後でのみ使用できます。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >配列およびマップのデータタイプは、この機能ではサポートされていません。 また、結合スキーマのデータのみがピッカーに表示されます。

1. リストから目的の XDM フィールドを選択し、「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 「**[!UICONTROL Add]**」ボタンをクリックして、追加データのリストに追加します。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. ワークフローに追加するすべての XDM フィールドに対して、これらの手順を繰り返します。

   >[!NOTE]
   >
   >1 つの **[!UICONTROL Read audience]** アクティビティに追加できる XDM フィールドは最大 20 個です。

1. すべてのフィールドを追加したら、「**[!UICONTROL Confirm]**」ボタンをクリックして変更を保存します。 これで、配信をパーソナライズできるようになります。

配信の作成およびパーソナライズ方法について詳しくは、次のCampaign Standard ドキュメントを参照してください。

* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
* [配信のパーソナライゼーション](../../designing/using/personalization.md)
