---
title: プロファイルの管理
description: APIを使用したプロファイルの管理方法について詳しく説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# プロファイルの管理{#managing-profiles}

## プロファイルの取得

プロファイルの取得は **GET要求で実行され** ます。

その後、フィルター、順序、ページ番号を使用して、検索を絞り込むことができます。 For more on this, refer to the [Additional operations](../../api/using/sorting.md) section.

<br/>

***リクエストの例***

* すべてのプロファイルを取得するためのGETリクエストの例。

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

* 最初の10個の電子メール値を取得するためのサンプルGETリクエスト。

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

## プロファイルの更新

プロファイルの更新は **PATCH要求で実行され** ます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. 最初の手順は、プロファ **イルを取得します**。

1. 2番目のリクエストでは、ペイロード内の完 **了した情報を使用して** 、プロファイルに対してPATCHリクエストを実行します。

1. PATCHリクエストがプロファイルを更新したかどうかを確認するために、最終的なGETリクエストを実行できます。

<br/>

***サンプルリクエスト***

プロファイルを取得するためのGETリクエストの例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
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
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

「phone」属性を更新するためのPATCHリクエスト。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

更新されたプロファイルを取得するためのPKEYとURLを返します。

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```

## プロファイルの作成

プロファイルの作成は、プロファイルリソ **ースに対して** POST要求を使用して実行されます。

>[!CAUTION]
>
>作成したプロファイルに <b>orgUnit</b> を関連付ける場合は、このフィールドを使用してプロファイルリソースを拡張し、拡張の公開後に、ProfileAndServicesExtエンドポイントでPOST要求を実行する必要があ <b>ります</b> 。
>
>プロファイルのリソース拡張機能について詳しくは、 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaignのドキュメントを参照してください</a>。

<br/>

***サンプルリクエスト***

電子メール「john.doe@mail.com」を含むプロファイルを作成するためのPOSTリクエストの例。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

新しく作成されたプロファイルを、「john.doe@mail.com」電子メールアドレスで返します。

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
