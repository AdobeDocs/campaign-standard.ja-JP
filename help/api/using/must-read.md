---
title: 必読
description: APIを使用する前にお読みください。
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

* Adobe Campaign APIは、サーバー間でのみ使用する必要があります。
* 実装するユースケースがAdobe Campaign APIで許可されるスケールと一致している場合は、必ずAdobeの技術担当者にお問い合わせください。
* Adobe I/Oアクセスを設定するには、特定の権限が必要です。問題が発生した場合は、Adobeサポートにお問い合わせください。

## 権限とアクセス

* デフォルトでは、Adobe Campaign APIは管理者コンテキストを使用するので、組織単位と役割は適用されません。
* Adobe Campaign APIは、ロールコンテキストから除外されます。
* 組織単位またはロールでAPIを設定する場合は、まず担当の担当者にお問い合わせのうえ、技術担当者にお問い合わせください。

## リソース表現

すべてのAPIリソースは、URL拡張子を持つ&#x200B;**JSON**&#x200B;またはHTTP Acceptヘッダー内で使用できます。

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>URLに拡張子がない場合、**json形式はcontent-typeのデフォルトの**&#x200B;です。

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

* 自分でURLを作成しないでください。 すべてのURLはAPIから返されます。 ただし、最上位のリソース名に基づいてURLを作成することはできます。

* この例を示す自動プライマリキー(PKey)値は、別の特定のデプロイメントでは機能しません。 これらはAdobe Campaign APIで生成されます。

* Adobe Campaignで生成される自動プライマリキー値は、外部のデータベースまたはWebサイトに保存しないでください。 データベース定義で特定のキーフィールドを生成し、開発時に使用する必要があります。

## カスタムキー {#custom-keys}

プロファイルリソースがカスタムキーフィールドを使用して拡張されている場合、Adobe Campaignによって生成される自動プライマリキーの代わりに、このフィールドをキーとして使用できます。

`GET /.../profileAndServicesExt/profile/<customKey>`

キー値が元のキーと異なる場合や、Adobeが提供するURIの代わりに独自のビジネスキーをURIとして使用している場合は、PATCH操作を使用してカスタムキーを変更することはできません。

**トップレベルのプロファイルリソース**&#x200B;に対してのみカスタムキーを使用します。 URLはAPIによって返され、自分で作成しないでください。

<br/>

***リクエストのサンプル***

カスタムキーを使用してプロファイルの購読を取得するには、カスタムキーに対してGET操作を実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

返されたGETURLに対してサブスクリプションリクエストを実行します。

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
