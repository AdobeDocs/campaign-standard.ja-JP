---
title: プロファイルの更新
description: APIを使用してプロファイルを更新する方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 4%

---

# プロファイルの更新 {#updating-profiles}

プロファイルの更新は、**PATCH**&#x200B;リクエストを使用して実行されます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. 最初の手順は、**プロファイル**&#x200B;を取得することです。

1. 2つ目のリクエストでは、ペイロード内の完了した情報を使用して、プロファイルに対して&#x200B;**PATCHリクエスト**&#x200B;を実行します。

1. PATCHリクエストがプロファイルを更新したかどうかを確認するには、最終的なGETリクエストを実行します。

<br/>

***リクエストのサンプル***

プロファイルを取得するGETリクエストの例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

リクエストへの応答。

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

PATCHリクエストで「phone」属性を更新します。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

PKEYとURLを返して、更新されたプロファイルを取得します。

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
