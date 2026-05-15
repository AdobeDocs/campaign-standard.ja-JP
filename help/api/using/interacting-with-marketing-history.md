---
title: マーケティング履歴の活用
description: プロファイルのマーケティング履歴の使用方法を説明します
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
TQID: https://experienceleague.adobe.com/C5r-qK6kpvssv6eFdJNuOw61OXFapg8L8hrlxyb0vcA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 4%

---

# マーケティング履歴の活用{#interacting-with-marketing-history}

**history** エンドポイントを使用すると、プロファイルのマーケティング履歴を操作できます。
これにより、例えば、プロファイルに送信された配信のミラーページを簡単に取得できます。 これを行うには、次の手順に従います。

1. **history** エンドポイントとプロファイルのプライマリキーを使用して、GETを実行します。
1. 返された&#x200B;**events** hrefに対してGET リクエストを実行します。
1. **mirrorPage** ノードのミラーページへのリンクを含むプロファイルのイベントのリストを返します。

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

「events」ノードは、プロファイル上のイベントへのアクセス権を与えるURLを返します。

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

返されたイベント hrefに対してGET リクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

「mirrorPage」ノードのミラーページへのリンクを含むプロファイルのイベントのリストを返します。

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
