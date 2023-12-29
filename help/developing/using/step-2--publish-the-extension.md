---
title: 手順 2：拡張機能の公開
description: 拡張機能を公開する方法について説明します。Campaign Standard シリーズのパート 2。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 20%

---

# 手順 2：拡張機能を公開する{#step-publish-the-extension}

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Publication]** を選択します。
1. 「**[!UICONTROL Prepare Publication]**」ボタンをクリックします。
1. を選択します。 **[!UICONTROL Create the Profiles & Services Ext API]** オプション。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >API が既に公開されている場合（つまり、このリソースまたは別のリソースでこのオプションを既に 1 回オンにしている場合）は、API の更新が強制されます。

1. 次をクリック： **[!UICONTROL Profiles & Services API Preview]** タブをクリックします。

   これにより、API の公開が profilesAndServicesExt API の現在のバージョンに適用される変更が示されます。

   ここで、「プロモーションコード」フィールド (ID: cusBrand) が API に挿入されます。

   ![](assets/extendpandsapi_diff.png)

1. 「**[!UICONTROL Publish]**」ボタンをクリックします。
