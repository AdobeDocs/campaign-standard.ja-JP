---
title: マーケティング履歴の操作
description: プロファイルのマーケティング履歴を操作する方法を説明します。
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# マーケティング履歴の操作 {#interacting-with-marketing-history}

履歴エ **ンドポイント** では、プロファイルのマーケティング履歴を操作できます。
これにより、例えば、プロファイルに送信された配信のミラーページを簡単に取得できます。 これをおこなうには、以下の手順に従います。

1. 履歴エンドポイントとプロ **ファイルの** プライマリキーを使用してGETを実行します。
1. 返されたイベントhrefに対してGET **要求を** 実行します。
1. mirrorPageノード内のミラーページへのリンクを持つプロファイルのイベントのリストを返 **します** 。

<br/>

***サンプルリクエスト***

GETリクエストを使用して、プロファイルのマーケティング履歴を取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/History/"<PKEY>" \
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

返されたイベントhrefに対してGET要求を実行します。

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
