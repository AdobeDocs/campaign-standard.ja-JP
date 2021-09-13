---
title: ページネーション
description: ページネーション操作の実行方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# ページネーション

デフォルトでは、25個のリソースがリストに読み込まれます。

**_lineCount**&#x200B;パラメーターを使用すると、応答に表示するリソースの数を制限できます。  その後、**next**&#x200B;ノードを使用して、次の結果を表示できます。

>[!NOTE]
>
>ページネーションリクエストを実行する場合は、必ず&#x200B;**次の**&#x200B;ノードで返されるURL値を使用します。
>
>**_lineStart**&#x200B;リクエストが計算され、常に&#x200B;**next**&#x200B;ノードで返されるURL内で使用する必要があります。

<br/>

***リクエストのサンプル***

プロファイルGETの1レコードを表示するサンプルリソースリクエスト。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

**next**&#x200B;ノードを使用してリクエストに応答し、ページネーションを実行します。

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

デフォルトでは、大量のデータを含むテーブルを操作する際に、**next**&#x200B;ノードは使用できません。 ページネーションを実行するには、呼び出しURLに&#x200B;**_forcePagination=true**&#x200B;パラメーターを追加する必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>上記のレコードの数のうち、テーブルの大きいと見なされるレコードの数は、Campaign Standard **XtkBigTableThreshold**&#x200B;オプションで定義されます。 デフォルト値は100,000レコードです。
