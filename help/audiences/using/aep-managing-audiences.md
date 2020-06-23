---
title: Adobe Experience Platform オーディエンスの管理
description: Campaign Standard内のAdobe Experience Platformを管理する方法を説明します。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d487600fc4f3004804e93347b83edfe4e01cceeb
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---


# Adobe Experience Platform オーディエンスの管理 {#about-audiences}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 アドビカスタマーケアにお問い合わせの際は、アドビカスタマーケアにご連絡ください。

## Adobe Experience Platformオーディエンスへのアクセス

Adobe Experience Platformセグメントビルダーにアクセスするには、Campaign Standardホームページの **[!UICONTROL Audiences]** カード(またはヘッダーの **[!UICONTROL Audiences]** リンク)に移動し、 **[!UICONTROL Adobe Experience Platform]** 環境を選択します。

![](assets/aep_audiences_access.png)

最初に、Adobe Experience Platformセグメントのリストページが表示されます。このページでは、既存のAdobe Experience Platformセグメントにアクセスして、さらに編集できます。

目的のAdobe Experience Platformセグメントを見つけるのに役立つ検索バーとフィルターが用意されています。

![](assets/aep_audiences_list.png)

## Adobe Experience Platformオーディエンスの作成

Campaign Standardで直接Adobe Experience Platformオーディエンスを作成するには、次の手順に従います。

1. Adobe Experience Platformセグメントのリストページで、右隅にある **[!UICONTROL New audience]** ボタンをクリックします。

   ![](assets/aep_audiences_creation_create.png)

1. セグメントビルダーがワークスペースに表示されます。 オーディエンスの作成に使用されるAdobe Experience Platformのデータを使用してセグメントを作成できます。

1. 右側のパネルでセグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. セグメントを正しく作成するには、このセグメントのマーケティング目的に合った **マージポリシー** を選択する必要があります。

   設定ウィンドウで、Platformの既定の結合ポリシーが選択されます。 結合ポリシーの詳細については、『 [セグメントビルダーユーザーガイド』の専用の節を参照してください](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

   ![](assets/aep_audiences_mergepolicy.png)

1. オーディエンスで取得するプロファイルを識別するルールを定義します。

   これを行うには、目的の属性やイベントを左側のパネルからワークスペースにドラッグし、対応するルールを定義してから、 **[!UICONTROL Create segment]** ボタンをクリックしてセグメントを保存します(「セグメントビルダーの [使用](../../audiences/using/aep-using-segment-builder.md)」を参照)。

   ![](assets/aep_audiences_creation_query.png)

これでオーディエンスをアクティブ化する準備が整い、キャンペーンのターゲットとして使用できます( [Adobe Experience Platformオーディエンスのターゲット設定を参照](../../automating/using/aep-targeting-audiences.md))。

## オーディエンスの編集

オーディエンスを編集するには、画像を開き、セグメントビルダーインターフェイス内で必要に応じてルールを変更します(「セグメントビルダーの [使用](../../audiences/using/aep-using-segment-builder.md)」を参照)。

変更が完了したら、 **[!UICONTROL Save segment]** ボタンをクリックしてオーディエンスを更新します。

![](assets/aep_audiences_editing.png)
