---
title: プロファイルの作成
description: APIを使用したプロファイルの作成方法を詳しく説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
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
