---
title: シグナルアクティビティのトリガー
description: API を使用してシグナルアクティビティをトリガー化する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f94e98f-fe04-4369-8946-1380e02cdece
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 2%

---

# シグナルアクティビティのトリガー {#triggering-a-signal-activity}

Adobe Campaign Standardワークフローには、1 つ以上の **外部シグナル** アクティビティ。 これらのアクティビティは、トリガーされるのを待つ「リスナー」です。

Campaign StandardAPI を使用すると、トリガーAPI で **外部シグナル** 「 」アクティビティを使用して、ワークフローを呼び出します。 API 呼び出しには、ワークフローのイベント変数に取り込まれるパラメーター（ターゲットにするオーディエンス名、読み込むファイル名、メッセージコンテンツの一部など）を含めることができます。 これにより、Campaign の自動化を外部システムと簡単に統合できます。

>[!NOTE]
>
>外部シグナルアクティビティは、10 分以上の頻度でトリガーできません。また、宛先ワークフローが既に実行されている必要があります。

ワークフローをトリガーするには、次の手順に従います。

1. の実行 **GET** 外部シグナルアクティビティのトリガーURL の取得をリクエストします。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. の実行 **POST** 返された URL に対するリクエストを使用して、シグナルアクティビティをトリガー化し、 **&quot;source&quot;** パラメーターを使用しているかどうかを確認します。 この属性は必須で、トリガーするリクエストのソースを指定できます。

パラメーターを指定してワークフローを呼び出す場合は、パラメーターを指定して、 **&quot;parameters&quot;** 属性。 構文は、パラメーターの名前とその値で構成されます（次のタイプがサポートされます）。 **文字列**, **数値**, **ブール型** および **日時**) をクリックします。

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
>ペイロードにパラメーターを追加する場合は、 **名前** および **type** の値は、「外部シグナル」アクティビティで宣言された情報と一致します。 また、ペイロードサイズは 64 Ko を超えないようにする必要があります。

<br/>

***リクエストのサンプル***

ワークフローでGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

ワークフローシグナルアクティビティと、関連するトリガーURL を返します。

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

シグナルアクティビティをトリガーするには、「source」を含むトリガーURL でPOSTリクエストを実行します。 パラメーターを指定してワークフローを呼び出す場合は、「parameters」属性を追加します。

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

「外部シグナル」アクティビティでいずれかのパラメーターが宣言されていない場合、POSTリクエストは以下のエラーを返し、見つからないパラメーターを示します。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
