---
title: データのターゲット化
seo-title: データのターゲット化
description: データのターゲット化
seo-description: 必要なデータをターゲットにして選択するさまざまな方法を学習します。
page-status-flag: 決して活性化されていない
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: ワークフロー全般運用
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# データのターゲット化{#targeting-data}

## データの選択 {#selecting-data}

次のアクティビティを使用してデータを選択できます。

* **[!UICONTROL Query]** このアクティビティでは、Adobe Campaignデータベースから要素の母集団をフィルタおよび抽出できます。[「クエリー」](../../automating/using/query.md) セクションを参照してください。
* **[!UICONTROL Incremental query]** このアクティビティでは、Adobe Campaignデータベースから要素の母集団をフィルタおよび抽出できます。このアクティビティが実行されるたびに、前回の実行の結果は除外されます。これにより、新しい要素のみをターゲットにすることができます。[インクリメンタルクエリ](../../automating/using/incremental-query.md) セクション。
* このアクティビティ **[!UICONTROL Read audience]** を使用すると、既存の対象者を取得し、追加のフィルタリング条件を適用することによってその対象者を絞り込むことができます。「閲覧者 [」](../../automating/using/read-audience.md) セクションを参照してください。

## データのセグメント化 {#segmenting-data}

Adobe Campaignでは、インバウンドデータのセットを処理できます。これにより、複数の個体群を結合したり、その一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。

* **[!UICONTROL Union]** アクティビティを使用すると、複数のアクティビティの結果を1つのターゲットに再グループ化できます。[「ユニオン](../../automating/using/union.md) 」セクションを参照してください。
* **[!UICONTROL Intersection]** アクティビティによって、アクティビティ内の異なるインバウンドポピュレーションに共通する要素のみを保持できます。[交差](../../automating/using/intersection.md) セクションを参照してください。
* **[!UICONTROL Exclusion]** アクティビティを使用すると、特定の条件に従って1つの母集団から要素を除外できます。[除外](../../automating/using/exclusion.md) セクションを参照してください。
* **[!UICONTROL Segmentation]** アクティビティでは、ワークフローの前に配置されたアクティビティによって計算された人口から、1つまたは複数のセグメントを作成できます。アクティビティの最後には、1つの遷移または異なる遷移で処理できます。[Segmentation](../../automating/using/segmentation.md) セクションを参照してください。

## データの濃縮 {#enriching-data}

識別および収集されたデータは、集約、集約、および操作され、ターゲットの構築を最適化できます。データマートでモデル化されていないデータを含めることにより、ターゲットプロセスを効率化および最適化できます。

および **[!UICONTROL Additional data]****[!UICONTROL Query]****[!UICONTROL Incremental query]** アクティビティのタブを使用すると、クエリの対象となるデータを充実させ、このデータを次のワークフローアクティビティに転送して、使用可能にすることができます。特に、次のように追加できます。

* シンプルなデータ
* 集計
* コレクション

**関連トピック**

* [ユースケース:1週間の電子メール配信を作成する](../../automating/using/workflow-weekly-offer.md)
* [ユースケース:場所にセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [ユースケース:補足を使用した搬送の作成](../../automating/using/workflow-created-query-with-complement.md)
* [ユースケース:新しい配送を非公開者に送信するワークフローの再ターゲット](../../automating/using/workflow-cross-channel-retargeting.md)
