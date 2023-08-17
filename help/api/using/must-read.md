---
title: 必読
description: API を使用する前にお読みください。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9e2d1b59-55a5-4715-adfb-35191a9df536
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# 必読 {#must-read}

## 技術要件

* Adobe Campaign API は、サーバー間でのみ使用する必要があります。
* 実装する使用例がAdobe Campaign API で許可されるスケールと一致している場合は、必ずAdobeの技術担当者にお問い合わせください。
* AdobeIO アクセスを設定するには、特定の権限が必要です。問題が発生した場合は、Adobeサポートに問い合わせてください。

## 権限とアクセス

* デフォルトでは、Adobe Campaign API は管理者のコンテキストを使用するので、組織単位と役割は適用されません。
* Adobe Campaign API は、役割コンテキストから除外されます。
* 組織単位またはロールで API を設定する場合は、まず担当の担当者に問い合わせて、テクニカルコンタクトのAdobeにお問い合わせください。

## リソース表現

すべての API リソースは、 **JSON** URL 拡張子または HTTP Accept ヘッダー内に：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>URL に拡張子がない場合、 **json 形式はデフォルトの形式です。** content-type の場合は。

<br/>

***リクエストのサンプル***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## プライマリキーと URL

* 自分で URL を作成しないようにしてください。 すべての URL は API から返されます。 ただし、最上位のリソース名に基づいて URL を作成することはできます。

* この例を示す自動プライマリキー (PKey) 値は、別の特定の配置で機能することを意図していません。 これらはAdobe Campaign API で生成されます。

* Adobe Campaignで生成される自動プライマリキーの値は、外部のデータベースまたは Web サイトに保存しないでください。 データベース定義で特定のキーフィールドを生成し、開発時に使用する必要があります。

## カスタムキー {#custom-keys}

プロファイルリソースがカスタムキーフィールドを使用して拡張されている場合、Adobe Campaignで生成される自動プライマリキーの代わりに、このフィールドをキーとして使用できます。

`GET /.../profileAndServicesExt/profile/<customKey>`

キーの値が元のキーと異なる場合や、Adobeが提供するキーの代わりに独自のビジネスキーを URI として使用している場合は、PATCH操作を使用してカスタムキーを変更することはできません。

カスタムキーを使用： **トップレベルのプロファイルリソース** のみ。 URL は API によって返されるので、自身で作成しないでください。

<br/>

***リクエストのサンプル***

カスタムキーを使用してプロファイルのサブスクリプションを取得するには、カスタムキーでGET操作を実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

返されたGETURL に対してデータリクエストを実行します。

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
