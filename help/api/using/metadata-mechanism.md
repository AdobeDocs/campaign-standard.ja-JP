---
solution: Campaign Standard
product: campaign
title: メタデータのメカニズム
description: メタデータのメカニズムについて詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# メタデータのメカニズム {#metadata-mechanism}

GET要求で **resourceType** :

`GET /profileAndServices/resourceType/<resourceName>`

応答は、リソースからメインメタデータを返します（他のすべてのフィールドは説明的または内部的です）。

* 「 **Content** 」ノードは、リソースのフィールドを返します。 「 **content** 」ノード内の各フィールドについて、次のフィールドを検索できます。

   * &quot;apiName&quot;:APIで使用される属性の名前。
   * &quot;type&quot;:これは、高レベルのタイプ定義(文字列、数値、リンク、コレクション、定義済みリストなど)です。
   * &quot;dataPolicy&quot;:フィールドの値は、指定したポリシールールに従う必要があります。 例えば、dataPolicyルールを「email」に設定する場合、値は有効な電子メールである必要があります。 PATCH中またはPOST中に、dataPolicyは値を確認したり、変換する値を変更したりできます（smartCaseなど）。
   * &quot;カテゴリ&quot;:は、クエリエディタでフィールドのカテゴリを示します。
   * &quot;resType&quot;:これは技術的なタイプです。

      「type」が値「link」または「collection」で完了した場合、resTarget値はリンクのターゲットとなるリソースの名前になります。
「type」が値「定義済みリスト」で完了した場合は、「values」フィールドが追加され、各定義済みリスト値が **values** ノードに詳細に設定されます。

* 「 **フィルター** 」ノードは、関連するフィルターを取得するためのURLを返します。 For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***サンプルリクエスト***

リソースに対してGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

プロファイルリソースの完全な説明を返します。

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
