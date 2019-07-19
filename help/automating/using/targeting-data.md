---
title: ターゲットデータ
seo-title: ターゲットデータ
description: ターゲットデータ
seo-description: 必要なデータをターゲットにして選択する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow- general- operation
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Targeting data{#targeting-data}

## Selecting data {#selecting-data}

次のアクティビティを使用してデータを選択できます。

* **[!UICONTROL Query]** アクティビティにより、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。[「クエリ](../../automating/using/query.md) 」セクションを参照してください。
* **[!UICONTROL Incremental query]** アクティビティにより、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。このアクティビティが実行されるたびに、前回の実行の結果は除外されます。これにより、新しい要素のみをターゲットにすることができます。[増分クエリ](../../automating/using/incremental-query.md) セクション。
* **[!UICONTROL Read audience]** このアクティビティでは、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。オーディエンスの [読み取り](../../automating/using/read-audience.md) セクションを参照してください。

## Segmenting data {#segmenting-data}

Adobe Campaignでは、受信データのセットを処理できます。その結果、複数の母集団を結合したり、一部を除外したり、複数のターゲットに共通のデータのみを保持したりできます。

* **[!UICONTROL Union]** アクティビティを使用すると、複数のアクティビティの結果を単一のターゲットに再グループ化できます。[「ユニオン](../../automating/using/union.md) 」セクションを参照してください。
* **[!UICONTROL Intersection]** アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを維持できます。[「交差」](../../automating/using/intersection.md) セクションを参照してください。
* **[!UICONTROL Exclusion]** アクティビティでは、特定の条件に従って、ある母集団からの要素を除外できます。[「除外](../../automating/using/exclusion.md) 」セクションを参照してください。
* **[!UICONTROL Segmentation]** アクティビティにより、ワークフローの前に配置したアクティビティによって計算された訪問者のセグメントを1つまたは複数作成できます。アクティビティの最後に、1つのトランジションまたは異なるトランジションで処理できます。[「セグメント化](../../automating/using/segmentation.md) 」セクションを参照してください。

## Enriching data {#enriching-data}

特定され、収集されたデータは、ターゲット構築を最適化し、集計して最適化することができます。データマートにモデル化されていないデータを含めることで、ターゲット設定プロセスをシンプル化し最適化できます。

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. 特に、以下を追加できます。

* 単純なデータ
* 集計
* コレクション

