---
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---


# Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

ワークフローがトリガーされると、パラメーターはイベント変数に取り込まれ、ワークフローのアクティビティをカスタマイズするために使用できます。

例えば、アクティビティで読み取るオーディエンス、 **[!UICONTROL Read audience]** アクティビティで転送するファイルの名前などを定義するために使用でき **[!UICONTROL Transfer file]** ます。 (see [](../../automating/using/customizing-workflow-external-parameters.md)).

## イベント変数の使用 {#using-events-variables}

イベント変数は、 [標準構文を満たす式内で使用されます](../../automating/using/advanced-expression-editing.md#standard-syntax)。

イベント変数を使用する構文は、次の形式に従い、アクティビティで定義されているパラメータ名を使用する必要があります(外部シグナルアクティビティでのパラメータの **[!UICONTROL External signal]** 宣言を参照 [](../../automating/using/declaring-parameters-external-signal.md))。

```
$(vars/@parameterName)
```

この構文では、 **$** 関数は **** 文字列データ型を返します。 別の種類のデータを指定する場合は、次の関数を使用します。

* **$long**:整数値。
* **$float**:10進数。
* **$boolean**:true/false。
* **$datetime**:timestamp.

アクティビティで変数を使用する場合、インターフェイスから変数を呼び出すのに役立ちます。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):ワークフローで使用可能なすべての変数の中からイベント変数を選択します。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):変数と関数を組み合わせた式の編集(を参照 [](../../automating/using/advanced-expression-editing.md))。

   ![](assets/wkf_test_activity_variables_expression.png)

   このリストは、複雑なフィルタリングを実行できる関数を提供します。 これらの機能については、 [この節で説明します](../../automating/using/list-of-functions.md)。

   また、次の関数を使用できます。これらの関数は、外部パラメーターを使用してワークフローを呼び出した後にイベント変数を使用できるすべてのアクティビティで使用できます(を参照 [](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables))。

   | 名前 | 説明 | 構文 |
   ---------|----------|---------
   | EndWith | 文字列（最初のパラメータ）が特定の文字列（2番目のパラメータ）で終わるかどうかを示します。 | EndWith(&lt;String>,&lt;String>) |
   | startWith | 特定の文字列（2番目のパラメータ）を持つ文字列（第1のパラメータ）開始かどうかを示します。 | startWith(&lt;String>,&lt;String>) |
   | 抽出 | 区切り文字を使用して、文字列の最初の文字を返します。 | Extract（&lt;文字列>,&lt;区切り文字>） |
   | ExtractRight | 区切り文字を使用して、文字列の最後の文字を返します。 | ExtractRight（&lt;文字列>,&lt;区切り文字>） |
   | DateFormat | 2番目のパラメーターで指定された形式を使用して日付を書式設定します(例： &#39;%4Y%2M%2D&#39;) | DateFormat（&lt;日付>,&lt;形式>） |
   | ファイル名 | ファイルパスの名前を返します。 | FileName（&lt;文字列>） |
   | FileExt | ファイルパスの拡張子を返します。 | FileExt(&lt;String>) |
   | IsNull | 文字列または日付がnullかを示します。 | IsNull（&lt;文字列/日付>） |
   | UrlUtf8Encode | URLをUTF8でエンコードします。 | UrlUtf8Encode(&lt;String>) |

## イベント変数を使用したアクティビティのカスタマイズ {#customizing-activities-with-events-variables}

イベント変数は、次の節に示すように、複数のアクティビティをカスタマイズするために使用できます。 アクティビティから変数を呼び出す方法について詳しくは、 [この節を参照してください](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]** アクティビティ:イベント変数に基づいてターゲットへのオーディエンスを定義します。 For more on how to use the activity, refer to [this section](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** アクティビティ:イベント変数に基づいて条件を作成します。 For more on how to use the activity, refer to [this section](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** アクティビティ:イベント変数に基づいて転送するファイルをカスタマイズします。 For more on how to use the activity, refer to [this section](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** アクティビティ:パラメーター変数と関数を組み合わせた式を使用して、クエリーでイベントーを参照できます。 これを行うには、ルールを追加し、リンクをクリックして式編集ウィンドウにアクセスします( **[!UICONTROL Advanced mode]** 詳細式編集を参照 [](../../automating/using/advanced-expression-editing.md))。

For more on how to use the activity, refer to [this section](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** アクティビティ:イベント変数に基づいて配信をパーソナライズします。

>[!NOTE]
>
>配信パラメータの値は、配信が準備されるたびに取得されます。
>
>反復配信の準備は、配信 **集計期間に基づいて行われます**。 たとえば、集計期間が「日別」の場合、配信は1日に1回のみ再準備されます。 配信パラメーターの値がその日中に変更された場合、既に1回準備されているので、配信では更新されません。
>
>ワークフローを1日に複数回呼び出す予定がある場合は、この [!UICONTROL No aggregation] オプションを使用して、配信のパラメーターが毎回更新されるようにします。 定期的な配信の設定について詳しくは、 [この節を参照してください](/help/automating/using/email-delivery.md#configuration)。

イベント変数に基づいて配信をパーソナライズするには、まず使用する変数を配信アクティビティに宣言する必要があります。

1. アクティビティを選択し、ボタンをクリックして設定にアクセスし ![](assets/dlv_activity_params-24px.png) ます。
1. タブを選択し、 **[!UICONTROL General]** 配信でパーソナライゼーションフィールドとして使用できるイベント変数を追加します。

   ![](assets/extsignal_activities_delivery.png)

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。

宣言済みイベント変数は、パーソナライゼーションフィールドのリストから使用できるようになりました。 配信でこれらを使用して、次の操作を実行できます。

* 配信に使用するテンプレートの名前を定義します。

   >[!NOTE]
   >
   >このアクションは、 **定期的な** 配信でのみ使用できます。

   ![](assets/extsignal_activities_template.png)

* 配信のパーソナライズ：パーソナライゼーションフィールドを選択して配信を設定する場合、イベント変数を **[!UICONTROL Workflow parameters]** 要素で使用できます。 配信の件名や送信者などを定義する場合など、任意のパーソナライゼーションフィールドとして使用できます。

   Delivery personalization is detailed in [this section](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**セグメントコード**:イベント変数に基づいてセグメントコードを定義します。

>[!NOTE]
>
>この操作は、セグメントコード(例えば、または **[!UICONTROL Query]****[!UICONTROL Segmentation]** アクティビティ)を定義できる任意のアクティビティから実行できます。

![](assets/extsignal_activities_segment.png)

**配信ラベル**:イベント変数に基づいて配信ラベルを定義します。

![](assets/extsignal_activities_label.png)
