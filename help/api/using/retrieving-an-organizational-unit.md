---
title: プロファイルの組織単位の取得
description: APIを使用したプロファイルの組織単位の使用方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 37048884-bd03-46ea-8e2e-a73ad568153b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# プロファイルの組織単位の取得 {#retrieving-organizational-units}

1. プロファイルPKeyでGETリクエストを実行して、 **orgUnit** URLを取得します。
1. URLでGETリクエストを実行して、組織単位に関する詳細を取得します。

<br/>

***リクエストのサンプル***

プロファイルレコードを取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

プロファイルのorgUnit URLを返します。

```
{
  ...
  "orgUnit": {
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

URLでGETリクエストを実行して、詳細を取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

組織単位に関する詳細を返します。

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "label": "Brand 4",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand4)"
}
```
