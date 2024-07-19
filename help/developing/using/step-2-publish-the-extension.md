---
title: 「手順 2：拡張機能のPublish」
description: Campaign Standardで拡張機能を公開する方法を説明します。 シリーズのパート 2。
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 20%

---

# 手順 2：拡張機能を公開する{#step-publish-the-extension}

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Publication]** を選択します。
1. 「**[!UICONTROL Prepare Publication]**」ボタンをクリックします。
1. **[!UICONTROL Create the Profiles & Services Ext API]** オプションを選択します。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >API が既に公開済みの場合（つまり、このリソースまたは別のリソースに対してこのオプションを既に 1 回オンにしている場合）、API の更新は強制的に行われます。

1. 「**[!UICONTROL Profiles & Services API Preview]**」タブをクリックします。

   これにより、API の公開が profilesAndServicesExt API の現在のバージョンに適用される変更が表示されます。

   ここでは、「プロモーションコード」フィールド（ID: cusBrand）が API に挿入されます。

   ![](assets/extendpandsapi_diff.png)

1. 「**[!UICONTROL Publish]**」ボタンをクリックします。
