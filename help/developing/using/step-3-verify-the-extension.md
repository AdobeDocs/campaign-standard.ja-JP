---
title: 手順 3：拡張機能を確認する
description: Rest APIを使用して拡張フィールドにアクセスする方法を説明します。
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
TQID: https://experienceleague.adobe.com/XadrenC5de4Xh6MSCUiQUc-qXaTKr-xpG-7znnlWeeQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: d5ef99fa-df0c-4153-bf94-105ad0724167
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 61
ht-degree: 16%

---

# 手順 3：拡張機能を確認する{#step-verify-the-extension}

1. Profiles &amp; Services Extension APIのメタデータに対してGET操作を実行し、Profiles カスタムリソースに追加されたフィールドが使用可能かどうかを確認します。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 次の結果が返されます。

   ![](assets/extendpandsapiview.png)

   フィールドは、今後の開発と統合のために使用できるようになりました。
