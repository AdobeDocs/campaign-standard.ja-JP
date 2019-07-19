---
title: Enhance
seo-title: Enhance
description: Enhance
seo-description: 強化アクティビティは、ワークフローで処理する追加データを定義できる高度なアクティビティです。
page-status-flag: 常にアクティブ化されていない
uuid: 8c1693ef-1312-422c- b05d-263553113f8f
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: f67c1cab-3284-4c34- a5b0-8654a95640ae
context-tags: engretion， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Enrichment{#enrichment}

## 説明 {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** アクティビティは高度なアクティビティで、ワークフローで処理する追加データを定義できます。

## Context of use {#context-of-use}

**[!UICONTROL Enrichment]** アクティビティは通常、ターゲットアクティビティの後、またはファイルのインポート後、ターゲットデータの使用を許可するアクティビティの前に使用されます。

This activity contains more advanced enrichment functions than the **[!UICONTROL Query]** activity. Some simple cases of enrichment can be directly performed in the [Query activity](../../automating/using/query.md#enriching-data).

**[!UICONTROL Enrichment]** アクティビティを使用すると、インバウンドトランジションを活用し、そのアクティビティを設定して、追加のデータを使用して出力トランジションを完了できます。複数のセットからのデータを組み合わせたり、一時リソースへのリンクを作成したりできます。

## Configuration {#configuration}

To configure an **[!UICONTROL Enrichment]** activity:

1. Drag and drop an **[!UICONTROL Enrichment]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If the activity has several inbound transitions, select the **[!UICONTROL Primary set]**. このアクティビティで設定された追加のデータは、アウトバウンドトランジションのこのプライマリセットに追加されます。

   プライマリセットに既にデータが含まれている場合は、そのデータを保持するか、削除するかを選択できます。**[!UICONTROL Keep all additional data from the main set]** このオプションの選択を解除すると、その選択したデータだけがアウトバウンド **[!UICONTROL Enrichment]** トランジションに保持されます。

1. If there are several inbound transitions, define relations between the primary set and the other inbound data in the **[!UICONTROL Advanced Relations]** tab of the activity. **[!UICONTROL Add element]** ボタンを使用して複数の関係を追加できます。

   新しい関係を定義する場合は、プライマリセットにリンクする受信データのセットを選択します。次に、関係のタイプを定義します。受信データとデータモデルに応じて、いくつかのタイプの関係を使用できます。

   * **[!UICONTROL 1 cardinality simple link]**:受信データの各レコードは、プライマリセットから1つのレコードのみに関連付けられます。プライマリセットのレコードごとに、リンクされたデータに1つのレコードが関連付けられています。
   * **[!UICONTROL N cardinality collection link]**:0、1またはその他（N）のリンクデータは、プライマリセットの1レコードに関連付けることができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:プライマリセットからのレコードは、リンクされたデータから0または1レコードに関連付けることができますが、複数のレコードに関連付けることはできません。
   Once the **[!UICONTROL Cardinality]** is defined, define a **[!UICONTROL Reconciliation criteria]**. The **[!UICONTROL Source expression]** of the reconciliation criteria can be a field from the target resource, an [expression](../../automating/using/advanced-expression-editing.md) or directly a value specified between quotes.

   **[!UICONTROL Label]** ワークフロー **[!UICONTROL ID]** の後半で簡単に識別できます。

   >[!NOTE]
   >
   >You can only define relations between the primary set and the other inbound transitions connected to the **[!UICONTROL Enrichment]** activity. For simpler cases aiming at defining relations with database resources, use a [Reconciliation](../../automating/using/reconciliation.md) activity.

1. Define the additional data from the **[!UICONTROL Additional data]** tab of the activity. You can define additional data (simple fields, aggregates and collections) related to the targeting dimension of the primary set or based on the links created in the **[!UICONTROL Advanced relations]** tab of the **[!UICONTROL Enrichment]** activity.

   Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

1. アクティビティの設定を確認し、ワークフローを保存します。

The data is now available to use in the activities connected after the **[!UICONTROL Enrichment]**. For example, you can find it under the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer in an email content.

## Example: Enriching profile data with data contained in a file {#example--enriching-profile-data-with-data-contained-in-a-file}

この例は、ファイルに含まれる購入データを含むプロファイルデータをエンリッチメントする方法を示しています。ここでは、購入データがサードパーティ製システムに保存されていることを考慮します。各プロファイルには、ファイルに複数の購入を格納できます。ワークフローの最終目標は、忠誠度のために、少なくとも2つの品目を購入したターゲットプロファイルに電子メールを送信することです。

ワークフローは次のように設定されます。

![](assets/enrichment_example_workflow.png)

* A **[!UICONTROL Query]** activity that targets the profiles who will receive the message.
* A **[!UICONTROL Load file]** activity that loads the purchase data. 次に例を示します。

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   この例のファイルでは、電子メールアドレスを使用してデータをデータベースプロファイルと調整します。You can also enable unique IDs as described in [this document](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** ファイルから読み込まれたトランザクションデータと、で選択 **[!UICONTROL Query]**&#x200B;したプロファイルとの間にリンクを作成するアクティビティ。The link is defined in the **[!UICONTROL Advanced relations]** tab of the activity. The link is based on the transition coming from the **[!UICONTROL Load file]** activity. プロファイルリソースの「電子メール」フィールドと、インポートされたファイルの「顧客」列を紐付け条件として使用します。

   ![](assets/enrichment_example_workflow2.png)

   Once the link is created, two sets of **[!UICONTROL Additional data]** are added:

   * 各プロファイルの最後の2つのトランザクションに対応する2行のコレクション。このコレクションでは、製品名、トランザクション日および製品の価格が追加データとして追加されます。データに降順の並べ替えが適用されます。To create the collection, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Check **[!UICONTROL Collection]** and specify the number of lines to retrieve (2 in this example). In this screen, you can customize the **[!UICONTROL Alias]** and the **[!UICONTROL Label]** of the collection. これらの値は、このコレクションを参照する際に、ワークフローの次のアクティビティに表示されます。

      ![](assets/enrichment_example_workflow4.png)

      As **[!UICONTROL Data]** to keep for the collection, select the columns that will be used in the final delivery.

      ![](assets/enrichment_example_workflow6.png)

      トランザクション日に降順を適用して、最新のトランザクションを確実に取得します。

      ![](assets/enrichment_example_workflow7.png)

   * 各プロファイルのトランザクションの合計数を集計する集計。この集計は、少なくとも2つのトランザクションが記録されているプロファイルをフィルターするために使用されます。To create the aggregate, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      As **[!UICONTROL Data]** to keep, define a **Count All** aggregate. 必要に応じて、次のアクティビティで簡単に検索するカスタムエイリアスを指定します。

      ![](assets/enrichment_example_workflow9.png)

* A **[!UICONTROL Segmentation]** activity with only one segment, that retrieves profiles of the initial target that have at least two transactions recorded. 1つのトランザクションのみを含むプロファイルは除外されます。そのためには、事前定義済みの集計でセグメント化のクエリーが実行されます。

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** プロファイルによって最後に行われた2つの購入を動的に取得する **[!UICONTROL Enrichment]** ために定義された追加のデータを使用するアクティビティ。The additional data can be found in the **Additional data (TargetData)** node when adding a personalization field.

   ![](assets/enrichment_example_workflow10.png)

