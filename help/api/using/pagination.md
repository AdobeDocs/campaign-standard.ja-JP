---
title: ページ編集
description: ページネーション操作の実行方法を説明します。
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
source-git-commit: 59405df2bbb51d7cd944a0630b2b82db864f3920

---


# ページ編集

デフォルトでは、25個のリソースがリストに読み込まれます。

_lineCountパラ **メーターを使用すると** 、応答に一覧表示されるリソースの数を制限できます。  その後、次のノードを使 **用して** 、次の結果を表示できます。

>[!NOTE]
>
>ページネーションリクエストを実行するには、必ず次 **のノード** に返されたURL値を使用します。
>
>**_lineStartリクエストが計算され** 、次のノードで返されるURL内で常に使用される必要が **あります** 。

<br/>

***サンプルリクエスト&#x200B;***

プロファイルリソースの1レコードを表示するGET要求の例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

次のノードを使用して **** 、リクエストに応答します。

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

デフォルトでは、大量の **データを含む** 、テーブルを操作する場合は次のノードを使用できません。 ページネーションを実行するには、 **_forcePagination=trueパラメーターを呼び出しURLに追加する必要があります** 。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>テーブルが大きいと見なされるレコードの数は、キャンペーン標準のXtkBigTableThresholdオプションで定義さ **れます** 。 デフォルト値は100,000レコードです。
