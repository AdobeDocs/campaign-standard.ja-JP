---
title: プロファイルの取得
description: APIを使用してプロファイルを取得する方法の詳細
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%
---
# APIによるプロファイルの取得 {#retrieving-profiles}

プロファイルの取得は、**GET**&#x200B;要求を使用して実行されます。

その後、フィルター、順序、ページ分割を使用して検索を絞り込むことができます。 詳しくは、[追加操作](../../api/using/sorting.md) セクションを参照してください。

さらに、Campaign Standard APIを使用すると、電子メール、名、姓、または任意のカスタムフィールドのいずれかのフィールドに基づいてプロファイルを検索できます。 詳しくは、[この節](#searching-field)を参照してください。

<br/>

***リクエストのサンプル***

* すべてのプロファイルを取得するためのGET リクエストのサンプル。

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

* 最初の10個のメール値を取得するためのGET リクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  リクエストへの応答。 「next」ノードは、次の10個のメール値にアクセスできるURLを返します。

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

**[!UICONTROL filterType]** パラメーターを使用すると、プロファイルリソースの拡張時に高度なフィルタリングで追加された電子メール、名、姓またはカスタムフィールドのいずれかのフィールドに基づいて、プロファイルを取得できます。

>[!NOTE]
>
>検索では大文字と小文字が区別され、プレフィックスに対してのみ実行されます。 例えば、姓の最後の文字を使用してプロファイルを検索することはできません。

***リクエストのサンプル***

* 名前に基づいてプロファイルをフィルタリングするリクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* 姓に基づいてプロファイルをフィルタリングするリクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* メールに基づいてプロファイルをフィルタリングするリクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* 「Hobby」カスタムフィールドに基づいてプロファイルをフィルタリングするリクエストのサンプル。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```
