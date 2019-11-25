---
title: 地理的単位の管理
description: APIを使用して地理的単位を管理する方法を説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# 地理的単位の管理 {#managing-geographical-units}

>[!CAUTION]
>
>地理的単位機能は、Campaign Standard 18.7リリースで廃止されました。
その結果、新しいCampaign Standardのインスタンスと、地理的単位が作成されていない既存のインスタンスでは、18.7リリースからこの機能を実装できません。
For more on this, refer to the <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">Deprecated features</a> page.

geoUnitBaseエン **ドポイントを使用すると** 、地理的単位を操作できます。例えば、その属性を更新したり、プロファイルの単位を更新したりできます。

プロファ **イルリソースを拡張する際に** 、「地理的単位」フィールドがプロファイルに追加されます。 そのため、必ずprofileAndServicesExtエンドポイントを使用して **地理的単位とやり取りします** 。 プロファイルのリソース拡張機能について詳しくは、 [Campaignのドキュメントを参照してください](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)。

## プロファイルの地理的単位の取得

1. プロファイルPKeyに対してGET要求を実行し、geoUnit **** URLを取得します。
1. URLに対してGETリクエストを実行し、地理的単位に関する詳細を取得します。

<br/>

***サンプルリクエスト***

プロファイルレコードを取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

プロファイルのgeoUnit URLを返します。

```
{
  ...
  "geoUnit": {
    "PKey": "@zYV4vIjP1wpBebml6s71hjGiDhs4_gHgbC_UhuJFk8h7XTZxZ5QnZrPnQPEfB__TxwR2ge6sz61D8RR4zvD75CLDZtc<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

URLに対してGETリクエストを実行し、詳細を取得します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

地理的単位に関する詳細を返します。

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "Default geographical entity (accessible to everyone)",
  "label": "All",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "all",
  "parentTitle": "",
  "title": "All (all)"
}
```

## プロファイルの地理単位の更新

1. 地理単位PKeyを取得するには、geoUnitBase **** リソースに対してGET要求を実行します。
1. ペイロード内の目的の地理単位PKeyを使用して、プロファイルPKeyに対してPATCH要求を実行します。

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

すべての地理単位を返します。 プロファイルを割り当てるユニットのPKeyを取得します。

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

ペイロード内の目的の地理単位のPKeyを使用して、プロファイルに対してPATCHリクエストを実行します。

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

## 地理的単位属性の更新

1. 地理単位PKeyを取得するには、geoUnitBase **** リソースに対してGET要求を実行します。
1. ペイロード内で更新する属性を使用して、地理的単位でPATCHリクエストを実行します。

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

すべての地理単位を返します。 目的のユニットのPKeyを取得します。

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

ペイロード内で更新する属性を使用して、地理的単位でPATCHリクエストを実行します。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->
