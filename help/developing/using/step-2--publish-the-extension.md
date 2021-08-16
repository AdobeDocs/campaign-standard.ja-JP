---
solution: Campaign Standard
product: campaign
title: '"手順 2：拡張機能を公開する"'
description: 拡張機能を公開する方法をCampaign Standard。 シリーズのパート2。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: データモデル
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
source-git-commit: d3482dfad245807aedee6deb36fd67e43c7a66b9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 25%

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
