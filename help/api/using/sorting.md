---
title: 並べ替え
description: 並べ替え操作の実行方法について詳しく見る
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
TQID: https://experienceleague.adobe.com/T3EzbDAi8kAK9dVJccPlvIF155gtACzDNnEjEKLpNis
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 89
ht-degree: 11%

---

# 並べ替え

並べ替えは、デフォルトで昇順で使用できます。 降順で並べ替えるには、**%20desc**&#x200B;を&#x200B;**_order** パラメーターの値に追加します。

フィールドを並べ替えることができるかどうかを確認するには、「sortable」パラメーターをリソースメタデータに確認します。 詳しくは、[この節](../../api/using/metadata-mechanism.md)を参照してください。

<br/>

***リクエストのサンプル***

* データベース内の電子メールをアルファベット順に取得するためのGET リクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  リクエストへの応答。

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* GET リクエストをサンプルして、データベース内のメールを降順アルファ順で取得します。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  リクエストへの応答。

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```
