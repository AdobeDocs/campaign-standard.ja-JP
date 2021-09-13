---
title: カスタムリソース
description: APIを使用したカスタムリソース管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---

# カスタムリソース {#custom-resources}

Adobe Campaignには、様々なリソースを介してデータが定義される、事前定義済みのデータモデルが付属しています。 リソースを拡張して独自のカスタムフィールドや、購入テーブルや製品テーブルなどのカスタムテーブルを追加することで、提供されるデータモデルをエンリッチメントできます。

カスタムリソースは、 **/profileAndServicesExt**&#x200B;エンドポイントとカスタムリソース名を使用して、APIを通じてアクセスできます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>標準で用意されていないリソースの場合は、常にリソース名の前に<b>&quot;cus&quot;</b>プレフィックスを使用します。

プロファイルテーブルにリンクされている限り、カスタムリソースを使用して任意の操作を実行できます。 例えば、次に示すテーブル構造を考えてみましょう。

![代替テキスト](assets/cusresources.png)

この場合、**Transaction**、**TransactionDetails**&#x200B;および&#x200B;**Product**&#x200B;テーブルが&#x200B;**Profile**&#x200B;テーブルにリンクされている限り、それらのテーブルのすべてのリソースを使用できます。

<br/>

***リクエストのサンプル***

拡張profileAndServicesExtリソースにアクセスするためのGETリクエストのサンプル。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

リンクされたすべてのカスタムリソースのリストを返します。 その後、リソースURLを使用して、このドキュメントに記載されているAPIタスクを実行できます。

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

データモデル拡張について詳しくは、Campaignのドキュメントを参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [APIの拡張](../../developing/using/about-extending-the-api.md)
* [他のリソースとのリンクの定義](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
