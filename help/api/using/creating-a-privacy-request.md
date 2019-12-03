---
title: プライバシーリクエストの作成
description: APIを使用してプライバシーリクエストを作成する方法を説明します。
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# プライバシーリクエストの作成 {#creating-a-privacy-request}

>[!CAUTION]
>
>「プライ [バシーコアサービス](https://adobe.io/apis/cloudplatform/gdpr.html) 」統合は、すべてのアクセスおよび削除要求に対して使用する必要がある方法です。 19.4以降、アクセスおよび削除のリクエストに対するCampaign APIとインターフェイスの使用は廃止されました。 Campaign Standardの廃止および削除された機能の詳細については、このページを参照 [してください](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。

プライバシーリクエストは **POSTリクエストを使用して作成され** ます。

 要求を作成する前に、使用する名前空間を定義する必要があります。詳しくは、プライバシー管理のドキュメント [を参照してください](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

ペイロードには、次のパラメーターが含まれている必要があります。

* **name**:一意の内部名
* **名前空間**:campaign Standardインターフェイスで設定された名前空間名
* **reconciliationValue**:名前空間で定義された調整キーに基づく調整値
* **label**:要求ラベル
* **type**:リクエストタイプ。 指定できる値は、「access」または「delete」です。
* **規則**:規則のタイプ。 例："GDPR"、"CCPA"。 このパラメーターは必須で、Campaign Standard 19.4リリース以降で使用できます。 古いビルドを使用している場合は、ペイロードに追加する必要はありません。

<br/>

***サンプルリクエスト***

このPOSTリクエストは、名前空間AMCDS2で定義された電子メール調整キーに基づいてプライバシーリクエストを作成します。

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
