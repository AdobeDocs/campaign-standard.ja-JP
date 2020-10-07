---
title: '"手順 3：拡張機能の確認"'
description: Rest APIを使用して拡張フィールドにアクセスする方法を説明します。
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---


# 手順 3：拡張機能の確認{#step-verify-the-extension}

1. プロファイル&amp;サービス拡張APIのメタデータに対してGET操作を行い、プロファイルのカスタムリソースに追加されたフィールドが現在使用可能かどうかを確認します。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 次の値が返されます。

   ![](assets/extendpandsapiview.png)

   このフィールドは、さらなる開発や統合に使用できます。

