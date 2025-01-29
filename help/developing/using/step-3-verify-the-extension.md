---
title: 手順 3：拡張機能を確認する
description: Rest API を使用して拡張フィールドにアクセスする方法を説明します。
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 16%

---

# 手順 3：拡張機能を確認する{#step-verify-the-extension}

1. プロファイルとサービス拡張機能 API のメタデータに対してGET操作を実行し、プロファイルのカスタムリソースに追加されたフィールドが使用できるかどうかを確認します。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 次の内容が返されます。

   ![](assets/extendpandsapiview.png)

   フィールドを、さらに開発および統合するために使用できるようになりました。
