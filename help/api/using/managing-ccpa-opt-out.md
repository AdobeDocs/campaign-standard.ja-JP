---
title: CCPA オプトアウトの管理
description: API を使用した CCPA オプトアウトの管理方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# CCPA オプトアウトの管理 {#managing-ccpa-optout}

プロファイルの CCPA オプトアウトステータスは、 **ccpaOptOut** profile 属性と「true」または「false」の値：

`"ccpaOptOut": <value>`

* **true**:個人情報の販売を禁止します。
* **false**:個人情報の販売を許可します。

>[!CAUTION]
>
>「CCPA オプトアウト」属性は、19.4 以降でのみ使用できます。19.3 環境の場合は、プロファイルリソースを拡張し、ブール値フィールドを追加する必要があります。 このフィールドは、選択されたラベルで API に追加されます。 「CCPA のオプトアウト」を使用することをお勧めします。
>
>詳しくは、 [プライバシーリクエストの管理ドキュメント](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

<br/>

***リクエストのサンプル***

* プロファイルの CCPA オプトアウトステータスを取得するためのGETリクエストの例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   GETリクエストへの応答。

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* プロファイルを CCPA オプトアウト用にマークするためのPOSTリクエストの例。

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

   GETリクエストへの応答。

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

* CCPA オプトアウト用にプロファイルを更新するためのPATCHリクエストの例。

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

   GETリクエストへの応答。

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
