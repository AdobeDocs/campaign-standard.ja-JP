---
title: 購読の取得
description: API を使用してサブスクリプションを取得する方法を説明します
feature: API
role: Data Engineer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# API を使用したサブスクリプションの取得 {#retrieving-subscriptions-api}

## サービスを購読しているプロファイルの取得

これは、2 つの手順で構成される手順です。

1. 目的のサービスの購読 URL を取得します。
1. サブスクリプション URL でGETリクエストを実行します。 サービスの購読のリストと、関連付けられた各プロファイルが返されます。

>[!CAUTION]
>
>REST API は、使用する URL を含む「href」プロパティを返します。 <b>後続の API リクエストをおこなうには、常に応答に含まれる URL を使用します</b>.

<br/>

***リクエストのサンプル***

サービスを取得するGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

サービスの購読 URL を返します。

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

サブスクリプション URL でGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

サービスの購読のリストと、関連付けられた各プロファイルが表示されます。

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## プロファイルが購読登録したサービスの取得

これは、2 つの手順で構成される手順です。

1. 特定のプロファイルの購読 URL を取得します。
1. URL でGETリクエストを実行します。 プロファイルの購読のリストと、関連する各サービスを返します。

<br/>

***リクエストのサンプル***

GETリクエストを実行して、プロファイルを取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

プロファイルの購読 URL が返されます。

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

サブスクリプション URL でGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

プロファイルが購読したサービスのリストを返します。

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
