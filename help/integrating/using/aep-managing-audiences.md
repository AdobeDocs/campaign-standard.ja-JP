---
title: Adobe Experience Platform オーディエンスの管理
description: Campaign Standard内でAdobe Experience Platformを管理する方法を学ぶ。
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
>Audience Destinations Service は現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

## Adobe Experience Platformオーディエンスへのアクセス

Adobe Experience Platformセグメントビルダーにアクセスするには、 **[!UICONTROL Audiences]** Campaign Standardのホームページ ( または **[!UICONTROL Audiences]** リンクをクリック )、 **[!UICONTROL Adobe Experience Platform]** 環境。

![](assets/aep_audiences_access.png)

最初に、Adobe Experience Platformのセグメントリストページが表示されます。このページでは、既に存在するAdobe Experience Platformセグメントにアクセスして、さらに編集することができます。

目的のAdobe Experience Platformセグメントを見つけるのに役立つ検索バーとフィルターが使用できます。

![](assets/aep_audiences_list.png)

## Adobe Experience Platformオーディエンスの作成

Campaign Standardで直接Adobe Experience Platformオーディエンスを作成するには、次の手順に従います。

1. Adobe Experience Platformのセグメントリストページで、 **[!UICONTROL New audience]** ボタンをクリックします。

   ![](assets/aep_audiences_creation_create.png)

1. セグメントビルダーがワークスペースに表示されます。 これにより、Adobe Experience Platformのデータを使用してセグメントを構築し、最終的にオーディエンスの作成に使用できます。

1. 右側のウィンドウでセグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. セグメントを正常に作成するには、 **結合ポリシー** このセグメントのマーケティング目的に一致する

   設定ウィンドウで、Platform のデフォルトの結合ポリシーが選択されます。 結合ポリシーについて詳しくは、 [セグメントビルダーユーザーガイド](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. オーディエンスで取得するプロファイルを識別するルールを定義します。

   これをおこなうには、目的の属性やイベントを左側のパネルからワークスペースにドラッグし、対応するルールを定義してから、 **[!UICONTROL Create segment]** ボタンをクリックしてセグメントを保存します ( [セグメントビルダーの使用](../../integrating/using/aep-using-segment-builder.md)) をクリックします。

   ![](assets/aep_audiences_creation_query.png)

オーディエンスをアクティブ化する準備が整い、キャンペーンのターゲットとして使用できます ( [Adobe Experience Platformオーディエンスのターゲティング](../../integrating/using/aep-targeting-audiences.md)) をクリックします。

## オーディエンスの編集

オーディエンスを編集するには、オーディエンスを開き、必要に応じてセグメントビルダーインターフェイス内でルールを変更します ( [セグメントビルダーの使用](../../integrating/using/aep-using-segment-builder.md)) をクリックします。

変更が完了したら、 **[!UICONTROL Save segment]** 」ボタンをクリックして、オーディエンスを更新します。

![](assets/aep_audiences_editing.png)
