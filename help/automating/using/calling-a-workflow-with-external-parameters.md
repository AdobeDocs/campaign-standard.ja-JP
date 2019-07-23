---
title: 外部パラメーターでのワークフローの呼び出し
seo-title: 外部パラメーターでのワークフローの呼び出し
description: 外部パラメーターでのワークフローの呼び出し
seo-description: この節では、外部パラメーターのワークフローを呼び出すための詳細について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow- general- operation
discoiquuid: 1676da91-55e3-414f- bcd3- bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 267e30c603baf67020aadefad578f91b40dc042d

---


# Calling a workflow with external parameters{#calling-a-workflow-with-external-parameters}

キャンペーンStandardでは、パラメーターのあるワークフロー（ターゲットとするオーディエンス名、インポートするファイル名、メッセージコンテンツの一部など）を呼び出すことができます。これにより、キャンペーン自動化を外部システムに容易に統合できます。

次の例では、CMSから電子メールを直接送信します。その場合、CMSにオーディエンスを選択して電子メールコンテンツを選択するようにシステムを設定できます。「送信」をクリックすると、これらのパラメーターを含むキャンペーンワークフローが呼び出され、これらのパラメーターをワークフローに使用して、配信で使用するオーディエンスおよびURLコンテンツを定義できます。

パラメーターを使用してワークフローを呼び出すプロセスは、次のとおりです。

1. **[!UICONTROL External signal]** アクティビティ内のパラメーターを宣言します。See [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).
1. Configure the **[!UICONTROL End]** activity or the API call to define the parameters and trigger the workflow **[!UICONTROL External signal]** activity.

ワークフローがトリガーされると、ワークフローのイベント変数にパラメーターが取り込まれ、ワークフロー内で使用できるようになります。See [Customizing a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters).

![](assets/extsignal_process.png)

## Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

The first step to call a workflow with parameters is to declare them in an **[!UICONTROL External signal]** activity.

1. **[!UICONTROL External signal]** アクティビティを開き、タブを **[!UICONTROL Parameters]** 選択します。
1. **[!UICONTROL Create element]** ボタンをクリックし、各パラメータの名前とタイプを指定します。

   >[!CAUTION]
   >
   >Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). さらに、パラメーターのタイプは、期待される値と一致する必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターが宣言されたら、ワークフロー設定を完了して実行します。

## Defining the parameters when calling the workflow {#defining-the-parameters-when-calling-the-workflow}

