---
title: 外部パラメーターを使用したワークフローのカスタマイズ
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8c1a47ed-3467-4fcd-8747-86f0e8f15cec
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---

# 外部パラメーターを使用したワークフローのカスタマイズ {#customizing-a-workflow-with-external-parameters}

ワークフローがトリガーされると、パラメーターがイベント変数に取り込まれ、ワークフローのアクティビティをカスタマイズするために使用できます。

例えば、**[!UICONTROL Read audience]** アクティビティで読み取るオーディエンスや **[!UICONTROL Transfer file]** アクティビティで転送するファイルの名前などを定義するために使用できます。 （[&#x200B; このページ &#x200B;](../../automating/using/customizing-workflow-external-parameters.md)）を参照してください。

## イベント変数の使用 {#using-events-variables}

イベント変数は、[&#x200B; 標準構文 &#x200B;](../../automating/using/advanced-expression-editing.md#standard-syntax) を遵守する必要がある式内で使用されます。

イベント変数を使用する構文は、次の形式に従い、**[!UICONTROL External signal]** アクティビティで定義されているパラメーターの名前を使用する必要があります（[&#x200B; 外部シグナルアクティビティでのパラメーターの宣言 &#x200B;](../../automating/using/declaring-parameters-external-signal.md) を参照）。

```
$(vars/@parameterName)
```

この構文では、**$** 関数は **string** データ型を返します。 別のタイプのデータを指定する場合は、次の関数を使用します。

* **$long**：整数。
* **$float**:10 進数です。
* **$boolean**: true/false です。
* **$datetime**: タイムスタンプ。

アクティビティで変数を使用する場合、インターフェイスにはそれを呼び出すためのヘルプが表示されます。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png)：ワークフローで使用可能なすべての変数の中からイベント変数を選択します。

  ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png)：変数と関数を組み合わせて式を編集します（[&#x200B; このページ &#x200B;](../../automating/using/advanced-expression-editing.md) を参照）。

  ![](assets/wkf_test_activity_variables_expression.png)

  このリストには、複雑なフィルタリングを実行できる関数が表示されます。 これらの関数について詳しくは、[&#x200B; この節 &#x200B;](../../automating/using/list-of-functions.md) を参照してください。

  さらに、以下の関数を使用できます。これらの関数は以下のすべてのアクティビティで利用でき、外部パラメーターを指定してワークフローを呼び出した後に、イベント変数を使用できます（[&#x200B; この節 &#x200B;](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables) を参照）。

  | 名前 | 説明 | 構文 |
  | ---------|----------|---------|
  | 終了 | 文字列（1 番目のパラメーター）が特定の文字列（2 番目のパラメーター）で終わるかどうかを示します。 | EndWith （&lt;String>,&lt;String>） |
  | startWith | 文字列（1 番目のパラメーター）が特定の文字列（2 番目のパラメーター）で開始するかどうかを示します。 | startWith （&lt;String>,&lt;String>） |
  | 抽出 | 区切り文字を使用して、文字列の最初の文字を返します。 | Extract （&lt;String>,&lt;Separator>） |
  | ExtractRight | 区切り文字を使用して、文字列の最後の文字を返します。 | ExtractRight （&lt;String>,&lt;Separator>） |
  | DateFormat | 2 番目のパラメーターで指定された形式を使用して日付を書式設定します（例：&#39;%4Y%2M%2D&#39;） | DateFormat （&lt;Date>,&lt;Format>） |
  | FileName | ファイルパスの名前を返します。 | FileName （&lt;String>） |
  | FileExt | ファイルパスの拡張子を返します。 | FileExt （&lt;String>） |
  | GetOption | 指定された関数の値を返します。 | GetOption （&lt;optionName>） |
  | IsNull | 文字列または日付が null かどうかを示します。 | IsNull （&lt;String/date>） |
  | UrlUtf8Encode | URL を UTF8 でエンコードします。 | UrlUtf8Encode （&lt;String>） |

## イベント変数を使用したアクティビティのカスタマイズ {#customizing-activities-with-events-variables}

イベント変数を使用して、以下の節に示すように、複数のアクティビティをカスタマイズできます。 アクティビティから変数を呼び出す方法について詳しくは、[&#x200B; この節 &#x200B;](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables) を参照してください。

**[!UICONTROL Read audience]** アクティビティ：イベント変数に基づいて、ターゲットにするオーディエンスを定義します。 アクティビティの使用方法について詳しくは、[&#x200B; この節 &#x200B;](../../automating/using/read-audience.md) を参照してください。

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** クティビティ：イベント変数に基づいて条件を作成します。 アクティビティの使用方法について詳しくは、[&#x200B; この節 &#x200B;](../../automating/using/test.md) を参照してください。

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** クティビティ：イベント変数に基づいて転送するファイルをカスタマイズします。 アクティビティの使用方法について詳しくは、[&#x200B; この節 &#x200B;](../../automating/using/transfer-file.md) を参照してください。

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** クティビティ：イベント変数と関数を組み合わせた式を使用して、クエリ内でパラメーターを参照できます。 これを行うには、ルールを追加し、「**[!UICONTROL Advanced mode]**」リンクをクリックして式編集ウィンドウにアクセスします（[&#x200B; 高度な式編集 &#x200B;](../../automating/using/advanced-expression-editing.md) を参照）。

アクティビティの使用方法について詳しくは、[&#x200B; この節 &#x200B;](../../automating/using/query.md) を参照してください。

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** アクティビティ：イベント変数に基づいて配信をパーソナライズします。

>[!NOTE]
>
>配信パラメーターの値は、配信が準備されるたびに取得されます。
>
>繰り返し配信の準備は、配信 **集計期間** に基づいて行われます。 例えば、集計期間が「日別」の場合、配信は 1 日に 1 回だけ再準備されます。 配信パラメーターの値が日中に変更された場合、その値は既に 1 回準備されているので、配信では更新されません。
>
>1 日に複数回ワークフローを呼び出す予定がある場合は、[!UICONTROL No aggregation] オプションを使用して、配信パラメーターが毎回更新されるようにします。 繰り返し配信の設定について詳しくは、[&#x200B; この節 &#x200B;](/help/automating/using/email-delivery.md#configuration) を参照してください。

イベント変数に基づいて配信をパーソナライズするには、使用する変数を最初に配信アクティビティに宣言する必要があります。

1. アクティビティを選択し、「![](assets/dlv_activity_params-24px.png)」ボタンをクリックして設定にアクセスします。
1. 「**[!UICONTROL General]**」タブを選択し、配信のパーソナライゼーションフィールドとして使用できるイベント変数を追加します。

   ![](assets/extsignal_activities_delivery.png)

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。

宣言されたイベント変数をパーソナライゼーションフィールドのリストから使用できるようになりました。 これらを配信で使用して、次のアクションを実行できます。

* 配信に使用するテンプレートの名前を定義します。

  >[!NOTE]
  >
  >このアクションは、**繰り返し** 配信でのみ使用できます。

  ![](assets/extsignal_activities_template.png)

* 配信をパーソナライズします。パーソナライゼーションフィールドを選択して配信を設定する場合、イベント変数を **[!UICONTROL Workflow parameters]** 要素で使用できます。 パーソナライゼーションフィールドとして使用できます（例：配信の件名、送信者などを定義する）。

  配信のパーソナライゼーションについて詳しくは、[&#x200B; この節 &#x200B;](../../designing/using/personalization.md) を参照してください。

  ![](assets/extsignal_activities_perso.png)

**セグメントコード**：イベント変数に基づいてセグメントコードを定義します。

>[!NOTE]
>
>このアクションは、**[!UICONTROL Query]** や **[!UICONTROL Segmentation]** アクティビティなどのセグメントコードを定義できる任意のアクティビティから実行できます。

![](assets/extsignal_activities_segment.png)

**配信ラベル**：イベント変数に基づいて配信ラベルを定義します。

![](assets/extsignal_activities_label.png)
