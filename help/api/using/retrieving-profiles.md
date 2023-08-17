---
title: プロファイルの取得
description: API を使用してプロファイルを取得する方法の詳細を説明します
feature: API
role: Data Engineer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 4%

---

# API を使用したプロファイルの取得 {#retrieving-profiles}

プロファイルの取得は、 **GET** リクエスト。

その後、フィルター、並べ替えおよびページネーションを使用して、検索を絞り込むことができます。 詳しくは、 [その他の操作](../../api/using/sorting.md) 」セクションに入力します。

さらに、Campaign StandardAPI を使用すると、E メール、名、姓または任意のカスタムフィールドのいずれかのフィールドに基づいてプロファイルを検索できます。 詳しくは、[この節](#searching-field)を参照してください。

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

* 最初の 10 個の電子メール値を取得するGETリクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  リクエストへの応答。 「次へ」ノードは、次の 10 個の電子メール値へのアクセスを提供する URL を返します。

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

The **[!UICONTROL filterType]** パラメーターを使用すると、E メール、名、姓、またはプロファイルリソースを拡張する際にアドバンスフィルターで追加されたカスタムフィールドのいずれかに基づいて、プロファイルを取得できます。

>[!NOTE]
>
>検索は大文字と小文字が区別され、プレフィックスでのみ実行されます。 例えば、姓の最後の文字を使用してプロファイルを検索することはできません。

***リクエストのサンプル***

* 名に基づいてプロファイルをフィルタリングするリクエストの例です。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* 姓に基づいてプロファイルをフィルタリングするリクエストの例です。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* E メールに基づいてプロファイルをフィルタリングするリクエストの例。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* 「ホビー」カスタムフィールドに基づいてプロファイルをフィルタリングするリクエストの例。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```
