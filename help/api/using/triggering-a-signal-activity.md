---
title: シグナルアクティビティのトリガー
description: APIを使用してシグナルアクティビティをトリガーする方法を説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---


# シグナルアクティビティのトリガー {#triggering-a-signal-activity}

Adobe Campaign Standardワークフローでは、1つ以上の **外部シグナル** アクティビティを使用できます。 これらのアクティビティは、トリガーを待機する「リスナー」です。

Campaign StandardAPIを使用すると、 **外部シグナル** アクティビティをトリガしてワークフローを呼び出すことができます。 API呼び出しには、ワークフローのイベント変数に取り込まれるパラメーター(ターゲットへのオーディエンス名、読み込むファイル名、メッセージコンテンツの一部など)を含めることができます。 これにより、キャンペーンの自動化を外部システムに容易に統合できます。

>[!NOTE]
>
>外部シグナルアクティビティは、10分に1回より頻繁にトリガーすることはできません。また、送信先ワークフローが既に実行されている必要があります。

ワークフローをトリガーするには、次の手順に従います。

1. ワークフローで **GET** 要求を実行し、外部シグナルアクティビティトリガURLを取得します。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 返されたURLに対して **POST** 要求を実行し、シグナルアクティビティをトリガーします。ペイロードには「 **source** 」パラメータが含まれます。 この属性は必須です。トリガーするリクエストソースを示すことができます。

パラメーターを使用してワークフローを呼び出す場合は、 **「parameters」属性を使用してペイロードに追加し** ます。 構文は、パラメーターの名前とその値で構成されます（次の型がサポートされています）。 **文字列**、 **数値**、 **ブール** 、 **日付/時刻**)。

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
>ペイロードにパラメーターを追加する場合、 **名前** と **** タイプの値が、外部シグナルアクティビティで宣言された情報と一致していることを確認します。 また、ペイロードサイズは64Koを超えてはなりません。

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

信号アクティビティをトリガーするには、「ソース」を含むトリガURLに対してPOSTリクエストを実行します。 パラメーター追加を使用してワークフローを呼び出す場合は、「parameters」属性を指定します。

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

外部シグナルアクティビティでパラメータの1つが宣言されていない場合、POSTリクエストは以下のエラーを返し、どのパラメータが足りないかを示します。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
