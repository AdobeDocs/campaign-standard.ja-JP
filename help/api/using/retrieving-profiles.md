---
title: プロファイルの取得
description: APIを使用してプロファイルを取得する方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 5%

---

# プロファイルの取得 {#retrieving-profiles}

プロファイルの取得は、**GET**&#x200B;リクエストを使用して実行されます。

その後、フィルター、並べ替え、ページネーションを使用して検索を絞り込むことができます。 詳しくは、[追加の操作](../../api/using/sorting.md)の節を参照してください。

さらに、Campaign StandardAPIを使用すると、次のいずれかのフィールドに基づいてプロファイルを検索できます。電子メール、名、姓または任意のカスタムフィールド。 詳しくは、[この節](#searching-field)を参照してください。

<br/>

***リクエストのサンプル***

* すべてのプロファイルを取得するGETリクエストのサンプル。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストへの応答。

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

* 最初の10個の電子メール値を取得するGETリクエストのサンプル。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストへの応答。 「次の」ノードは、次の10個の電子メール値にアクセスできるURLを返します。

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

## フィールドに基づくプロファイルの検索 {#searching-field}

**[!UICONTROL filterType]**&#x200B;パラメーターを使用すると、次のフィールドの1つに基づいてプロファイルを取得できます。プロファイルリソースを拡張する際にアドバンスフィルターで追加された、電子メール、名、姓、カスタムフィールド。

>[!NOTE]
>
>検索では大文字と小文字が区別され、プレフィックスでのみ実行されます。 例えば、姓の最後の文字を使用してプロファイルを検索することはできません。

***リクエストのサンプル***

* 名に基づいてプロファイルをフィルタリングするリクエストの例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 姓に基づいてプロファイルをフィルターするリクエストの例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Eメールに基づいてプロファイルをフィルタリングするリクエストの例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* 「ホビー」カスタムフィールドに基づいてプロファイルをフィルターするリクエストの例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```
