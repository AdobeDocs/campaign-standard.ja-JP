---
title: プライバシーリクエストの作成
description: API を使用してプライバシーリクエストを作成する方法を説明します
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 28%

---

# プライバシーリクエストの作成 {#creating-a-privacy-request}

>[!CAUTION]
>
>この [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) 統合は、すべてのアクセスリクエストと削除リクエストに使用する必要があるメソッドです。 19.4 以降、アクセスリクエストと削除リクエストに対する Campaign API およびインターフェイスの使用は非推奨（廃止予定）になりました。Campaign Standard の廃止および削除された機能の詳細については、 [こちらのページ](../../rn/using/deprecated-features.md)を参照してください。

プライバシーリクエストは、 **POST** リクエスト。

 要求を作成する前に、使用する名前空間を定義する必要があります。詳しくは、 [プライバシー管理に関するドキュメント](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

ペイロードには、次のパラメーターが含まれている必要があります。

* **名前**:一意の内部名
* **名前空間**:名前空間インターフェイスで設定されたCampaign Standard名
* **reconciliationValue**:名前空間で定義された紐付けキーに基づく紐付け値
* **ラベル**:リクエストラベル
* **type**:リクエストのタイプ。 指定できる値は、「access」または「delete」です。
* **規則**:規制のタイプ。 例：「GDPR」、「CCPA」などのルールが含まれている場合にのみ有効です。 このパラメーターは必須で、Campaign Standard19.4 リリース以降で使用できます。 古いビルドを使用している場合は、ペイロードに追加する必要はありません。

<br/>

***リクエストのサンプル***

このPOSTリクエストは、名前空間 AMCDS2 で定義された E メールの紐付けキーに基づいて、プライバシーリクエストを作成します。

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

応答リクエストに対するPOST。

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
