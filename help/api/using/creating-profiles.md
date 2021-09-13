---
title: プロファイルの作成
description: APIを使用してプロファイルを作成する方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---

# プロファイルの作成 {#creating-profiles}

プロファイルの作成は、プロファイルリソースに対して&#x200B;**POST**&#x200B;リクエストを使用して実行されます。

>[!CAUTION]
>
><b>orgUnit</b>を作成したプロファイルに関連付ける場合は、このフィールドでプロファイルリソースを拡張し、拡張機能の公開後に、<b>ProfileAndServicesExt</b>エンドポイントでPOSTリクエストを実行します。
>
>プロファイルのリソース拡張について詳しくは、<a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaignのドキュメント</a>を参照してください。

<br/>

***リクエストのサンプル***

POSTリクエストのサンプルを使用して、Eメール「john.doe@mail.com」でプロファイルを作成します。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

新しく作成されたプロファイルと、「john.doe@mail.com」の電子メールアドレスが返されます。

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
