---
title: プロファイルの更新
description: APIを使用してプロファイルを更新する方法について詳しく見る
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# APIを使用したプロファイルの更新{#updating-profiles-api}

プロファイルの更新は、**PATCH** リクエストで実行されます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. 最初の手順は、**プロファイルを取得**&#x200B;することです。

1. 2回目のリクエストでは、プロファイルに対して&#x200B;**PATCH リクエスト**&#x200B;を実行し、ペイロードの完了情報を確認します。

1. PATCH リクエストがプロファイルを更新したかどうかを確認するには、最終的なGET リクエストを実行します。

<br/>

***サンプルリクエスト***

プロファイルを取得するためのGET リクエストのサンプル。

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

PATCHは、「phone」属性の更新をリクエストします。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

更新されたプロファイルを取得するためのPKEYとURLを返します。

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
