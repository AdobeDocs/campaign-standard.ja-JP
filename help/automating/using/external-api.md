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
source-git-commit: cad3a63d3e0dd94e4e308110996ed15c75beb904
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 1%

---


# 外部 API {#external-api}

## 説明 {#description}

![](assets/wf_externalAPI.png)

この **[!UICONTROL External API]** アクティビティは、 **HTTP API****呼び出しを介して、** 外部システムからデータをワークフローに取り込みます。

外部システムエンドポイントには、パブリックAPIエンドポイント、顧客管理システム、またはサーバーレスアプリケーションインスタンス( [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html)など)を使用して、いくつかのカテゴリについて言及できます。

>[!NOTE]
>
>セキュリティ上の理由から、JSSPの使用はCampaign Standardではサポートされていません。 コードを実行する必要がある場合は、External APIアクティビティを介してAdobe I/Oランタイムインスタンスを呼び出すことができます。

このアクティビティの主な特徴は次のとおりです。

* JSON形式のデータをサードパーティのREST APIエンドポイントに渡す機能
* JSON応答を受け取り、それを出力テーブルにマッピングして、他のワークフローアクティビティに下流に渡す機能。
* 送信固有のトランジションでの失敗管理

### ベータ版からGAへの移行 {#from-beta-to-ga}

Campaign Standard20.3リリースでは、外部API機能により、tromベータ版がGA (General Availability)に移行しました。

>[!CAUTION]
>
>そのため、ベータ版External APIアクティビティを使用していた場合は、すべてのワークフローでそれらをGA External APIアクティビティに置き換える必要があります。  ベータ版のExternal APIを使用するワークフローは、20.3リリースから動作を停止します。

外部APIアクティビティを置き換える場合は、新しい外部APIアクティビティをワークフローに追加し、設定の詳細を手動でコピーしてから、古いアクティビティを削除します。

>[!NOTE]
>
>ヘッダー値はアクティビティ内でマスクされるので、ヘッダー値をコピーすることはできません。

次に、新しいExternal APIアクティビティのデータを参照する、または使用するベータ外部APIアクティビティのデータを参照する、または使用するワークフロー内の他のアクティビティを再設定します。 アクティビティの例： 電子メール配信(パーソナライゼーションフィールド)、エンリッチメントアクティビティなど

### 制限とガードレール {#guardrails}

このアクティビティには、次のガードレールが適用されます。

* 5MB http応答データサイズ制限
* 要求のタイムアウトは1分です
* HTTPリダイレクトは許可されません
* HTTPS以外のURLは拒否されます
* 「受け入れ： application/json」リクエストヘッダーと「Content-Type: application/json&quot;の応答ヘッダーを許可

>[!CAUTION]
>
>このアクティビティは、キャンペーン全体のデータ(最新のオファーセット、最新のスコアなど)を取得する目的で行われ、各プロファイルの特定の情報を取得する目的で行われるので、大量のデータが転送される可能性があるので注意してください。 使用事例で必要な場合は、「ファイルを [転送](../../automating/using/transfer-file.md) 」アクティビティを使用することをお勧めします。


JSON用に特定のガードレールが配置されました。

* **JSONの最大深度**: 処理できるカスタムのネストされたJSONの最大深さを10レベルに制限します。
* **JSONの最大キー長**: 生成される内部キーの最大長を255に制限します。 このキーは列IDに関連付けられています。
* **JSON最大重複キーの許可**:  列IDとして使用される重複JSONプロパティ名の合計数の上限は150です。


アクティビティは次のようにJSON構造をサポートしていません。

* 配列オブジェクトと配列以外の要素の結合
* JSON配列オブジェクトが、1つ以上の中間配列オブジェクト内にネストされています。


## 設定 {#configuration}

ワークフローに **[!UICONTROL External API]** アクティビティをドラッグ&amp;ドロップし、アクティビティを開いて設定を開始します。

### 受信マッピング

インバウンドマッピングは、以前のインバウンドアクティビティによって生成された一時テーブルで、UIにJSONとして表示および送信されます。
この一時テーブルに基づいて、ユーザーは受信データを変更できます。

![](assets/externalAPI-inbound.png)

「 **Inbound resource** 」ドロップダウンでは、一時テーブルを作成するクエリアクティビティを選択できます。

「 **count parameter** 」チェックボックスをオンにすると、一時テーブルからの各行に対してカウント値が追加されます。 このチェックボックスは、受信アクティビティが一時テーブルを生成している場合にのみ使用できます。

