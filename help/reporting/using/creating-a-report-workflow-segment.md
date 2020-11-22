---
solution: Campaign Standard
product: campaign
title: ワークフローセグメントに基づくレポートの作成
description: レポート内のワークフローのセグメントに応じて、配信の成功を確認する方法を説明します。
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 2%

---


# ワークフローセグメントに基づくレポートの作成{#creating-a-report-workflow-segment}

ワークフローを作成し、訪問者を様々なターゲットオーディエンスにフィルタリングした後、このターゲット設定ワークフローで定義されたセグメントに基づいて、マーケティングキャンペーンの効率を測定できます。
レポートにこれらのセグメントをターゲットするには：

* [手順1:セグメントを含むプロファイルのカスタムリソースの更新](#step-1--update-profiles-custom-resource-segments)
* [手順2:セグメントを使用したワークフローの作成](#step-2--create-a-workflow-segments)
* [手順3:セグメントをフィルターする動的レポートの作成](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>動的なレポートの使用許諾契約は、これらのデータを収集する開始に対して受け入れられる必要があります。
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## 手順1:セグメントを含むプロファイルのカスタムリソースの更新{#step-1--update-profiles-custom-resource-segments}

セグメントコードにレポートする前に、セグメントコードが保存されるように **[!UICONTROL Profiles]** カスタムリソースを更新する必要があります。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. タブの **[!UICONTROL Sending logs extension]** メニューで、ターゲットワークフローからセグメントコードをストレージし、動的レポートに送信できるようにするかどうかをチェック **[!UICONTROL Data structure]****[!UICONTROL Add segment code]** します。

   こ **[!UICONTROL Segment code]****[!UICONTROL Profile]** れで、レポートのディメンションセクションでこのレポートを使用できるようになります。

   ![](assets/report_segment_4.png)

1. カスタムリソースを保存します。

1. 次に、カスタムリソースを発行する必要があります。
詳細設定メニューで、/ **[!UICONTROL Administration]** /を選択し **[!UICONTROL Development]** ま **[!UICONTROL Publishing]**&#x200B;す。

   ![](assets/custom_profile_7.png)

1. 準備が完了 **[!UICONTROL Prepare publication]** したら、をクリックし、 **[!UICONTROL Publish]** ボタンをクリックします。 For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

これで、セグメントコードを使用したワークフローの作成開始を作成できます。

セグメントコードは、でセグメントコードを有効にするとすぐに収集され **[!UICONTROL Sending logs extension]**&#x200B;ます。

## 手順2:セグメントを使用したワークフローの作成 {#step-2--create-a-workflow-segments}

>[!NOTE]
>電子メール配信の入力トランジションが空の場合、デフォルトでは、前のトランジションのセグメントコードが追加されます。

まず、異なるターゲット母集団のワークフローを作成する必要があります。 ここでは、オーディエンスの年齢に応じてパーソナライズされた電子メールを送信します。1人は20歳から30歳のプロファイルの配信で、もう1人は30歳から40歳のプロファイルの人です。

1. ワークフローを作成します。 For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. Add a **[!UICONTROL Query]** activity by dragging it from the palette and dropping it in the workspace.

1. 20歳から40歳のターゲットプロファイルが、それらをより的を絞った集団に分類します。

   ![](assets/report_segment_1.png)

1. クエリ結果を2つのター追加ゲット母集団に分割するアクティビティ。 **[!UICONTROL Segmentation]** For more on segmentation, refer to this [page](../../automating/using/segmentation.md).

1. 重複が **[!UICONTROL Segmentation]** アクティビティをクリックして設定します。 最初のセグメントを編集するには、をクリックし **[!UICONTROL Edit properties]**&#x200B;ます。

   ![](assets/report_segment_7.png)

1. 20歳から30歳までのクエリプロファイルが完了したらクリック **[!UICONTROL Confirm]** します。

   ![](assets/report_segment_8.png)

1. 2つ目のセグメント **[!UICONTROL Add an element]** を作成するには、をクリックし、上記の手順に従って30 ～ 40才のプロファイルをターゲットします。

1. 動的レポート **[!UICONTROL Segment code]** を介して渡される各訪問者のを編集します。

   >[!NOTE]
   >この手順は必須です。必須でない場合は、どのセグメントをレポートするかを理解できません。

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. ターゲット母集団の種類に応じて配信をパーソナライズします。 For more on email creation, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. ワークフローを保存します。

1. ワークフロー **[!UICONTROL Start]** の準備が整ったら、をクリックします。

これで、レポートにアクセスしてセグメントコードを追跡できるようになります。

## 手順3:セグメントをフィルターする動的レポートの作成 {#step-3--create-a-dynamic-report-filter-segments}

ワークフローで配信を送信した後、ワークフローのセグメントコードを使用してレポートを分類できます。

1. タブからあらかじめ用意されているレポートを選択するか、 **[!UICONTROL Reports]** ボタンをクリックしてレポートを最初から開始 **[!UICONTROL Create new project]** します。

   ![](assets/custom_profile_18.png)
1. ディメンションをフリーフォームテーブルにドラッグ&amp;ドロップし **[!UICONTROL Delivery]** ます。

   ![](assets/report_segment_5.png)

1. 様々な指標（データのフィルタリングに使用する指標や指標）をテーブルにドラッグ&amp;ドロップ **[!UICONTROL Open]** し、 **[!UICONTROL Click]** 開始に適用します。
1. カテゴリ内で、ディメンションをクリックし、ワークフローの配信にディメンションをドラッグ&amp;ドロップして、ターゲットとなる訪問者に基づく電子メール配信の成功を測定します。 **[!UICONTROL Dimensions]****[!UICONTROL Profile]****[!UICONTROL Segment code]**

   ![](assets/report_segment_6.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_10.png)
