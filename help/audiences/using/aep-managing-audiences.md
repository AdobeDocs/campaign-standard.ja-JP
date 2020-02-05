---
title: Adobe Experience Platformオーディエンスの管理
description: Campaign Standard内でAdobe Experience Platformを管理する方法を説明します。
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
source-git-commit: 2ef524d1d276abb1ff0a7149462452cafe8e5cd3

---


# Adobe Experience Platformオーディエンスの管理 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Serviceは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

## Adobe Experience Platformオーディエンスへのアクセス

Adobe Experience Platformのセグメントビルダーにアクセスするには、Campaign Standardのホームページ（またはヘッダーのリンク）のカ **[!UICONTROL Audiences]**ードに移動し、環境を選択し**[!UICONTROL Audiences]****[!UICONTROL Adobe Experience Platform]**ます。

![](assets/aep_audiences_access.png)

最初に、Adobe Experience Platformのセグメントリストページが表示されます。このページで、既存のAdobe Experience Platformセグメントにアクセスして、さらに編集できます。

目的のAdobe Experience Platformセグメントを見つけるのに役立つ検索バーとフィルターが用意されています。

![](assets/aep_audiences_list.png)

## Adobe Experience Platformオーディエンスの作成

Campaign StandardでAdobe Experience Platformオーディエンスを直接作成するには、次の手順に従います。

1. Adobe Experience Platformのセグメントリストページで、右隅にあ **[!UICONTROL New audience]**るボタンをクリックします。

   ![](assets/aep_audiences_creation_create.png)

1. これで、統合セグメントビルダーがワークスペースに表示されます。 これにより、最終的にオーディエンスの作成に使用されるAdobe Experience Platformのデータを使用してセグメントを作成できます。

1. 右側のパネルでセグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. セグメントを正しく作成するには、このセグメントのマーケティング **目的に一致する** 、マージポリシーを選択する必要があります。

   設定ウィンドウで、「プラットフォームのデフォルトの結合ポリシー」が選択されます。 結合ポリシーの詳細については、『セグメントビルダーユーザーガイド』の専用 [の節を参照してください](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

   ![](assets/aep_audiences_mergepolicy.png)

1. オーディエンスで取得するプロファイルを識別するルールを定義します。

   これを行うには、左側のパネルから目的の属性やイベントをワークスペースにドラッグし、対応するルールを定義し、ボタンをクリックしてセグメントを保存します(「Unified Segment Builderの使用 **[!UICONTROL Create segment]**[](../../audiences/using/aep-using-segment-builder.md)」を参照)。

   ![](assets/aep_audiences_creation_query.png)

これでオーディエンスをアクティブ化する準備が整い、キャンペーンのターゲットとして使用できます(「Adobe Experience Platformオーディエ [ンスのターゲット設定](../../automating/using/aep-targeting-audiences.md)」を参照)。

## オーディエンスの編集

オーディエンスを編集するには、オーディエンスを開き、必要に応じて統合セグメントビルダーインターフェイス内でル [ールを変更します(「統合セグメントビルダーの使用](../../audiences/using/aep-using-segment-builder.md)」を参照)。

変更が完了したら、ボタンをクリックしてオ **[!UICONTROL Save segment]**ーディエンスを更新します。

![](assets/aep_audiences_editing.png)
