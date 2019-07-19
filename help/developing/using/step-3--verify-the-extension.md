---
title: 「手順3:「拡張機能の検証」
seo-title: 「手順3:「拡張機能の検証」
description: 「手順3:「拡張機能の検証」
seo-description: REST APIを使用して拡張フィールドにアクセスする方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 35ba89a5- a354-466f-91a0-50de111a2e00
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: use- case——extending- the- api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Step 3: Verify the extension{#step-verify-the-extension}

1. Profiles&amp; Services Extension APIのメタデータでGET操作を行い、プロファイルカスタムリソースに追加されたフィールドが使用可能かどうかを確認します。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 返されます。

   ![](assets/extendpandsapiview.png)

   このフィールドは、さらなる開発と統合に使用できるようになりました。

