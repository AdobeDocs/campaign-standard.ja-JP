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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Enhance{#enrichment}

## 説明 {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** アクティビティは高度なアクティビティで、ワークフローで処理する追加データを定義できます。

## 使用コンテキスト {#context-of-use}

**[!UICONTROL Enrichment]** アクティビティは通常、ターゲットアクティビティの後、またはファイルのインポート後、ターゲットデータの使用を許可するアクティビティの前に使用されます。

このアクティビティには **[!UICONTROL Query]** 、アクティビティよりも高度な強化関数が含まれています。シンプル化の単純なケースは [、クエリアクティビティで直接実行](../../automating/using/query.md#enriching-data)できます。

**[!UICONTROL Enrichment]** アクティビティを使用すると、インバウンドトランジションを活用し、そのアクティビティを設定して、追加のデータを使用して出力トランジションを完了できます。複数のセットからのデータを組み合わせたり、一時リソースへのリンクを作成したりできます。

## 設定 {#configuration}

アクティビティを **[!UICONTROL Enrichment]** 設定するには:

1. アクティビティを **[!UICONTROL Enrichment]** ワークフローにドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用してそのアクティビティを開きます。
1. アクティビティにインバウンドトランジションが複数ある場合は、を選択 **[!UICONTROL Primary set]**&#x200B;します。このアクティビティで設定された追加のデータは、アウトバウンドトランジションのこのプライマリセットに追加されます。

   プライマリセットに既にデータが含まれている場合は、そのデータを保持するか、削除するかを選択できます。**[!UICONTROL Keep all additional data from the main set]** このオプションの選択を解除すると、その選択したデータだけがアウトバウンド **[!UICONTROL Enrichment]** トランジションに保持されます。

1. 複数のインバウンドトランジションがある場合は、アクティビティのタブ内 **[!UICONTROL Advanced Relations]** のプライマリセットと他の受信データとの関係を定義します。**[!UICONTROL Add element]** ボタンを使用して複数の関係を追加できます。

   新しい関係を定義する場合は、プライマリセットにリンクする受信データのセットを選択します。次に、関係のタイプを定義します。受信データとデータモデルに応じて、いくつかのタイプの関係を使用できます。

   * **[!UICONTROL 1 cardinality simple link]**:受信データの各レコードは、プライマリセットから1つのレコードのみに関連付けられます。プライマリセットのレコードごとに、リンクされたデータに1つのレコードが関連付けられています。
   * **[!UICONTROL N cardinality collection link]**:0、1またはその他（N）のリンクデータは、プライマリセットの1レコードに関連付けることができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:プライマリセットからのレコードは、リンクされたデータから0または1レコードに関連付けることができますが、複数のレコードに関連付けることはできません。
   定義が完了 **[!UICONTROL Cardinality]** したら、を定義 **[!UICONTROL Reconciliation criteria]**&#x200B;します。紐付け条件 **[!UICONTROL Source expression]** の例としては、ターゲットリソースのフィールド、 [式](../../automating/using/advanced-expression-editing.md) 、引用符間で指定した値などがあります。

   **[!UICONTROL Label]** ワークフロー **[!UICONTROL ID]** の後半で簡単に識別できます。

   >[!NOTE]
   >
   >プライマリセットと **[!UICONTROL Enrichment]** そのアクティビティに接続されている他のインバウンドトランジションとの関係のみを定義できます。データベースリソースとの関係の定義を目的とした単純なケースについては [、紐付け](../../automating/using/reconciliation.md) アクティビティを使用します。

1. アクティビティの **[!UICONTROL Additional data]** タブから追加のデータを定義します。プライマリセットのターゲットディメンション、またはアクティビティの **[!UICONTROL Advanced relations]** タブで作成されたリンクに基づいて、追加のデータ（単純なフィールド、集計およびコレクション）を定義 **[!UICONTROL Enrichment]** できます。

   詳しくは、 [「データの絞り込み」](../../automating/using/query.md#enriching-data) の節を参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。

これで、その後に接続されたアクティビティでデータを使用できるよう **[!UICONTROL Enrichment]**&#x200B;になります。例えば、電子メールコンテンツのパーソナライゼーションフィールドエクスプローラ **[!UICONTROL Additional data (targetData)]** のリンクの下に表示されます。

## 例:ファイルに含まれるデータを含むプロファイルデータの絞り込み {#example--enriching-profile-data-with-data-contained-in-a-file}

この例は、ファイルに含まれる購入データを含むプロファイルデータをエンリッチメントする方法を示しています。ここでは、購入データがサードパーティ製システムに保存されていることを考慮します。各プロファイルには、ファイルに複数の購入を格納できます。ワークフローの最終目標は、忠誠度のために、少なくとも2つの品目を購入したターゲットプロファイルに電子メールを送信することです。

ワークフローは次のように設定されます。

![](assets/enrichment_example_workflow.png)

* メッセージを受信するプロファイルをターゲットにする **[!UICONTROL Query]** アクティビティ。
* 購入データを読み込む **[!UICONTROL Load file]** アクティビティ。次に例を示します。

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   この例のファイルでは、電子メールアドレスを使用してデータをデータベースプロファイルと調整します。このドキュメントの [説明に従って、一意のIDを有効](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)にすることもできます。

* **[!UICONTROL Enrichment]** ファイルから読み込まれたトランザクションデータと、で選択 **[!UICONTROL Query]**&#x200B;したプロファイルとの間にリンクを作成するアクティビティ。リンクは、アクティビティの **[!UICONTROL Advanced relations]** タブで定義されます。リンクは **[!UICONTROL Load file]** 、アクティビティからの移行に基づいています。プロファイルリソースの「電子メール」フィールドと、インポートされたファイルの「顧客」列を紐付け条件として使用します。

   ![](assets/enrichment_example_workflow2.png)

   リンクが作成されると、次の2セットが追加 **[!UICONTROL Additional data]** されます。

   * 各プロファイルの最後の2つのトランザクションに対応する2行のコレクション。このコレクションでは、製品名、トランザクション日および製品の価格が追加データとして追加されます。データに降順の並べ替えが適用されます。コレクションを **[!UICONTROL Additional data]** タブから作成するには:

      アクティビティのタブで **[!UICONTROL Advanced relations]** 定義済みのリンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      取得する行数をチェック **[!UICONTROL Collection]** して指定します（この例では2）。この画面では、コレクションを **[!UICONTROL Alias]** カスタマイズして **[!UICONTROL Label]** カスタマイズできます。これらの値は、このコレクションを参照する際に、ワークフローの次のアクティビティに表示されます。

      ![](assets/enrichment_example_workflow4.png)

      コレクションを維持するため **[!UICONTROL Data]** に、最終配信で使用する列を選択します。

      ![](assets/enrichment_example_workflow6.png)

      トランザクション日に降順を適用して、最新のトランザクションを確実に取得します。

      ![](assets/enrichment_example_workflow7.png)

   * 各プロファイルのトランザクションの合計数を集計する集計。この集計は、少なくとも2つのトランザクションが記録されているプロファイルをフィルターするために使用されます。集計を **[!UICONTROL Additional data]** タブから作成するには:

      アクティビティのタブで **[!UICONTROL Advanced relations]** 定義済みのリンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      維持するには **[!UICONTROL Data]** 、「すべて **カウント」** 集計を定義します。必要に応じて、次のアクティビティで簡単に検索するカスタムエイリアスを指定します。

      ![](assets/enrichment_example_workflow9.png)

* 1つ以上のセグメントを持つ **[!UICONTROL Segmentation]** アクティビティで、少なくとも2つのトランザクションが記録されている初期ターゲットのプロファイルを取得します。1つのトランザクションのみを含むプロファイルは除外されます。そのためには、事前定義済みの集計でセグメント化のクエリーが実行されます。

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** プロファイルによって最後に行われた2つの購入を動的に取得する **[!UICONTROL Enrichment]** ために定義された追加のデータを使用するアクティビティ。追加データは、パーソナライゼーションフィールドを追加するときに **追加データ（targetData）** ノードにあります。

   ![](assets/enrichment_example_workflow10.png)

**関連トピック:**

* [外部データによる顧客プロファイルの充実](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

