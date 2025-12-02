---
title: Adobe Experience Platform オーディエンスの管理
description: Campaign Standard内でAdobe Experience Platformを管理する方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 2%

---

# Adobe Experience Platform オーディエンスの管理 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations サービスは現在ベータ版です。予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様を Azure でホストする必要があります（現在は北米向けのベータ版のみ）。 へのアクセスを希望する場合は、Adobe カスタマーケアにお問い合わせください。

## Adobe Experience Platform オーディエンスへのアクセス

Adobe Experience Platform セグメントビルダーにアクセスするには、Campaign Standard ホームページの **[!UICONTROL Audiences]** カード（またはヘッダー内の **[!UICONTROL Audiences]** リンク）に移動して、**[!UICONTROL Adobe Experience Platform]** 環境を選択します。

![](assets/aep_audiences_access.png)

最初にAdobe Experience Platform セグメントリストページに移動します。このページから既存のAdobe Experience Platform セグメントにアクセスして、さらに編集することができます。

検索バーとフィルターを使用すると、目的のAdobe Experience Platform セグメントを見つけるのに役立ちます。

![](assets/aep_audiences_list.png)

## Adobe Experience Platform オーディエンスの作成

Adobe Experience Platform オーディエンスをCampaign Standardで直接作成するには、次の手順に従います。

1. Adobe Experience Platform セグメントリストページで、右隅にある「**[!UICONTROL New audience]**」ボタンをクリックします。

   ![](assets/aep_audiences_creation_create.png)

1. セグメントビルダーがワークスペースに表示されます。 これにより、Adobe Experience Platformのデータを使用してセグメントを作成し、最終的にオーディエンスの作成に使用できます。

1. 右側のペインでセグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. セグメントを正常に作成するには、このセグメントのマーケティング目的に一致する **結合ポリシー** を選択する必要があります。

   設定ペインで、Platform のデフォルトの結合ポリシーが選択されます。 結合ポリシーについて詳しくは、『 [&#x200B; セグメントビルダーユーザーガイド &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja) の該当する節を参照してください。

   ![](assets/aep_audiences_mergepolicy.png)

1. オーディエンスで取得するプロファイルを識別するルールを定義します。

   これを行うには、目的の属性やイベントを左側のペインからワークスペースにドラッグし、対応するルールを定義して、「**[!UICONTROL Create segment]**」ボタンをクリックしてセグメントを保存します（[&#x200B; セグメントビルダーの使用 &#x200B;](../../integrating/using/aep-using-segment-builder.md) を参照）。

   ![](assets/aep_audiences_creation_query.png)

これでオーディエンスをアクティブ化する準備が整い、キャンペーンのターゲットとして使用できるようになります（[Adobe Experience Platform オーディエンスのターゲティング &#x200B;](../../integrating/using/aep-targeting-audiences.md) を参照）。

## オーディエンスの編集

オーディエンスを編集するには、オーディエンスを開き、セグメントビルダーインターフェイス内で必要に応じてルールを変更します（[&#x200B; セグメントビルダーの使用 &#x200B;](../../integrating/using/aep-using-segment-builder.md) を参照）。

変更が完了したら、「**[!UICONTROL Save segment]**」ボタンをクリックしてオーディエンスを更新します。

![](assets/aep_audiences_editing.png)
