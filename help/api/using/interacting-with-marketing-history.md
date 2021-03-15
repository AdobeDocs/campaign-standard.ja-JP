---
solution: Campaign Standard
product: campaign
title: マーケティング履歴の操作
description: プロファイルのマーケティング履歴を操作する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 10%

---


# マーケティング履歴の操作 {#interacting-with-marketing-history}

**履歴**エンドポイントを使用すると、プロファイルのマーケティング履歴とやり取りできます。
これにより、例えば、プロファイルに送信された配信のミラーページを簡単に取得できます。 これをおこなうには、以下の手順に従います。

1. **履歴**&#x200B;エンドポイントとプロファイルのプライマリキーを使用してGETを実行します。
1. 返された&#x200B;**イベント** hrefに対してGETリクエストを実行します。
1. **mirrorPage**&#x200B;ノード内のミラーページへのリンクを持つプロファイルのイベントのリストを返します。

<br/>

***サンプルリクエスト***

GETリクエストを使用して、プロファイルのマーケティング履歴を取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

「イベント」ノードは、プロファイル上のイベントへのアクセスを提供するURLを返します。

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

「mirrorPage」ノード内のミラーページへのリンクを持つプロファイルのイベントのリストを返します。

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
