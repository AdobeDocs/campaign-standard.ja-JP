---
title: 並べ替え
description: 並べ替え操作の実行方法の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---

# 並べ替え

並べ替えは、昇順または降順で使用できます。 これをおこなうには、 **%20desc** または **%20asc** パラメーターをリクエストに追加します。

フィールドを並べ替えることができるかどうかを知るには、リソースメタデータに「sortable」パラメーターをチェックします。 詳しくは、[この節](../../api/using/metadata-mechanism.md)を参照してください。

<br/>

***リクエストのサンプル***

* GET内の E メールをアルファベット順に取得するサンプルデータリクエスト。

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

* GET内の E メールを降順で取得するサンプルデータリクエスト。

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
