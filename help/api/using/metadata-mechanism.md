---
title: メタデータのメカニズム
description: メタデータのメカニズムについての詳細。
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# メタデータのメカニズム {#metadata-mechanism}

GET要求でresourceTypeを使用して、リソースメタデ **ータを取得できます** 。

`GET /profileAndServices/resourceType/<resourceName>`

応答は、リソースからメインメタデータを返します（その他のすべてのフィールドは説明的または内部的です）。

* Contentノ **ードは** 、リソースのフィールドを返します。 contentノードの各フィール **ドに** 、次のフィールドがあります。

   * "apiName":apiで使用される属性の名前。
   * "type":これは、高レベルのタイプ定義（文字列、数値、リンク、コレクション、列挙など）です。
   * "dataPolicy":フィールドの値は、指定したポリシールールに従う必要があります。 例えば、dataPolicyルールが「email」に設定されている場合、値は有効な電子メールである必要があります。 PATCHまたはPOSTの実行中に、dataPolicyは値を確認したり、変換する値を変更したりできます（smartCaseなど）。
   * "category":クエリエディター内のフィールドのカテゴリを示します。
   * "resType":これは技術的なタイプです。

      「type」が値「link」または「collection」で完了した場合、resTarget値はリンクのターゲットとなるリソースの名前になります。
「type」が値「enumeration」で完了した場合、「values」フィールドが追加され、各列挙値がvaluesノードに詳細 **になります** 。

* 「フィ **ルター** 」ノードは、関連するフィルターを取得するURLを返します。 For more on filters, refer to [this section](../../api/using/filtering.md) section.

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
