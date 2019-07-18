---
title: 増分クエリ
seo-title: 増分クエリ
description: 増分クエリ
seo-description: 増分クエリーアクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルターおよび抽出できます。
page-status-flag: 常にアクティブ化されていない
uuid: 73b42422- e815-43ef-84c0-97c4433ccc98
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: 80961e73-42ec-463a-8496- cff69fab0475
context-tags: incremental， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15bba7a6f76cbd17b07f1243075da0832619278b

---


# Incremental query{#incremental-query}

## 説明 {#description}

![](assets/incremental.png)

**[!UICONTROL Incremental query]** アクティビティにより、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。このアクティビティが実行されるたびに、前回の実行の結果は除外されます。これにより、新しい要素のみをターゲットにすることができます。

You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. このデータは、追加の列に保存され、進行中のワークフローにのみ使用できます。

アクティビティでは、クエリエディターツールが使用されます。This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

An **[!UICONTROL Incremental query]** has to be linked to a **[!UICONTROL Scheduler]** in order to define the execution frequency of the workflow, and therefore the query.

**[!UICONTROL Processed data]** このアクティビティに固有のタブは、必要に応じてアクティビティの以前の実行の結果を表示できます。

**[!UICONTROL Incremental query]** アクティビティは、様々なタイプの用途で使用できます。

* 個人をセグメント化して、メッセージ、オーディエンスなどのターゲットを定義します。
* データのエクスポート

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Incremental query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

1. **[!UICONTROL Target]** タブで、ルールを定義して組み合わせてクエリを実行します。
1. **[!UICONTROL Processed data]** タブで、ワークフローの次の実行に使用する増分モードを選択します。

   * **[!UICONTROL Use the exclusion of the results of previous executions]**:新しい実行ごとに前回の実行の結果が除外されます。
   * **[!UICONTROL Use a date field]**:次の実行では、選択した日付フィールドが **[!UICONTROL Incremental query]** アクティビティの最後の実行日以上になった結果を考慮します。**[!UICONTROL Properties]** タブで選択したリソースに関連する日付フィールドを選択できます。ログデータなどの大きなリソースをクエリーする際に、このモードのパフォーマンスが向上しました。

      ワークフローの最初の実行後、次の実行時に使用される最後の実行日がこのタブに表示されます。ワークフローが実行されるたびに自動的に更新されます。必要に応じて新しい入力を手動で入力することで、この値を上書きできます。
   >[!NOTE]
   >
   >**[!UICONTROL Use a date field]** このモードでは、選択した日付フィールドに応じて柔軟性が高まります。例えば、選択したフィールドが修正日に対応している場合、日付フィールドモードでは最近更新されたデータを取得できますが、他のモードでは、前回の実行でターゲット設定されていた記録を除外するだけで、ワークフローの最後の実行以降に変更された記録が除外されます。

   ![](assets/incremental_query_usedatefield.png)

1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. このデータは、追加の列に保存され、進行中のワークフローにのみ使用できます。特に、クエリーのターゲティングディメンションにリンクされているAdobe Campaignデータベーステーブルからデータを追加できます。Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.
1. アクティビティの設定を確認し、ワークフローを保存します。

## Enriching data {#enriching-data}

Just as for a query, you can enrich the data from an **[!UICONTROL Incremental query]**. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

## Example: incremental query on subscribers to a service {#example--incremental-query-on-subscribers-to-a-service}

The following example shows the configuration of an **[!UICONTROL Incremental query]** activity which filters the profiles in the Adobe Campaign database that are subscribed to the **Running Newsletter** service, to send them a welcome email containing a promo code.

ワークフローは次の要素で構成されています。

![](assets/incremental_query_example1.png)

* **[!UICONTROL Scheduler]** アクティビティ（午前7時にワークフローを実行するためのアクティビティ）。

   ![](assets/incremental_query_example2.png)

* **[!UICONTROL Incremental query]** アクティビティは、最初の実行時に現在のすべての加入者をターゲットにし、次の実行中にその週の新規登録者のみをターゲットとします。

   ![](assets/incremental_query_example3.png)

* **[!UICONTROL Email delivery]** アクティビティ。ワークフローは週に1度実行されますが、送信される電子メールの集計や、1週間だけではなく、1か月の間のレポート生成などの結果を集計できます。

   To do this, choose to create a **[!UICONTROL Recurring email]** here regrouping the emails and the results **[!UICONTROL By month]**.

   電子メールのコンテンツを定義し、ウェルカムプロモーションコードを挿入します。

   For more on this, refer to the [Email delivery](../../automating/using/email-delivery.md) and [Defining email content](../../designing/using/about-personalization.md) sections.

次に、ワークフローの実行を開始します。毎週、新規登録者にプロモコードを含むお知らせメールが届きます。

## Example: incremental query on delivery logs {#example--incremental-query-on-delivery-logs}

**[!UICONTROL Incremental query]** アクティビティを使用して、ファイルに新しいログを定期的にエクスポートできます。これは、外部のレポートまたはBIツールにログデータを使用する場合に便利です。

A complete example is available in the [Exporting logs](../../automating/using/exporting-logs.md) section.
