---
title: ターゲティングアクティビティについて
description: ターゲティングアクティビティには、画面の左側からアクセスできます。
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
TQID: https://experienceleague.adobe.com/PPDlvoeHKNpeLfYe4qYFq7mzQUb3oR7XkrMK-jQFpmY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 62%

---

# ターゲティングアクティビティについて{#about-targeting-activities}

パレットの画面左側で、「**[!UICONTROL Targeting]**」セクションを展開します。

これらのアクティビティは、ターゲティング、母集団データの操作、およびアクティビティのフィルタリングに固有です。 これらは、セットを定義し、積集合、和集合、除外演算を使用してこれらのセットを分割または結合することで、1つ以上のターゲットを作成できます。

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

**[!UICONTROL Targeting]** アクティビティを使用すると、アウトバウンドトランジション用に&#x200B;**セグメントコード**&#x200B;を定義できます。 その結果、これらのセグメントコードに基づいてレポートを作成して、マーケティングキャンペーンの効率を測定できます。 詳しくは、[この節](../../reporting/using/creating-a-report-workflow-segment.md)を参照してください。

## データの選択 {#selecting-data}

次のアクティビティを使用してデータを選択できます。

* 「**[!UICONTROL Query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。 「[&#x200B; クエリ &#x200B;](../../automating/using/query.md)」セクションを参照してください。
* 「**[!UICONTROL Incremental query]**」アクティビティを使用すると、Adobe Campaign データベースから要素の母集団をフィルタリングして抽出できます。 このアクティビティが実行されるたびに、以前の実行結果が除外されます。 これにより、新しい要素のみをターゲットにできます。 [増分クエリ &#x200B;](../../automating/using/incremental-query.md) セクション。
* 「**[!UICONTROL Read audience]**」アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用してそのオーディエンスを絞り込むことができます。「[&#x200B; オーディエンスの読み取り](../../automating/using/read-audience.md)」セクションを参照してください。

## データのセグメント化 {#segmenting-data}

Adobe Campaignでは、インバウンドデータでデータセットを処理できます。 したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。

* 「**[!UICONTROL Union]**」アクティビティを使用すると、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。 [和集合](../../automating/using/union.md)の節を参照してください。
* 「**[!UICONTROL Intersection]**」アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。 [積集合](../../automating/using/intersection.md)の節を参照してください。
* ［**[!UICONTROL Exclusion]**］アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。 「[除外](../../automating/using/exclusion.md)」セクションを参照してください。
* 「**[!UICONTROL Segmentation]**」アクティビティを使用すると、ワークフローで既に配置されているアクティビティによって計算された母集団から、1 つまたは複数のセグメントを作成できます。 アクティビティの最後に、1 つのトランジションまたは複数のトランジションで処理できます。 「[&#x200B; セグメント化](../../automating/using/segmentation.md)」を参照してください。

## データのエンリッチメント {#enriching-data}

識別され、収集されたデータに対して、ターゲットの構築を最適化するために、エンリッチメントや集計、操作を行うことができます。 データマートでモデル化されていないデータを含めることで、ターゲティングプロセスを簡素化および最適化できます。

**[!UICONTROL Query]**&#x200B;および&#x200B;**[!UICONTROL Incremental query]** アクティビティの&#x200B;**[!UICONTROL Additional data]** タブを使用すると、クエリでターゲットとするデータを強化し、このデータを次のワークフローアクティビティに転送して利用できます。 特に、以下を追加できます。

* シンプルなデータ
* 集計
* コレクション

**関連トピック：**

* [ユースケース：追加データを使用したメールのパーソナライズ](../../automating/using/personalizing-email-with-additional-data.md)
