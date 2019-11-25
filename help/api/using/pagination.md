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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# ページ編集

デフォルトでは、25個のリソースがリストに読み込まれます。

_lineCountパラ **メーターを使用すると** 、応答に一覧表示されるリソースの数を制限できます。  その後、次のノードを使 **用して** 、次の結果を表示できます。

>[!NOTE]&gt;
>
>ページネーションリクエストを実行するには、必ず次 **のノード** に返されたURL値を使用します。
>
>**_lineStartリクエストが計算され** 、次のノードで返されるURL内で常に使用される必要が **あります** 。

<!-- serverside pagination. quand table très longue (au delà de 100.000), on peut plus faire de next. doit utiliser à la place les trucs type lineStart etc. si false: voudra dirre que ça a atteint la limite-->

<br/>

***サンプルリクエスト***

プロファイルリソースの1レコードを表示するGET要求の例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- dans l'exemple, avoir le node "next"-->

リクエストへの応答。

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
    ...
}
```
