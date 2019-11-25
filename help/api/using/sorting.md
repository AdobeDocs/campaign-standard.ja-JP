---
title: 並べ替え
description: 並べ替え操作の実行方法の詳細
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


# 並べ替え

並べ替えは、昇順または降順で行うことができます。 これを行うには、%20desc **または** %20asc **** パラメーターをリクエストに使用します。

フィールドが並べ替え可能かどうかを確認するには、「並べ替え可能」パラメータをリソースメタデータにチェックインします。 詳しくは、[この節](../../api/using/metadata-mechanism.md)を参照してください。

<br/>

***リクエストの例***

* データベース内の電子メールをアルファベット順に取得するGETリクエストの例です。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストへの応答。

   ```
   {
   "content": [
       "adam@email.com",
       "allison.durance@example.com",
       "amy.dakota@mail.com",
       "andrea.johnson@mail.com",
       ...
   ]
   ...
   }
   ```

* データベース内の電子メールを降順で取得するためのGETリクエストの例です。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストへの応答。

   ```
   {
   "content": [
       "tombinder@example.com",
       "tombinder@example.com",
       "timross@example.com",
       "john.smith@example.com",
       ...
   ]
   }
   ```
