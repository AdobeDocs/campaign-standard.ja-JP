---
title: ページネーション
description: ページネーション操作を実行する方法を説明します。
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

デフォルトでは、25 個のリソースがリストに読み込まれます。

この **_lineCount** パラメーターを使用すると、応答に表示されるリソースの数を制限できます。  その後、 **次へ** ノードを選択し、次の結果を表示します。

>[!NOTE]
>
>常に、 **次へ** ノードを使用して、ページネーションリクエストを実行します。
>
>この **_lineStart** リクエストが計算され、常に **次へ** ノード。

<br/>

***リクエストのサンプル***

プロファイルGETの 1 レコードを表示するサンプルリソースです。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

リクエストに対する応答。 **次へ** ページネーションを実行するノード。

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

デフォルトでは、 **次へ** 大量のデータを含むテーブルを操作する場合、ノードは使用できません。 ページネーションを実行するには、 **_forcePagination=true** パラメーターを呼び出し URL に追加します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>テーブルが大きいと見なされるレコードの数は、Campaign Standardで定義されます **XtkBigTableThreshold** オプション。 デフォルト値は 100,000 レコードです。
