---
solution: Campaign Standard
product: campaign
title: プロファイルの作成
description: APIを使用したプロファイルの作成方法を詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# プロファイルの作成 {#creating-profiles}

プロファイルの作成は、プロファイルリソースに対する **POST** 要求を使用して実行されます。

>[!CAUTION]
>
>作成したプロファイルに <b>orgUnit</b> を関連付ける場合は、プロファイルリソースをこのフィールドに拡張し、拡張機能の発行後に、 <b>ProfileAndServicesExt</b> エンドポイントでPOST要求を実行する必要があります。
>
>プロファイルのリソース拡張機能について詳しくは、 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">キャンペーンのドキュメントを参照してください</a>。

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
