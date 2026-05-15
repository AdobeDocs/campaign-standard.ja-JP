---
title: 手順 2：拡張機能を公開する
description: Campaign Standardで拡張機能を公開する方法を説明します。 シリーズの第2部。
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
TQID: https://experienceleague.adobe.com/BPvEkhFMAe2Xiwllo4RwTzGeXo-IPxYiEp-1sGUzK-A
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 109
ht-degree: 24%

---

# 手順 2：拡張機能を公開する{#step-publish-the-extension}

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Publication]** を選択します。
1. 「**[!UICONTROL Prepare Publication]**」ボタンをクリックします。
1. 「**[!UICONTROL Create the Profiles & Services Ext API]**」オプションを選択します。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >APIが既に公開されている場合（つまり、このリソースまたは別のリソースに対してこのオプションを1回チェックした場合）、APIの更新が強制されます。

1. 「**[!UICONTROL Profiles & Services API Preview]**」タブをクリックします。

   これにより、APIの公開が現在のバージョンのprofilesAndServicesExt APIに適用される変更が表示されます。

   ここでは、プロモーションコード フィールド（ID:cusBrand）がAPIに挿入されます。

   ![](assets/extendpandsapi_diff.png)

1. 「**[!UICONTROL Publish]**」ボタンをクリックします。
