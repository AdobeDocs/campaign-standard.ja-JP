---
title: カスタムリソース
description: API を使用したカスタムリソース管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 3%

---

# カスタムリソース {#custom-resources}

Adobe Campaignには、様々なリソースを使用してデータが定義される、事前定義済みのデータモデルが付属しています。 リソースを拡張して独自のカスタムフィールドや、購入テーブルや製品テーブルなどのカスタムテーブルを追加することで、提供されるデータモデルをエンリッチメントできます。

カスタムリソースには、 **/profileAndServicesExt** エンドポイント、およびカスタムリソース名。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>標準では提供されていないリソースの場合、常に <b>&quot;cus&quot;</b> プレフィックスを付けます。

プロファイルテーブルにリンクされている限り、カスタムリソースを使用して任意の操作を実行できます。 例えば、以下のテーブル構造を考えてみましょう。

![代替テキスト](assets/cusresources.png)

その場合、 **トランザクション**, **TransactionDetails** および **製品** テーブルは、リンクされている限り使用できます **プロファイル** 表。

<br/>

***リクエストのサンプル***

拡張 profileAndServicesExt リソースにアクセスするためのGETリクエストの例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

リンクされたすべてのカスタムリソースのリストを返します。 その後、リソース URL を使用して、このドキュメントで説明されている任意の API タスクを実行できます。

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

データモデルの拡張について詳しくは、次の Campaign ドキュメントを参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [API の拡張](../../developing/using/about-extending-the-api.md)
* [他のリソースとのリンクの定義](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
