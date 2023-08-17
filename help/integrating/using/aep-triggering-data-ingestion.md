---
title: API によるデータ取り込みのトリガー
description: API を使用したデータ取り込みのトリガー化の方法を説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 6%

---

# API によるデータ取り込みのトリガー {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector は現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

Adobe Campaign Standardでは、API を使用して、データマッピングの即時取り込みをトリガーし、取り込みリクエストのステータスを取得できます。

このページでは、データマッピングの取り込みステータスをトリガーおよび取得する方法について説明します。 Campaign StandardAPI に関するグローバル情報については、 [この節](../../api/using/get-started-apis.md).

## 前提条件 {#prerequisites}

API を使用する前に、データマッピングを設定し、Campaign Standardインターフェイス内で公開する必要があります。 詳しくは、以下の節を参照してください。

* [マッピングの定義](../../integrating/using/aep-mapping-definition.md)
* [マッピングのアクティベーション](../../integrating/using/aep-mapping-activation.md)

データマッピングを作成したら、実行を停止し、必要に応じて API からトリガーを設定する必要があります。 これを行うには、次の手順に従います。

1. Campaign Standardで、 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** メニュー。

1. データマッピングをダブルクリックして開き、 **[!UICONTROL Stop]** 」ボタンをクリックします。

   ![](assets/aep_datamapping_stop.png)

1. 変更を保存します。

これで、データマッピングの実行が停止しました。 Campaign StandardAPI を使用して、手動でトリガーを設定できます。

## データマッピングの即時取り込みの開始 {#starting-immediate-ingestion}

XDM マッピングのAdobe Experience Platformへの即時取り込みは、次のPOST操作でトリガーされます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>取り込みPOSTAPI 呼び出しを実行するには、 **SQL 関数の実行** ロール。以下の JS スクリプトを実行することで、Campaign Standard管理者から提供されます。
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

POST操作は、作成されたリクエストのステータスに関する情報を返します。

* XDM マッピングのリクエストが正常に送信されました：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDM マッピングのリクエストは既に進行中です：

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* XDM マッピングが公開されていないか停止されているので、リクエストに失敗しました：

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

取り込みリクエストのステータスは、GET操作で取得でき、必要なリクエスト ID をパラメーターに指定して取得できます。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>XDM マッピングリクエストのステータスと関連ジョブに関する詳細情報は、Campaign Standardインターフェイスの **[!UICONTROL Status of data export to platform]** メニュー ( [マッピングの有効化](../../integrating/using/aep-mapping-activation.md)) をクリックします。

このGET操作は、次の情報を返します。

* **batchId**：このフィールドは、バッチの準備とアップロード後にエラーが発生した場合にのみ入力されます。
* **情報**:XDM マッピング ID
* **numRecords**：取り込まれたレコードの数（成功ステータスのみ）
* **ステータス**：取り込みリクエストのステータス（成功/失敗/進行中）

以下に、GET操作に対する応答を示します。

* 取り込みリクエストが成功しました：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ",
  "numRecords": 15,
  "requestId": 3520,
  "status": "Success"
  }
  ```

* 取り込みリクエストが 0 件のレコードを取り込んで失敗しました：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
  "numRecords": 0,
  "requestId": 3520,
  "status": "Failed"
  }
  ```

* 取り込みリクエストが失敗し、一部のレコードがバッチにアップロードされました：

  ```
  {
  "batchId": "<value>",
  "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Failed"
  }
  ```

* 一部のレコードを取り込んだ後に取り込みリクエストが中止されました（クラッシュシナリオで発生する場合があります）。

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Aborted"
  }
  ```

* 取り込みリクエストが進行中です（リクエストがバッチでデータをアップロードした場合、またはバッチがリクエストの準備を行っている場合）。

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "In Progress"
  }
  ```
