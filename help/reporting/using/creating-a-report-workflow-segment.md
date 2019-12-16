---
title: ワークフローセグメントに基づくレポートの作成
description: レポート内のワークフローのセグメントに応じて配信の成功を確認する方法について説明します。
page-status-flag: never-activated
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: customizing-reports
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# ワークフローセグメントに基づくレポートの作成{#creating-a-report-workflow-segment}

ワークフローを作成し、訪問者を様々なターゲットオーディエンスにフィルタリングした後、このターゲット設定ワークフローで定義されたセグメントに基づいて、マーケティングキャンペーンの効率を測定できます。
レポートでこれらのセグメントをターゲットにするには：

* [手順1:セグメントを使用したプロファイルカスタムリソースの更新](#step-1--update-profiles-custom-resource-segments)
* [手順2:セグメントを使用したワークフローの作成](#step-2--create-a-workflow-segments)
* [手順3:セグメントをフィルタリングする動的レポートの作成](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>これらのデータの収集を開始するには、動的レポートの使用許諾契約に同意する必要があります。
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## 手順1:セグメントを使用したプロファイルカスタムリソースの更新{#step-1--update-profiles-custom-resource-segments}

セグメントコードをレポートする前に、セグメントコードを保存するた **[!UICONTROL Profiles]** めのカスタムリソースを更新する必要があります。

1. アドバンスメニューで、Adobe Campaignロゴを使用して、// **[!UICONTROL Administration]** を選択 **[!UICONTROL Development]** し、 **[!UICONTROL Custom resources]**&#x200B;リソースを選択し **[!UICONTROL Profile (profile)]** ます。
1. タブのメニ **[!UICONTROL Sending logs extension]** ューで、ターゲッ **[!UICONTROL Data structure]** ト設定ワークフ **[!UICONTROL Add segment code]** ローのセグメントコードを保存し、動的レポートに送信できるようにします。

   レポー **[!UICONTROL Segment code]** トのディメンションセクションで **[!UICONTROL Profile]** が使用できるようになります。

   ![](assets/report_segment_4.png)

1. カスタムリソースを保存します。

1. 次に、カスタムリソースを発行する必要があります。
アドバンスメニューで、// **[!UICONTROL Administration]** を選 **[!UICONTROL Development]** 択しま **[!UICONTROL Publishing]**&#x200B;す。

   ![](assets/custom_profile_7.png)

1. 準備が **[!UICONTROL Prepare publication]** 完了したら、をクリックし、ボタンをクリック **[!UICONTROL Publish]** します。 For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

これで、セグメントコードを使用したワークフローの作成を開始できます。

セグメントコードは、でセグメントコードを有効にするとすぐに収集されま **[!UICONTROL Sending logs extension]**&#x200B;す。

## 手順2:セグメントを使用したワークフローの作成 {#step-2--create-a-workflow-segments}

>[!NOTE]
>電子メール配信の入力の移行が空の場合、デフォルトでは前の移行のセグメントコードが追加されます。

まず、異なるターゲット母集団を持つワークフローを作成する必要があります。 ここでは、閲覧者の年齢に応じてパーソナライズされる電子メールを送信します。1回は20～30歳のプロフィールで、もう1回は30～40歳のプロファイルです。

1. ワークフローを作成します。 ワークフローの作成方法の詳細については、このページを参照してく [ださい](../../automating/using/building-a-workflow.md)。

1. アクティビティ **[!UICONTROL Query]** を追加するには、パレットからアクティビティをドラッグし、ワークスペースにドロップします。

1. 20 ～ 40歳のプロファイルをターゲットにし、後でより多くのターゲットを定めた訪問者に分類します。

   ![](assets/report_segment_1.png)

1. クエリー結果を2 **[!UICONTROL Segmentation]** つのターゲット設定された訪問者に分割するアクティビティを追加します。 For more on segmentation, refer to this [page](../../automating/using/targeting-data.md#segmenting-data).

1. アクティビティをダブ **[!UICONTROL Segmentation]** ルクリックして設定します。 最初のセグメントをクリックして編集しま **[!UICONTROL Edit properties]**&#x200B;す。

   ![](assets/report_segment_7.png)

1. 20 ～ 30才のプロファイルをクエリし、完了したらク **[!UICONTROL Confirm]** リックします。

   ![](assets/report_segment_8.png)

1. 2番目 **[!UICONTROL Add an element]** のセグメントを作成し、上記の手順に従って、30歳から40歳の間のプロファイルをターゲットに設定する場合にクリックします。

1. 動的レポ **[!UICONTROL Segment code]** ートで渡される各訪問者のを編集します。

   >[!NOTE]
   >この手順は必須です。必須でない場合は、レポートするセグメントを把握できなくなります。

   ![](assets/report_segment_9.png)

1. セグメントの後にアクティビティ **[!UICONTROL Email delivery]** をドラッグ&amp;ドロップします。

   ![](assets/report_segment_3.png)

1. 様々なターゲット訪問者に応じて配信をパーソナライズします。 For more on email creation, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. ワークフローを保存します。

1. ワークフロー **[!UICONTROL Start]** の準備が整ったら、をクリックします。

これで、レポートにアクセスしてセグメントコードを追跡できます。

## 手順3:セグメントをフィルタリングする動的レポートの作成 {#step-3--create-a-dynamic-report-filter-segments}

ワークフローで配信を送信した後、ワークフローのセグメントコードを使用してレポートを分類できます。

1. タブから **[!UICONTROL Reports]** あらかじめ用意されているレポートを選択するか、ボタンをクリックして **[!UICONTROL Create new project]** 最初からレポートを開始します。

   ![](assets/custom_profile_18.png)
1. フリーフォームテーブルにディメ **[!UICONTROL Delivery]** ンションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_5.png)

1. 表に様々な指標（指標や指標など）をドラッグ&amp;ドロップして、デ **[!UICONTROL Open]** ータのフ **[!UICONTROL Click]** ィルタリングを開始します。
1. カテゴリ **[!UICONTROL Dimensions]** 内でディメンションをク **[!UICONTROL Profile]** リックし、ワークフローの配信にディメンションをドラッグ&amp;ドロ **[!UICONTROL Segment code]** ップして、ターゲット訪問者に応じた電子メール配信の成功を測定します。

   ![](assets/report_segment_6.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_10.png)
