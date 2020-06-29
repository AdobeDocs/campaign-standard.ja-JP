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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 18%

---


# ターゲティングアクティビティについて{#about-targeting-activities}

パレットの画面左側で、 **[!UICONTROL Targeting]** セクションを展開します。

これらのアクティビティは、訪問者のターゲット設定、訪問者データの操作、アクティビティのフィルターに固有です。 セットを定義し、交差、和集合または除外の演算を使用してセットを分割または組み合わせることで、1つ以上のターゲットを作成できます。

![](assets/wkf_targeting_activities.png)

この **[!UICONTROL Targeting]** 節では、次のアクティビティについて説明します。

* [クエリ](../../automating/using/query.md)
* [増分クエリ](../../automating/using/incremental-query.md)
* [和集合](../../automating/using/union.md)
* [積集合](../../automating/using/intersection.md)
* [除外](../../automating/using/exclusion.md)
* [セグメント化](../../automating/using/segmentation.md)
* [オーディエンスの閲覧](../../automating/using/read-audience.md)
* [オーディエンスの保存](../../automating/using/save-audience.md)
* [重複排除](../../automating/using/deduplication.md)
* [エンリッチメント](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** アクティビティを使用すると、送信トランジションの **セグメントコード** を定義できます。 その後、これらのセグメントコードに基づいてレポートを作成し、マーケティングキャンペーンの効率性を測定できます。 詳しくは、[この節](../../reporting/using/creating-a-report-workflow-segment.md)を参照してください。

## データの選択 {#selecting-data}

次のアクティビティを使用して、データを選択できます。

* この **[!UICONTROL Query]** アクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。 「 [クエリ](../../automating/using/query.md) 」の節を参照してください。
* この **[!UICONTROL Incremental query]** アクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。 このアクティビティが実行されるたびに、以前の実行の結果が除外されます。 これにより、新しい要素のみをターゲットできます。を参照してください。 [増分処理クエリ](../../automating/using/incremental-query.md) ・セクション。
* この **[!UICONTROL Read audience]** アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。詳しくは、「 [オーディエンスの読み取り](../../automating/using/read-audience.md) 」の項を参照してください。

## データのセグメント化 {#segmenting-data}

Adobe Campaign では、インバウンドデータをセットで処理できます。したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。

* この **[!UICONTROL Union]** アクティビティを使用すると、複数のアクティビティの結果を1つのターゲットに再グループ化できます。 「 [和集合](../../automating/using/union.md) 」の節を参照してください。
* この **[!UICONTROL Intersection]** アクティビティでは、アクティビティ内の異なる受信訪問者に共通の要素のみを保持できます。 「 [積集合](../../automating/using/intersection.md) 」の節を参照してください。
* この **[!UICONTROL Exclusion]** アクティビティを使用すると、特定の条件に従って1つの訪問者から要素を除外できます。 「 [除外](../../automating/using/exclusion.md) 」の節を参照してください。
* この **[!UICONTROL Segmentation]** アクティビティでは、ワークフローの前のバージョンに配置されたアクティビティによって計算された訪問者から、1つまたは複数のセグメントを作成できます。 アクティビティの最後に、1つのトランジションまたは異なるトランジションで処理できます。 「 [セグメント化](../../automating/using/segmentation.md) 」の節を参照してください。

## データのエンリッチメント {#enriching-data}

識別され、収集されたデータに対して、ターゲットの構築を最適化するために、エンリッチメントや集計、操作をおこなうことができます。データマートでモデル化されていないデータを含めることで、ターゲティングプロセスを簡略化し、最適化できます。

との **[!UICONTROL Additional data]** アクティビティの **[!UICONTROL Query]****[!UICONTROL Incremental query]** タブを使用すると、クエリが対象とするデータを拡充し、このデータを次のワークフローアクティビティに転送して利用できます。 特に、以下を追加できます。

* 単純なデータ
* 集計
* コレクション

**関連トピック：**

* [使用例： 電子メールと追加データのパーソナライズ](../../automating/using/personalizing-email-with-additional-data.md)
