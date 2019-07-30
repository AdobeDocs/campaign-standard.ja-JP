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
source-git-commit: eb908d4e0ff23319025d3193bb9b22d006b5901e

---


# External API {#external-api}

## 説明 {#description}

![](assets/wf_externalAPI.png)

**[!UICONTROL External API]** アクティビティにより、REST API呼び出しを介して **外部システム** からワークフローにデータ **が送信** されます。

The REST endpoints can be a customer management system, an [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) instance or an Experience Cloud REST endpoints (Data Platform, Target, Analytics, Campaign, etc).

>[!CAUTION]
>
>この機能は現在パブリックベータ版です。External APIアクティビティを使用する前に、使用規約に同意する必要があります。このパブリックベータ版機能はまだアドビによって商用リリースされていないので、Adobe ClientCareではサポートされていません。エラーが含まれている可能性があります。また、他のリリース機能と同様に機能しないこともあります。

このアクティビティの主な特性は次のとおりです。

* サードパーティREST APIエンドポイントにデータをJSON形式で渡す機能
* JSON応答を受信し、出力テーブルにマップして、他のワークフローアクティビティにダウンストリームを渡すことができます。
* アウトバウンド特定のトランジションによる失敗管理

このアクティビティでは次のグァドラリオが配置されました。

* 5MB HTTP応答データサイズ制限
* リクエストのタイムアウトは60秒です
* HTTPリダイレクトは許可されません
* HTTPS以外のURLが拒否されました
* 「同意:application/json" request header and"Content- Type:application/json"responseヘッダーが許可されます

>[!CAUTION]
>
>アクティビティは、キャンペーン全体のデータ（最新のオファー、最新のスコアなど）を取得するためのものであることに注意してください。データが大量に転送される可能性があるため、各プロファイルの特定の情報を取得することはできません。If the use case requires this, the recommendation is to use the [Transfer File](../../automating/using/transfer-file.md) activity.

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

The JSON structure pattern is: `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

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

>[!NOTE]
>
>This tab appears when the **response data format** is completed and validated in Outbound Mapping tab.

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

## トラブルシューティング

この新しいワークフローアクティビティに追加されるログメッセージには、次の2種類があります。情報とエラーを参照してください。潜在的な問題のトラブルシューティングに役立ちます。

### 情報

これらのログメッセージは、ワークフローアクティビティの実行中に有用なチェックポイントに関する情報をログに記録するために使用されます。具体的には、次のログメッセージを使用して、最初の試行と、APIにアクセスするための再試行の試み（最初の試行の失敗）も記録されます。

<table> 
 <thead> 
  <tr> 
   <th> Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> API URL'% s'を呼び出しています。</td> 
   <td> <p>API URL'https://example.com/api/v1/web-coupon?count=2'を呼び出します。</p></td> 
  </tr> 
  <tr> 
   <td> API URL"% s"を再試行しています。以前の試行に失敗しました（'% s'）。</td> 
   <td> <p>API URL'https://example.com/api/v1/web-coupon?count=2'を再試行しています。前の試行に失敗しました（'HTTP-401'）。</p></td>
  </tr> 
  <tr> 
   <td> "% s"からコンテンツを転送しています（% s/% s）。</td> 
   <td> <p>"https://example.com/api/v1/web-coupon?count=2'（1234/1234）からのコンテンツの転送」を参照してください。</p></td> 
  </tr>
 </tbody> 
</table>

### エラー

これらのログメッセージは、予期しないエラー状態に関する情報をログに記録するために使用され、最終的にワークフローアクティビティが失敗します。

<table> 
 <thead> 
  <tr> 
   <th> Code - Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250- APIリクエストの本文を超過しました（制限:'% d'）。</td> 
   <td> <p>APIリクエストの本文が上限を超えました（制限:"5242880"）。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239- API応答を超過しました（制限:'% d'）。</td> 
   <td> <p>API応答を超過しました（制限:5242880'）。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245- API URLを解析できません（エラー:'% d'）。</td> 
   <td> <p>API URLを解析できません（エラー:'-2010'）。</p>
   <p> 注意:このエラーは、API URLに検証ルールが失敗した場合に記録されます。</p></td>
  </tr> 
  <tr>
   <td> WKF-560244- API URLホストは、"localhost"またはIPアドレスリテラル（URLホスト）にすることはできません。'% s'）。</td> 
   <td> <p>API URLホストは、"localhost"またはIPアドレスリテラル（URLホスト）にすることはできません。"localhost"）。</p>
    <p>API URLホストは、"localhost"またはIPアドレスリテラル（URLホスト）にすることはできません。"192.168.0.5"）。</p>
    <p>API URLホストは、"localhost"またはIPアドレスリテラル（URLホスト）にすることはできません。'[2001]'）.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238- API URLは、安全なURL（https）である必要があります（要求されたURL:'% s'）。</td> 
   <td> <p>API URLは、安全なURL（https）である必要があります（https）。'https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249:リクエスト本文のJSONを作成できませんでした。"% s"を追加する際にエラーが発生しました。</td> 
   <td> <p>リクエスト本文のJSONを作成できませんでした。"params"を追加する際にエラーが発生しました。</p>
    <p>リクエスト本文のJSONを作成できませんでした。"data"を追加する際にエラーが発生しました。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246: HTTPヘッダーキーが不正です（ヘッダーキー:'% s'）。</td> 
   <td> <p>HTTPヘッダーキーが不正です（ヘッダーキー:'% s'）。</p>
   <p> 注意:このエラーは、カスタムヘッダーキーが[RFC]（https://tools.ietf.org/html/rfc7230#section-3.2.html)）に従って検証できない場合に記録されます</p></td> 
  </tr>
 <tr> 
   <td> WKF-560248: HTTPヘッダーキーは許可されません（ヘッダーキー）。'% s'）。</td> 
   <td> <p>HTTPヘッダーキーは許可されません（ヘッダーキー:"Accept"）。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247- AHTTPヘッダー値が不正です（ヘッダー値:'% s'）。</td> 
   <td> <p>HTTPヘッダー値が不正です（ヘッダー値:'% s'）。 </p>
    <p>注意:このエラーは、カスタムヘッダ値が[RFC]（https://tools.ietf.org/html/rfc7230#section-3.2.html)）に従って検証に失敗した場合に記録されます</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240- JSONペイロードに不正なプロパティ'% s'があります。</td> 
   <td> <p>JSONペイロードに不正なプロパティ"blah"があります。</p></td>
  </tr> 
  <tr>
   <td> WKF-560241- JSON形式または受け入れ不能な形式です。</td> 
   <td> <p>JSON形式または受け入れ不可能な形式です。</p>
   <p>注意:このメッセージは、外部APIからの応答の本文の解析にのみ適用され、応答本文がこのアクティビティによって規定されたJSON形式に準拠しているかどうかを検証しようとすると記録されます。</p></td>
  </tr>
  <tr> 
   <td> WKF-560246-アクティビティに失敗しました（理由:'% s'）。</td> 
   <td> <p>HTTP401エラー応答が原因でアクティビティが失敗した場合-アクティビティ失敗（理由:'HTTP-401'）</p>
        <p>内部呼び出しに失敗したためにアクティビティが失敗した場合-アクティビティ失敗（理由:"IRC-- NN"）。</p>
        <p>Content- Typeヘッダーが無効なことが原因でアクティビティが失敗した場合。- アクティビティに失敗しました（理由:"Content- Type- application/html"）。</p></td> 
  </tr>
 </tbody> 
</table>

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
