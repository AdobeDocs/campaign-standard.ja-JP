---
solution: Campaign Standard
product: campaign
title: プロファイルの取得
description: APIを使用したプロファイルの取得方法を詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: da0aa6c111f3e44bb502c1e5c4ad7feff9108d81
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 5%

---


# プロファイルの取得 {#retrieving-profiles}

プロファイルの検索は、**GET**&#x200B;リクエストで実行されます。

その後、フィルター、順序、ページネーションを使用して、検索結果を絞り込むことができます。 詳しくは、「[追加の操作](../../api/using/sorting.md)」の節を参照してください。

また、Campaign StandardAPIを使用すると、次のいずれかのフィールドに基づいてプロファイルを検索できます。電子メール、名、姓、または任意のカスタムフィールド。 詳しくは、[こちらの節](#searching-field)を参照してください。

<br/>

***リクエストのサンプル***

* すべてのプロファイルを取得するためのサンプルGETリクエスト。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストに対する応答。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           },
           ...
   }
   ```

* 最初の10個の電子メール値を取得するサンプルGETリクエスト。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストに対する応答。 「次の」ノードは、次の10個の電子メール値にアクセスできるURLを返します。

   ```
   {
   "content": [
       "amy.dakota@mail.com",
       "kristen.smith@mail.com",
       "omalley@mail.com",
       "xander.harrys@mail.com",
       "jane.summer@mail.com",
       "gloria.boston@mail.com",
       "edward.snow@mail.com",
       "dorian.simons@mail.com",
       "peter.paolini@mail.com",
       "mingam+test08@adobe.com"
   ],
   "next": {
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
       lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
   }
   }
   ```

## フィールド{#searching-field}に基づくプロファイルの検索

**[!UICONTROL filterType]**&#x200B;パラメーターを使用すると、次のフィールドのいずれかに基づいてプロファイルを取得できます。プロファイルリソースを拡張する際にアドバンスフィルターで追加された電子メール、名、姓、またはカスタムフィールド。

>[!NOTE]
>
>検索では大文字と小文字が区別され、プリフィックスでのみ実行されます。 例えば、姓の最後の文字を使用してプロファイルを検索することはできません。

***リクエストのサンプル***

* 名に基づいてプロファイルをフィルターするリクエストのサンプル。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 姓に基づいてプロファイルをフィルターするリクエストのサンプル。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 電子メールに基づいてプロファイルをフィルタリングするリクエストのサンプル。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 「Hobby」カスタムフィールドに基づいてプロファイルをフィルターするリクエストのサンプル。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```
