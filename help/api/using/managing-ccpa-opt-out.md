---
title: CCPA オプトアウトの管理
description: APIを使用したCCPAオプトアウトの管理方法
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 9240686a36146b45de6dfd07fc50a71fab663001
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---


# CCPA オプトアウトの管理 {#managing-ccpa-optout}

プロファイルのCCPAオプトアウトステータスは、ccpaOptOut **** プロファイル属性と「true」または「false」値を使用して監視および管理できます。

`"ccpaOptOut": <value>`

* **true**: 個人情報の販売を禁じる。
* **false**:個人情報の販売を許可します。

>[!CAUTION]
>
>「CCPAオプトアウト」属性は、19.4からのみ使用できます。19.3環境の場合は、プロファイルリソースを拡張し、ブール値フィールドを追加する必要があります。 このフィールドは、選択したラベルと共にAPIに追加されます。 「CCPAのオプトアウト」を使用することをお勧めします。
>
>詳しくは、「プライバシーリクエストの [管理」のドキュメントを参照してください](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

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
