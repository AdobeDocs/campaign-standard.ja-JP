---
title: 購読の実行
description: APIを使用してサブスクリプションを実行する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 64f321a3-436a-4b7c-99d8-0c006203012e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# 購読の実行 {#performing-subscriptions}

## 方法1:プロファイルのサービスへの購読登録

GETリクエストを実行して、プロファイルを取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

プロファイルの購読URLを返します。

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

ペイロード内の目的のサービスPOSTキーを使用して、サブスクリプションURLに対してプライマリリクエストを実行します。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"service":{"PKey":"<PKEY>"}}'
```

サービスノードが完了した更新済みプロファイルを返します。

```
{
  ...
  "service": {
    "PKey": "<PKEY>",
    "title": "Sport Newsletter (SVC1)"
  },
  "serviceName": "",
  "subscriber": ...,
  ...
}
```

## 方法2:サービス購読者へのプロファイルの追加

サービスを取得するGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

サービスの購読URLを返します。

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

ペイロード内の目的のPOSTプロファイルキーを使用して、購読URLのプライマリリクエストをおこないます。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign//profileAndServices/service/<PKEY>/subscriptions/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"subscriber":{"PKey":"<PKEY>"}}'
```

購読者ノードが完了した更新されたサービスを返します。

```
{
  ...
  "service": ...,
  "serviceName": "",
  "subscriber": {
    "PKey": "<PKEY>",
    ...
  },
}
```
