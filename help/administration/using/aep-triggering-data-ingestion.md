---
title: API によるデータ取り込みのトリガー
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
source-git-commit: 57b87896281efa7dd1e6a612926f59061a0fdcb8

---


# API によるデータ取り込みのトリガー {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米の場合のみベータ版）。 ご利用になりたい場合は、アドビカスタマーケアにお問い合わせください。

Adobe Campaign標準を使用すると、APIを介してデータマッピングの即時取り込みをトリガーし、取り込みリクエストのステータスを取得できます。

このページでは、データマッピングのインジェストステータスをトリガーおよび取得する方法について説明します。 Campaign StandardAPIのグローバル情報については、この節を参 [照してくださ](../../api/using/about-campaign-standard-apis.md)い。

## 前提条件 {#prerequisites}

APIを使用する前に、データマッピングを設定し、Campaign Standardインターフェイス内で公開する必要があります。 詳しくは、以下の節を参照してください。

* [マッピング定義](../../administration/using/aep-mapping-definition.md)
* [マッピングの有効化](../../administration/using/aep-mapping-activation.md)

データマッピングを作成したら、実行を停止し、APIからいつでもトリガーできるようにする必要があります。 それには、次の手順に従います。

1. Campaign Standardで、// **[!UICONTROL Administration]** メニュー **[!UICONTROL Development]** に移動 **[!UICONTROL Platform]** し **[!UICONTROL Status of data export to platform]** ます。

1. 重複マッピングをクリックして開き、ボタンをクリック **[!UICONTROL Stop]** します。

   ![](assets/aep_datamapping_stop.png)

1. 変更の保存

データマッピングの実行が停止されました。 Campaign StandardAPIを使用して、手動でトリガーできます。

## データマッピングの即時取り込みの開始 {#starting-immediate-ingestion}

XDMマッピングをAdobe Experience Platformに即座に取り込むと、次のPOST操作が実行されます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>取り込みPOST API呼び出しを実行するには、 **** SQL関数の実行ロールが必要です。このロールは、Campaign Standard管理者が次のJSスクリプトを実行することで提供できます。
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

* XDMマッピングが公開されていないか、または停止しているため、要求が失敗しました：

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

## 取り込みリクエストのステータスの取得 {#retrieving-status}

取り込み要求のステータスは、GET操作と、パラメータ内の目的の要求IDを使用して取得できます。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
XDMマッピング要求のステータスと関連するジョブに関する詳細な情報は、Campaign Standardインターフェイスの **!UICONTROL [Status of data export to platform ]**（プラットフォームへのデータのエクスポートのステータス）で確認できます[(マッピング](../../administration/using/aep-mapping-activation.md)アクティベーションを参照)。

GET操作は、次の情報を返します。

* **batchId**:このフィールドは、バッチの準備とアップロードの後にエラーが発生した場合にのみ入力されます。
* **info**:xdmマッピングID、
* **numRecords**:取り込まれたレコードの数（成功ステータスのみ）、
* **status**:取り込み要求のステータス（成功/失敗/進行中）

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

* 取り込み要求が失敗し、いくつかのレコードがバッチの下にアップロードされました：

   ````
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```
   
* 一部のレコードの取り込み後に取り込み要求が中止されました（クラッシュシナリオで発生する場合があります）。

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 取り込み要求が進行中（要求がデータをバッチにアップロードした場合、またはバッチが要求の準備を行う場合）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
