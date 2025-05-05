---
title: カスタムリソース
description: API を使用したカスタムリソース管理の詳細情報/
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

Adobe Campaignには事前定義済みのデータモデルが付属しており、データは様々なリソースを使用して定義されます。 リソースを拡張することで提供されるデータモデルをエンリッチメントし、独自のカスタムフィールドや、購入テーブルや製品テーブルなどのカスタムテーブルを追加できます。

カスタムリソースには、API から **/profileAndServicesExt** エンドポイントとカスタムリソース名を使用してアクセスできます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>標準で使用されていないリソースの場合は、リソース名の前に必ず <b>&quot;cus&quot;</b> プレフィックスを付けてください。

カスタムリソースがプロファイルテーブルにリンクされている限り、カスタムリソースを使用してあらゆる操作を実行できます。 例えば、次のテーブル構造について考えてみましょう。

![ 代替テキスト ](assets/cusresources.png)

この場合、**Profile** テーブルにリンクされている限り、**Transaction** テーブル、**TransactionDetails** テーブル、および **Product** テーブルのすべてのリソースを使用できます。

<br/>

***リクエストのサンプル***

拡張された profileAndServicesExt リソースにアクセスするためのサンプルGETリクエスト。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

リンクされたすべてのカスタムリソースのリストを返します。 その後、リソースの URL を使用して、このドキュメントで説明している API タスクを実行できます。

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

データモデル拡張について詳しくは、次の Campaign ドキュメントを参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [API の拡張](../../developing/using/about-extending-the-api.md)
* [ 他のリソースとのリンクの定義 ](https://helpx.adobe.com/jp/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
