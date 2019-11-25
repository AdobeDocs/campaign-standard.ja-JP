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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Custom resources {#custom-resources}

Adobe Campaignには、データが様々なリソースを介して定義される、定義済みのデータモデルが付属しています。 リソースを拡張して、購入テーブルや製品テーブルなどの独自のカスタムフィールドを追加することで、提供されるデータモデルを拡張できます。

カスタムリソースは、 **/profileAndServicesExtエンドポイントとカスタムリソ** ース名を使用して、APIを通じてアクセスできます。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>標準搭載されていないリソースの場合は、リソース名の前に必ず「 <b>cus</b> 」プレフィックスを付けてください。

カスタムリソースがプロファイルテーブルにリンクされている限り、任意の操作を実行できます。 例えば、次の表の構造を考えてみましょう。

![代替テキスト](assets/cusresources.png)

この場合、 **Transaction**、 **TransactionDetails** 、 **Product** の各表のリソースは、ProfileTableにリンクされている限り使用 **** できます。

<br/>

***サンプルリクエスト***

拡張profileAndServicesExtリソースにアクセスするためのサンプルGET要求。

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

データモデルの拡張機能について詳しくは、Campaignのドキュメントを参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [APIの拡張](../../developing/using/about-extending-the-api.md)
* [他のリソースとのリンクの定義](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
