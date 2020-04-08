---
title: シグナルアクティビティのトリガー
description: APIを使用してシグナルアクティビティをトリガーする方法。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f5c91f886335e43940caac4d3b18924c020a2d2b

---


# シグナルアクティビティのトリガー {#triggering-a-signal-activity}

Adobe Campaign標準ワークフローには、1つ以上の外部信号 **アクティビティがあります** 。 これらのアクティビティは、トリガーされるのを待つ「リスナー」です。

Campaign StandardAPIを使用すると、外部シグナル **アクティビティをトリガし** 、ワークフローを呼び出すことができます。 API呼び出しには、イベントのオーディエンス変数に取り込まれるパラメータ(ターゲットのパラメータ名、読み込むファイル名、メッセージコンテンツの一部など)を含めることができます。 これにより、システムの自動化を外部キャンペーンと簡単に統合できます。

>[!NOTE]
>
>外部信号アクティビティは、10分間隔より頻繁にトリガーされることはなく、宛先ワークフローが既に実行されている必要があります。

ワークフローをトリガーするには、次の手順に従います。

1. ワークフローで **GET** リクエストを実行し、外部シグナルアクティビティトリガURLを取得します。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 返された **URLに対して** POST **リクエストを実行し、シグナルアクティビティをトリガーします。ペイロードに「** source」パラメーターが含まれます。 この属性は必須で、トリガーするリクエストのソースを示すことができます。

パラメーターを使用してワークフローを呼び出す場合は、「parameters」属性を使用してペイロード **に追加し** ます。 構文は、パラメーターの名前とその値で構成されます（次のタイプがサポートされています）。 **string** number **、** boolean **、** date/time **、** date/time。

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>ペイロードにパラメータを追加する場合は、名前とタイプの値が **** 、外部シグナル **** アクティビティで宣言された情報と一致していることを確認します。 また、ペイロードサイズは64Koを超えてはなりません。

<br/>

***サンプルリクエスト***

ワークフローでGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

ワークフローシグナルアクティビティと関連するトリガーURLを返します。

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

シグナルアクティビティをトリガーするには、「source」を含むトリガーURLに対してPOSTリクエストを実行します。 パラ追加メーターを使用してワークフローを呼び出す場合は、「parameters」属性を指定します。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

いずれかのパラメータが外部シグナルアクティビティで宣言されていない場合、POST要求は次のエラーを返し、どのパラメータが見つからないかを示します。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
