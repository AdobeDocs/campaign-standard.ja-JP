---
title: '"手順 3：拡張機能を確認する"'
description: Rest APIを使用して拡張フィールドにアクセスする方法を説明します。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---

# 手順 3：拡張機能を確認する{#step-verify-the-extension}

1. Profiles &amp; Services拡張APIのメタデータに対してGET操作を実行し、Profilesカスタムリソースに追加されたフィールドが使用可能になったかどうかを確認します。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 次の値を返します。

   ![](assets/extendpandsapiview.png)

   「 」フィールドをさらに開発および統合できるようになりました。
