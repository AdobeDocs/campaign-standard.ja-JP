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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 21%

---


# プライバシーリクエストの作成 {#creating-a-privacy-request}

>[!CAUTION]
>
>The [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) Integration is the method you should use for all access and delete requests. 19.4 以降、アクセス要求および削除要求に対する Campaign API およびインターフェイスの使用は廃止されます。廃止および削除された機能のCampaign Standardについて詳しくは、 [このページを参照してください](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)。

プライバシーリクエストは、 **POST** リクエストを使用して作成されます。

 要求を作成する前に、使用する名前空間を定義する必要があります。詳しくは、 [プライバシー管理のドキュメントを参照してください](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

ペイロードには、次のパラメーターを含める必要があります。

* **name**:一意の内部名
* **名前空間**:campaign standardインターフェイスで設定された名前空間名
* **reconcilationValue**:名前空間で定義された紐付けキーに基づく調整値
* **label**:要求ラベル
* **type**:リクエストタイプ。 指定できる値は、「access」または「delete」です。
* **規則**:規則の種類。 例：&quot;GDPR&quot;、&quot;CCPA&quot;。 このパラメーターは必須で、Campaign Standard19.4リリースから使用できます。 古いビルドを使用している場合は、ペイロードに追加する必要はありません。

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
