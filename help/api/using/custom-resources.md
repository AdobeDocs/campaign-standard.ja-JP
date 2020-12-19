---
solution: Campaign Standard
product: campaign
title: カスタムリソース
description: API/を使用したカスタムリソース管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# カスタムリソース {#custom-resources}

Adobe Campaignには定義済みのデータモデルが付属しており、データは様々なリソースを介して定義されます。 独自のカスタムフィールドやカスタムテーブル（購入テーブルや製品テーブルなど）を追加するためにリソースを拡張することで、提供されるデータモデルを拡張できます。

カスタムリソースには、**/profileAndServicesExt**&#x200B;エンドポイントとカスタムリソース名を使用して、APIを介してアクセスできます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>標準では提供されていないリソースの場合は、リソース名の前に必ず<b>&quot;cus&quot;</b>プレフィックスを付けてください。

カスタムリソースがプロファイルテーブルにリンクされている限り、任意の操作を実行できます。 例えば、次のテーブル構造を考えてみましょう。

![代替テキスト](assets/cusresources.png)

この場合、**Transaction**、**TransactionDetails**、**Product**&#x200B;テーブルが&#x200B;**プロファイル**&#x200B;テーブルにリンクされている限り、それらのリソースを利用できます。

<br/>

***サンプルリクエスト***

拡張profileAndServicesExtリソースにアクセスするためのサンプルGETリクエスト。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

リンクされたすべてのカスタムリソースのリストを返します。 その後、リソースURLを使用して、このドキュメントで説明されているAPIタスクを実行できます。

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

データモデル拡張の詳細については、次のキャンペーンドキュメントを参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [APIの拡張](../../developing/using/about-extending-the-api.md)
* [他のリソースとのリンクの定義](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
