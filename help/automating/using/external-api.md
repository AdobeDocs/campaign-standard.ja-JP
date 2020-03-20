---
title: 外部 API
description: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: externalAPI,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f3c8f9a167f11ba5ded2be34a50b52edeeb6412

---


# 外部 API {#external-api}

## 説明 {#description}

![](assets/wf_externalAPI.png)

アクティビティ **[!UICONTROL External API]** は、 **REST API呼び出しを介して外部システム** からワークフ **ローにデータを取り込みます** 。

RESTエンドポイントは、顧客管理システム、 [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) Instance、またはExperience Cloud RESTエンドポイント（Data Platform、Target、Analytics、Campaignなど）です。

>[!NOTE]
>
>セキュリティ上の理由から、JSSPの使用はCampaign Standardではサポートされていません。 コードを実行する必要がある場合は、External APIアクティビティを介してAdobe I/O Runtimeインスタンスを呼び出すことができます。

>[!IMPORTANT]
>
>この機能は現在ベータ版です。 External APIアクティビティの使用を開始する前に、使用許諾契約に同意する必要があります。 このベータ版機能はアドビがまだ市販していないので、Adobe ClientCareではサポートされていないので、エラーが含まれ、他のリリースされた機能と同様に機能しない場合があります。

このアクティビティの主な特徴は次のとおりです。

* JSON形式のデータをサードパーティのREST APIエンドポイントに渡す機能
* JSON応答を受け取り、出力テーブルにマッピングして、他のワークフローアクティビティに下流に渡す機能。
* アウトバウンド固有の移行による失敗管理

このアクティビティに対して、次のガードレールが配置されました。

* 50MB HTTP応答のデータサイズの制限
* 要求のタイムアウトは10分です
* HTTPリダイレクトは許可されません
* HTTPS以外のURLは拒否されます
* 「受け入れ：application/json&quot;リクエストヘッダーと&quot;Content-Type:application/json&quot;応答ヘッダーを使用できます

>[!CAUTION]
>
>アクティビティは、キャンペーン全体のデータ（最新のオファーのセット、最新のスコアなど）を取得する目的で作成されます。各プロファイルの特定の情報を取得する場合は除きます。これにより、大量のデータが転送される可能性があります。 使用事例で必要な場合は、「ファイルを転送」アクティビティを使 [用すること](../../automating/using/transfer-file.md) が推奨されます。

## 設定 {#configuration}

アクティビティをワークフ **[!UICONTROL External API]** ローにドラッグ&amp;ドロップし、アクティビティを開いて設定を開始します。

### 受信マッピング

インバウンドマッピングは、以前のインバウンドアクティビティによって生成された一時テーブルで、UIにJSONとして表示および送信されます。
この一時テーブルに基づいて、ユーザーは受信データを変更できます。

![](assets/externalAPI-inbound.png)

[受信 **リソース** ]ドロップダウンでは、一時テーブルを作成するクエリアクティビティを選択できます。

「カウ **ントパラメータを追加** 」チェックボックスをオンにすると、一時テーブルからの各行のカウント値が表示されます。 このチェックボックスは、受信アクティビティで一時テーブルが生成されている場合にのみ使用できます。

「受信 **列」セクションで** 、ユーザーは受信移行テーブルから任意のフィールドを追加できます。 選択した列は、データオブジェクトのキーになります。 JSON内のデータオブジェクトは、受信遷移テーブルの各行から選択した列のデータを含む配列リストになります。

「 **customize parameter** 」テキストボックスを使用すると、外部APIで必要なデータを含む有効なJSONを追加できます。 この追加データは、生成されたJSON内のparamsオブジェクトに追加されます。

### 送信マッピング

このタブでは、API呼び出しによって返さ **れるサンプル** JSON構造を定義できます。

![](assets/externalAPI-outbound.png)