「 **受信列** 」セクションでは、受信トランジションテーブルから任意のフィールドを追加できます。 選択した列は、データオブジェクトのキーになります。 JSON内のデータオブジェクトは、受信トランジションテーブルの各行から選択した列のデータを含む配列リストになります。

「 **customize parameter** 」テキストボックスを使用すると、有効なJSONをExternal APIで必要な追加データと共に追加できます。 この追加データは、生成されたJSON内のparamsオブジェクトに追加されます。

### 送信マッピング

このタブでは、API呼び出しによって返されるサンプル **JSON構造を定義できます** 。

![](assets/externalAPI-outbound.png)

JSONパーサーは、標準のJSON構造パターンタイプに対応するように設計されていますが、一部例外があります。 標準パターンの例を次に示します。`{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

サンプルのJSON定義には **次の特性が必要です**。

* **配列要素には** 、第1レベルのプロパティを含める必要があります（より深いレベルはサポートされません）。
   **プロパティ名** は、出力された一時テーブルの出力スキーマの列名になります。
* **取り込むJSON要素** は、JSON応答内で10レベル以下のネストにする必要があります。
* **列名の定義は** 、「data」配列の最初の要素に基づきます。
列定義（追加/削除）とプロパティのタイプ値は、「 **列定義** 」タブで編集できます。

**チェックボックス** ・ビヘイビアーの統合：

「分割・統合」チェックボックス(デフォルト： )は、JSONをキー/値のマップに統合するかどうかを示すためにオフにされています。

* この **チェックボックスが無効（オフ）の場合** 、サンプルJSONは配列オブジェクトを探すために解析されます。 ユーザーが使用したい配列をAdobe Campaignが正確に判断できるように、API応答のサンプルJSON形式のトリミングバージョンを提供する必要があります。 ワークフローオーサリング時に、ネストされた配列オブジェクトへのパスが決定され、記録されます。これにより、実行時に、API呼び出しから受け取ったJSON応答本体からその配列オブジェクトにアクセスできるようになります。

* この **チェックボックスが有効（オン）の場合** 、サンプルJSONはフラット化され、指定されたサンプルJSONで指定されたすべてのプロパティが出力一時テーブルの列の作成に使用され、「列の定義」タブに表示されます。 サンプルJSONに配列オブジェクトがある場合、それらの配列オブジェクトのすべての要素も統合されます。


**解析が検証されると**、メッセージが表示され、「列定義」タブのデータマッピングをカスタマイズするように促されます。 その他の場合は、エラーメッセージが表示されます。

### 実行

このタブでは、ACSにデータを送信する **HTTPSエンドポイント** を定義できます。 必要に応じて、次のフィールドに認証情報を入力できます。
![](assets/externalAPI-execution.png)

### プロパティ

このタブを使用すると、UIに表示されるラベルなど **** 、外部APIアクティビティの一般的なプロパティを制御できます。 内部IDはカスタマイズできません。

![](assets/externalAPI-properties.png)

### 列の定義

>[!NOTE]
>
>このタブは、 **応答データ形式** が「アウトバウンドマッピング」タブで完了し、検証された場合に表示されます。

「 **列定義** 」タブでは、エラーのないデータをインポートし、将来の操作のためにAdobe Campaignデータベースに既に存在するデータ型と一致させるために、各列のデータ構造を正確に指定できます。

![](assets/externalAPI-column.png)

例えば、列のラベルを変更し、そのタイプ（文字列、整数、日付など）を選択すると、 またはエラー処理を指定することもできます。

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### トランジション

このタブでは、 **アウトバウンドトランジション** とそのラベルをアクティブ化できます。 この特定のトランジションは、 **タイムアウトの場合** 、またはペイロードが **データサイズ制限を超える場合に役立ちます**。

![](assets/externalAPI-transition.png)

### 実行オプション

このタブは、ほとんどのワークフローアクティビティで使用できます。 詳しくは、「 [アクティビティプロパティ](../../automating/using/activity-properties.md) 」セクションを参照してください。

![](assets/externalAPI-options.png)

## トラブルシューティング

この新しいワークフローアクティビティには、2種類のログメッセージが追加されています。 情報とエラー 潜在的な問題のトラブルシューティングに役立ちます。

### 情報

これらのログメッセージは、ワークフローアクティビティの実行中に、有用なチェックポイントに関する情報を記録するために使用されます。 特に、次のログメッセージを使用して、APIへのアクセスの再試行と同様に、最初の試行をログに記録します（最初の試行が失敗した理由）。

<table> 
 <thead> 
  <tr> 
   <th> メッセージのフォーマット<br /> </th> 
   <th> 例<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> API URL '%s'を呼び出しています。</td> 
   <td> <p>API URLを呼び出しています： https://example.com/api/v1/web-coupon?count=2'</p></td> 
  </tr> 
  <tr> 
   <td> API URL '%s'を再試行していますが、前回の試行は失敗しました('%s')。</td> 
   <td> <p>API URL 'https://example.com/api/v1/web-coupon?count=2'を再試行していますが、前回の試行に失敗しました('HTTP - 401')。</p></td>
  </tr> 
  <tr> 
   <td> コンテンツを'%s' (%s / %s)から転送しています。</td> 
   <td> <p>「https://example.com/api/v1/web-coupon?count=2'」からコンテンツを転送しています(1234 / 1234)。</p></td> 
  </tr>
 </tbody> 
</table>

### エラー数

これらのログメッセージは、予期しないエラー状態に関する情報を記録するために使用されます。これにより、ワークフローアクティビティが失敗する可能性があります。

<table> 
 <thead> 
  <tr> 
   <th> コード — メッセージの形式<br /> </th> 
   <th> 例<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - API要求本文が制限を超えました(制限： '%d')。</td> 
   <td> <p>API要求本文が制限を超えました(制限： '5242880')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - API応答が制限を超えました(制限： '%d')。</td> 
   <td> <p>API応答が制限を超えました(制限： 5242880')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - API URLを解析できませんでした(エラー： '%d')。</td> 
   <td> <p>API URLを解析できませんでした(エラー： '-2010')。</p>
   <p> 注意： このエラーは、API URLが検証ルールに失敗した場合に記録されます。</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - API URLホストを'localhost'またはIPアドレスリテラル(URLホスト： '%s')。</td> 
   <td> <p>API URLホストを「localhost」またはIPアドレスリテラル(URLホスト： 'localhost')。</p>
    <p>API URLホストを「localhost」またはIPアドレスリテラル(URLホスト： '192.168.0.5')。</p>
    <p>API URLホストを「localhost」またはIPアドレスリテラル(URLホスト： '[2001]')。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - APIのURLは、セキュリティで保護されたURL (https) (要求されたURL: '%s')。</td> 
   <td> <p>API URLは、セキュリティで保護されたURL (https)である必要があります(要求されたURL: 'https://example.com/api/v1/web-coupon?count=2')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 — 要求本文JSONを作成できませんでした。 '%s'の追加中にエラーが発生しました。</td> 
   <td> <p>要求本文JSONを作成できませんでした。 'params'を追加中にエラーが発生しました。</p>
    <p>要求本文JSONを作成できませんでした。 'data'の追加中にエラーが発生しました。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - HTTPヘッダーキーが正しくありません(ヘッダーキー： '%s')。</td> 
   <td> <p>HTTPヘッダーキーが正しくありません(ヘッダーキー： '%s')。</p>
   <p> 注意： このエラーは、 <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFCに従った検証に失敗したカスタムヘッダーキーが記録されます</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - HTTPヘッダーキーは使用できません(ヘッダーキー： '%s')。</td> 
   <td> <p>HTTPヘッダーキーは使用できません(ヘッダーキー： '受け入れ')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - AHTTPヘッダー値が正しくありません(ヘッダー値： '%s')。</td> 
   <td> <p>HTTPヘッダー値が正しくありません(ヘッダー値： '%s')。 </p>
    <p>注意： このエラーは、 <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFCに従ったカスタムヘッダ値の検証に失敗した場合に記録されます</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - JSONペイロードに不正なプロパティ'%s'があります。</td> 
   <td> <p>JSONペイロードに不正なプロパティ'blah'があります。</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - JSONの形式が正しくないか、無効な形式です。</td> 
   <td> <p>無効な形式のJSONまたは無効な形式です。</p>
   <p>注意： このメッセージは、外部APIからの解析応答本文にのみ適用され、応答本文がこのアクティビティで必須のJSON形式に準拠しているかどうかを検証しようとすると記録されます。</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 -アクティビティに失敗しました(理由： '%s')。</td> 
   <td> <p>HTTP 401エラー応答が原因でアクティビティに失敗した場合 —アクティビティに失敗しました(理由： 'HTTP - 401')</p>
        <p>内部呼び出しの失敗によりアクティビティが失敗した場合 —アクティビティに失敗しました(理由： 'iRc - -Nn')。</p>
        <p>Content-Typeヘッダーが無効でアクティビティに失敗した場合。 -アクティビティに失敗しました(理由： 'Content-Type - application/html')。</p></td> 
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
