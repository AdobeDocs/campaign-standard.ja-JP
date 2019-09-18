---
title: ワークフローセグメントに基づくレポートの作成
seo-title: ワークフローセグメントに基づくレポートの作成
description: ワークフローセグメントに基づくレポートの作成
seo-description: レポート内のワークフローのセグメントに応じて、配信の成功を確認する方法を説明します。
page-status-flag: 未活性化の
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: 良い
products: SG_CAMPAIGN/STANDARD
audience: 報告
content-type: 参照
topic-tags: レポートのカスタマイズ
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# ワークフローセグメントに基づくレポートの作成{#creating-a-report-workflow-segment}

ワークフローを作成し、個人を別のターゲット対象ユーザーにフィルタリングした後、このターゲットワークフローで定義されたセグメントに基づいて、マーケティングキャンペーンの効率を測定できます。
レポート内の次のセグメントをターゲットにする手順は、次のとおりです。

* [ステップ1:プロファイルのカスタムリソースをセグメントで更新](#step-1--update-profiles-custom-resource-segments)
* [手順2:セグメントを含むワークフローを作成する](#step-2--create-a-workflow-segments)
* [ステップ3:セグメントをフィルタする動的レポートを作成する](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>これらのデータの収集を開始するには、動的レポート使用許諾契約に同意する必要があります。
>本契約の詳細については、このページを参照してく [ださい](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## ステップ1:プロファイルのカスタムリソースをセグメントで更新{#step-1--update-profiles-custom-resource-segments}

セグメントコードに関するレポートを作成する前に、セグメントコードを保存す **[!UICONTROL Profiles]** るためにカスタムリソースを更新する必要があります。

1. 詳細メニューから、Adobe Campaignロゴを使用して、 &gt; **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]**&gt;を選択し、リソースを選択し **[!UICONTROL Profile (profile)]** ます。
1. タブのメニ **[!UICONTROL Sending logs extension]** ューで、ターゲッ **[!UICONTROL Data structure]** トワークフローからセグメントコードを保存し、動 **[!UICONTROL Add segment code]** 的レポートに送信できるようにするかどうかをチェックします。

   レポ **[!UICONTROL Segment code]** ートのディメンションセク **[!UICONTROL Profile]** ションでを使用できます。

   ![](assets/report_segment_4.png)

1. カスタムリソースを保存します。

1. 次に、カスタムリソースを発行する必要があります。
詳細メニューから、 &gt; **[!UICONTROL Administration]** &gt;を選 **[!UICONTROL Development]** 択します **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 準備が完 **[!UICONTROL Prepare publication]** 了したら、をクリックし、ボタンをクリック **[!UICONTROL Publish]** します。 カスタムリソースの詳細については、このページを参照してく [ださい](../../developing/using/updating-the-database-structure.md)。

セグメントコードを使用してワークフローの作成を開始できます。

でセグメントコードを有効にすると、セグメントコードがすぐに収集されます **[!UICONTROL Sending logs extension]**。

## 手順2:セグメントを含むワークフローを作成する {#step-2--create-a-workflow-segments}

>[!NOTE]
>電子メール配信の入力遷移が空の場合は、前の遷移のセグメントコードが既定で追加されます。

最初に、ターゲットの母集団が異なるワークフローを作成する必要があります。 ここでは、対象ユーザーの年齢に応じてパーソナライズされるEメールを送信します。1つは20 ~ 30年の古いプロファイル用、もう1つは30 ~ 40年のプロファイル用です。

1. ワークフローを作成します。 ワークフローの作成方法の詳細については、このページを参照してく [ださい](../../automating/using/building-a-workflow.md)。

1. アクティビティを **[!UICONTROL Query]** パレットからドラッグし、ワークスペースにドロップして追加します。

1. 20歳から40歳までの標的の分布は、後により多くの標的の集団に分類される。

   ![](assets/report_segment_1.png)

1. クエリ結果を2つ **[!UICONTROL Segmentation]** のターゲット集団に分割するアクティビティを追加します。 セグメンテーションの詳細については、このページを参照して [ください](../../automating/using/targeting-data.md#segmenting-data)。

1. アクティビティをダブ **[!UICONTROL Segmentation]** ルクリックして構成します。 をクリックして、最初のセグメントを編集しま **[!UICONTROL Edit properties]**&#x200B;す。

   ![](assets/report_segment_7.png)

1. 20 ~ 30歳の間のプロファイルを照会し、完了したらク **[!UICONTROL Confirm]** リックします。

   ![](assets/report_segment_8.png)

1. クリック **[!UICONTROL Add an element]** して2番目のセグメントを作成し、上記の手順に従って30~40歳の間のプロファイルをターゲットに設定します。

1. 動的レポート **[!UICONTROL Segment code]** を通じて渡される各母集団のを編集します。

   >[!NOTE]
   >この手順は必須です。そうでない場合は、レポートするセグメントを理解できません。

   ![](assets/report_segment_9.png)

1. セグメントの後にアクティビティをド **[!UICONTROL Email delivery]** ラッグ·アンド·ドロップします。

   ![](assets/report_segment_3.png)

1. ターゲット·ポピュレーションに応じて、搬送をパーソナライズします。 電子メールの作成の詳細については、このページを参照して [ください](../../designing/using/overview.md)。

1. ワークフローを保存します。

1. ワークフ **[!UICONTROL Start]** ローの準備ができたら、をクリックします。

これで、レポートにアクセスしてセグメントコードを追跡できます。

## ステップ3:セグメントをフィルタする動的レポートを作成する {#step-3--create-a-dynamic-report-filter-segments}

ワークフローと共に搬送を送信した後、ワークフローのセグメント·コードを使用してレポートを分解できます。

1. タブから **[!UICONTROL Reports]** 、最新のレポートを選択するか、ボタンをクリックして、最 **[!UICONTROL Create new project]** 初から開始します。

   ![](assets/custom_profile_18.png)
1. フリーフォーム表に寸法 **[!UICONTROL Delivery]** をドラッグアンドドロップします。

   ![](assets/report_segment_5.png)

1. データのフィルタを開始するには、およびメトリックなど、異なるメトリッ **[!UICONTROL Open]** クをテ **[!UICONTROL Click]** ーブルにドラッグ·アンド·ドロップします。
1. カテゴリ **[!UICONTROL Dimensions]** で、次元をクリックし、次 **[!UICONTROL Profile]****[!UICONTROL Segment code]** にワークフローの配信に対して次元をドラッグ·アンド·ドロップして、ターゲットの人口に応じて電子メール配信の成功を測定します。

   ![](assets/report_segment_6.png)

1. 必要に応じて、ワークスペース内でビジュアル化をドラッグ&amp;ドロップします。

   ![](assets/report_segment_10.png)
