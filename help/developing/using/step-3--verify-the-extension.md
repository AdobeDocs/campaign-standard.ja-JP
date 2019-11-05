---
title: '"手順 3：拡張機能の確認"'
description: Rest APIを使用して拡張フィールドにアクセスする方法を説明します。
page-status-flag: 非活性化の
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: use-case—extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 手順 3：拡張機能の確認{#step-verify-the-extension}

1. Profiles &amp; Services Extension APIのメタデータに対してGET操作を行い、Profilesカスタムリソースに追加されたフィールドが利用可能になったかどうかを確認します。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 次の値が返されます。

   ![](assets/extendpandsapiview.png)

   このフィールドは、今後の開発と統合に使用できるようになります。

