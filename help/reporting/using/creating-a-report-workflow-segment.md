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
source-wordcount: '640'
ht-degree: 2%

---

# ワークフローセグメントに基づくレポートの作成{#creating-a-report-workflow-segment}

>[!CAUTION]
> ターゲッ **[!UICONTROL Segment code]** できるのは、メールと SMS 配信のみです。

ワークフローを作成し、母集団を様々なターゲットオーディエンスにフィルタリングした後、このターゲティングワークフローで定義されたセグメントに基づいてマーケティングキャンペーンの効率を測定できます。
レポートでこれらのセグメントをターゲットにするには：

* [手順 1：セグメントを使用したプロファイルのカスタムリソースの更新](#step-1--update-profiles-custom-resource-segments)
* [手順 2：セグメントを使用したワークフローの作成](#step-2--create-a-workflow-segments)
* [手順 3：セグメントをフィルタリングするための動的レポートの作成](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>これらのデータの収集を開始するには、動的レポート使用契約に同意する必要があります。
>
>本契約について詳しくは、この [ ページ ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) を参照してください。

## 手順 1：セグメントを使用したプロファイルのカスタムリソースの更新{#step-1--update-profiles-custom-resource-segments}

セグメントコードのレポートを作成する前に、セグメントコードを保存するために **[!UICONTROL Profiles]** のカスタムリソースを更新する必要があります。

1. 詳細メニューから、Adobe Campaign ロゴを使用して **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** を選択し、**[!UICONTROL Profile (profile)]** リソースを選択します。
1. 「**[!UICONTROL Data structure]**」タブの **[!UICONTROL Sending logs extension]** メニューで、「**[!UICONTROL Add segment code]**」をチェックして、ターゲティングワークフローからのセグメントコードの保存を許可し、動的レポートに送信します。

   その後、**[!UICONTROL Segment code]** は、レポートの「**[!UICONTROL Profile]** ディメンション」セクションで使用できるようになります。

   ![](assets/report_segment_4.png)

1. カスタムリソースを保存します。

1. 次に、カスタムリソースを公開する必要があります。
詳細メニューから、**[!UICONTROL Administration]**/**[!UICONTROL Development]**/**[!UICONTROL Publishing]** を選択します。

   ![](assets/custom_profile_7.png)

1. 「」をクリック **[!UICONTROL Prepare publication]**、準備が完了したら「**[!UICONTROL Publish]**」ボタンをクリックします。 カスタムリソースについて詳しくは、この [ ページ ](../../developing/using/updating-the-database-structure.md) を参照してください。

これで、セグメントコードを使用してワークフローの作成を開始できます。

セグメントコードは、**[!UICONTROL Sending logs extension]** でセグメントコードを有効にするとすぐに収集されます。

## 手順 2：セグメントを使用したワークフローの作成 {#step-2--create-a-workflow-segments}

>[!NOTE]
>メール配信の入力トランジションが空の場合、前のトランジションのセグメントコードがデフォルトで追加されます。

まず、ターゲット母集団が異なるワークフローを作成する必要があります。 ここでは、オーディエンスの年齢に応じてパーソナライズされたメールを送信します。1 つは 20～30 歳のプロファイル用の配信、もう 1 つは 30～40 歳のプロファイル用の配信です。

1. ワークフローを作成します。 ワークフローの作成方法について詳しくは、この [ ページ ](../../automating/using/building-a-workflow.md) を参照してください。

1. **[!UICONTROL Query]** アクティビティをパレットからドラッグし、ワークスペースにドロップして追加します。

1. 20～40 歳のプロファイルをターゲットに、よりターゲットの絞られた母集団にセグメント化します。

   ![](assets/report_segment_1.png)

1. **[!UICONTROL Segmentation]** アクティビティを追加して、クエリ結果を 2 つのターゲット母集団に分割します。 セグメント化について詳しくは、この [ ページ ](../../automating/using/segmentation.md) を参照してください。

1. **[!UICONTROL Segmentation]** アクティビティをダブルクリックして設定します。 **[!UICONTROL Edit properties]** をクリックして、最初のセグメントを編集します。

   ![](assets/report_segment_7.png)

1. 20～30 歳のプロファイルにクエリを実行し、完了したら「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/report_segment_8.png)

1. 「**[!UICONTROL Add an element]**」をクリックして 2 つ目のセグメントを作成し、上記の手順の説明に従って設定し、30～40 歳のプロファイルをターゲットにします。

1. 動的レポートを通じて渡される各母集団の **[!UICONTROL Segment code]** を編集します。

   >[!NOTE]
   >この手順は必須です。実行しないと、レポートするセグメントを把握できなくなります。

   ![](assets/report_segment_9.png)

1. **[!UICONTROL Email delivery]** アクティビティをセグメントの後にドラッグ&amp;ドロップします。

   ![](assets/report_segment_3.png)

1. 様々なターゲット母集団に応じて配信をパーソナライズします。 メール作成について詳しくは、この [ ページ ](../../designing/using/designing-content-in-adobe-campaign.md) を参照してください。

1. ワークフローを保存します。

1. ワークフローの準備が整ったら、「**[!UICONTROL Start]**」をクリックします。

これで、レポートにアクセスしてセグメントコードを追跡できるようになりました。

## 手順 3：セグメントをフィルタリングするための動的レポートの作成 {#step-3--create-a-dynamic-report-filter-segments}

ワークフローで配信を送信した後、ワークフローのセグメントコードを使用してレポートを分類できます。

1. 「**[!UICONTROL Reports]**」タブから、標準提供のレポートを選択するか、「**[!UICONTROL Create new project]**」ボタンをクリックして最初から作成します。

   ![](assets/custom_profile_18.png)
1. **[!UICONTROL Delivery]** ディメンションをフリーフォームテーブルにドラッグ&amp;ドロップします。

   ![](assets/report_segment_5.png)

1. **[!UICONTROL Open]** 指標や **[!UICONTROL Click]** 指標など、別の指標をテーブルにドラッグ&amp;ドロップして、データのフィルタリングを開始します。
1. **[!UICONTROL Dimensions]** カテゴリで、**[!UICONTROL Profile]** ディメンションをクリックし、**[!UICONTROL Segment code]** ディメンションをワークフローの配信にドラッグ&amp;ドロップして、ターゲットの母集団に応じてメール配信の成功を測定します。

   ![](assets/report_segment_6.png)

1. 必要に応じて、ビジュアライゼーションをワークスペースにドラッグ&amp;ドロップします。

   ![](assets/report_segment_10.png)
