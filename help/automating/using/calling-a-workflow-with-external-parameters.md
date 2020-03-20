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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# 外部パラメーターを使用したワークフローの呼び出し{#calling-a-workflow-with-external-parameters}

Campaign Standardでは、パラメーター（ターゲットとするオーディエンス名、インポートするファイル名、メッセージコンテンツの一部など）を使用してワークフローを呼び出すことができます。 これにより、キャンペーンの自動化を外部システムと簡単に統合できます。

次の例で、CMSから直接電子メールを送信する例を見てみましょう。 この場合、オーディエンスを選択し、CMSに電子メールコンテンツを送信するようにシステムを設定できます。 「送信」をクリックすると、これらのパラメーターを使用してCampaignワークフローが呼び出され、それらをワークフローで使用して、配信で使用するオーディエンスとURLコンテンツを定義できます。

パラメーターを使用してワークフローを呼び出すプロセスは、次のとおりです。

1. アクティビティのパラメーターを宣言 **[!UICONTROL External signal]** します。 Externalシグナル [アクティビティでのパラメーターの宣言を参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)い。
1. アクティビティま **[!UICONTROL End]** たはAPI呼び出しを設定して、パラメーターを定義し、ワークフローアクティビティをトリガ **[!UICONTROL External signal]** ーします。

ワークフローがトリガーされると、パラメーターはワークフローのイベント変数に取り込まれ、ワークフロー内で使用できます。 詳しくは、外 [部パラメータを使用したワークフローのカスタマイズを参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)い。

![](assets/extsignal_process.png)

## 外部シグナルアクティビティでのパラメーターの宣言 {#declaring-the-parameters-in-the-external-signal-activity}

パラメーターを使用してワークフローを呼び出す最初の手順は、アクティビティで宣言するこ **[!UICONTROL External signal]** とです。

