---
title: シグナルアクティビティのトリガ
description: APIを使用してシグナルアクティビティをトリガする方法を説明します。
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# シグナルアクティビティのトリガ {#triggering-a-signal-activity}

Adobe Campaign Standardのワークフローでは、1つ以上の外部シグナルアクティビティが **存在する** 。 これらのアクティビティは、トリガーされるのを待つ「リスナー」です。

キャンペーン標準APIを使用すると、外部シグナル **アクティビティをトリガし** 、ワークフローを呼び出すことができます。 API呼び出しには、ワークフローのイベント変数に取り込まれるパラメーター（ターゲットとするオーディエンス名、読み込むファイル名、メッセージコンテンツの一部など）を含めることができます。 これにより、キャンペーンの自動化を外部システムと簡単に統合できます。

>[!NOTE]
>
>外部シグナルアクティビティは、10分ごとにトリガーされる頻度が最も高く、宛先ワークフローが既に実行されている必要があります。

ワークフローをトリガするには、次の手順に従います。

1. ワークフローで **GET** リクエストを実行し、外部シグナルアクティビティトリガURLを取得します。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 返された **URLに対して** POST **リクエストを実行し、ペイロードに「source** 」パラメーターを指定して、シグナルアクティビティをトリガーします。 この属性は必須で、トリガーするリクエストソースを示すことができます。

パラメーターを使用してワークフローを呼び出す場合は、「parameters」属性を使用してペイロード **に追加し** ます。 構文は、パラメーターの名前とその値で構成されます（次の型がサポートされています）。 **string** number **、** boolean **、** date **/time** folean)。

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
>ペイロードにパラメーターを追加する場合は、その名前と **型の値が****** 、Externalシグナルアクティビティで宣言された情報と一致していることを確認します。 また、ペイロードサイズは64Koを超えてはなりません。

<br/>

***サンプルリクエスト***

ワークフローに対してGETリクエストを実行します。

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

シグナルアクティビティをトリガーするには、「source」を含むトリガーURLに対してPOSTリクエストを実行します。 パラメーターを使用してワークフローを呼び出す場合は、「parameters」属性を追加します。

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

Externalシグナルアクティビティでパラメーターの1つが宣言されていない場合、POSTリクエストは、以下のエラーを返し、不足しているパラメーターを示します。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
