---
solution: Campaign Standard
product: campaign
title: '"手順 3：拡張機能の確認"'
description: Rest APIを使用して拡張フィールドにアクセスする方法を説明します。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 15%

---


# 手順 3：拡張機能の確認{#step-verify-the-extension}

1. プロファイル&amp;サービス拡張APIのメタデータに対してGET操作を行い、プロファイルのカスタムリソースに追加されたフィールドが現在使用可能かどうかを確認します。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 次の値が返されます。

   ![](assets/extendpandsapiview.png)

   このフィールドは、さらなる開発や統合に使用できます。

