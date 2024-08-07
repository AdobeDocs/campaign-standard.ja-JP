---
title: 並べ替え
description: 詳しくは、並べ替え操作の実行方法を参照してください
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 13fc1b011f61d67dda128e77b854032801bda263
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---

# 並べ替え

デフォルトでは、昇順で並べ替えることができます。 降順で並べ替えるには、**_order** パラメーターの値に **%20desc** を追加します。

フィールドが並べ替え可能かどうかを知るには、リソースメタデータに対して「並べ替え可能」パラメーターを確認します。 詳しくは、[この節](../../api/using/metadata-mechanism.md)を参照してください。

<br/>

***サンプルリクエスト***

* データベース内のメールをアルファベット順に取得するサンプルGETリクエスト。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  リクエストに対する応答。

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

* データベース内のメールをアルファベットの降順で取得するサンプルGETリクエスト。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  リクエストに対する応答。

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
