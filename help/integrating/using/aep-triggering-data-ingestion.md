---
title: API によるデータ取り込みのトリガー
description: API を使用してデータ取得のトリガーを設定する方法を説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 6%

---

# API によるデータ取り込みのトリガー {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>現在、Adobe Experience Platform Data Connector はベータ版です。予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様を Azure でホストする必要があります（現在は北米向けのベータ版のみ）。 へのアクセスを希望する場合は、Adobe カスタマーケアにお問い合わせください。

Adobe Campaign Standardでは、API を使用してデータマッピングの即時取り込みをトリガーし、取り込みリクエストのステータスを取得できます。

このページでは、データマッピングの取り込みステータスをトリガーおよび取得する方法について説明します。 Campaign Standard API に関する全般的な情報については、[&#x200B; この節 &#x200B;](../../api/using/get-started-apis.md) を参照してください。

## 前提条件 {#prerequisites}

API を使用する前に、まずCampaign Standard インターフェイス内でデータマッピングを設定して公開する必要があります。 詳しくは、以下の節を参照してください。

* [マッピングの定義](../../integrating/using/aep-mapping-definition.md)
* [マッピングのアクティベーション](../../integrating/using/aep-mapping-activation.md)

データマッピングが作成されたら、必要に応じて API からトリガーできるように、データマッピングの実行を停止する必要があります。 これを行うには、次の手順に従います。

1. Campaign Standardで、**[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Platform]** / **[!UICONTROL Status of data export to platform]** メニューに移動します。

1. データマッピングをダブルクリックして開き、「**[!UICONTROL Stop]**」ボタンをクリックします。

   ![](assets/aep_datamapping_stop.png)

1. 変更を保存します

データマッピングの実行は停止しました。 Campaign Standard API を使用すると、手動でトリガーできます。

## データマッピングの即時取り込みの開始 {#starting-immediate-ingestion}

Adobe Experience Platformへの XDM マッピングの即時取り込みは、POST 操作でトリガーされます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>POST API 呼び出しの取り込みを実行するには、ユーザーに **SQL function execution** ロールが必要です。このロールは、以下の JS スクリプトを実行することでCampaign Standard管理者から提供されます。
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

POST 操作は、作成されたリクエストステータスに関する情報を返します。

* XDM マッピングのリクエストが正常に送信されました：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDM マッピングのリクエストは既に処理中です。

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* XDM マッピングが公開されていないか、停止しているので、リクエストに失敗しました：

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

取り込みリクエストのステータスは、GET操作と、目的のリクエスト ID をパラメーターで取得できます。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>XDM マッピングリクエストのステータスとその関連ジョブに関する詳細は、Campaign Standard インターフェイスの **[!UICONTROL Status of data export to platform]** メニューで確認できます（[&#x200B; マッピングのアクティブ化 &#x200B;](../../integrating/using/aep-mapping-activation.md) を参照）。

GET操作を実行すると、次の情報が返されます。

* **batchId**：このフィールドは、バッチ準備とアップロード後にエラーが発生した場合にのみ設定されます。
* **info**:XDM マッピング ID、
* **numRecords**：取り込まれたレコードの数（成功ステータスのみ）
* **ステータス**：取り込みリクエストのステータス（成功/失敗/処理中）

GET操作に対して可能な応答は次のとおりです。

* 取り込みリクエストに成功しました：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ",
  "numRecords": 15,
  "requestId": 3520,
  "status": "Success"
  }
  ```

* 0 件のレコードが取り込まれましたが、取り込みリクエストに失敗しました：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
  "numRecords": 0,
  "requestId": 3520,
  "status": "Failed"
  }
  ```

* 一部のレコードがバッチでアップロードされたため、取り込みリクエストが失敗しました：

  ```
  {
  "batchId": "<value>",
  "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Failed"
  }
  ```

* 一部のレコードの取り込み後に取り込みリクエストが中止されました（これはクラッシュシナリオで発生する場合があります）。

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Aborted"
  }
  ```

* 取り込みリクエストの処理中（リクエストがデータをバッチにアップロードした場合、またはリクエストのバッチ準備を行っている場合）:

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "In Progress"
  }
  ```
