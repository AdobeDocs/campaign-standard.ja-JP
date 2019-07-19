---
title: クエリ
seo-title: クエリ
description: クエリ
seo-description: クエリーアクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルターおよび抽出できます。
page-status-flag: 常にアクティブ化されていない
uuid: b3c629fa-370e-481c- b347- fcf9f5a5e847
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: クエリ、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Query{#query}

## 説明 {#description}

![](assets/query.png)

**[!UICONTROL Query]** アクティビティにより、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. このデータは、追加の列に保存され、進行中のワークフローにのみ使用できます。

アクティビティでは、クエリエディターツールが使用されます。This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

**[!UICONTROL Query]** アクティビティは、様々なタイプの用途で使用できます。

* 個人をセグメント化して、メッセージ、オーディエンスなどのターゲットを定義します。
* Adobe Campaignデータベーステーブル全体のデータのエンリッチメント。
* データのエクスポート

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear. デフォルトでは、プロファイルを検索するためにアクティビティが事前設定されています。
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

   For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)

1. **[!UICONTROL Target]** タブで、ルールを定義して組み合わせてクエリを実行します。
1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. このデータは、追加の列に保存され、進行中のワークフローにのみ使用できます。特に、クエリーのターゲティングディメンションにリンクされているAdobe Campaignデータベーステーブルからデータを追加できます。Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

   >[!NOTE]
   >
   >By default, the **[!UICONTROL Remove duplicate rows (DISTINCT)]** option is checked in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Additional data]** tab of the query. **[!UICONTROL Query]** アクティビティに定義されている追加データが多数含まれている場合は、パフォーマンス上の理由からこのオプションの選択を解除することをお勧めします。このオプションのチェックを解除すると、クエリーされたデータに応じて重複が発生する可能性があります。

1. **[!UICONTROL Transition]** このタブで **[!UICONTROL Enable an outbound transition]** は、データがない場合でも、クエリーアクティビティの後にアウトバウンドトランジションを追加できます。

   The outbound transition's segment code can be personalized using a standard expression and events variables (see [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).

1. アクティビティの設定を確認し、ワークフローを保存します。

## Targeting dimensions and resources {#targeting-dimensions-and-resources}

ターゲティングディメンションとリソースを使用して、クエリーを基にして配信のターゲットを決定する要素を定義できます。

ターゲットディメンションは、ターゲットマッピングで定義されます。For more on this, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

### Defining the targeting dimension and resource of a query {#defining-the-targeting-dimension-and-resource-of-a-query}

Targeting dimension and resources are defined when creating a workflow, in the **[!UICONTROL Properties]** tab of a Query activity.

