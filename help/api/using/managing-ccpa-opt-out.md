---
title: CCPA オプトアウトの管理
description: APIを使用したCCPAオプトアウトの管理方法を説明します。
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

プロファイルのCCPAオプトアウトステータスは、 **ccpaOptOut**&#x200B;プロファイル属性と「true」または「false」値を使用して監視および管理できます。

`"ccpaOptOut": <value>`

* **true**:個人情報の販売を禁止します。
* **false**:個人情報の販売を許可します。

>[!CAUTION]
>
>「CCPAオプトアウト」属性は、19.4以降でのみ使用できます。19.3環境の場合は、プロファイルリソースを拡張し、ブール値フィールドを追加する必要があります。 このフィールドは、選択されたラベルでAPIに追加されます。 「CCPAのオプトアウト」を使用することをお勧めします。
>
>詳しくは、プライバシーリクエストの管理に関するドキュメント[を参照してください。](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)

<br/>

***リクエストのサンプル***

* プロファイルのCCPAオプトアウトステータスを取得するためのGETリクエストの例。

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

* プロファイルをCCPAオプトアウト用にマークするためのPOSTリクエストの例。

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

* PATCHリクエストの例（CCPAオプトアウト用のプロファイルの更新）。

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
