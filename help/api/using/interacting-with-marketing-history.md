---
title: マーケティング履歴の操作
description: プロファイルのマーケティング履歴を操作する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 10%

---

# マーケティング履歴の操作 {#interacting-with-marketing-history}

**履歴**エンドポイントを使用して、プロファイルのマーケティング履歴を操作できます。
これにより、例えば、プロファイルに送信された配信のミラーページを簡単に取得できます。 これは、次の手順に従って行います。

1. **履歴**&#x200B;エンドポイントとプロファイルのプライマリキーでGETを実行します。
1. 返された&#x200B;**events** hrefに対してGETリクエストを実行します。
1. **mirrorPage**&#x200B;ノード内のミラーページへのリンクを含む、プロファイルのイベントのリストを返します。

<br/>

***リクエストのサンプル***

GETリクエストを使用して、プロファイルのマーケティング履歴を取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

「events」ノードは、プロファイル上のイベントにアクセスできるURLを返します。

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

返されたイベントhrefに対してGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

「mirrorPage」ノード内のミラーページへのリンクを含む、プロファイルのイベントのリストを返します。

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
