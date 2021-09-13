---
title: GET/POST/PATCH/DELETE動詞
description: Campaign StandardAPIで使用される動詞について詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: de97a194-d497-4665-906e-53178fd3b119
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# GET/POST/PATCH/DELETE動詞 {#verbs}

リソースに対して操作を実行するために使用できる動詞は次のとおりです。

* `GET`:1つの要素または要素のコレクションを取得します
* `POST`:は、パラメータを持つリソースを作成します。
* `PATCH`:リソースをパラメーターで更新します。
* `DELETE`:リソースを削除します。

<!-- ajouter codes retour -->

<br/>

***リクエストのサンプル***

* プロファイルコレクションでのGETリクエストのサンプル。


   ```
   $curl  
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   プロファイルの配列を返します。


   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "Olivia",
               "lastName": "Varney",
               "birthDate": "1977-09-°4",
               "email": "o.varney@mail.com",
           },
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName": "Doe",
               "birthDate": "1985-08-17",
               "email": "johndoe@mail.com",
           }
       ],
   }
   ```

* 特定のプロファイルでのGETリクエストのサンプル。


   ```
   $curl  
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストされたプロファイルが返されます。


   ```
   {
       "PKey": "<PKEY>",
       "firstName": "John",
       "lastName": "Doe",
       "birthDate": "1985-08-17",
       "email": "johndoe@mail.com",
       ...
   }
   ```

* POSTを作成するためのサンプルプロファイルリクエスト。


   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -d '{"lastName":"Doe"}'
   ```

   デフォルトのフィールドを持つプロファイルを返します。

   ```
   {
       "PKey": "<PKEY>",
       "firstName": "John",
       "lastName": "Doe",
       "birthDate": "1985-08-17",
       "email": "johndoe@mail.com",
   }
   ```

* PATCHを更新するためのサンプルプロファイルリクエスト。

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -d '{"firstName":"Mark"',"lastName":"Smith"}'
   ```

   PKEYとURLを返して、更新されたプロファイルを取得します。

   ```
   {
       "PKey": "<PKEY>",
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>"
   }
   ```

* プロファイルを削除するDELETEリクエストの例。

   ```
   -X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストが200個の応答を返し、プロファイルが削除されたことを確認します。
