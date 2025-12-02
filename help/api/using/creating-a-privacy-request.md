---
title: プライバシーリクエストの作成
description: API を使用してプライバシーリクエストを作成する方法を説明します
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 4%

---

# プライバシーリクエストの作成 {#creating-a-privacy-request}

>[!CAUTION]
>
>[Privacy Core Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service) 統合は、すべてのアクセスリクエストと削除リクエストに使用する必要がある方法です。<!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

プライバシーリクエストは、**POST** リクエストを使用して作成されます。

リクエストを作成する前に、名前空間を定義する必要があります。 詳しくは、[&#x200B; プライバシー管理ドキュメント &#x200B;](../../start/using/privacy-requests.md) を参照してください。

ペイロードには、次のパラメーターを含める必要があります。

* **name**：一意の内部名
* **namespace**:Campaign Standard インターフェイスで設定された名前空間名
* **reconciliationValue**：名前空間で定義された紐付けキーに基づく紐付け値
* **label**：リクエストラベル
* **type**：リクエストのタイプ。 指定できる値は、「access」または「delete」です。
* **regulation**：規制タイプ。 例：「GDPR」、「CCPA」。 このパラメーターは必須で、Campaign Standard 19.4 リリース以降で使用できます。 古いビルドを使用している場合は、ペイロードに追加する必要はありません。

<br/>

***リクエストのサンプル***

この POST リクエストは、名前空間 AMCDS2 で定義されたメール紐付けキーに基づいてプライバシーリクエストを作成します。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

POST リクエストへの応答。

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```
