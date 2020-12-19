---
solution: Campaign Standard
product: campaign
title: プロファイルの地理的単位の更新
description: APIを使用して地理的単位を管理する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 10%

---


# プロファイルの地理的単位の更新 {#updating-a-geographical-unit}

1. **geoUnitBase**&#x200B;リソースに対してGET要求を実行し、地理単位PKeyを取得します。
1. プロファイルのPKeyに対して、目的のGeographical単位PKeyを使用してPATCH要求を実行します。

<br/>

***サンプルリクエスト***

地理的単位のリストを取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

すべての地理的単位を返します。 プロファイルを割り当てるユニットのPKeyを取得します。

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

ペイロード内の目的のGeographicalユニットのPKeyを使用して、プロファイルに対するPATCH要求を実行します。

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