>[!NOTE]
>
>The targeting dimension can also be defined when creating an audience (see [this section](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

ターゲットディメンションとリソースはリンクされます。使用可能なターゲットディメンションは、選択したリソースによって異なります。

For example, for the Resource **[!UICONTROL Profiles (profile)]**, the following targeting dimensions will be available:

![](assets/targeting_dimension2.png)

While for **[!UICONTROL Deliveries (delivery)]**, the list will contain the following targeting dimensions:

![](assets/targeting_dimension3.png)

ターゲットディメンションとリソースを指定すると、クエリで異なるフィルターを使用できます。

**[!UICONTROL Profiles (profile)]** リソースに使用できるフィルターの例:

![](assets/targeting_dimension4.png)

**[!UICONTROL Deliveries (delivery)]** リソースに使用できるフィルターの例:

![](assets/targeting_dimension5.png)

### Using resources different from targeting dimensions {#using-resources-different-from-targeting-dimensions}

デフォルトでは、ターゲット設定ディメンションとリソースは、プロファイルをターゲットに設定します。

ただし、遠隔テーブル内の特定のレコードを検索する場合は、ターゲットディメンションと異なるリソースを使用すると便利です。

**例1:"Welcome back!"というラベルを付けて配信されるプロファイルを識別**&#x200B;します。

* この場合、プロファイルをターゲットにします。We will set the targeting dimension to **[!UICONTROL Profiles (profile)]**.
* 配信ラベルに従って選択したプロファイルをフィルタリングします。We will therefore set the resource to **[!UICONTROL Delivery logs]**. これにより、配信ログテーブルで直接フィルタリングして、より良いパフォーマンスを提供します。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**例2:"Welcome back!"というラベルを付けて配信されなかったプロファイルを識別する**

前述の例では、ターゲットディメンションとは異なるリソースを使用していました。This operation is only possible if you want to find a record that **is present** in the distant table (delivery logs in our example).

If we want to find a record that **is not present** in the distant table (for example, profiles who were not targeted by a specific delivery), you must use the same resource and targeting dimension, as the record will not be present in the distant table (delivery logs).

* この場合、プロファイルをターゲットにします。We will set the targeting dimension to **[!UICONTROL Profiles (profile)]**.
* 配信ラベルに従って選択したプロファイルをフィルタリングします。配信ログテーブルに存在しないレコードを探す際に、配信ログで直接フィルターすることはできません。We will therefore set the resource to **[!UICONTROL Profile (profile)]** and build our query on the profiles table.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)

## Enriching data {#enriching-data}

**[!UICONTROL Additional data]** また **[!UICONTROL Query]****[!UICONTROL Incremental query]****[!UICONTROL Enrichment]** 、このデータのタブを使用すると、ターゲティングされたデータを次のワークフローアクティビティに追加し、利用可能な以下のワークフローアクティビティに転送できます。特に、以下を追加できます。

* 単純なデータ
* 集計
* コレクション

For aggregates and collections, an **[!UICONTROL Alias]** is automatically defined to give a technical ID to a complex expression. このエイリアスは一意である必要があり、集約とコレクションを容易に見つけることができます。わかりやすい名前を付けるように変更できます。

>[!NOTE]
>
>エイリアスは、次の構文ルールを順守する必要があります。英数字と"_"文字のみが認証されます。エイリアスでは大文字と小文字が区別されます。エイリアスは"@"文字で始まる必要があります。"@"の直後の文字は数値ではありません。次に例を示します。@ MyAlias_1and@_1エイリアスが正しい;@ MyAlias#1および@1エイリアスが正しくありません。

追加のデータを追加した後、定義した追加のデータに基づいて条件を作成することで、最初にターゲット設定されたデータにフィルターレベルを適用できます。

>[!NOTE]
>
>By default, the **[!UICONTROL Remove duplicate rows (DISTINCT)]** option is checked in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Additional data]** tab of the query. **[!UICONTROL Query]** アクティビティに定義されている追加データが多数含まれている場合は、パフォーマンス上の理由からこのオプションの選択を解除することをお勧めします。このオプションのチェックを解除すると、クエリーされたデータに応じて重複が発生する可能性があります。

### Adding a simple field {#adding-a-simple-field}

単純なフィールドを追加データとして追加すると、そのフィールドはアクティビティのアウトバウンドトランジションに直接表示されます。これにより、ユーザーはクエリのデータを目的のデータにすることができます。

1. **[!UICONTROL Additional data]** タブから新しい要素を追加します。
1. In the window that opens, in the **[!UICONTROL Expression]** field, select one of the fields available directly in the targeting dimension or in one of the linked dimensions. 式を編集したり、関数を使用したり、ディメンションフィールドから単純な演算（集計を除く）を使用したりできます。

   An **[!UICONTROL Alias]** is automatically created if you edit an expression that is not a simple XPATH path (for example: "Year(&lt;@birthDate&gt;)"). 必要に応じて、変更できます。If you only select one field (for example: "@age"), you do not need to define an **[!UICONTROL Alias]**.

1. Select **[!UICONTROL Add]** to confirm adding the field to the additional data. クエリが実行されると、追加されたフィールドに対応する列がアクティビティのアウトバウンドトランジションに存在します。

