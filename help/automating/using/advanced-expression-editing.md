---
title: 詳細式の編集
seo-title: 詳細式の編集
description: 詳細式の編集
seo-description: クエリエディションウィザードでは、高度な式を定義できます。
page-status-flag: 常にアクティブ化されていない
uuid: a635f999-27ce-41e0- a88c-8a3882e31efe
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: filtering- data
discoiquuid: 4375153c-0621-4d4c- bfcc-66d157f04f6c
context-tags: queryFilter， overview;オーディエンス、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Advanced expression editing{#advanced-expression-editing}

## About advanced expression editing {#about-advanced-expression-editing}

式を編集するには、条件を手動で入力することが必要です。

このモードでは、高度な関数を使用できます。これらの関数を使用すると、日付、文字列、数値フィールド、並べ替えなどの特定のクエリを実行するために使用する値を操作できます。

また、式の編集時にイベント変数を使用することもできます。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

式は次の順序で編集できます。

* Define a query, via the **[!UICONTROL Advanced mode]** option which is available when a rule is added.

   ![](assets/expression_editor_2.png)

* ワークフローで式を編集します。例えば、アクティビティにデータを追加する場合などです。
* 表示条件を編集して、HTMLコンテンツエディターのブロックの表示方法を定義します。この場合、式はJavaScript形式で編集され、高度な関数の使用は標準として提供されません。

## Edit an expression {#edit-an-expression}

アドバンス式のエディションでは、ニーズに対応する式を手動で定義できます。

編集式は、電子メールの作成中、またはワークフローの作成中に、オーディエンスウィンドウで使用できます。

1. Access the expression editing window via one of the methods detailed in the [About advanced expression editing](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) section. これには、次の要素が含まれます。

   * 式が定義されている入力フィールドです。
   * The list of available fields that can be used in the expression and correspond to the targeting dimension of the query (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * 使用可能な関数のリスト。カテゴリ別に並べ替えられます。
   ![](assets/expression_editor_1.png)

1. 対応するフィールドに直接式を入力するか、使用可能なフィールドと関数のリストを使用して式を編集します。

   フィールドまたは数式をダブルクリックすると、カーソルが置かれている式に追加されます。

   ワークフローのevents変数を使用して式を作成できます。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. 必要に応じてルールに特定の名前を付けます。入力した名前は、クエリエディターワークスペースにルール名として表示されます。

式を編集することで、必要に応じて訪問者をターゲット設定するオーディエンス式をパーソナライズできます。

**関連トピック:**

* [式の構文](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [関数のリスト](../../automating/using/list-of-functions.md)

## Expression Syntax {#expression-syntax}

### Standard syntax {#standard-syntax}

標準式は、以下の構文要素を考慮した1つまたは複数の条件で構成されます。

* Each condition takes the form of **&lt;value1&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; value1&gt;** はフィールドまたは関数です。For example **@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt;比較演算子&gt;** は [、比較演算子](../../automating/using/advanced-expression-editing.md#comparison-operators) セクションに一覧表示されている演算子の1つです。This operator defines the comparison method between **&lt;value1&gt;** and **&lt;value2&gt;**.
   * **&lt; value2&gt;** は、フィールド、関数、または手動で入力された値です。
   >[!NOTE]
   >
   >**&lt; value1&gt;** および **&lt; value2&gt;** タイプデータは同じである必要があります。**例えば、&lt; value1&gt;** が日付の場合、 **&lt; value2&gt;** も日付である必要があります。

* 複数の条件を使用する場合は、論理演算子を使用して組み合わせることができます。

   * **[!UICONTROL AND]**:2つの条件が交差しています。
   * **[!UICONTROL OR]**:2つの条件が組み合わされます。

次に例を示します。

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

この例では、作成日が現在の月と年のプロファイルをターゲットにしています。

### JavaScript syntax {#javascript-syntax}

HTMLコンテンツエディターのテキストタイプブロックの視認性条件を定義するときは、JavaScriptタイプの構文を使用して式を使用する必要があります。

JavaScript式は1つまたは複数の条件で構成され、次の構文要素を使用します。

* Each condition takes the form of **&lt;context&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; context&gt;** は、コンテキストを指定するためのフィールドまたは関数です。**例えば、context. profileとします。@email** for a profile's email address or **context.profile.firstName.length()** for the number of characters of a profile's first name.
   * **&lt;比較演算子&gt;** は [、比較演算子](../../automating/using/advanced-expression-editing.md#comparison-operators) セクションに一覧表示されている演算子の1つです。This operator defines the comparison method between **&lt;context&gt;** and **&lt;value2&gt;**.
   * **&lt; value2&gt;** は、フィールド、関数、または手動で入力された値です。
   >[!NOTE]
   **&lt; context&gt;** および **&lt; value2&gt;** タイプデータは同じである必要があります。**例えば、&lt; context&gt;** が日付の場合、 **&lt; value2&gt;** も日付である必要があります。

* 複数の条件を使用する場合は、論理演算子を使用して組み合わせることができます。

   * **[!UICONTROL &&]**:2つの条件が交差しています。
   * **[!UICONTROL ||]**:2つの条件が組み合わされます。

次に例を示します。

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In this example, profiles older than 21 years of age and whose first name has been provided (symbolized by the fact that the **firstName** field contains at least one character).

## Comparison operators {#comparison-operators}

一部のルールでは、クエリーエディターで条件を定義する値を選択できます。

条件は、次の演算子のいずれかを使用して値にリンクする必要があります。

<table> 
 <thead> 
  <tr> 
   <th> 演算子<br /> </th> 
   <th> Standard syntax<br /> </th> 
   <th> JavaScript syntax<br /> </th> 
   <th> 説明<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">次と等しい</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> The first value must be completely identical to the second value.<br /> </td> 
   <td> <strong>@ lastName= Martin</strong> は、姓が"Martin"で、同一の文字のみを持つプロファイルを取得します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次よりも大きい</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> The first value must categorically be more than the second value.<br /> </td> 
   <td> <strong>@ age&gt;50</strong> を指定すると、50より古いプロファイルが取得され、"51"、"51"、"52"などが返されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次より小さい</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> The first value must categorically be less than the second value.<br /> </td> 
   <td> <strong>@ created&lt; daysago（100）</strong> を作成すると、データベースで作成されたすべてのプロファイルが100日前に取得されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次よりも大きいか等しい</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> The first value must be more than or equal to the second value.<br /> </td> 
   <td> <strong>@ age&gt;=30</strong> は30歳以上のプロファイルを取得します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次よりも小さいか等しい</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> The first value must be less than or equal to the second value.<br /> </td> 
   <td> <strong>@ age&lt;=60</strong> は60才以下のプロファイルを取得します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">異なる </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> The first value must be different from the second value.<br /> </td> 
   <td> <strong>@ language!= English</strong> retrieves profiles that have not been defined as English speaking.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次を含む</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must contain the second value.<br /> </td> 
   <td> <strong>@ domain INメール</strong>。ここでは、"mail"値を持つすべてのドメイン名が結果に返されます。Consequently, the 'gmail.com' domain name will make up part of the returned results.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">いいね!</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">「いい</span> ね!»は?«次を含む<span class="uicontrol"></span>It lets you insert a <span class="uicontrol">%</span> wild card character in the value that is being searched.<br /> </td> 
   <td> <strong>@ lastName LIKE smine% n</strong>.Here, the substitution character <strong>%</strong> serves as a "joker" to find the name "Martin" in the hypothetical case that the spelling is not correct.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">好ましくない</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. 入力した値を復元することはできません。Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@ lastName NOT prop% h</strong>.ここでは、受信者は"Partners% h"（Smithなど）に対応しています。are not returned as a result.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">空の場合</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must correspond to an empty value.<br /> </td> 
   <td> <strong>@ MobilePhone IS NULL</strong> は、携帯電話番号が提供されていないすべてのプロファイルを取得します。<br /> </td> 
  </tr> 
 </tbody> 
</table>