1. アクティビティ **[!UICONTROL External signal]** を開き、タブを選択 **[!UICONTROL Parameters]** します。
1. ボタンをク **[!UICONTROL Create element]** リックし、各パラメータの名前とタイプを指定します。

   >[!CAUTION]
   >
   >パラメーターの名前と数が、ワークフローの呼び出し時に定義されたものと同じであることを確認します(ワークフローの呼び出し時 [のパラメーターの定義を参照](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。 また、パラメーターの型は、期待される値と一致している必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターが宣言されたら、ワークフローの設定を終了し、実行します。

## ワークフロー呼び出し時のパラメーターの定義 {#defining-the-parameters-when-calling-the-workflow}

この節では、ワークフローを呼び出す際のパラメーターの定義方法について詳しく説明します。 API呼び出しからこの操作を実行する方法について詳しくは、REST APIのドキュメントを参照 [してください](../../api/using/triggering-a-signal-activity.md)。

パラメーターを定義する前に、次のことを確認します。

* パラメーターがアクティビティで宣言され **[!UICONTROL External Signal]** ました。 Externalシグナル [アクティビティでのパラメーターの宣言を参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)い。
* シグナルアクティビティを含むワークフローが実行中です。

アクティビティを設 **[!UICONTROL End]** 定するには、次の手順に従います。

1. アクティビティ **[!UICONTROL End]** を開き、タブを選択 **[!UICONTROL External signal]** します。
1. 呼び出すワークフローと外部シグナルアクティビティを選択します。
1. ボタンをク **[!UICONTROL Create element]** リックしてパラメータを追加し、名前と値を入力します。

   * **[!UICONTROL Name]**:アクティビティで宣言された名前( **[!UICONTROL External signal]** Externalシグナルア [クティビティでのパラメーターの宣言を参照](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity))。
   * **[!UICONTROL Value]**:パラメーターに割り当てる値。 この値は、この節で説明する **Standardの構文**(英語のみ [)に従う必](../../automating/using/advanced-expression-editing.md#standard-syntax)要があります。
   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >アクティビティですべてのパラメーターが宣言されていることを確認 **[!UICONTROL External signal]** します。 そうしないと、アクティビティの実行時にエラーが発生します。

1. パラメーターを定義したら、アクティビティを確認し、ワークフローを保存します。

## イベント変数の監視 {#monitoring-the-events-variables}

宣言された外部パラメーターを含む、ワークフローで使用可能なイベント変数を監視できます。 これをおこなうには、以下の手順に従います。

1. アクティビティの後に続くアクティビティ **[!UICONTROL External signal]** を選択し、ボタンをクリック **[!UICONTROL Log and tasks]** します。
1. タブで、ボ **[!UICONTROL Tasks]** タンをクリック ![](assets/edit_darkgrey-24px.png) します。

   ![](assets/extsignal_monitoring_2.png)

1. タスクの実行コンテキスト（ID、ステータス、期間など）が表示されます。この中には、ワークフローで使用できるすべてのイベント変数が含まれています。

   ![](assets/extsignal_monitoring_3.png)

## Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

ワークフローがトリガーされると、パラメーターがイベント変数に取り込まれ、ワークフローのアクティビティをカスタマイズするために使用できます。

例えば、アクティビティで読み取るオーディエンスや、アクティビティで転送するフ **[!UICONTROL Read audience]** ァイルの名前などを定義するために使用 **[!UICONTROL Transfer file]** できます。

イベント変数を使用してカスタマイズできるアクティビティについては、この節で [詳しく説明しま](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)す。

### イベント変数の使用 {#using-events-variables}

イベント変数は、標準の構文を考慮する式の中で使用 **[されます](../../automating/using/advanced-expression-editing.md#standard-syntax)**。

イベント変数を使用する構文は、次の形式に従い、アクティビティで定義されたパラメーターの名前を使用する必要があります( **[!UICONTROL External signal]**[ External signal activityでのパラメーターの宣言を参照](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity))。

```
$(vars/@parameterName)
```

この構文では、$関数は **stringデ** ータ型 **を返します** 。 別の種類のデータを指定する場合は、次の関数を使用します。

* **$long**:整数。
* **$float**:10進数
* **$boolean**:true/false。
* **$datetime**:タイムスタンプ。

アクティビティで変数を使用する場合、インターフェイスは変数を呼び出す際に役立ちます。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):ワークフローで使用可能なすべての変数の中からイベント変数を選択します。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):変数と関数を組み合わせた式を編集します。 For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**関連トピック：**

* [式の編集](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [標準構文](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [関数のリスト](../../automating/using/list-of-functions.md)

### イベント変数を使用したアクティビティのカスタマイズ {#customizing-activities-with-events-variables}

イベント変数を使用して、以下の節に示す複数のアクティビティをカスタマイズできます。 アクティビティから変数を呼び出す方法について詳しくは、この節を参照 [してください](../../automating/using/calling-a-workflow-with-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]** アクティビティ：イベント変数に基づいてターゲットを定義するオーディエンスを定義します。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** アクティビティ：イベント変数に基づいて条件を作成します。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** アクティビティ：イベント変数に基づいて転送するファイルをカスタマイズします。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** アクティビティ：パラメーターは、イベント変数と関数を組み合わせた式を使用して、クエリ内で参照できます。 これを行うには、ルールを追加し、リンクをクリックし **[!UICONTROL Advanced mode]** て式の編集ウィンドウにアクセスします(詳細な式 [の編集を参照](../../automating/using/advanced-expression-editing.md))。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** アクティビティ：イベント変数に基づいて配信をパーソナライズします。

>[!NOTE]
>
>配信パラメータの値は、配信が準備されるたびに取得されます。
>
>定期的な配信の準備は、配信の集計期間に基 **づいています**。 例えば、集計期間が「日別」の場合、配信は1日に1回のみ再準備されます。 配信パラメータの値がその日中に変更された場合、既に1回の準備が完了しているので、配信内では更新されません。
>
>ワークフローを1日に複数回呼び出す場合は、このオプションを使用し [!UICONTROL No aggregation] て、配信パラメーターが毎回更新されるようにします。 定期的な配信の設定について詳しくは、この節を参照 [してください](/help/automating/using/email-delivery.md#configuration)。

イベント変数に基づいて配信をパーソナライズするには、まず使用する変数を配信アクティビティに宣言する必要があります。

1. アクティビティを選択し、ボタンをクリ ![](assets/dlv_activity_params-24px.png) ックして設定にアクセスします。
1. タブを選択 **[!UICONTROL General]** し、配信のパーソナライゼーションフィールドとして使用できるイベント変数を追加します。

   ![](assets/extsignal_activities_delivery.png)

1. ボタンをクリッ **[!UICONTROL Confirm]** クします。

宣言済みイベント変数が、パーソナライゼーションフィールドのリストから使用できるようになりました。 配信でこれらを使用して、次のアクションを実行できます。

* 配信に使用するテンプレートの名前を定義します。

   >[!NOTE]
   >
   >このアクションは、定期的な配信 **での** み使用できます。

   ![](assets/extsignal_activities_template.png)

* 配信のパーソナライズ：パーソナライゼーションフィールドを選択して配信を設定する場合、要素内でイベント変数を使用で **[!UICONTROL Workflow parameters]** きます。 これらを任意のパーソナライゼーションフィールドとして使用できます。例えば、配信の件名や送信者などを定義する場合などです。

   配信のパーソナライゼーションについ [ては、この節](../../designing/using/personalization.md)。

   ![](assets/extsignal_activities_perso.png)

**セグメントコード**:イベント変数に基づいてセグメントコードを定義します。

>[!NOTE]
>
>このアクションは、セグメントコードを定義できる任意のアクティビティ（例えば、アクティビティ）から実行で **[!UICONTROL Query]** き **[!UICONTROL Segmentation]** ます。

![](assets/extsignal_activities_segment.png)

**配信ラベル**:イベント変数に基づいて配信ラベルを定義します。

![](assets/extsignal_activities_label.png)

## 使用例 {#use-case}

次の使用例は、ワークフロー内でパラメーターを使用してワークフローを呼び出す方法を示しています。

目的は、外部パラメーターを使用したAPI呼び出しからワークフローをトリガーすることです。 このワークフローは、ファイルからデータベースにデータを読み込み、関連するオーディエンスを作成します。 オーディエンスが作成されると、API呼び出しで定義された外部パラメーターを使用してパーソナライズされたメッセージを送信するための2つ目のワークフローがトリガーされます。

この使用例を実行するには、次のアクションを実行する必要があります。

1. **外部パラメーターを使用して** 、ワークフロー1をトリガーするAPI呼び出しを作成します。 手順1を [参照してください。API呼び出しの設定](../../automating/using/calling-a-workflow-with-external-parameters.md#step-1--configuring-the-api-call)。
1. **ワークフローの構築1**:ワークフローはファイルを転送し、データベースに読み込みます。 次に、データが空かどうかをテストし、最終的にプロファイルをオーディエンスに保存します。 最後に、ワークフロー2がトリガーされます。 手順2を [参照してください。ワークフロー1の設定](../../automating/using/calling-a-workflow-with-external-parameters.md#step-2--configuring-workflow-1)。
1. **ワークフローの構築2**:ワークフローは、ワークフロー1で作成されたオーディエンスを読み取り、パーソナライズされたメッセージをプロファイルに送信し、パラメーターを使用してカスタマイズされたセグメントコードを送信します。 手順3を [参照してください。ワークフローの設定2](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2)。

![](assets/extsignal_uc_process.png)

### 前提条件 {#prerequisites}

ワークフローを設定する前に、それぞれのアクティビティを持つワークフロー1と2を作 **[!UICONTROL External signal]** 成する必要があります。 これにより、ワークフローを呼び出す際に、これらのシグナルアクティビティをターゲットに設定できます。

### 手順1:API呼び出しの設定 {#step-1--configuring-the-api-call}

API呼び出しを行い、ワークフロー1をパラメーターと共にトリガーします。 API呼び出しの構文について詳しくは、『キャンペーン標準REST APIsドキ [ュメント』を参照してください](../../api/using/triggering-a-signal-activity.md)。

この例では、次のパラメーターを使用してワークフローを呼び出します。

* **fileToTarget**:データベースにインポートするファイルの名前。
* **discountDesc**:割引の配信に表示する説明。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

### 手順2:ワークフローの設定1 {#step-2--configuring-workflow-1}

ワークフロー1は次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ：ワークフロー内で使用するために外部パラメーターを宣言する必要がある場所です。
* **[!UICONTROL Transfer file]** アクティビティ：パラメーターで定義された名前を持つファイルを読み込みます。
* **[!UICONTROL Load file]** アクティビティ：読み込んだファイルのデータをデータベースに読み込みます。
* **[!UICONTROL Update data]** アクティビティ：インポートしたファイルのデータを使用してデータベースを挿入または更新します。
* **[!UICONTROL Test]** アクティビティ：データがインポートされているかどうかを確認します。
* **[!UICONTROL Save audience]** アクティビティ：ファイルにデータが含まれている場合は、プロファイルをオーディエンスに保存します。
* **[!UICONTROL End activity]** アクティビティ：ワークフロー2を呼び出し、その中で使用するパラメーターを指定します。

![](assets/extsignal_uc_wkf1.png)

次の手順に従って、ワークフローを設定します。

1. API呼び出しで定義されたパラメーターを宣言します。 これを行うには、アクティビティ **[!UICONTROL External signal]** を開き、パラメーターの名前とタイプを追加します。

   ![](assets/extsignal_uc1.png)

1. データをデー **[!UICONTROL Transfer file]** タベースにインポートするアクティビティを追加します。これを行うには、アクティビティをドラッグ&amp;ドロップして開き、タブを選択 **[!UICONTROL Protocol]** します。
1. このオプション **[!UICONTROL Use a dynamic file path]** を選択し、転送するファ **イルとしてfileToTarget** パラメーターを使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. ファイルのデータをデータベースに読み込みます。

   これを行うには、アクティビティをワークフ **[!UICONTROL Load file]** ローにドラッグ&amp;ドロップし、必要に応じて設定します。

1. インポートしたファイルのデータを使用してデータベースを挿入し、更新します。

   これを行うには、アクティビティをドラッグ&amp;ド **[!UICONTROL Update data]** ロップし、タブを選択 **[!UICONTROL Identification]** して調整条件(この場合は電子メールフィールド **** )を追加します。

   ![](assets/extsignal_uc3.png)

1. タブを選 **[!UICONTROL Fields to update]** 択し、データベースで更新するフィールドを指定します(この場合は「 **firstname** 」フィールドと「 **email** 」フィールド)。

   ![](assets/extsignal_uc4.png)

1. データがファイルから取得されるかどうかを確認します。 これを行うには、アクティビティをワークフ **[!UICONTROL Test]** ローにドラッグ&amp;ドロップし、ボタンをク **[!UICONTROL Add an element]** リックして条件を追加します。
1. 条件に名前を付けて定義します。 この例では、アウトバウンドトランジションに次の構文のデータが含まれているかどうかをテストします。

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. データを取得した場合は、オーディエンスに保存します。 これを行うには、空ではないトランジシ **[!UICONTROL Save audience]** ョンにアクテ **ィビティを追加し** 、それを開きます。
1. このオプシ **[!UICONTROL Use a dynamic label]** ョンを選択し、 **fileToTarget** パラメーターをオーディエンスのラベルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. ワークフロー2を呼び出すア **[!UICONTROL End]** クティビティをパラメーターと共にドラッグ&amp;ドロップし、開きます。
1. タブを選択し **[!UICONTROL External signal]** 、トリガーするワークフローと、それに関連するシグナルアクティビティを指定します。
1. ワークフロー2内で使用するパラメーターと、関連する値を定義します。

   この例では、API呼び出し(**fileToTarget** 、 **discountDesc**)で最初に定義されたパラメーターと、定数値（「20%割引」）を持つ追加の **segmentCode** パラメーターを渡します。

   ![](assets/extsignal_uc7.png)

ワークフロー1が設定され、ワークフロー2を構築できるようになりました。 詳しくは、[この節](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2)を参照してください。

### 手順3:ワークフローの設定2 {#step-3--configuring-workflow-2}

ワークフロー2は次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ：ワークフロー内で使用するためにパラメーターを宣言する必要がある場所です。
* **[!UICONTROL Read audience]** アクティビティ：ワークフロー1に保存されたオーディエンスを読み上げます。
* **[!UICONTROL Email delivery]** アクティビティ：パラメーターを使用してパーソナライズされた、ターゲットオーディエンスに定期的なメッセージを送信します。

![](assets/extsignal_uc_wkf2.png)

次の手順に従って、ワークフローを設定します。

1. ワークフロー1で定義したパラメーターを宣言します。

   これを行うには、アクティビティを開 **[!UICONTROL External signal]** き、ワークフロー1のアクティビティで定義された各パラメーターの名前と **[!UICONTROL End]** タイプを追加します。

   ![](assets/extsignal_uc8.png)

1. ワークフロー1で保存されたオーディエンスを使用します。 これを行うには、アクティビティをワークフ **[!UICONTROL Read audience]** ローにドラッグ&amp;ドロップし、開きます。
1. このオプション **[!UICONTROL Use a dynamic audience]** を選択し、読み取るオーデ **ィエンスの名前としてfileToTarget** パラメーターを使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. segmentCodeパラメーターに従って、アウトバウンドトランジションに名 **前を付け** ます。

   これを行うには、タブを選択し **[!UICONTROL Transition]** てから、オプションを選択 **[!UICONTROL Use a dynamic segment code]** します。

1. 外部移行の名 **前として** 、segmentCodeパラメーターを使用します。

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. アクティビティをドラッグ&amp;ド **[!UICONTROL Email delivery]** ロップして、オーディエンスにメッセージを送信します。
1. メッセージ内で使用するパラメータを識別し、discountDescパラメータを使用してパーソナライズ **します** 。 これを行うには、アクティビティの詳細オプションを開き、パラメーター名と値を追加します。

   ![](assets/extsignal_uc10b.png)

1. これで、メッセージを設定できます。 アクティビティを開き、を選択しま **[!UICONTROL Recurring email]**&#x200B;す。

   ![](assets/extsignal_uc11.png)

1. 使用するテンプレートを選択し、必要に応じて電子メールのプロパティを定義します。
1. パーソナライゼー **ションフィールドとして** 、discountDescパラメータを使用します。 これを行うには、パーソナライゼーションフィールドリストから選択します。

   ![](assets/extsignal_uc13.png)

1. これで、メッセージの設定を完了し、通常どおりに送信できます。

   ![](assets/extsignal_uc14.png)

### ワークフローの実行 {#executing-the-workflows}

ワークフローが構築されたら、それらを実行できます。 API呼び出しを実行する前に、2つのワークフローが開始されていることを確認します。
