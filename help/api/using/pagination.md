---
solution: Campaign Standard
product: campaign
title: ページ編集
description: ページネーション操作の実行方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# ページ編集

デフォルトでは、25個のリソースがリストに読み込まれます。

**_lineCount**&#x200B;パラメーターを使用すると、応答に含めるリソースの数を制限できます。  その後、**次の**&#x200B;ノードを使用して、次の結果を表示できます。

>[!NOTE]
>
>**次の**&#x200B;ノードで返されたURL値を常に使用して、ページネーションリクエストを実行します。
>
>**_lineStart**&#x200B;リクエストが計算され、**次の**&#x200B;ノードで返されるURL内で常に使用される必要があります。

<br/>

***サンプルリクエスト***

プロファイルリソースの1レコードを表示するサンプルGETリクエスト。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

**次の**&#x200B;ノードを使用して、リクエストに応答し、ページネーションを実行します。

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

デフォルトでは、大量のデータを含むテーブルを操作する場合、**次の**&#x200B;ノードは使用できません。 ページ番号割り付けを実行するには、呼び出しURLに&#x200B;**_forcePagination=true**&#x200B;パラメーターを追加する必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>テーブルが大きいと見なされるレコードの数は、Campaign Standard **XtkBigTableThreshold**&#x200B;に定義されています。 デフォルト値は100,000レコードです。