ここでは、ワークフローの呼び出し時にパラメーターを定義する方法について説明します。For more on how to perform this operation from an API call, refer to the [REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

パラメーターを定義する前に、次のことを確認してください。

* **[!UICONTROL External Signal]** アクティビティでパラメーターが宣言されました。See [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).
* シグナルアクティビティを含むワークフローが実行されています。

**[!UICONTROL End]** アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL End]** アクティビティを開き、タブを **[!UICONTROL External signal]** 選択します。
1. 呼び出すワークフローと外部シグナルアクティビティを選択します。
1. Click the **[!UICONTROL Create element]** button to add a parameter, then fill in its name and value.

   * **[!UICONTROL Name]**: **[!UICONTROL External signal]** アクティビティで宣言された名前（外部シグナル [アクティビティ](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)でのパラメーターの宣言を参照）。
   * **[!UICONTROL Value]**:パラメーターに割り当てる値。The value should follow the **Standard syntax**, described in [this section](../../automating/using/advanced-expression-editing.md#standard-syntax).
   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >**[!UICONTROL External signal]** アクティビティですべてのパラメーターが宣言されていることを確認してください。そうしないと、アクティビティの実行時にエラーが発生します。

1. 定義したパラメーターを確認し、ワークフローを保存します。

## Monitoring the events variables {#monitoring-the-events-variables}

宣言された外部パラメーターなど、ワークフローで使用できるイベント変数を監視できます。これを行うには、次の手順に従います。

1. Select the activity that follows the **[!UICONTROL External signal]** activity, then click the **[!UICONTROL Log and tasks]** button.
1. **[!UICONTROL Tasks]** タブで、 ![](assets/edit_darkgrey-24px.png) ボタンをクリックします。

   ![](assets/extsignal_monitoring_2.png)

1. ワークフローで使用できるすべてのイベント変数を含む、タスクの実行コンテキスト（ID、ステータス、継続時間など）が表示されます。

   ![](assets/extsignal_monitoring_3.png)

## Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

ワークフローがトリガーされると、パラメーターはイベント変数に取り込まれ、ワークフローのアクティビティをカスタマイズするために使用できます。

They can, for example, be used to define which audience to read in the **[!UICONTROL Read audience]** activity, the name of the file to transfer in the **[!UICONTROL Transfer file]** activity, etc.

Activities that can be customized with events variables are detailed in [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

### Using events variables {#using-events-variables}

Events variables are used within an expression that must respect the **[Standard syntax](../../automating/using/advanced-expression-editing.md#standard-syntax)**.

The syntax to use events variables must follow the format below, and use the parameter's name that has been defined in the **[!UICONTROL External signal]** activity (see [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)):

```
$(vars/@parameterName)
```

In this syntax, the **$** function returns **string** data type. 別の種類のデータを指定する場合は、次の関数を使用します。

* **$ long**:整数値。
* **$ float**:decimal number。
* **$ boolean**:true/false。
* **$ datetime**:timestamp、

アクティビティで変数を使用する場合、インターフェイスはその変数を呼び出すのに役立ちます。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):ワークフローで使用可能なすべての変数でイベント変数を選択します（を参照）。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):編集式を使用して、変数と関数を組み合わせることができます。For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**関連トピック:**

* [式の編集](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [標準構文](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [関数のリスト](../../automating/using/list-of-functions.md)

### Customizing activities with events variables {#customizing-activities-with-events-variables}

イベント変数を使用して、以下の節に示す複数のアクティビティをカスタマイズできます。For more on how to call a variable from an activity, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** アクティビティ:オーディエンスを定義します。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** アクティビティ:イベント変数に基づいて作成することができます。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** アクティビティ:イベント変数に基づいて転送するファイルをカスタマイズします。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** アクティビティ:パラメーターは、イベント変数と関数を組み合わせた式を使用して、クエリで参照できます。To do this, add a rule then click the **[!UICONTROL Advanced mode]** link to access the expression editing window (see [Advanced expression editing](../../automating/using/advanced-expression-editing.md)).

For more on how to use the activity, refer to the [dedicated section](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** アクティビティ:イベント変数に基づいて配信をパーソナライズします。

>[!NOTE]
>
>配信パラメーターの値は、配信が準備されるたびに取得されます。
>
>Recurring deliveries preparation is based on the delivery **aggregation period**. 例えば、集計期間が「日ごと」の場合、配信は1日1回のみ再準備されます。配信パラメーターの値が日の中で変更された場合、既に準備されているので、配信では更新されません。
>
>If you plan on calling the workflow multiple times a day, use the [!UICONTROL No aggregation] option, so that the delivery parameters are updated each time. For more on recurring deliveries configuration, refer to [this section](/help/automating/using/email-delivery.md#configuration).

イベント変数に基づいて配信をパーソナライズするには、まず、使用する変数を配信アクティビティに宣言する必要があります。

1. Select the activity, then click the ![](assets/dlv_activity_params-24px.png) button to access the settings.
1. **[!UICONTROL General]** タブを選択し、配信でパーソナライゼーションフィールドとして使用できるイベント変数を追加します。

   ![](assets/extsignal_activities_delivery.png)

1. Click the **[!UICONTROL Confirm]** button.

宣言されたイベント変数がパーソナライゼーションフィールドのリストから使用できるようになりました。これらを配信で使用して、以下のアクションを実行できます。

* 配信に使用するテンプレートの名前を定義します。

   >[!NOTE]
   >
   >This action is available for **recurring** deliveries only.

   ![](assets/extsignal_activities_template.png)

* Personalize the delivery: when selecting a personalization field to configure a delivery, events variables are available in the **[!UICONTROL Workflow parameters]** element. 例えば、配信の件名や送信者などを定義するなど、任意のパーソナライゼーションフィールドとして使用できます。

   Delivery personalization is detailed in [this section](../../designing/using/about-personalization.md).

   ![](assets/extsignal_activities_perso.png)

**セグメントコード**:セグメントコードを定義します。

>[!NOTE]
>
>This action can be performed from any activity that lets you define a segment code like, for example, **[!UICONTROL Query]** or **[!UICONTROL Segmentation]** activities.

![](assets/extsignal_activities_segment.png)

**配信ラベル**:イベント変数に基づいて配信ラベルを定義します。

![](assets/extsignal_activities_label.png)

## Use case {#use-case}

以下の使用例は、ワークフロー内でパラメーターを使用してワークフローを呼び出す方法を示しています。

目的は、外部パラメーターを持つAPI呼び出しからワークフローをトリガーすることです。このワークフローでは、ファイルからデータベースにデータを読み込んで、関連するオーディエンスを作成します。オーディエンスが作成されると、API呼び出しで定義された外部パラメーターと共にメッセージを送信するための2つ目のワークフローがトリガーされます。

この使用事例を実行するには、以下のアクションを実行する必要があります。

1. **外部パラメーターを使用してワークフロー1をトリガー** するAPI呼び出しを作成します。[手順1を参照してください。API呼び出しを設定](../../automating/using/calling-a-workflow-with-external-parameters.md#step-1--configuring-the-api-call)します。
1. **ビルドワークフロー1**:ワークフローによってファイルが転送され、データベースに読み込まれます。その後、データが空かどうかテストし、最終的にオーディエンスにプロファイルを保存します。最後に、ワークフロー2をトリガーします。[手順2を参照してください。ワークフロー1](../../automating/using/calling-a-workflow-with-external-parameters.md#step-2--configuring-workflow-1)の設定を参照してください。
1. **ビルドワークフロー2**:ワークフローは、ワークフロー1で作成されたオーディエンスを読み取り、パーソナライズされたメッセージをプロファイルに送信し、パラメーターを使用してカスタマイズされたセグメントコードを使用します。[手順3を参照してください。ワークフロー2](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2)の設定を参照してください。

![](assets/extsignal_uc_process.png)

### Prerequisites {#prerequisites}

Before configuring the workflows, you need to create Workflow 1 and 2 with an **[!UICONTROL External signal]** activity in each of them. これにより、ワークフローを呼び出す際に、これらのシグナルアクティビティをターゲット設定できます。

### Step 1: Configuring the API call {#step-1--configuring-the-api-call}

パラメーター付きのワークフロー1をトリガーするAPI呼び出しを作成します。For more on the API call syntax, refer to the [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

この場合、以下のパラメーターを使用してワークフローを呼び出します。

* **FileToTarget**:データベースに読み込むファイルの名前。
* **discountDesc**:割引のために配信に表示する説明。

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

### Step 2: Configuring Workflow 1 {#step-2--configuring-workflow-1}

ワークフロー1は次のように作成されます。

* **[!UICONTROL External signal]** アクティビティ:ワークフロー内で使用するために外部パラメーターを宣言する必要があります。
* **[!UICONTROL Transfer file]** アクティビティ:パラメーターで定義されている名前でファイルを読み込みます。
* **[!UICONTROL Load file]** アクティビティ:を使用して、インポートされたファイルからデータベースにデータを読み込みます。
* **[!UICONTROL Update data]** アクティビティ:インポートするか、インポートされたファイルのデータを使用してデータベースを更新します。
* **[!UICONTROL Test]** アクティビティ:データがインポートされているかどうかを確認します。
* **[!UICONTROL Save audience]** アクティビティ:ファイルにデータが含まれている場合、プロファイルはオーディエンスに保存されます。
* **[!UICONTROL End activity]** アクティビティ:ワークフロー2を呼び出し、そこで使用するパラメーターを指定します。

![](assets/extsignal_uc_wkf1.png)

ワークフローを設定するには、次の手順に従います。

1. API呼び出しで定義されているパラメーターを宣言します。To do this, open the **[!UICONTROL External signal]** activity, then add the parameters' names and types.

   ![](assets/extsignal_uc1.png)

1. **[!UICONTROL Transfer file]** データをデータベースにインポートするアクティビティを追加します。この操作を行うには、アクティビティをドラッグ&amp;ドロップしてから、タブを **[!UICONTROL Protocol]** 選択します。
1. Select the **[!UICONTROL Use a dynamic file path]** option, then use the **fileToTarget** parameter as the file to transfer:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. ファイルからデータベースにデータを読み込みます。

   To do this, drag and drop a **[!UICONTROL Load file]** activity into the workflow, then configure it according to your needs.

1. インポートしたファイルのデータを使用して、データベースを挿入して更新します。

   To do this, drag and drop an **[!UICONTROL Update data]** activity, then select the **[!UICONTROL Identification]** tab to add a reconciliation criteria (in our case the **email** field).

   ![](assets/extsignal_uc3.png)

1. **[!UICONTROL Fields to update]** タブを選択して、データベースで更新するフィールドを指定します（例: **firstname** および **email** フィールド）。

   ![](assets/extsignal_uc4.png)

1. データがファイルから取得されたかどうかを確認します。To do this, drag and drop a **[!UICONTROL Test]** activity into the workflow, then click the **[!UICONTROL Add an element]** button to add a condition.
1. 条件を名前と定義します。この場合、アウトバウンドトランジションに次の構文を持つデータが含まれているかテストします。

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. データを取得するとオーディエンスに保存されます。To do this, add a **[!UICONTROL Save audience]** activity to the **Target not empty** transition, then open it.
1. **[!UICONTROL Use a dynamic label]** このオプションを選択して、オーディエンスのラベルとして **FileToTarget** パラメーターを使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Drag and drop an **[!UICONTROL End]** activity that will call Workflow 2 with parameters, then open it.
1. **[!UICONTROL External signal]** タブを選択して、トリガーするワークフローと関連するシグナルアクティビティを指定します。
1. ワークフロー2内で使用するパラメーターとそれに関連する値を定義します。

   In our case, we want to pass the parameters originally defined in the API call (**fileToTarget** and **discountDesc**), and an additional **segmentCode** parameter with a constant value ("20% discount").

   ![](assets/extsignal_uc7.png)

ワークフロー1が設定されているため、ワークフロー2を構築できるようになりました。For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2).

### Step 3: Configuring Workflow 2 {#step-3--configuring-workflow-2}

ワークフロー2は次のように作成されます。

* **[!UICONTROL External signal]** アクティビティ:ワークフロー内で使用するためにパラメーターを宣言する必要があります。
* **[!UICONTROL Read audience]** アクティビティ:ワークフロー1に保存されたオーディエンスを読み取ります。
* **[!UICONTROL Email delivery]** アクティビティ:は、パラメーターを使用してパーソナライズされたターゲットオーディエンスに定期的なメッセージを送信します。

![](assets/extsignal_uc_wkf2.png)

ワークフローを設定するには、次の手順に従います。

1. ワークフロー1で定義されているパラメーターを宣言します。

   To do this, open the **[!UICONTROL External signal]** activity, then add the name and type of each parameter defined in the **[!UICONTROL End]** activity of Workflow 1.

   ![](assets/extsignal_uc8.png)

1. ワークフロー1に保存されているオーディエンスを使用します。To do this, drag and drop a **[!UICONTROL Read audience]** activity into the workflow, then open it.
1. **[!UICONTROL Use a dynamic audience]** このオプションを選択し、 **次に読み取るオーディエンスの名前としてFileToTarget** パラメーターを使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Name the outbound transition according to the **segmentCode** parameter.

   To do this, select the **[!UICONTROL Transition]** tab, then the **[!UICONTROL Use a dynamic segment code]** option.

1. Use the **segmentCode** parameter as the name of the outbound transition:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity to send a message to the audience.
1. Identify the parameters to use in the message to personalize it with the **discountDesc** parameter. これを行うには、アクティビティのアドバンスオプションを開き、パラメーター名と値を追加します。

   ![](assets/extsignal_uc10b.png)

1. メッセージを設定できるようになりました。Open the activity, then select **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. 使用するテンプレートを選択し、必要に応じて電子メールのプロパティを定義します。
1. **discountDesc** パラメーターをパーソナライゼーションフィールドとして使用します。これを行うには、パーソナライゼーションフィールドのリストから選択します。

   ![](assets/extsignal_uc13.png)

1. これで、メッセージの設定を完了して、通常どおり送信できます。

   ![](assets/extsignal_uc14.png)

### Executing the workflows {#executing-the-workflows}

ワークフローが構築されたら、それを実行できます。API呼び出しを実行する前に、2つのワークフローが開始されていることを確認してください。
