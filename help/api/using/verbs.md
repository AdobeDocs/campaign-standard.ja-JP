---
solution: Campaign Standard
product: campaign
title: GET/POST/PATCH/DELETE動詞
description: Campaign StandardAPIで使用される動詞について詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 0%

---


# GET/POST/PATCH/DELETE動詞{#verbs}

リソースに対して操作を実行するために使用できる動詞は次のとおりです。

* `GET`:1つの要素または要素のコレクションを取得します
* `POST`:パラメータを持つリソースを作成します。
* `PATCH`:パラメーターを使用してリソースを更新します。
* `DELETE`:リソースを削除します。

<!-- ajouter codes retour -->

<br/>

***リクエストのサンプル***

* プロファイル収集でのサンプルGETリクエスト。


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

* 特定のプロファイルに対するGETリクエストのサンプル。


   ```
   $curl  
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   要求されたプロファイルを返します。


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

* プロファイルを作成するためのサンプルPOSTリクエスト。


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

* プロファイルを更新するためのPATCHリクエストのサンプル。

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -d '{"firstName":"Mark"',"lastName":"Smith"}'
   ```

   PKEYとURLを返し、更新されたプロファイルを取得します。

   ```
   {
       "PKey": "<PKEY>",
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>"
   }
   ```

* プロファイルを削除するためのサンプルDELETEリクエスト。

   ```
   -X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストは、プロファイルが削除されたことを確認する200件の応答を返します。
