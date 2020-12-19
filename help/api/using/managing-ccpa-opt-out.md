---
solution: Campaign Standard
product: campaign
title: CCPA オプトアウトの管理
description: APIを使用したCCPAオプトアウトの管理方法
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# CCPA オプトアウトの管理 {#managing-ccpa-optout}

プロファイルのCCPAオプトアウトステータスは、**ccpaOptOut**&#x200B;プロファイル属性と「true」または「false」値を使用して監視および管理できます。

`"ccpaOptOut": <value>`

* **true**:個人情報の販売を禁じる。
* **false**:個人情報の販売を許可します。

>[!CAUTION]
>
>「CCPAオプトアウト」属性は、19.4からのみ使用できます。19.3環境の場合は、プロファイルリソースを拡張し、ブール値フィールドを追加する必要があります。 このフィールドは、選択したラベルと共にAPIに追加されます。 「CCPAのオプトアウト」を使用することをお勧めします。
>
>詳しくは、[プライバシーリクエストの管理のドキュメント](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)を参照してください。

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

* プロファイルにCCPAオプトアウトのマークを付けるPOSTリクエストの例。

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

* CCPAオプトアウト用にプロファイルを更新するためのPATCHリクエストの例。

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
