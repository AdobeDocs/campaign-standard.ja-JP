---
title: '"手順 2：拡張機能を公開する"'
description: 拡張機能を公開する方法をCampaign Standard。 シリーズのパート2。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 23%

---

# 手順 2：拡張機能を公開する{#step-publish-the-extension}

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Publication]** を選択します。
1. 「**[!UICONTROL Prepare Publication]**」ボタンをクリックします。
1. **[!UICONTROL Create the Profiles & Services Ext API]**&#x200B;オプションを選択します。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >APIが既に公開されている場合（このリソースまたは別のリソースに対してこのオプションを既に1回オンにしている場合）は、APIの更新が強制されます。

1. 「**[!UICONTROL Profiles & Services API Preview]**」タブをクリックします。

   これにより、APIの公開が現在のバージョンのprofilesAndServicesExt APIに適用される変更が示されます。

   ここでは、「プロモーションコード」フィールド(ID:cusBrand )がAPIに挿入されます。

   ![](assets/extendpandsapi_diff.png)

1. 「**[!UICONTROL Publish]**」ボタンをクリックします。
