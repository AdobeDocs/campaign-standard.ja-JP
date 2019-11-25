---
title: 必読
description: APIを使用する前に読む必要があります。
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


# 必読 {#must-read}

## 技術要件

* Adobe Campaign APIは、サーバー間でのみ使用する必要があります。
* 導入するユースケースがAdobe Campaign APIで許可されているスケールと一致する場合は、必ずアドビのテクニカル担当者にお問い合わせください。
* Adobe IOアクセスの設定には特定の権限が必要です。問題が発生した場合は、アドビサポートにお問い合わせください。

## リソース表現

すべてのAPIリソースは、 **URL拡張子が付いた** JSON、またはHTTP受け入れヘッダー内で使用できます。

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>URLに拡張子がない場合、 **json形式はcontent-typeのデフォルトの形式** になります。

<br/>

***要求サンプル***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## 主キーとURL

* URLを自分で作成しないでください。 すべてのURLがAPIから返されます。 ただし、最上位のリソース名に基づいてURLを作成することは可能です。

* この例を示す自動主キー(PKey)値は、別の特定の展開で動作することを意図していません。 これらは、Adobe Campaign APIによって生成されます。

* Adobe Campaignで生成された自動主キーの値は、外部のデータベースやWebサイトに保存しないでください。 データベース定義で特定のキーフィールドを生成し、開発時に使用する必要があります。

## カスタムキー {#custom-keys}

プロファイルリソースがカスタムキーフィールドを使用して拡張されている場合、Adobe Campaignで生成された自動主キーの代わりに、このフィールドをキーとして使用できます。

`GET /.../profileAndServicesExt/profile/<customKey>`

キー値が元のキーと異なる場合、またはアドビが提供するキーの代わりに独自のビジネスキーをURIとして使用している場合は、PATCH操作を使用してカスタムキーを変更することはできません。

トップレベルのプロファイルリ **ソースに対してのみカスタムキーを使用** 。 URLはAPIによって返され、決して独自に作成する必要はありません。

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