JSON構造のパターンは次のとおりです。 `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

サンプルJSON定義には、次の特性が必要 **です**。

* **dataは** JSON内の必須のプロパティ名で、「data」の内容はJSON配列です。
* **配列要素には** 、第1レベルのプロパティが含まれている必要があります（より深いレベルはサポートされていません）。
   **プロパティ名は** 、出力一時テーブルの出力スキーマの列名になります。
* **列名の定義は** 、「データ」配列の最初の要素に基づいています。
列の定義（追加/削除）とプロパティのタイプ値は、「列の定義」タブで編 **集できます** 。

解析が検証さ **れると** 、メッセージが表示され、「列の定義」タブでデータマッピングをカスタマイズするように招待されます。 その他の場合は、エラーメッセージが表示されます。

### 実行

このタブでは、ACSにデータを送信する **HTTPSエンドポイント** (HTTPS Endpoint)を定義できます。 必要に応じて、次のフィールドに認証情報を入力できます。
![](assets/externalAPI-execution.png)

### プロパティ

このタブを使用すると、UIに表 **示されるラベルなど** 、外部APIアクティビティの一般的なプロパティを制御できます。 内部IDはカスタマイズできません。

![](assets/externalAPI-properties.png)

### 列の定義

>[!NOTE]
>
>このタブは、応答データの形式が **完了し** 、「送信マッピング」タブで検証されたときに表示されます。

「列の定 **義** 」タブでは、各列のデータ構造を正確に指定して、エラーを含まないデータをインポートし、今後の操作のためにAdobe Campaignデータベースに既に存在するタイプと一致させることができます。

![](assets/externalAPI-column.png)

例えば、列のラベルを変更し、そのタイプ（文字列、整数、日付など）を選択できます。 またはエラー処理を指定することもできます。

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### トランジション

このタブでは、アウトバウンドトランジションと **そのラベルを** 、アクティブ化できます。 この特定の移行は、タイムアウトの場合や、ペ **イロードが** データサイズの制限を超えた場合に **役立ちます**。

![](assets/externalAPI-transition.png)

### 実行オプション

このタブは、ほとんどのワークフローアクティビティで使用できます。 詳しくは、「アクティビティのプロパティ」 [の節を参照してくださ](../../automating/using/executing-a-workflow.md#activity-properties) い。

![](assets/externalAPI-options.png)

## トラブルシューティング

この新しいワークフローアクティビティに追加されるログメッセージには、次の2種類があります。情報とエラー。 潜在的な問題のトラブルシューティングに役立ちます。

### 情報

これらのログメッセージは、ワークフローアクティビティの実行中に役立つチェックポイントに関する情報を記録するために使用されます。 具体的には、次のログメッセージを使用して、APIへのアクセスの再試行（および最初の試行に失敗した理由）と共に、最初の試行をログに記録します。

<table> 
 <thead> 
  <tr> 
   <th> メッセージのフォーマット<br /> </th> 
   <th> 例 ：<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> API URL '%s'を呼び出しています。</td> 
   <td> <p>API URLを呼び出しています： https://example.com/api/v1/web-coupon?count=2'</p></td> 
  </tr> 
  <tr> 
   <td> API URL '%s'を再試行していますが、前回の試行に失敗しました('%s')。</td> 
   <td> <p>API URL 'https://example.com/api/v1/web-coupon?count=2''を再試行していますが、以前の試行は失敗しました('HTTP - 401')。</p></td>
  </tr> 
  <tr> 
   <td> '%s'からコンテンツを転送中(%s / %s)。</td> 
   <td> <p>'https://example.com/api/v1/web-coupon?count=2' (1234 / 1234)からコンテンツを転送しています。</p></td> 
  </tr>
 </tbody> 
</table>

### エラー数

これらのログメッセージは、予期しないエラー状態に関する情報を記録するために使用されます。これにより、最終的にワークフローのアクティビティが失敗する可能性があります。

<table> 
 <thead> 
  <tr> 
   <th> コード — メッセージの形式<br /> </th> 
   <th> 例 ：<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - API要求本文が制限を超えました(制限：'%d')。</td> 
   <td> <p>APIリクエスト本文が制限を超えました(制限：'5242880')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - API応答が制限を超えました(制限：'%d')。</td> 
   <td> <p>API応答が制限を超えました(制限：5242880')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - API URLを解析できませんでした(エラー：'%d')。</td> 
   <td> <p>API URLを解析できませんでした(エラー：'-2010')。</p>
   <p> 注意：このエラーは、API URLが検証ルールに失敗した場合に記録されます。</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - APIのURLホストは'localhost'またはIPアドレスリテラル(URLホスト：'%s')。</td> 
   <td> <p>API URLホストは'localhost'またはIPアドレスリテラル(URLホスト：'localhost')。</p>
    <p>API URLホストは'localhost'またはIPアドレスリテラル(URLホスト：'192.168.0.5')。</p>
    <p>API URLホストは'localhost'またはIPアドレスリテラル(URLホスト：'[2001]')。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238:API URLは安全なURL (https)である必要があります(要求されたURL:'%s')。</td> 
   <td> <p>API URLは、セキュリティで保護されたURL(https)である必要があります(要求されたURL:'https://example.com/api/v1/web-coupon?count=2')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 — 要求本文JSONを作成できませんでした。 '%s'の追加中にエラーが発生しました。</td> 
   <td> <p>要求本文JSONを作成できませんでした。 'params'の追加中にエラーが発生しました。</p>
    <p>要求本文JSONを作成できませんでした。 「データ」の追加中にエラーが発生しました。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - HTTPヘッダーキーが正しくありません(ヘッダーキー：'%s')。</td> 
   <td> <p>HTTPヘッダーキーが正しくありません(ヘッダーキー：'%s')。</p>
   <p> 注意：このエラーは、 <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFCに従ってカスタムヘッダーキーの検証に失敗した場合に記録されます</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - HTTPヘッダーキーは使用できません(ヘッダーキー：'%s')。</td> 
   <td> <p>HTTPヘッダーキーは使用できません(ヘッダーキー：'受け入れ')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - AHTTPヘッダー値が正しくありません(ヘッダー値：'%s')。</td> 
   <td> <p>HTTPヘッダー値が正しくありません(ヘッダー値：'%s')。 </p>
    <p>注意：このエラーは、 <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFCに従ったカスタムヘッダ値の検証に失敗した場合に記録されます</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - JSONペイロードのプロパティ'%s'が正しくありません。</td> 
   <td> <p>JSONペイロードに不正なプロパティ'blah'があります。</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 — 形式が正しくないか、受け入れられない形式です。</td> 
   <td> <p>形式が正しくないか、受け入れられない形式です。</p>
   <p>注意：このメッセージは、外部APIからの応答本文の解析にのみ適用され、応答本文がこのアクティビティで必須のJSON形式に準拠しているかどうかを検証しようとすると記録されます。</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 — 操作に失敗しました(理由：'%s')。</td> 
   <td> <p>HTTP 401エラー応答が原因でアクティビティが失敗した場合 — アクティビティが失敗しました(理由：'HTTP - 401')</p>
        <p>内部呼び出しの失敗によりアクティビティが失敗した場合 — アクティビティが失敗しました(理由：'iRc - -Nn')。</p>
        <p>Content-Typeヘッダーが無効でアクティビティが失敗した場合。  — アクティビティが失敗しました(理由：「Content-Type - application/html」)。</p></td> 
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
