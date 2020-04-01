---
title: Adobe Experience Platform オーディエンスの管理
description: Adobe Experience Platformを管理する方法をCampaign Standard。
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
source-git-commit: e1fa546313e8d543685ef30a072ae2d97c5bf236

---


# Adobe Experience Platform オーディエンスの管理 {#about-audiences}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米の場合のみベータ版）。 ご利用になりたい場合は、アドビカスタマーケアにお問い合わせください。

## Adobe Experience Platformへのアクセスオーディエンス

Adobe Experience Platformのセグメントビルダーにアクセスするには、Campaign Standardホームページのカード(またはヘッ **[!UICONTROL Audiences]** ダー内のリンク) **[!UICONTROL Audiences]** に移動し、環境を選択し **[!UICONTROL Adobe Experience Platform]** ます。

![](assets/aep_audiences_access.png)

最初に、Adobe Experience Platformのセグメントリストページが表示されます。このページでは、既存のAdobe Experience Platformのセグメントにアクセスして、さらに編集を行うことができます。

目的のAdobe Experience Platformセグメントを見つけるのに役立つ検索バーとフィルターを使用できます。

![](assets/aep_audiences_list.png)

## Adobe Experience Platformオーディエンス

Adobe Experience PlatformオーディエンスをCampaign Standardで直接作成するには、次の手順に従います。

1. Adobe Experience Platformのセグメントリストページで、右 **[!UICONTROL New audience]** 隅にあるボタンをクリックします。

   ![](assets/aep_audiences_creation_create.png)

1. これで、統合セグメントビルダーがワークスペースに表示されます。 Adobe Experience Platformのデータを使用してセグメントを作成し、最終的にこのデータを使用してセグメントを作成できます。このデータは、最終的にオーディエンスの作成に使用されます。

1. 右側のパネルでセグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. セグメントを正常に作成するには、このセグメントのマーケティング目 **的に一致する** 、マージポリシーを選択する必要があります。

   設定ウィンドウで、「プラットフォームのデフォルトの結合ポリシー」が選択されます。 結合ポリシーの詳細については、『セグメントビルダーユーザガイド』の専用の [節を参照してください](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

   ![](assets/aep_audiences_mergepolicy.png)

1. ユーザーのオーディエンスで取得するプロファイルを識別するルールを定義します。

   これを行うには、目的の属性やイベントを左側のパネルからワークスペースにドラッグし、対応するルールを定義し、ボタンをクリックしてセグメントを保存します(統合セグメントビル **[!UICONTROL Create segment]** ダーの使用 [](../../audiences/using/aep-using-segment-builder.md))。

   ![](assets/aep_audiences_creation_query.png)

これでオーディエンスをアクティベートする準備が整い、キャンペーンのターゲットとして使用できます(「Adobe Experience Platformのターゲ [ット設定」オーディエンスを参照](../../automating/using/aep-targeting-audiences.md))。

## 編集オーディエンス

オーディエンスを編集するには、そのセグメントを開き、必要に応じて統合セグメントビルダーインターフェイス内でルールを変更します( [統合セグメントビルダーの使用](../../audiences/using/aep-using-segment-builder.md))。

変更が完了したら、ボタンをクリックして **[!UICONTROL Save segment]** オーディエンスを更新します。

![](assets/aep_audiences_editing.png)
