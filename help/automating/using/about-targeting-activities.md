---
title: ターゲティングアクティビティについて
description: ターゲティングアクティビティは、画面の左側からアクセスできます。
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 44%

---

# ターゲティングアクティビティについて{#about-targeting-activities}

パレットの画面左側で、「**[!UICONTROL Targeting]**」セクションを展開します。

これらのアクティビティは、ターゲティング、母集団データの操作、フィルタリングアクティビティに固有です。 セットを定義し、積集合、和集合、除外の各操作を使用して分割または組み合わせることで、1 つ以上のターゲットを作成できます。

![](assets/wkf_targeting_activities.png)

「**[!UICONTROL Targeting]**」セクションでは、次のアクティビティオプションを提供しています。

* [クエリ](../../automating/using/query.md)
* [増分クエリ](../../automating/using/incremental-query.md)
* [和集合](../../automating/using/union.md)
* [積集合](../../automating/using/intersection.md)
* [除外](../../automating/using/exclusion.md)
* [セグメント化](../../automating/using/segmentation.md)
* [オーディエンスを読み取り](../../automating/using/read-audience.md)
* [オーディエンスを保存](../../automating/using/save-audience.md)
* [重複排除](../../automating/using/deduplication.md)
* [エンリッチメント](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** 「 」アクティビティでは、 **セグメントコード** 送信トランジション用に作成されます。 その結果、これらのセグメントコードに基づいてレポートを作成して、マーケティングキャンペーンの効率を測定できます。詳しくは、[この節](../../reporting/using/creating-a-report-workflow-segment.md)を参照してください。

## データの選択 {#selecting-data}

次のアクティビティを使用してデータを選択できます。

* 「**[!UICONTROL Query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。詳しくは、 [クエリ](../../automating/using/query.md) 」セクションに入力します。
* 「**[!UICONTROL Incremental query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。このアクティビティが実行されるたびに、以前の実行結果が除外されます。これにより、新しい要素のみをターゲットにすることができます。を参照してください。 [増分処理クエリ](../../automating/using/incremental-query.md) 」セクションに入力します。
* The **[!UICONTROL Read audience]** 「 」アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用してそのオーディエンスを絞り込むことができます。詳しくは、 [オーディエンスの閲覧](../../automating/using/read-audience.md) 」セクションに入力します。

## データのセグメント化 {#segmenting-data}

Adobe Campaignを使用すると、受信データのセットを処理できます。 したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。

* The **[!UICONTROL Union]** 「 」アクティビティを使用すると、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。 [和集合](../../automating/using/union.md)の節を参照してください。
* The **[!UICONTROL Intersection]** 「 」アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。 [積集合](../../automating/using/intersection.md)の節を参照してください。
* The **[!UICONTROL Exclusion]** 「 」アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。 詳しくは、 [除外](../../automating/using/exclusion.md) 」セクションに入力します。
* 「**[!UICONTROL Segmentation]**」アクティビティを使用すると、ワークフローで既に配置されているアクティビティによって計算された母集団から、1 つまたは複数のセグメントを作成できます。アクティビティの最後に、1 つのトランジションまたは異なるトランジションで処理できます。 詳しくは、 [セグメント化](../../automating/using/segmentation.md) 」セクションに入力します。

## データのエンリッチメント {#enriching-data}

識別され、収集されたデータに対して、ターゲットの構築を最適化するために、エンリッチメントや集計、操作を行うことができます。データマートでモデル化されていないデータを含めることで、ターゲティングプロセスを簡素化し、最適化できます。

The **[!UICONTROL Additional data]** タブ **[!UICONTROL Query]** および **[!UICONTROL Incremental query]** 「 」アクティビティを使用すると、クエリのターゲットとなるデータをエンリッチメントし、このデータを次のワークフローアクティビティに転送して使用できます。 特に、以下を追加できます。

* シンプルなデータ
* 集計
* コレクション

**関連トピック：**

* [使用例：追加データを含む E メールのパーソナライズ](../../automating/using/personalizing-email-with-additional-data.md)
