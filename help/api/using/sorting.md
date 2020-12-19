---
solution: Campaign Standard
product: campaign
title: 並べ替え
description: 並べ替え操作の実行方法の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---


# 並べ替え

並べ替えは、昇順または降順で行うことができます。 これを行うには、**%20desc**&#x200B;または&#x200B;**%20asc**&#x200B;パラメーターをリクエストに使用します。

フィールドが並べ替え可能かどうかを確認するには、「並べ替え可能」パラメータをリソースメタデータにチェックインします。 詳しくは、[こちらの節](../../api/using/metadata-mechanism.md)を参照してください。

<br/>

***リクエストのサンプル***

* GET内の電子メールをアルファベット順に取得する場合のデータリクエスト例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストに対する応答。

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

* GET内の電子メールを降順で取得するためのサンプルデータリクエストです。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストに対する応答。

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
