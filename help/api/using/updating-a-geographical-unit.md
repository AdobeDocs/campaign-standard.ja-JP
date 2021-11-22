---
title: プロファイルの地理的単位の更新
description: API を使用して地理的単位を管理する方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9dc07d86-00b2-4885-b6ac-0a6f9bc45236
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 10%

---

# プロファイルの地理的単位の更新 {#updating-a-geographical-unit}

1. でのGETリクエストの実行 **geoUnitBase** 地理的単位 PKey を取得するリソース。
1. 目的のPATCH単位 PKey をペイロードで使用して、プロファイル PKey に対してペイロードリクエストを実行します。

<br/>

***リクエストのサンプル***

地理的単位のリストを取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

すべての地理的単位が返されます。 プロファイルを割り当てるユニットの PKey を取得します。

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

目的の地理的単位の PKey をペイロードに含めて、プロファイルでPATCHリクエストを実行します。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
