---
title: External API
seo-title: External API
description: External API
seo-description: null
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
context-tags: ExternalAPI、ワークフロー、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1444a636f401ed9c34295aaca1a2b3271d6700a4

---


# External API {#external-api}

## 説明 {#description}

![](assets/wf_externalAPI.png)

**[!UICONTROL External API]** アクティビティにより、REST API呼び出しを介して **外部システム** からワークフローにデータ **が送信** されます。

The REST endpoints can be a Customer management system, an [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) or an Experience Cloud REST endpoints (Data Platform, Target, Analytics, Campaign, etc).

このアクティビティの主な特性は次のとおりです。

* 5MB HTTP応答データサイズ制限
* アウトバウンド特定のトランジションによる失敗管理
* リクエストのタイムアウトは60秒です
* HTTPリダイレクトは許可されません
* HTTPS以外のURLが拒否されました
* 「同意:application/json" request header and"Content- Type:application/json"responseヘッダーが許可されます

## Configuration {#configuration}

Drag and drop an **[!UICONTROL External API]** activity into your workflow and open the activity to start the configuration.

### Inbound Mapping

インバウンドマッピングは、以前のインバウンドアクティビティによって生成される一時的なテーブルで、UIでJSONとして表示および送信されます。
この一時テーブルに基づいて、ユーザーは受信データを変更できます。

![](assets/externalAPI-inbound.png)

**「受信済みリソース** 」ドロップダウンでは、一時テーブルを作成するクエリーアクティビティを選択できます。

The **Add count parameter** checkbox will a count value for each row coming from the temporary table. このチェックボックスは、受信アクティビティが一時テーブルを生成している場合にのみ使用できます。

**「受信列」** セクションでは、受信移行テーブルから任意のフィールドを追加できます。選択した列がデータオブジェクト内のキーになります。JSON内のデータオブジェクトは、受信移行テーブルの各行から選択した列のデータを含む配列リストになります。

The **customize parameter** text box lets you add a valid JSON with additional data needed by the external API. この追加のデータは、生成されたJSONのparamsオブジェクトに追加されます。

### アウトバウンドマッピング

This tab lets you define the sample **JSON structure** returned by the API Call.

![](assets/externalAPI-outbound.png)

The JSON structure pattern is: **{“data”:[{“key”:“value”}, {“key”:“value”},...]}**

The sample JSON definition must have the **following characteristics**:

* **data** は、JSONで必須のプロパティ名で、"data"のコンテンツはJSON配列です。
* **配列要素** には、第1レベルのプロパティを含める必要があります（より深いレベルはサポートされていません）。
   **プロパティ名** が出力時テーブルの出力スキーマの列名になります。
* **列名** の定義は、"data"配列の最初の要素に基づいています。
Columns definition (add/remove) and the type value of the property can be edited in the **Column definition** tab.

**解析が検証されると、メッセージ** が表示され、「列定義」タブのデータマッピングをカスタマイズするように招待されます。他のケースでは、エラーメッセージが表示されます。

### 実行

This tab lets you define the **HTTPS Endpoint** that will send data to ACS. If needed, you can enter authentication information in the fields below.
![](assets/externalAPI-execution.png)

### プロパティ

This tab lets you control **general properties** on the external API activity like the displayed label in the UI. 内部IDはカスタマイズできません。

![](assets/externalAPI-properties.png)

### 列の定義

    &gt;[!注]
    &gt;
    &gt;このタブは、**応答データ形式**が完了し、「アウトバウンドマッピング」タブで検証されたときに表示されます。

**「列の定義」** タブでは、エラーを含まないデータをインポートし、今後の操作用にAdobe Campaignデータベースに存在するタイプと一致させるために、各列のデータ構造を正確に指定できます。

![](assets/externalAPI-column.png)

例えば、列のラベルを変更したり、タイプ（文字列、整数、日付など）を選択したりできます。または、エラー処理を指定します。

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### トランジション

This tab lets you activate the **outbound transition** and its label. This specific transition is useful in case of **timeout** or if the payload exceed the **data size limit**.

![](assets/externalAPI-transition.png)

### 実行オプション

このタブは、ほとんどのワークフローアクティビティで使用できます。For more information, consult the [Activity properties](../../automating/using/executing-a-workflow.md#activity-properties) section.

![](assets/externalAPI-options.png)

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
