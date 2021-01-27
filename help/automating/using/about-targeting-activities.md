---
solution: Campaign Standard
product: campaign
title: ターゲティングアクティビティについて
description: ターゲットアクティビティは、画面の左側からアクセスできます。
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

**[!UICONTROL Targeting]** アクティビティを使用すると、アウトバウンドトランジションの **セグメント** コードを定義できます。その結果、これらのセグメントコードに基づいてレポートを作成して、マーケティングキャンペーンの効率を測定できます。詳しくは、[この節](../../reporting/using/creating-a-report-workflow-segment.md)を参照してください。

## データの選択 {#selecting-data}

次のアクティビティを使用して、データを選択できます。

* 「**[!UICONTROL Query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。[クエリ](../../automating/using/query.md)の節を参照してください。
* 「**[!UICONTROL Incremental query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。このアクティビティが実行されるたびに、以前の実行結果が除外されます。これにより、新しい要素のみをターゲットできます。を参照してください。 [増分](../../automating/using/incremental-query.md) クエリセクション。
* **[!UICONTROL Read audience]**&#x200B;アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。[オーディエンス](../../automating/using/read-audience.md)を読み取るのセクションを参照してください。

## データのセグメント化 {#segmenting-data}

Adobe Campaign では、インバウンドデータをセットで処理できます。したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。

* 「**[!UICONTROL Union]**」アクティビティを使用すると、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。[和集合](../../automating/using/union.md)の節を参照してください。
* 「**[!UICONTROL Intersection]**」アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。[積集合](../../automating/using/intersection.md)の節を参照してください。
* ［**[!UICONTROL Exclusion]**］アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。「[除外](../../automating/using/exclusion.md)」の節を参照してください。
* 「**[!UICONTROL Segmentation]**」アクティビティを使用すると、ワークフローで既に配置されているアクティビティによって計算された母集団から、1 つまたは複数のセグメントを作成できます。アクティビティの最後に、1 つのトランジションまたは複数のトランジションで処理できます。「[セグメント化](../../automating/using/segmentation.md)」の節を参照してください。

## データのエンリッチメント {#enriching-data}

識別され、収集されたデータに対して、ターゲットの構築を最適化するために、エンリッチメントや集計、操作をおこなうことができます。データマートでモデル化されていないデータを含めることで、ターゲティングプロセスを簡略化し、最適化できます。

**[!UICONTROL Query]**&#x200B;と&#x200B;**[!UICONTROL Incremental query]**&#x200B;アクティビティの&#x200B;**[!UICONTROL Additional data]**&#x200B;タブを使用すると、クエリが対象とするデータを拡充し、このデータを次のワークフローアクティビティに転送して利用できます。 特に、以下を追加できます。

* シンプルなデータ
* 集計
* コレクション

**関連トピック：**

* [使用例：電子メールと追加データのパーソナライズ](../../automating/using/personalizing-email-with-additional-data.md)
