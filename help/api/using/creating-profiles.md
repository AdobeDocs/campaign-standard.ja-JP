---
solution: Campaign Standard
product: campaign
title: プロファイルの作成
description: APIを使用したプロファイルの作成方法を詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 4%

---


# プロファイルの作成 {#creating-profiles}

プロファイルの作成は、プロファイルリソースに対して&#x200B;**POST**&#x200B;リクエストを実行します。

>[!CAUTION]
>
>作成したプロファイルに<b>orgUnit</b>を関連付ける場合は、このフィールドでプロファイルリソースを拡張し、拡張機能の発行後に、<b>ProfileAndServicesExt</b>エンドポイントでPOST要求を実行する必要があります。
>
>プロファイルのリソース拡張子について詳しくは、<a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">キャンペーンドキュメント</a>を参照してください。

<br/>

***サンプルリクエスト***

電子メール「john.doe@mail.com」を含むプロファイルを作成するためのサンプルPOSTリクエスト。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

新しく作成されたプロファイルと、「john.doe@mail.com」電子メールアドレスが返されます。

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
