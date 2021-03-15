---
solution: Campaign Standard
product: campaign
title: 必読
description: APIを使用する前に読む必要があります。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---


# 必ず読む{#must-read}

## 技術要件

* Adobe CampaignAPIは、サーバー間でのみ使用する必要があります。
* 導入したい使用事例が、Adobe CampaignAPIで許可されている規模と一致する場合は、必ずAdobeのテクニカルコンタクトにお問い合わせください。
* Adobe IOアクセスの設定には、特定の権限が必要です。問題が発生した場合は、Adobeサポートに問い合わせてください。

## リソースの表現

すべてのAPIリソースは、URL拡張子が付いた&#x200B;**JSON**&#x200B;で、またはHTTP Accept Header内で入手できます。

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>URLに拡張子がない場合、**json形式はcontent-typeのデフォルトの形式です**。

<br/>

***リクエストサンプル***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## プライマリキーとURL

* 自分でURLを作成しないでください。 すべてのURLがAPIから返されます。 ただし、最上位のリソース名に基づいてURLを作成することは可能です。

* この例を示す自動主キー(PKey)値は、別の特定の展開で機能することを意図していません。 これらはAdobe CampaignAPIによって生成されます。

* Adobe Campaignが生成する自動プライマリキーの値を、外部のデータベースまたはWebサイトに保存しないでください。 データベース定義で特定のキーフィールドを生成し、開発時に使用する必要があります。

## カスタムキー{#custom-keys}

プロファイルリソースがカスタムキーフィールドを使用して拡張されている場合は、Adobe Campaignが生成する自動プライマリキーの代わりに、このフィールドをキーとして使用できます。

`GET /.../profileAndServicesExt/profile/<customKey>`

キーの値が接触チャネルキーと異なる場合や、Adobeが提供するキーではなく独自のビジネスキーをURIとして使用している場合は、PATCH操作を使用してカスタムキーを変更することはできません。

**トップレベルのプロファイルリソース**&#x200B;に対してのみ、カスタムキーを使用します。 URLはAPIから返されるので、決して自分で作成しないでください。

<br/>

***サンプルリクエスト***

カスタムキーを使用してプロファイルの購読を取得するには、カスタムキーに対してGET操作を実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

返された購読URLに対してGETリクエストを実行します。

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

プロファイルの購読のリストを返します。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