![](assets/enrichment_add_simple_field.png)

### Adding an aggregate {#adding-an-aggregate}

集計を使用すると、ターゲットディメンションのフィールドまたはターゲットディメンションにリンクされているディメンションのフィールドから値を計算できます。次に例を示します。プロファイルによって購入された平均金額。

1. **[!UICONTROL Additional data]** タブから新しい要素を追加します。
1. In the window that opens, select the collection that you want to use to create your aggregate in the **[!UICONTROL Expression]** field.

   An **[!UICONTROL Alias]** is created automatically. If you like, you can modify it by going back to the query's **[!UICONTROL Additional data]** tab.

   集計定義ウィンドウが開きます。

1. **[!UICONTROL Data]** タブから集計を定義します。Depending on the type of aggregate selected, only the elements whose data is compatible are available in the **[!UICONTROL Expression]** field. 例えば、合計値は数値データでのみ計算できます。

   ![](assets/enrichment_add_aggregate.png)

   選択したコレクションのフィールドに複数の集計を追加できます。アクティビティのアウトバウンドデータの詳細の列を区別するには、明示的なラベルを定義してください。

   また、各集計に対して自動的に定義されるエイリアスを変更することもできます。

   ![](assets/enrichment_add_aggregate2.png)

1. 必要に応じて、考慮したデータを制限するフィルターを追加できます。

   Refer to the [Filtering added data](../../automating/using/query.md#filtering-added-data) section.

1. Select **[!UICONTROL Confirm]** to add aggregates.

>[!NOTE]
>
>You cannot create an expression containing an aggregate directly from the **[!UICONTROL Expression]** field of the **[!UICONTROL New additional data]** window.

### Adding a collection {#adding-a-collection}

1. **[!UICONTROL Additional data]** タブから新しい要素を追加します。
1. In the window that opens, select the collection that you want to add in the **[!UICONTROL Expression]** field. An **[!UICONTROL Alias]** is created automatically. If you like, you can modify it by going back to the query's **[!UICONTROL Additional data]** tab.
1. Select **[!UICONTROL Add]**. 新しいウィンドウが開き、表示するコレクションデータを絞り込むことができます。
1. **[!UICONTROL Parameters]** タブで、追加するコレクションの行数を選択 **[!UICONTROL Collection]** して定義します。For example, if you want to get the three most recent purchases carried out by each profile, enter "3" in the **[!UICONTROL Number of lines to return]** field.

   >[!NOTE]
   >
   >1以上の数値を入力する必要があります。

1. **[!UICONTROL Data]** タブから、各行に表示するコレクションのフィールドを定義します。

   ![](assets/enrichment_add_collection.png)

1. 必要に応じて、考慮されるコレクションラインを制限するフィルターを追加できます。

   Refer to the [Filtering added data](../../automating/using/query.md#filtering-added-data) section.

1. 必要に応じて、データの並べ替えを定義できます。

   For example, if you have selected 3 lines to return in the **[!UICONTROL Parameters]** tab, and you want to determine the three most recent purchases, you can define a descending sort on the "date" field of the collection that corresponds to the transactions.

1. Refer to the [Sorting additional data](../../automating/using/query.md#sorting-additional-data) section.
1. Select **[!UICONTROL Confirm]** to add the collection.

### Filtering added data {#filtering-added-data}

集計またはコレクションを追加するときに、表示するデータを制限する追加のフィルターを指定できます。

For example, if you want to only process the collection lines of transactions with amounts of 50 dollars and above, you can add a condition on the field corresponding to the transaction amount from the **[!UICONTROL Filter]** tab.

![](assets/enrichment_filter_data.png)

### Sorting additional data {#sorting-additional-data}

クエリーのデータに集計またはコレクションを追加する場合、フィールドの値に基づいて昇順または降順にソートするか、または定義された式に基づいてソートを適用するかを指定できます。

For example, if you want to save only the transaction that was carried out most recently by a profile, enter "1" in the **[!UICONTROL Number of lines to return]** field of the **[!UICONTROL Parameters]** tab, and apply a descending sort on the field corresponding to the transaction date via the **[!UICONTROL Sort]** tab.

![](assets/enrichment_sort_data.png)

### Filtering the targeted data according to additional data {#filtering-the-targeted-data-according-to-additional-data}

Once you have added additional data, a new **[!UICONTROL Output filtering]** tab appears in the **[!UICONTROL Query]**. This tab allows you to apply an additional filter on the data initially targeted in the **[!UICONTROL Target]** tab, by taking into account the added data.

For example, if you have targeted all of the profiles that carried out at least one transaction and an aggregate calculating the average transaction amount carried out for each profile was added to the **[!UICONTROL Additional data]**, you can refine the population initially calculated using this average.

To do this, in the **[!UICONTROL Output filtering]** tab, simply add a condition on this additional data.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)

### Example: personalizing an email with additional data {#example--personalizing-an-email-with-additional-data}

次の例では、クエリに追加のデータタイプを追加し、電子メールでパーソナライゼーションフィールドとして使用することを示しています。

For this example, [custom resources](../../developing/using/data-model-concepts.md) are used:

* **プロファイル** リソースが拡張され、各プロファイルのロイヤルティポイントを保存できるフィールドを追加できるようになりました。
* **トランザクション** リソースが作成され、データベース内のプロファイルによって実行されるすべての購入が識別されます。トランザクションごとに、購入日、価格、製品が保存されます。
* **製品** リソースが作成され、購入できる製品が参照されます。

目的は、少なくとも1つのトランザクションが保存されているプロファイルに電子メールを送信することです。この電子メール経由で、クライアントは最後のトランザクションのリマインダーを受け取り、すべてのトランザクションの概要を確認します。購入された製品数、合計滞在時間の合計。

ワークフローは次のように表示されます。

![](assets/enrichment_example1.png)

1. **[!UICONTROL Query]** 少なくとも1つのトランザクションを実行したプロファイルをターゲットにすることができるアクティビティを追加します。

   ![](assets/enrichment_example2.png)

   From the query's **[!UICONTROL Additional data]** tab, define the different data to be displayed in the final email:

   * The simple field of the **profile** dimension corresponding to the loyalty points. Refer to the [Adding a simple field](../../automating/using/query.md#adding-a-simple-field) section.
   * トランザクションコレクションに基づく2つの集計:購入した製品数と合計支出金額。**[!UICONTROL Data]****Count** および **Sum** 集計を使用して、集計設定ウィンドウのタブから追加できます。Refer to the [Adding an aggregate](../../automating/using/query.md#adding-an-aggregate) section.
   * 滞在時間、日付、最後のトランザクションの製品が返されるコレクション。

      To do this, you have to add the different fields that you want to display from the **[!UICONTROL Data]** tab of the collection configuration window.

      To return only the most recent transaction, you have to enter "1" for the **[!UICONTROL Number of lines to return]** and apply a descending sort on the **Date** field of the collection from the **[!UICONTROL Sort]** tab.

      Refer to the [Adding a collection](../../automating/using/query.md#adding-a-collection) and [Sorting additional data](../../automating/using/query.md#sorting-additional-data) sections.
   ![](assets/enrichment_example4.png)

   If you would like to check that the data is correctly transferred by the activity's outbound transition, start the workflow for the first time (without the **[!UICONTROL Email delivery]** activity) and open the query's outbound transition.

   ![](assets/enrichment_example5.png)

1. **[!UICONTROL Email delivery]** アクティビティを追加します。電子メールコンテンツで、クエリーで計算されたデータに対応するパーソナライゼーションフィールドを挿入します。You can find it via the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer.

   ![](assets/enrichment_example3.png)

ワークフローを実行できるようになりました。クエリをターゲットにしたプロファイルは、トランザクションから計算されたデータを含むパーソナライズされた電子メールを受け取ります。

## Query samples {#query-samples}

### Targeting on simple profile attributes {#targeting-on-simple-profile-attributes}

次の例は、ロンドン在住の18才から30才までの男性をターゲットにするように設定されたクエリアクティビティを示しています。

![](assets/query_sample_1.png)

### Targeting on email attributes {#targeting-on-email-attributes}

次の例は、電子メールアドレスドメイン"orange.co.uk"を使用してプロファイルをターゲット設定するように設定されたクエリーアクティビティを示しています。

![](assets/query_sample_emaildomain.png)

次の例は、電子メールアドレスが提供されているプロファイルをターゲットに設定したクエリーアクティビティを示しています。

![](assets/query_sample_emailnotempty.png)

### Targeting profiles whose birthday is today {#targeting-profiles-whose-birthday-is-today}

次の例は、誕生日が今日のプロファイルをターゲットに設定したクエリーアクティビティを示しています。

1. Drag the **[!UICONTROL Birthday]** filter in your query.

   ![](assets/query_sample_birthday.png)

1. **[!UICONTROL Filter type]** 宛先 **[!UICONTROL Relative]** を設定して選択 **[!UICONTROL Today]**&#x200B;します。

   ![](assets/query_sample_birthday2.png)

### Targeting profiles who opened a specific delivery {#targeting-profiles-who-opened-a-specific-delivery}

次の例は、ラベル"Summer Time"を使用して配信を開いたプロファイルをフィルターするように設定されたクエリーアクティビティを示しています。

1. Drag the **[!UICONTROL Opened]** filter in your query.

   ![](assets/query_sample_opened.png)

1. Select the delivery then click **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

### Targeting profiles for whom deliveries failed for a specific reason {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

次の例は、メールボックスがいっぱいになったために配信が失敗したプロファイルをフィルターするように設定されたクエリーアクティビティを示しています。This query is only available for users with administration rights and belonging to the **[!UICONTROL All (all)]** organizational units (see [this section](../../administration/using/organizational-units.md)).

1. Select the **[!UICONTROL Delivery logs]** resource in order to filter directly in the delivery log table (see [Using resources different from targeting dimensions](../../automating/using/query.md#using-resources-different-from-targeting-dimensions)).

   ![](assets/query_sample_failure1.png)

1. Drag the **[!UICONTROL Nature of failure]** filter in your query.

   ![](assets/query_sample_failure2.png)

1. ターゲットにする失敗のタイプを選択します。**[!UICONTROL Mailbox full]**&#x200B;この場合は、

   ![](assets/query_sample_failure3.png)

### Targeting profiles not contacted during the last 7 days {#targeting-profiles-not-contacted-during-the-last-7-days}

次の例は、最近7日間に接続されていないプロファイルをフィルターするように設定されたクエリーアクティビティを示しています。

1. Drag the **[!UICONTROL Delivery logs (logs)]** filter in your query.

   ![](assets/query_sample_7days.png)

   Select **[!UICONTROL Does not exist]** in the drop-down list, then drag the **[!UICONTROL Delivery]** filter.

   ![](assets/query_sample_7days1.png)

1. 次のようにフィルターを設定します。

   ![](assets/query_sample_7days2.png)

### Targeting profiles who clicked a specific link {#targeting-profiles-who-clicked-a-specific-link-}

1. Drag the **[!UICONTROL Tracking logs (tracking)]** filter in your query.

   ![](assets/query_sample_trackinglogs.png)

1. **[!UICONTROL Label (urlLabel)]** フィルターをドラッグします。

   ![](assets/query_sample_trackinglogs2.png)

1. **[!UICONTROL Value]** フィールドに、配信にリンクを挿入するときに定義されたラベルを入力し、確認します。

   ![](assets/query_sample_trackinglogs3.png)

