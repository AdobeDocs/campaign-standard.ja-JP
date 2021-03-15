---
solution: Campaign Standard
product: campaign
title: プライバシーリクエストの作成
description: APIを使用してプライバシーリクエストを作成する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 20%

---


# プライバシーリクエストの作成 {#creating-a-privacy-request}

>[!CAUTION]
>
>[プライバシーコアサービス](https://adobe.io/apis/cloudplatform/gdpr.html)統合は、すべてのアクセス要求と削除要求で使用する必要がある方法です。 19.4 以降、アクセス要求および削除要求に対する Campaign API およびインターフェイスの使用は廃止されます。廃止および削除された機能のCampaign Standardについて詳しくは、[このページ](../../rn/using/deprecated-features.md)を参照してください。

プライバシーリクエストは、**POST**&#x200B;リクエストを使用して作成されます。

 要求を作成する前に、使用する名前空間を定義する必要があります。詳しくは、[プライバシー管理ドキュメント](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)を参照してください。

ペイロードには、次のパラメーターを含める必要があります。

* **name**:一意の内部名
* **名前空間**:Campaign Standardインターフェイスで設定された名前空間名
* **reconcilationValue**:名前空間で定義された紐付けキーに基づく調整値
* **label**:要求ラベル
* **type**:リクエストタイプ。指定できる値は、「access」または「delete」です。
* **規則**:規則の種類。例：&quot;GDPR&quot;、&quot;CCPA&quot;。 このパラメーターは必須で、Campaign Standard19.4リリースから使用できます。 古いビルドを使用している場合は、ペイロードに追加する必要はありません。

<br/>

***サンプルリクエスト***

このPOSTリクエストは、名前空間AMCDS2で定義されている電子メール紐付けキーに基づいて、プライバシーリクエストを作成します。

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

POSTリクエストへの応答。

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
