---
solution: Campaign Standard
product: campaign
title: サービスの作成
description: APIを使用したサービスの作成方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 9%

---


# サービスの作成 {#creating-a-service}

サービスリソースに対する&#x200B;**POST**&#x200B;要求を使用して、サービスの作成が実行されます。

特定の属性を持つサービスを作成する場合は、ペイロードに追加します。 それ以外の場合は、新しいサービスはデフォルトのサービスで作成されます。

<br/>

***サンプルリクエスト***

特定の属性を持つサービスを作成するためのサンプルPOST要求です。

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

新しく作成されたサービスと、更新された属性を返します。

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
