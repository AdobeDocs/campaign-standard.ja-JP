---
title: '"手順 2：拡張機能の公開"'
description: null
page-status-flag: never-activated
uuid: 0c944ed0-3007-4c1b-8960-41c7ef6121cf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: b57042e5-5073-4e79-a3e3-1eed824ac537
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 26%

---


# 手順 2：拡張機能の公開{#step-publish-the-extension}

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Publication]** を選択します。
1. 「**[!UICONTROL Prepare Publication]**」ボタンをクリックします。
1. オプションを選択し **[!UICONTROL Create the Profiles & Services Ext API]** ます。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >APIが既に公開されている場合（つまり、このリソースまたは他のリソースに対して、このオプションを1回既にチェックしている場合）、APIの更新が強制的に行われます。

1. タブをクリックし **[!UICONTROL Profiles & Services API Preview]** ます。

   これは、APIのパブリケーションがprofilesAndServicesExt APIの現在のバージョンに適用する変更を示します。

   ここでは、プロモーションコードフィールド(ID:cusBrand)がAPIに挿入されます。

   ![](assets/extendpandsapi_diff.png)

1. 「**[!UICONTROL Publish]**」ボタンをクリックします。

