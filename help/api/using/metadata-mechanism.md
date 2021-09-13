---
title: メタデータのメカニズム
description: メタデータメカニズムの詳細を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---

# メタデータのメカニズム {#metadata-mechanism}

GETリクエストで&#x200B;**resourceType**&#x200B;を使用して、リソースメタデータを取得できます。

`GET /profileAndServices/resourceType/<resourceName>`

応答は、リソースからメインメタデータを返します（その他のすべてのフィールドは、説明的または内部的です）。

* **Content**&#x200B;ノードは、リソースのフィールドを返します。 **content**&#x200B;ノードの各フィールドについて、次のフィールドを見つけることができます。

   * &quot;apiName&quot;:APIで使用される属性の名前。
   * &quot;type&quot;:これは、大まかなタイプ定義（文字列、数値、リンク、コレクション、列挙など）です。
   * &quot;dataPolicy&quot;:フィールドの値は、指定されたポリシールールに従う必要があります。 例えば、dataPolicyルールが「email」に設定されている場合、値は有効な電子メールである必要があります。 PATCHまたはPOST中、dataPolicyは値を確認したり、変換する値を変更したりできます（smartCaseなど）。
   * &quot;category&quot;:クエリエディターでフィールドのカテゴリを指定します。
   * &quot;resType&quot;:技術的なタイプ。

      「type」に「link」または「collection」という値を指定した場合、resTargetの値はリンクのターゲットリソースの名前になります。
「type」に値「enumeration」を入力すると、「values」フィールドが追加され、各列挙値の詳細が**values**&#x200B;ノードに表示されます。

* **Filters**&#x200B;ノードは、関連するフィルターを取得するURLを返します。 フィルターについて詳しくは、[この節](../../api/using/filtering.md)を参照してください。

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***リクエストのサンプル***

リソースでGETリクエストを実行します。

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
