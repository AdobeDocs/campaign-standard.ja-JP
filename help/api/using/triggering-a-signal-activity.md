---
solution: Campaign Standard
product: campaign
title: シグナルアクティビティのトリガー
description: APIを使用したシグナルアクティビティのトリガー方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---


# シグナルアクティビティのトリガー {#triggering-a-signal-activity}

Adobe Campaign Standardワークフローでは、1つ以上の&#x200B;**外部シグナル**&#x200B;アクティビティが存在する場合があります。 これらのアクティビティは、トリガーを待機する「リスナー」です。

Campaign StandardAPIを使用すると、**外部シグナル**&#x200B;アクティビティをトリガーしてワークフローを呼び出すことができます。 API呼び出しには、ワークフローのイベント変数に取り込まれるパラメーター(ターゲットへのオーディエンス名、読み込むファイル名、メッセージコンテンツの一部など)を含めることができます。 これにより、キャンペーンの自動化を外部システムに容易に統合できます。

>[!NOTE]
>
>外部シグナルアクティビティは、10分に1回より頻繁にトリガーすることはできません。また、送信先ワークフローが既に実行されている必要があります。

ワークフローをトリガーするには、次の手順に従います。

1. ワークフローで&#x200B;**GET**&#x200B;リクエストを実行し、外部信号アクティビティトリガーURLを取得します。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 返されたURLに対して&#x200B;**POST**&#x200B;リクエストを実行し、トリガーに&#x200B;**&quot;source&quot;**&#x200B;パラメーターを付けて、シグナルアクティビティをペイロードにします。 この属性は必須です。トリガーするリクエストソースを示すことができます。

パラメーターを使用してワークフローを呼び出す場合は、**&quot;parameters&quot;**&#x200B;属性を使用してペイロードに追加します。 構文は、パラメーターの名前とその値で構成されます（次の型がサポートされています）。**string**、**number**、**boolean**、**date/time**)。

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
>ペイロードにパラメーターを追加する場合、**name**&#x200B;と&#x200B;**type**&#x200B;の値が、外部信号アクティビティで宣言された情報と一致していることを確認します。 また、ペイロードサイズは64Koを超えてはなりません。

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

信号アクティビティをトリガーするには、「source」を含むトリガーURLに対してPOSTリクエストを実行します。 パラメーター追加を使用してワークフローを呼び出す場合は、「parameters」属性を指定します。

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
