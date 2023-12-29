---
title: 組織単位属性の更新
description: 組織単位属性を更新する方法を説明します
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 90841afd-ebc2-4b6a-895e-a96ef65740d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 0%

---

# 組織単位属性の更新 {#updating-organizational-unit-attributes}

1. でのGETリクエストの実行 **orgUnitBase** 組織単位 PKey を取得するリソース。
1. 組織単位でPATCHリクエストを実行し、ペイロードで更新する属性を指定します。

<br/>

***リクエストのサンプル***

組織単位のリストを取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

すべての組織単位が返されます。 目的のユニットの PKey を取得します。

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

組織単位でPATCHリクエストを実行し、ペイロードで更新する属性を指定します。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->
