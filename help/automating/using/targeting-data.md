---
title: データのターゲティング
description: 必要なデータをターゲットにして選択する様々な方法について説明します。
page-status-flag: 非活性化の
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow-general-operation
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# データのターゲティング{#targeting-data}

## データの選択 {#selecting-data}

次のアクティビティを使用して、データを選択できます。

* このア **[!UICONTROL Query]** クティビティでは、Adobe Campaignデータベースから要素の母集団をフィルターして抽出できます。 「クエリー」を参 [照してください](../../automating/using/query.md) 。
* このア **[!UICONTROL Incremental query]** クティビティでは、Adobe Campaignデータベースから要素の母集団をフィルターして抽出できます。 このアクティビティが実行されるたびに、以前の実行の結果が除外されます。 これにより、新しい要素のみをターゲットにすることができます。を参照してください。 [増分クエリー](../../automating/using/incremental-query.md) ・セクション。
* このア **[!UICONTROL Read audience]** クティビティでは、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。「オーディエンスを読み取る [](../../automating/using/read-audience.md) 」の節を参照してください。

## データのセグメント化 {#segmenting-data}

Adobe Campaign では、インバウンドデータをセットで処理できます。したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。

* アクティビテ **[!UICONTROL Union]** ィを使用すると、複数のアクティビティの結果を1つのターゲットに再グループ化できます。 Unionの節を参 [照](../../automating/using/union.md) 。
* アクテ **[!UICONTROL Intersection]** ィビティでは、アクティビティ内の異なる受信訪問者に共通の要素のみを保持できます。 「交差」の節を参 [照してください](../../automating/using/intersection.md) 。
* アクテ **[!UICONTROL Exclusion]** ィビティを使用すると、特定の条件に従って1つの訪問者から要素を除外できます。 「除外」の節を参 [照してください](../../automating/using/exclusion.md) 。
* アクティビティ **[!UICONTROL Segmentation]** を使用すると、ワークフローの前の方に配置されたアクティビティによって計算された訪問者から、1つまたは複数のセグメントを作成できます。 アクティビティの最後に、1つのトランジションまたは異なるトランジションで処理できます。 「分類」の節を参 [照してください](../../automating/using/segmentation.md) 。

## データのエンリッチメント {#enriching-data}

識別され、収集されたデータに対して、ターゲットの構築を最適化するために、エンリッチメントや集計、操作をおこなうことができます。データマートでモデル化されていないデータを含めることで、ターゲット化プロセスを簡素化し、最適化できます。

およびア **[!UICONTROL Additional data]** クティビティのタ **[!UICONTROL Query]** ブを使 **[!UICONTROL Incremental query]** 用すると、クエリーの対象となるデータを強化し、このデータを次のワークフローアクティビティに転送して、そのデータを利用できます。 特に、以下を追加できます。

* 単純なデータ
* 集計
* コレクション

**関連トピック**

* [使用例：週に1回の電子メール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [使用例：場所でセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [使用例：補完を含む配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [使用例：未開封者に新しい配信を送信する再ターゲットワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)
