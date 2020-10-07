---
title: カスタムリソース
description: API/を使用したカスタムリソース管理の詳細
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
source-wordcount: '204'
ht-degree: 5%

---


# カスタムリソース {#custom-resources}

Adobe Campaignには定義済みのデータモデルが付属しており、データは様々なリソースを介して定義されます。 独自のカスタムフィールドやカスタムテーブル（購入テーブルや製品テーブルなど）を追加するためにリソースを拡張することで、提供されるデータモデルを拡張できます。

カスタムリソースは、 **/profileAndServicesExt** エンドポイントとカスタムリソース名を使用して、APIを介してアクセスできます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>リソースがすぐに使用できない場合は、リソース名の前に必ず「 <b>cus</b> 」プレフィックスを付けてください。

カスタムリソースがプロファイルテーブルにリンクされている限り、任意の操作を実行できます。 例えば、次のテーブル構造を考えてみましょう。

![代替テキスト](assets/cusresources.png)

この場合、 **Transaction**、TransactionDetails **、** Product **表のリソースは、****** プロファイル表にリンクされている限り、すべて使用できます。

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
