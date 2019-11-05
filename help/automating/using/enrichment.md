---
title: エンリッチメント
description: 強化アクティビティは、ワークフローで処理する追加のデータを定義できる高度なアクティビティです。
page-status-flag: 非活性化の
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲティング活動
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: 濃縮，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# エンリッチメント{#enrichment}

## 説明 {#description}

![](assets/enrichment.png)

アクテ **[!UICONTROL Enrichment]** ィビティは、ワークフローで処理する追加のデータを定義できる高度なアクティビティです。

## 使用状況 {#context-of-use}

通常、ア **[!UICONTROL Enrichment]** クティビティは、ターゲット設定アクティビティの後、またはファイルをインポートした後、ターゲット設定されたデータを使用できるアクティビティの前に使用されます。

このアクティビティには、アクティビティよりも高度なエンリッチメント機能が含ま **[!UICONTROL Query]** れています。 一部の単純な拡張機能は、 [Queryアクティビティで直接実行できます](../../automating/using/query.md#enriching-data)。

アクティビティ **[!UICONTROL Enrichment]** を使用すると、受信トランジションを利用し、追加のデータを含む出力トランジションを完了するようにアクティビティを設定できます。 複数のセットからのデータを組み合わせたり、一時的なリソースへのリンクを作成したりできます。

## 設定 {#configuration}

アクティビティを設定す **[!UICONTROL Enrichment]** るには：

1. アクティビティをワークフロー **[!UICONTROL Enrichment]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. アクティビティに複数のインバウンド遷移がある場合は、を選択しま **[!UICONTROL Primary set]**&#x200B;す。 このアクティビティで設定された追加のデータは、アウトバウンド移行でこのプライマリセットに追加されます。

   プライマリセットに既に追加のデータが含まれている場合は、保持するか、削除するかを選択できます。 このオプションをオフ **[!UICONTROL Keep all additional data from the main set]** にした場合、で設定された追加のデータのみがア **[!UICONTROL Enrichment]** ウトバウンドトランジションに保持されます。

1. 複数のインバウンド移行がある場合は、アクティビティのタブでプライマリセットと他のインバウンドデータの間の **[!UICONTROL Advanced Relations]** 関係を定義します。 ボタンを使用して複数のリレーションを追加で **[!UICONTROL Add element]** きます。

   新しい関係を定義する場合は、主セットにリンクする受信データのセットを選択します。 次に、関係のタイプを定義します。 インバウンドデータとデータモデルに応じて、いくつかのタイプの関係を使用できます。

   * **[!UICONTROL 1 cardinality simple link]**:受信データの各レコードは、プライマリセットから1つのレコードに関連付けられます。 プライマリセットの各レコードには、リンクされたデータ内の1つのレコードが関連付けられています。
   * **[!UICONTROL N cardinality collection link]**:リンクされたデータの0、1、または複数の(N)レコードを、プライマリセットの1レコードに関連付けることができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:プライマリセットのレコードは、リンクされたデータの0または1レコードに関連付けることができますが、複数のレコードに関連付けることはできません。
   を定義し **[!UICONTROL Cardinality]** たら、を定義します **[!UICONTROL Reconciliation criteria]**。 調整条 **[!UICONTROL Source expression]** 件のフィールドは、ターゲットリソースのフィールド、式、または引用符 [で囲んで指定した](../../automating/using/advanced-expression-editing.md) 値にすることができます。

   ワークフロー **[!UICONTROL Label]** の後半で識 **[!UICONTROL ID]** 別しやすいと思われるANDを定義します。

   >[!NOTE]
   >
   >主セットと、アクティビティに接続された他のインバウンド推移との間の関係のみを定義で **[!UICONTROL Enrichment]** きます。 データベース・リソースとの関係の定義を目的とした、よりシンプルなケースの場合は、調整アクティビティ [を使用し](../../automating/using/reconciliation.md) ます。

1. アクティビティのタブから追加 **[!UICONTROL Additional data]** データを定義します。 プライマリセットのターゲットディメンションに関連する追加のデータ（単純なフィールド、集計およびコレクション）を定義するか、アクティビティのタブで作成されたリン **[!UICONTROL Advanced relations]** クに基づいて定義で **[!UICONTROL Enrichment]** きます。

   「データを豊 [富にする](../../automating/using/query.md#enriching-data) 」を参照。

1. アクティビティの設定を確認し、ワークフローを保存します。

これで、データは、後で接続されたアクティビティで使用できるようになりま **[!UICONTROL Enrichment]**&#x200B;す。 例えば、電子メールコンテンツのパーソナライゼーション **[!UICONTROL Additional data (targetData)]** フィールドエクスプローラーのリンクの下にあります。

## 例：ファイルに含まれるデータを使用してプロファイルデータを豊富にする {#example--enriching-profile-data-with-data-contained-in-a-file}

この例は、ファイルに含まれる購入データをプロファイルデータに含める方法を示しています。 ここでは、購入データがサードパーティのシステムに保存されることを考慮します。 各プロファイルには、ファイルに保存された購入が複数存在する場合があります。 ワークフローの最後の目的は、少なくとも2つの品目を購入したターゲットプロファイルに電子メールを送信し、その忠誠度に感謝することです。

ワークフローは次のように設定します。

![](assets/enrichment_example_workflow.png)

* メッセージ **[!UICONTROL Query]** を受け取るプロファイルをターゲットにするアクティビティ。
* 購入デ **[!UICONTROL Load file]** ータを読み込むアクティビティ。 次に例を示します。

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   この例のファイルでは、電子メールアドレスを使用して、データをデータベースプロファイルと調整します。 また、本書で説明するように、一意のIDを有効にするこ [ともできます](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。

* ファイ **[!UICONTROL Enrichment]** ルから読み込まれたトランザクションデータと、で選択したプロファイルとの間にリンクを作成するアクティビティ **[!UICONTROL Query]**。 リンクは、アクティビティのタ **[!UICONTROL Advanced relations]** ブで定義されます。 リンクは、アクティビティからのトランジションに基づいてい **[!UICONTROL Load file]** ます。 プロファイルリソースの「電子メール」フィールドと、インポートしたファイルの「顧客」列を調整条件として使用します。

   ![](assets/enrichment_example_workflow2.png)

   リンクが作成されると、次の2つのセットが追加 **[!UICONTROL Additional data]** されます。

   * 各プロファイルの2つの最後のトランザクションに対応する2行のコレクション。 このコレクションの場合、製品名、取引日、および製品の価格が追加データとして追加されます。 データに降順の並べ替えが適用されます。 コレクションを作成するには、タブから次の操作を **[!UICONTROL Additional data]** 行います。

      アクティビティのタブで以前に定義した **[!UICONTROL Advanced relations]** リンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      取得 **[!UICONTROL Collection]** する行数をチェックして指定します（この例では2）。 この画面では、コレクションのおよびを **[!UICONTROL Alias]** カスタマイズ **[!UICONTROL Label]** できます。 これらの値は、このコレクションを参照する際に、ワークフローの次のアクティビティで表示されます。

      ![](assets/enrichment_example_workflow4.png)

      コレ **[!UICONTROL Data]** クションの保持については、最終配信で使用する列を選択します。

      ![](assets/enrichment_example_workflow6.png)

      最新のトランザクションを確実に取得するために、トランザクション日に降順の並べ替えを適用します。

      ![](assets/enrichment_example_workflow7.png)

   * 各プロファイルのトランザクションの合計数をカウントする集計。 この集計は、少なくとも2つのトランザクションが記録されたプロファイルのフィルタリングに後で使用されます。 集計を作成するには、タブから次の操作を行 **[!UICONTROL Additional data]** います。

      アクティビティのタブで以前に定義した **[!UICONTROL Advanced relations]** リンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      保持す **[!UICONTROL Data]** るには、「すべてカウント」集 **計を定義します** 。 必要に応じて、次のアクティビティですばやく見つけられるようにカスタムエイリアスを指定します。

      ![](assets/enrichment_example_workflow9.png)

* 1つのセ **[!UICONTROL Segmentation]** グメントのみを持つアクティビティ。最低2つのトランザクションが記録された初期ターゲットのプロファイルを取得します。 トランザクションが1つだけのプロファイルは除外されます。 これを行うには、前に定義した集計に対してセグメント化のクエリを実行します。

   ![](assets/enrichment_example_workflow5.png)

* プロフ **[!UICONTROL Email delivery]** ァイルによって行われた2つの最後の購入を動的に取得するた **[!UICONTROL Enrichment]** めに、で定義された追加のデータを使用するアクティビティ。 追加のデータは、パーソナライゼーションフィールドを追 **加する際に、Additional data(TargetData)** ノードで確認できます。

   ![](assets/enrichment_example_workflow10.png)

**関連トピック：**

* [外部データによる顧客プロファイルの強化](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

