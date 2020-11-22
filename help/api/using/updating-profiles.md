---
solution: Campaign Standard
product: campaign
title: プロファイルの更新
description: APIを使用してプロファイルを更新する方法について詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 4%

---


# プロファイルの更新 {#updating-profiles}

プロファイルの更新は、 **PATCH** 要求を使用して実行されます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. 最初の手順は、プロファイルを **取得することです**。

1. 2つ目のリクエストでは、ペイロード内の完了した情報を使用して、プロファイル上で **PATCHリクエスト** を実行します。

1. PATCH要求がプロファイルを更新したかどうかを確認するために、最終的なGET要求を実行できます。

<br/>

***サンプルリクエスト***

プロファイルを取得するためのサンプルGETリクエスト。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

リクエストに対する応答。

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

「phone」属性を更新するためのPATCH要求です。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

PKEYとURLを返し、更新されたプロファイルを取得します。

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
