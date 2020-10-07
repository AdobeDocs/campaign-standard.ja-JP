---
title: ターゲティングアクティビティについて
description: ターゲットアクティビティは、画面の左側からアクセスできます。
page-status-flag: never-activated
uuid: a6cbc431-1ae3-428e-b2c9-893454b32ae2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 5f7607a1-5f71-4d66-9688-3e5a1774f1b4
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 59%

---


# ターゲティングアクティビティについて{#about-targeting-activities}

パレットの画面左側で、「**[!UICONTROL Targeting]**」セクションを展開します。

これらのアクティビティは、訪問者のターゲット設定、訪問者データの操作、アクティビティのフィルターに固有です。 セットを定義し、交差、和集合または除外の演算を使用してセットを分割または組み合わせることで、1つ以上のターゲットを作成できます。

![](assets/wkf_targeting_activities.png)

「**[!UICONTROL Targeting]**」セクションでは、次のアクティビティオプションを提供しています。

* [クエリ](../../automating/using/query.md)
* [増分処理クエリ](../../automating/using/incremental-query.md)
* [和集合](../../automating/using/union.md)
* [積集合](../../automating/using/intersection.md)
* [除外](../../automating/using/exclusion.md)
* [セグメント化](../../automating/using/segmentation.md)
* [オーディエンスの閲覧](../../automating/using/read-audience.md)
* [オーディエンスの保存](../../automating/using/save-audience.md)
* [重複排除](../../automating/using/deduplication.md)
* [エンリッチメント](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** アクティビティを使用すると、送信トランジションの **セグメントコード** を定義できます。 その結果、これらのセグメントコードに基づいてレポートを作成して、マーケティングキャンペーンの効率を測定できます。詳しくは、[この節](../../reporting/using/creating-a-report-workflow-segment.md)を参照してください。

## データの選択 {#selecting-data}

次のアクティビティを使用して、データを選択できます。

* 「**[!UICONTROL Query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。「 [クエリ](../../automating/using/query.md) 」の節を参照してください。
* 「**[!UICONTROL Incremental query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。このアクティビティが実行されるたびに、以前の実行結果が除外されます。これにより、新しい要素のみをターゲットできます。を参照してください。 [増分処理クエリ](../../automating/using/incremental-query.md) ・セクション。
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## データのセグメント化 {#segmenting-data}

Adobe Campaign では、インバウンドデータをセットで処理できます。したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。

* 「**[!UICONTROL Union]**」アクティビティを使用すると、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。「 [和集合](../../automating/using/union.md) 」の節を参照してください。
* 「**[!UICONTROL Intersection]**」アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。「 [積集合](../../automating/using/intersection.md) 」の節を参照してください。
* ［**[!UICONTROL Exclusion]**］アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。「 [除外](../../automating/using/exclusion.md) 」の節を参照してください。
* 「**[!UICONTROL Segmentation]**」アクティビティを使用すると、ワークフローで既に配置されているアクティビティによって計算された母集団から、1 つまたは複数のセグメントを作成できます。アクティビティの最後に、1 つのトランジションまたは複数のトランジションで処理できます。「 [セグメント化](../../automating/using/segmentation.md) 」の節を参照してください。

## データのエンリッチメント {#enriching-data}

識別され、収集されたデータに対して、ターゲットの構築を最適化するために、エンリッチメントや集計、操作をおこなうことができます。データマートでモデル化されていないデータを含めることで、ターゲティングプロセスを簡略化し、最適化できます。

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. 特に、以下を追加できます。

* シンプルなデータ
* 集計
* コレクション

**関連トピック：**

* [使用例：電子メールと追加データのパーソナライズ](../../automating/using/personalizing-email-with-additional-data.md)
