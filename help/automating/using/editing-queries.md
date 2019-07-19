---
title: クエリーの編集
seo-title: クエリーの編集
description: クエリーの編集
seo-description: 事前定義済みのフィルターとルールに基づいて、母集団を構築します。
page-status-flag: 常にアクティブ化されていない
uuid: a49c7739- a96c-45cb-9ac5-1ce299161a97
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: filtering- data
discoiquuid: 84306a1e-0d9f-44cc-88a7-36d7e5b4da1f
context-tags: queryFilter， overview;オーディエンス、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Editing queries{#editing-queries}

## About query editor {#about-query-editor}

クエリーエディターは、Adobe Campaignデータベースに含まれるデータをフィルターするためのウィザードです。

この機能により、事前定義済みのフィルターやルールにより、受信者をより的確にターゲット設定することができます。

いくつかのアプリケーション機能では、次のものが使用されます。

* **クエリ** タイプ **オーディエンスの作成**
* **電子メール** ターゲットの定義
* **ワークフロー** アクティビティでの母集団の定義

## Query editor interface {#query-editor-interface}

The query editor is made up of a **Palette** and a **Workspace**.

![](assets/query_editor_overview.png)

### Palette {#palette}

エディターの左側にあるパレットは2つのタブに分かれており、要素をテーマブロックに分割しています。これらのタブは次のとおりです。

* **デフォルト**&#x200B;で使用可能なショートカット。またはインスタンス管理者によって作成されます。以下に、フィールド、ノード、グループ、1対1のリンク、1- Nリンク、その他の定義済みフィルターを示します。
* The **Explorer** which allows you to access all available fields in the target resource: nodes, grouping elements, links (1-1 and 1-N).

クエリーを設定するには、タブに含まれる要素をワークスペースに移動し、それをワークスペースに移動する必要があります。Depending on the targeting dimension selected (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)), you can:

* オーディエンスまたはプロファイルを1つずつ選択
* 定義済みフィルターの使用
* 選択したフィールドの単純なルールを定義する
* 特定のフィールドに関数を適用できる高度なルールの定義

### Workspace {#workspace}

ワークスペースは中央のゾーンで、ルール、オーディエンスおよび定義済みのフィルターをパレットから追加して、組み合わせることができます。

When you move an element from the palette into the workspace, a new window opens and you can start [Creating queries](../../automating/using/editing-queries.md#creating-queries).

## Creating queries {#creating-queries}

クエリエディターを使用して、メッセージ内のオーディエンスまたはテストプロファイル、ワークフローの母集団、およびクエリタイプオーディエンスを定義できます。

Queries can be defined in the **[!UICONTROL Audience]** window while creating a delivery or in a **Query** activity while creating a workflow.

1. パレットからワークスペースに要素を移動します。ルールを編集するウィンドウが開きます。

   * For a string or numerical **field**, specify the comparison operator and the value.

      ![](assets/query_editor_audience_definition2.png)

   * For a date or date and time **field**, you can choose to define a specific date, a range between two dates, or a period relative to the query's execution date.

      ![](assets/query_editor_date_field.png)

   * For a Boolean **field**, check the boxes linked to the possible values for the field.
   * **グループ** 化フィールドでは、ルールを作成するグループ化フィールドを選択し、他のフィールドと同じ方法で条件を定義します。

      ![](assets/query_editor_audience_definition4.png)

   * **別のデータベースリソースと1対1** のリンクの場合は、ターゲット設定されているテーブルから直接値を選択します。

      ![](assets/query_editor_audience_definition5.png)

   * For a **1-N** link with another database resource, you can define a sub-query on the fields of this second resource.

      サブ条件を指定する必要はありません。

      For example, you can only select the **[!UICONTROL Exists]** operator on the profile tracking logs and approve the rule. ルールは、トラッキングログが存在するすべてのプロファイルを返します。

      ![](assets/query_editor_audience_definition6.png)

   * **事前定義済みのフィルター**&#x200B;の場合は、提供する条件に応じて、「いいね!"を入力または選択します。

      管理者は、複雑なクエリーと繰り返しクエリーを容易にするフィルターを作成できます。これらは事前設定されたルールの形式でクエリエディターに表示され、ユーザーが実行する必要のあるステップ数を制限します。

      ![](assets/query-editor_filter_email-audience_filter.png)

1. ルールの名前を指定できます。これは、ワークスペースにルール名として表示されます。ルールに名前が付けられていない場合は、条件の自動説明が表示されます。
1. ワークスペース要素を組み合わせるには、相互にロックして異なるグループやグループレベルを作成します。その後、論理演算子を選択して、同じレベルの要素を組み合わせることができます。

   * **[!UICONTROL AND]**:2つの条件の共通部分。各条件に一致する要素のみが考慮されます。
   * **[!UICONTROL OR]**:2つの条件の統合。少なくとも2つの条件のいずれかに一致する要素が考慮されます。
   * **[!UICONTROL EXCEPT]**:除外条件を使用します。最初の条件に一致する要素も、2つ目の条件に一致する場合を除き考慮されます。

1. You can now calculate and preview the number of elements targeted by your query using the ![](assets/count.png) and ![](assets/preview.png) buttons from the action bar.

   ![](assets/query_editor_combining_rules.png)

クエリの要素を変更する場合は、編集アイコンをクリックします。ルールは以前に設定されたとおりに開かれ、必要な調整を行うことができます。

クエリが作成および定義されるので、配信をパーソナライズするために母集団を構築できます。

**関連トピック:**

* [高度な関数](../../automating/using/advanced-expression-editing.md)
* [フィルターの定義](../../developing/using/configuring-filter-definition.md)

