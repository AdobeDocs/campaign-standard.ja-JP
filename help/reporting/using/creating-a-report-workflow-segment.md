---
title: ワークフローセグメントに基づくレポートの作成
description: レポート内のワークフローのセグメントに応じて、配信の成功を確認する方法を説明します。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# ワークフローセグメントに基づくレポートの作成{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**は、E メールおよび SMS 配信のみをターゲットにできます。

ワークフローを作成し、母集団を異なるターゲットオーディエンスにフィルタリングした後、このターゲティングワークフローで定義されたセグメントに基づいて、マーケティングキャンペーンの効率を測定できます。
レポートでこれらのセグメントをターゲットにするには：

* [手順 1:プロファイルのカスタムリソースをセグメントで更新](#step-1--update-profiles-custom-resource-segments)
* [手順 2:セグメントを含むワークフローの作成](#step-2--create-a-workflow-segments)
* [手順 3:セグメントをフィルタリングするための動的レポートの作成](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>これらのデータの収集を開始するには、動的レポート使用契約への同意が必要です。
>
>この契約について詳しくは、こちらを参照してください。 [ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## 手順 1:プロファイルのカスタムリソースをセグメントで更新{#step-1--update-profiles-custom-resource-segments}

セグメントコードのレポートを作成する前に、 **[!UICONTROL Profiles]** 保存するセグメントコードのカスタムリソース。

1. 詳細設定メニューのAdobe Campaignロゴから、を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**&#x200B;を選択し、 **[!UICONTROL Profile (profile)]** リソース。
1. 内 **[!UICONTROL Sending logs extension]** メニュー **[!UICONTROL Data structure]** タブ、チェック **[!UICONTROL Add segment code]** ：セグメントコードをターゲティングワークフローから保存し、動的レポートに送信できるようにします。

   この **[!UICONTROL Segment code]** が **[!UICONTROL Profile]** ディメンションセクションで使用できます。

   ![](assets/report_segment_4.png)

1. カスタムリソースを保存します。

1. 次に、カスタムリソースを公開する必要があります。
詳細設定メニューから、 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. クリック **[!UICONTROL Prepare publication]** 準備が完了したら、 **[!UICONTROL Publish]** 」ボタンをクリックします。 カスタムリソースについて詳しくは、 [ページ](../../developing/using/updating-the-database-structure.md).

これで、セグメントコードを使用したワークフローの作成を開始できます。

セグメントコードは、 **[!UICONTROL Sending logs extension]**.

## 手順 2:セグメントを含むワークフローの作成 {#step-2--create-a-workflow-segments}

>[!NOTE]
>E メール配信の入力トランジションが空の場合、前のトランジションのセグメントコードはデフォルトで追加されます。

最初に、異なるターゲット母集団を持つワークフローを作成する必要があります。 ここでは、オーディエンスの年齢に応じてパーソナライズされる E メールを送信します。1 つは 20 歳から 30 歳のプロファイル用、もう 1 つは 30 歳から 40 歳のプロファイル用です。

1. ワークフローを作成します。 ワークフローの作成方法について詳しくは、 [ページ](../../automating/using/building-a-workflow.md).

1. を追加します。 **[!UICONTROL Query]** アクティビティをドラッグして、ワークスペースにドロップします。

1. 20 歳から 40 歳のプロファイルをターゲティングし、後でそれらをよりターゲット化された母集団にセグメント化します。

   ![](assets/report_segment_1.png)

1. を追加します。 **[!UICONTROL Segmentation]** 「 」アクティビティを使用して、クエリ結果を 2 つのターゲット母集団に分割します。 セグメント化について詳しくは、 [ページ](../../automating/using/segmentation.md).

1. 次をダブルクリックします。 **[!UICONTROL Segmentation]** 「 」アクティビティを使用して設定します。 最初のセグメントを編集するには、 **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. 20 歳から 30 歳までのプロファイルをクエリし、 **[!UICONTROL Confirm]** 完了したら、

   ![](assets/report_segment_8.png)

1. クリック **[!UICONTROL Add an element]** 2 番目のセグメントを作成し、上記の手順に従って設定して、30 歳から 40 歳までのプロファイルをターゲットにします。

1. を編集します。 **[!UICONTROL Segment code]** 動的レポートを使用して渡される各母集団の

   >[!NOTE]
   >この手順は必須です。必須でない場合は、レポートするセグメントを理解できません。

   ![](assets/report_segment_9.png)

1. ドラッグ&amp;ドロップ **[!UICONTROL Email delivery]** アクティビティを作成します。

   ![](assets/report_segment_3.png)

1. ターゲット母集団に応じて、配信をパーソナライズします。 E メールの作成について詳しくは、 [ページ](../../designing/using/designing-content-in-adobe-campaign.md).

1. ワークフローを保存します。

1. クリック **[!UICONTROL Start]** ワークフローの準備が整ったら、次の手順に従います。

これで、レポートにアクセスしてセグメントコードを追跡できます。

## 手順 3:セグメントをフィルタリングするための動的レポートの作成 {#step-3--create-a-dynamic-report-filter-segments}

ワークフローで配信を送信した後、ワークフローのセグメントコードを使用して分類レポートを作成できます。

1. 次の **[!UICONTROL Reports]** 」タブで、標準のレポートを選択するか、 **[!UICONTROL Create new project]** ボタンをクリックして、一から開始します。

   ![](assets/custom_profile_18.png)
1. 次をドラッグ&amp;ドロップ： **[!UICONTROL Delivery]** ディメンションをフリーフォームテーブルに追加します。

   ![](assets/report_segment_5.png)

1. テーブルに、例えば **[!UICONTROL Open]** および **[!UICONTROL Click]** 指標を使用して、データのフィルタリングを開始します。
1. 内 **[!UICONTROL Dimensions]** カテゴリの **[!UICONTROL Profile]** ディメンションをドラッグ&amp;ドロップします **[!UICONTROL Segment code]** ディメンションを使用して、ターゲット母集団に応じて e メール配信の成功を測定します。

   ![](assets/report_segment_6.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_10.png)
