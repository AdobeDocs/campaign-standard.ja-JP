---
title: CCPA オプトアウトの管理
description: APIを使用したCCPA オプトアウトの管理方法について説明します
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
source-git-commit: ac925ec5f59f1bb57b56b430fd175a27b08c3bfe
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 6%

---

# CCPA オプトアウトの管理 {#managing-ccpa-optout}

プロファイルのCCPA オプトアウトステータスは、**ccpaOptOut** プロファイル属性と「true」または「false」の値を使用して監視および管理できます。

`"ccpaOptOut": <value>`

* **true**：個人情報の販売を禁止します。
* **false**：個人情報の販売を許可します。

<!--
The “CCPA Opt-Out” attribute is only available starting 19.4. For 19.3 environments, you need to extend the Profiles resource and add a boolean field. This field will be added to the API with the chosen label. We suggest you use “Opt-Out for CCPA”.
>
>For more on this, refer to the [Managing Privacy requests documentation](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).
-->

<br/>

***リクエストのサンプル***

* プロファイルのCCPA オプトアウトステータスを取得するためのGET リクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  ```

  GET リクエストに対する応答。

  ```
  {
  "PKey": "<PKEY>",
    "ccpaOptOut": false,
    "firstName": "John",
    "lastName": "Doe",
  ...
  }
  ```

* CCPA オプトアウトのプロファイルをマークするPOST リクエストのサンプル。

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  -i
  -d {
  -d  "firstName": "John",
  -d  "lastName": "Doe",
  -d  "email": "jdoe@mail.com",
  -d  "ccpaOptOut": true
  -d }'
  ```

  GET リクエストに対する応答。

  ```
  {
      ...
      "email": "john.doe@mail.com",
      "firstName": "John",
      "lastName": "Doe",
      "ccpaOptOut": true,
      ...
  }
  ```

* CCPA オプトアウトのプロファイルを更新するためのPATCH リクエストのサンプル。

  ```
  -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  -i
  -d {
  -d  "ccpaOptOut": true
  -d }'
  ```

  GET リクエストに対する応答。

  ```
  {
      ...
      "email": "john.doe@mail.com",
      "firstName": "John",
      "lastName": "Doe",
      "ccpaOptOut": true,
      ...
  }
  ```
