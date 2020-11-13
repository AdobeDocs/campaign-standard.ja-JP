---
title: API によるデータ取得トリガー
description: APIを使用してデータ取り込みをトリガーする方法を説明します。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
translation-type: tm+mt
source-git-commit: 66417375168a9e4cbecdba71b1dcd94e844589c2
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---


# API によるデータ取得トリガー {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platformデータコネクタは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

Adobe Campaign Standardでは、APIを使用してデータマッピングをすぐに取り込むことをトリガーし、取り込みリクエストのステータスを取得できます。

このページでは、データマッピングのインジェストステータスをトリガーおよび取得する方法について説明します。 Campaign StandardAPIのグローバル情報については、 [この節を参照してください](../../api/using/get-started-apis.md)。

## 前提条件 {#prerequisites}

APIを使用する前に、Campaign Standardインターフェイス内でデータマッピングを設定および公開しておく必要があります。 詳しくは、以下の節を参照してください。

* [マッピング定義](../../developing/using/aep-mapping-definition.md)
* [マッピングのアクティベーション](../../developing/using/aep-mapping-activation.md)

データマッピングを作成したら、実行を停止して、APIからいつでもトリガーできるようにする必要があります。 それには、次の手順に従います。

1. Campaign Standardで、// **[!UICONTROL Administration]** / **[!UICONTROL Development]** メニューに移動し **[!UICONTROL Platform]****[!UICONTROL Status of data export to platform]** ます。

1. 重複を押しながらデータマッピングをクリックして開き、 **[!UICONTROL Stop]** ボタンをクリックします。

   ![](assets/aep_datamapping_stop.png)

1. 変更を保存する

現在、データマッピングの実行が停止しています。 Campaign StandardAPIを使用して手動でトリガーできます。

## データマッピングの即時取り込みの開始 {#starting-immediate-ingestion}

XDMマッピングをAdobe Experience Platformに直ちに取り込むと、POST操作によって次のようにトリガされます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>取り込みPOSTAPI呼び出しを実行するには、 **SQL関数の実行** (以下のJSスクリプトを実行するとCampaign Standard管理者が提供できる)ロールが必要です。
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

POST操作は、作成された要求ステータスに関する情報を返します。

* XDMマッピングの要求は正常に送信されました：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDMマッピングの要求は既に進行中です：

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* XDMマッピングが発行されていないか、または停止されているため、要求に失敗しました：

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

## 取り込み要求のステータスの取得 {#retrieving-status}

取り込み要求のステータスは、GET操作と、パラメータ内の目的の要求IDを使用して取得できます。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>XDMマッピング要求のステータスと関連するジョブに関する詳細は、メニューのCampaign Standardインターフェイスで **[!UICONTROL Status of data export to platform]** 確認できます( [マッピングアクティベーションを参照](../../developing/using/aep-mapping-activation.md))。

GET操作は次の情報を返します。

* **batchId**:このフィールドは、バッチの準備とアップロードの後にエラーが発生した場合にのみ入力されます。
* **info**:XDMマッピングID、
* **numRecords**:取り込まれた記録の数（成功状況のみ）
* **status**:取り込み要求の状態（成功/失敗/進行中）

GET操作に対する応答は次のとおりです。

* 取り込み要求が正常に完了しました：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* 取り込み要求は0レコードの取り込みで失敗しました：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 取り込み要求が失敗し、いくつかのレコードがバッチにアップロードされました：

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* 一部のレコードを取り込んだ後で取り込み要求が中止されました（クラッシュシナリオで発生する場合があります）。

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 取り込み要求が進行中です（要求がデータをバッチでアップロードした場合、またはバッチが要求の準備を行う場合）。

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
