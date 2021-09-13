---
title: Adobe Experience Platform オーディエンスの管理
description: Campaign Standard内でAdobe Experience Platformを管理する方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---

# Adobe Experience Platform オーディエンスの管理 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Serviceは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

## Adobe Experience Platformオーディエンスへのアクセス

Adobe Experience Platformセグメントビルダーにアクセスするには、Campaign Standardのホームページ（またはヘッダーの&#x200B;**[!UICONTROL Audiences]**&#x200B;リンク）の&#x200B;**[!UICONTROL Audiences]**&#x200B;カードに移動し、**[!UICONTROL Adobe Experience Platform]**&#x200B;環境を選択します。

![](assets/aep_audiences_access.png)

最初にAdobe Experience Platformのセグメントリストページが表示されます。このページでは、既に存在するAdobe Experience Platformのセグメントにアクセスして、さらに編集することができます。

目的のAdobe Experience Platformセグメントを見つけるのに役立つ検索バーとフィルターが用意されています。

![](assets/aep_audiences_list.png)

## Adobe Experience Platformオーディエンスの作成

Adobe Experience PlatformオーディエンスをCampaign Standardで直接作成するには、次の手順に従います。

1. Adobe Experience Platformのセグメントリストページで、右隅にある「**[!UICONTROL New audience]**」ボタンをクリックします。

   ![](assets/aep_audiences_creation_create.png)

1. セグメントビルダーがワークスペースに表示されます。 これにより、Adobe Experience Platformのデータを使用してセグメントを構築し、最終的にオーディエンスの作成に使用できます。

1. 右側のウィンドウでセグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. セグメントを正しく作成するには、このセグメントのマーケティング目的に合う&#x200B;**結合ポリシー**&#x200B;を選択する必要があります。

   設定ペインで、プラットフォームのデフォルトの結合ポリシーが選択されます。 結合ポリシーの詳細については、『[セグメントビルダーユーザガイド](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)』の該当する節を参照してください。

   ![](assets/aep_audiences_mergepolicy.png)

1. オーディエンスで取得するプロファイルを識別するルールを定義します。

   これをおこなうには、目的の属性やイベントを左側のパネルからワークスペースにドラッグし、対応するルールを定義した後、「**[!UICONTROL Create segment]**」ボタンをクリックしてセグメントを保存します（[セグメントビルダーの使用](../../integrating/using/aep-using-segment-builder.md)を参照）。

   ![](assets/aep_audiences_creation_query.png)

これで、オーディエンスをアクティブ化する準備が整い、キャンペーンのターゲットとして使用できます([Adobe Experience Platformオーディエンスのターゲット設定](../../integrating/using/aep-targeting-audiences.md)を参照)。

## オーディエンスの編集

オーディエンスを編集するには、オーディエンスを開き、必要に応じてセグメントビルダーインターフェイス内でルールを変更します（[セグメントビルダーの使用](../../integrating/using/aep-using-segment-builder.md)を参照）。

変更が完了したら、「**[!UICONTROL Save segment]**」ボタンをクリックしてオーディエンスを更新します。

![](assets/aep_audiences_editing.png)
