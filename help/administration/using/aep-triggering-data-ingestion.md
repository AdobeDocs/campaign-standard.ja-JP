---
title: APIを使用したデータ取り込みのトリガー
description: APIを使用してデータ取り込みをトリガーする方法を説明します。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5f3bf4c2d0bba095182194ac28b3107eae2c54a6

---


# APIを使用したデータ取り込みのトリガー {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>キャンペーン標準データサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

Adobe Campaign Standardでは、APIを使用してデータマッピングを直ちに取り込み、取り込みリクエストのステータスを取り出すことができます。

>[!NOTE]
>
>このページでは、データマッピングのインジェスト・ステータスをトリガし、取得する方法について説明します。 Campaign Standard APIのグローバル情報については、この節を参照 [してください](../../api/using/about-campaign-standard-apis.md)。

## 前提条件 {#prerequisites}

APIを使用する前に、データマッピングを設定し、Campaign Standardインターフェイス内で公開する必要があります。 詳しくは、以下の節を参照してください。

* [マッピング定義](../../administration/using/aep-mapping-definition.md)
* [マッピングの有効化](../../administration/using/aep-mapping-activation.md)

データマッピングを作成したら、必要に応じてAPIからトリガーできるように、データマッピングの実行を停止する必要があります。 それには、次の手順に従います。

1. Campaign Standardで、///メニューに **[!UICONTROL Administration]**移動し**[!UICONTROL Development]** ま **[!UICONTROL Platform]****!UICONTROL Status of data export to platform]**す。

1. データマッピングをダブルクリックして開き、ボタンをクリック **[!UICONTROL Stop]**します。

   ![](assets/aep_datamapping_stop.png)

1. 変更の保存

これで、データマッピングの実行が停止しました。 キャンペーン標準APIを使用して、手動でトリガーできます。

## データマッピングの即時取り込みの開始 {#starting-immediate-ingestion}

XDMマッピングをAdobe Experience Platformに直ちに取り込むと、POST操作によって次のようにトリガーされます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>取り込みPOST API呼び出しを実行するには、 **** SQL関数実行ロールが必要です。このロールは、Campaign Standard管理者が以下のJSスクリプトを実行することで提供できます。
>
>`var sqlRoleObj = REST.head.roleBase.sql.get();
REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);`

POST操作は、作成されたリクエストのステータスに関する情報を返します。

* 要求はXDMマッピングに対して正常に送信されました：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDMマッピングの要求は既に処理中です：

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* XDMマッピングが発行されていないか、または停止しているため、要求が失敗しました：

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## インジェストリクエストのステータスの取得 {#retrieving-status}

取り込み要求のステータスは、GET操作と、パラメーター内の目的の要求IDを使用して取得できます。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
XDMマッピングリクエストのステータスとその関連ジョブに関する詳細情報は、Campaign Standardインターフェイスの **!UICONTROL [Status of data export to platform]** （プラットフォームへのデータエクスポートのステータス）で確認できます [(マッピングのアクテ](../../administration/using/aep-mapping-activation.md)ィブ化を参照)。

GET操作は、次の情報を返します。

* **batchId**:このフィールドは、バッチの準備とアップロードの後にエラーが発生した場合にのみ、
* **info**:xdmマッピングID、
* **numRecords**:取り込まれたレコードの数（成功状況のみ）、
* **status**:取り込みリクエストのステータス（成功、失敗、進行中）

GET操作に対する応答は次のとおりです。

* 取り込み要求が成功しました：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ````

* 取り込み要求が0件のレコードを取り込み中に失敗しました：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 取り込み要求が失敗し、一部のレコードがバッチの下にアップロードされました：

   ````
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```
   
* 一部のレコードを取り込んだ後で取り込み要求が中止されました（クラッシュシナリオで発生する可能性があります）。

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 取り込み要求が進行中（要求がデータをバッチにアップロードした場合、またはバッチが要求に対して準備中の場合）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
