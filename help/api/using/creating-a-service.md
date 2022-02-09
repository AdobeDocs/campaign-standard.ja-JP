---
title: サービスの作成
description: API を使用してサービスを作成する方法を説明します
feature: API
role: Data Engineer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 4%

---

# API を使用したサービスの作成{#creating-a-service-api}

サービスの作成には **POST** サービスリソースに対するリクエスト。

特定の属性を使用してサービスを作成する場合は、ペイロードに追加します。 それ以外の場合は、新しいサービスはデフォルトのサービスを使用して作成されます。

<br/>

***リクエストのサンプル***

特定の属性を持つサービスを作成するPOSTリクエストのサンプル。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

新しく作成されたサービスと、更新された属性が返されます。

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
