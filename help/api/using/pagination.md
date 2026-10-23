---
title: ページネーション
description: ページネーション操作の実行方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
TQID: 'https://experienceleague.adobe.com/DIJnMC-Y1Bk2I4qexYlNlnQDm76SbjDzAFmBnxCA9qs'
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
source-wordcount: '160'
ht-degree: 1%
---
# ページネーション

デフォルトでは、25個のリソースがリストに読み込まれます。

**_lineCount** パラメーターを使用すると、応答にリストされるリソースの数を制限できます。  次に、**next** ノードを使用して、次の結果を表示できます。

>[!NOTE]
>
>ページネーション要求を実行するには、常に&#x200B;**next** ノードで返されるURL値を使用してください。
>
>**_lineStart** リクエストは計算され、**next** ノードで返されるURL内で常に使用する必要があります。

<br/>

***サンプルリクエスト***

プロファイルリソースの1つのレコードを表示するGET リクエストのサンプル。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

リクエストに応答し、**next** ノードを使用してページネーションを実行します。

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

デフォルトでは、大量のデータを含むテーブルを操作する場合、**next** ノードは使用できません。 ページネーションを実行するには、呼び出しURLに&#x200B;**_forcePagination=true** パラメーターを追加する必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>テーブルが大きいと見なされるレコードの数は、Campaign Standard **XtkBigTableThreshold** オプションで定義されています。 デフォルト値は100,000 レコードです。
