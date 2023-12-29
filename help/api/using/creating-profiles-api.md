---
title: API を使用したプロファイルの作成
description: API を使用してプロファイルを作成する方法について詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 0%

---

# API を使用したプロファイルの作成 {#creating-profiles-api}

プロファイルの作成は、 **POST** プロファイルリソースに対するリクエスト。

>[!CAUTION]
>
>を <b>orgUnit</b> 作成したプロファイルに対し、このフィールドを使用してプロファイルリソースを拡張し、拡張機能の公開後に、でPOSTリクエストを実行する必要があります。 <b>ProfileAndServicesExt</b> endpoint.
>
>プロファイルのリソース拡張について詳しくは、 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign ドキュメント</a>.

<br/>

***リクエストのサンプル***

サンプルPOSTリクエストを使用した、電子メール「john.doe@mail.com」を含むプロファイルの作成。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

新しく作成されたプロファイルと、「john.doe@mail.com」E メールアドレスが返されます。

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
