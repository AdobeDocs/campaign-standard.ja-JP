---
title: 高度な式の編集
description: Query Editionウィザードを使用すると、高度な式を定義できます。
page-status-flag: 非活性化の
uuid: a635f999-27ce-41e0-a88c-8a3882e31efe
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: filtering-data
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 高度な式の編集{#advanced-expression-editing}

## 高度な式の編集について {#about-advanced-expression-editing}

式を編集する場合は、手動で条件を入力してルールを作成します。

このモードでは、高度な機能を使用できます。 これらの関数を使用すると、日付、文字列、数値フィールド、並べ替えなどの特定のクエリを実行する際に使用する値を操作できます。

また、式の編集時にイベント変数を使用することもできます。 詳しくは、「イベント変数を使用したアクティビティ [のカスタマイズ」の節を参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) い。

式は次の目的で編集できます。

* ルールの追加時に使用できるオ **[!UICONTROL Advanced mode]** プションを使用して、クエリを定義します。

   ![](assets/expression_editor_2.png)

* ワークフロー内の式を編集します。 例えば、アクティビティに追加のデータを追加する場合です。
* 表示条件を編集して、HTMLコンテンツエディターでのブロックの表示方法を定義します。 この場合、式はJavaScript形式で編集され、標準として高度な関数を使用することはできません。

## 式の編集 {#edit-an-expression}

Advanced expression editionでは、ニーズに合った式を手動で定義できます。

式の編集は、電子メールの作成時にオーディエンスウィンドウで使用したり、ワークフローの作成時にクエリアクティビティで使用したりできます。

1. 「高度な式の編集について」で詳しく説明している方法の1つを使用して、式の [編集ウィンドウにアクセスします](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) 。 次の要素が含まれます。

   * 式が定義されている入力フィールド。
   * 式で使用でき、クエリーのターゲットディメンションに対応する、使用可能なフィールドのリストです(ディメンションとリソ [ースのターゲット](../../automating/using/query.md#targeting-dimensions-and-resources))。
   * カテゴリ別に並べ替えた、使用可能な関数のリスト。
   ![](assets/expression_editor_1.png)

1. 式を編集するには、対応するフィールドに式を直接入力するか、使用可能なフィールドと関数のリストを使用します。

   フィールドまたは式をダブルクリックすると、カーソルが置かれた式に追加されます。

   ワークフローのイベント変数を使用して式を作成できます。 詳しくは、「イベント変数を使用したアクティビティ [のカスタマイズ」の節を参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) い。

1. 必要に応じて、ルールに特定の名前を付けます。 入力した名前は、クエリエディターワークスペースにルール名として表示されます。

式を編集すると、必要に応じて訪問者をターゲット設定するために、オーディエンス式をパーソナライズできます。

**関連トピック：**

* [式の構文](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [関数のリスト](../../automating/using/list-of-functions.md)

## 式の構文 {#expression-syntax}

### 標準構文 {#standard-syntax}

標準式は、次の構文要素を考慮した1つまたは複数の条件で構成されます。

* 各条件は、&lt;value1&gt; &lt;comparison operator&gt; **&lt;value2&gt;の形式で、次のようになります** 。

   * **&lt;value1&gt;はフィールド** または関数です。 例えば、 **プロファイルが作成された日付の場合は** 「@created」、プロファイルが作成された年の場合は「 **Year(@created)** 」です。
   * **&lt;comparison operator&gt;は** 、比較演算子の節に示す演算子の1 [つです](../../automating/using/advanced-expression-editing.md#comparison-operators) 。 この演算子は、&lt;value1&gt;と **&lt;value2&gt;の間の比較** 方法 **を定義します**。
   * **&lt;value2&gt;は** 、手動で入力したフィールド、関数、または値です。
   >[!NOTE]
   >
   >&lt;value1&gt; **と&lt;value2&gt;の型のデ** ータは同じである必要があります **** 。 例えば、&lt;value1&gt;が **日付の場合** 、 **&lt;value2&gt;も日付である必要があります** 。

* 複数の条件を使用する場合は、論理演算子を使用して組み合わせることができます。

   * **[!UICONTROL AND]**:2つの条件が交差します。
   * **[!UICONTROL OR]**:2つの条件が組み合わされます。

次に例を示します。

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

この例では、作成日が現在の月と年に設定されているプロファイルがターゲットになります。

### JavaScript構文 {#javascript-syntax}

HTMLコンテンツエディターのテキストタイプブロックの表示条件を定義する場合は、式とJavaScriptタイプ構文を使用する必要があります。

JavaScript式は1つ以上の条件で構成され、次の構文要素を使用します。

* 各条件は、&lt;context&gt; &lt;comparison operator&gt; **&lt;value2&gt;の形式で、次のようになります** 。

   * **&lt;context&gt;は** 、コンテキストを指定できるフィールドまたは関数です。 例えば、 **context.profileとします。プロファイルの** 電子メールアドレスの場合は@email、プロファイルの名の文字数の場合は **context.profile.firstName.length()** 。
   * **&lt;comparison operator&gt;は** 、比較演算子の節に示す演算子の1 [つです](../../automating/using/advanced-expression-editing.md#comparison-operators) 。 この演算子は、&lt;context&gt;と **&lt;value** 2&gt;の間の比較方法 **を定義します**。
   * **&lt;value2&gt;は** 、手動で入力したフィールド、関数、または値です。
   >[!NOTE]
   &lt;context&gt; **と&lt;value2&gt;の型のデー** タは同じでなければなりません **** 。 例えば、&lt;context&gt;が日 **付の場合** 、 **&lt;value2&gt;も日付である必要があります** 。

* 複数の条件を使用する場合は、論理演算子を使用して組み合わせることができます。

   * **[!UICONTROL &&]**:2つの条件が交差します。
   * **[!UICONTROL ||]**:2つの条件が組み合わされます。

次に例を示します。

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

この例では、21歳を超え、名が指定されているプロファイル( **firstName** フィールドに少なくとも1文字含まれていることを示します)。

## 比較演算子 {#comparison-operators}

一部のルールでは、クエリーエディターで値を選択して条件を定義できます。

条件は、次の演算子のいずれかを使用して値にリンクする必要があります。

<table> 
 <thead> 
  <tr> 
   <th> 演算子<br /> </th> 
   <th> 標準構文<br /> </th> 
   <th> JavaScript構文<br /> </th> 
   <th> 説明<br /> </th> 
   <th> 例 ：<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">次と等しい</span> <br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> 最初の値は、2番目の値と完全に同じである必要があります。<br /> </td> 
   <td> <strong>@lastName = Martinは</strong> 、姓が「Martin」で、これらの同一の文字のみを含むプロファイルを取得します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">より大きい</span> <br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> 最初の値は、分類的に2番目の値より大きい必要があります。<br /> </td> 
   <td> <strong>@age &gt; 50</strong> は、「50」より古いプロファイル、「51」、「52」などを取得します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">より小さい</span> <br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> 最初の値は、分類的に2番目の値より小さい必要があります。<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)は、100日前にデータベースで作成されたすべてのプロファイルを取得します。</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次よりも大きいか等しい</span> <br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> 1つ目の値は2つ目の値以上である必要があります。<br /> </td> 
   <td> <strong>@age &gt;= 30は</strong> 、30歳以上のプロファイルを取得します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次よりも小さいか等しい</span> <br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> 1つ目の値は2つ目の値以下である必要があります。<br /> </td> 
   <td> <strong>@age &lt;= 60の場合、60歳以下の</strong> プロファイルが取得されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">異な </span> る <br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> 1つ目の値は2つ目の値とは異なる必要があります。<br /> </td> 
   <td> <strong>@language !=英語</strong> ：英語として定義されていないプロファイルを取得します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次を含む</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> なし<br /> </td> 
   <td> 最初の値には2番目の値が含まれている必要があります。<br /> </td> 
   <td> <strong>@domain IN mail</strong>。 ここで、'mail'値を持つすべてのドメイン名が結果に返されます。 その結果、返される結果の一部は「gmail.com」ドメイン名で構成されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">いいね</span> ! <br /> </td> 
   <td> LIKE<br /> </td> 
   <td> なし<br /> </td> 
   <td> 「<span class="uicontrol">次に類似</span>」は、「<span class="uicontrol">次を含む</span>」演算子と非常によく似ています。検索する値に <span class="uicontrol">%</span> ワイルドカード文字を挿入できます。<br /> </td> 
   <td> <strong>@lastName LIKEマート%n</strong>. ここで、置換文字 <strong>%</strong> は「冗談」として、スペルが正しくないという仮定の場合に「Martin」という名前を見つけます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">次に類似しない</span> <br /> </td> 
   <td>  NOT<br /> </td> 
   <td> なし<br /> </td> 
   <td> 「<span class="uicontrol">次に類似</span>」と似ています。入力した値を元に戻すことはできません。 この演算子でも、入力した値に <span class="uicontrol">％</span> ワイルドカード文字が含まれている必要があります。<br /> </td> 
   <td> <strong>@lastName NOT Smi%h</strong>。 ここで、受信者は「Smi%h」という名前に対応します（Smithなど）。が返されない場合、<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">空である</span> <br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> なし<br /> </td> 
   <td> 最初の値は空の値に対応している必要があります。<br /> </td> 
   <td> <strong>@mobilePhone IS NULLは、携帯電話番号が指定されていないすべてのプロファイルを取得します。</strong><br /> </td> 
  </tr> 
 </tbody> 
</table>

