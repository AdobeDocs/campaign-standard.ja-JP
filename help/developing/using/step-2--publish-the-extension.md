---
solution: Campaign Standard
product: campaign
title: '"手順 2：拡張機能の公開"'
description: null
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 26%

---


# 手順 2：拡張機能の公開{#step-publish-the-extension}

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Publication]** を選択します。
1. 「**[!UICONTROL Prepare Publication]**」ボタンをクリックします。
1. **[!UICONTROL Create the Profiles & Services Ext API]**&#x200B;オプションを選択します。

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >APIが既に公開されている場合（つまり、このリソースまたは他のリソースに対して、このオプションを1回既にチェックしている場合）、APIの更新が強制的に行われます。

1. 「**[!UICONTROL Profiles & Services API Preview]**」タブをクリックします。

   これは、APIのパブリケーションがprofilesAndServicesExt APIの現在のバージョンに適用する変更を示します。

   ここでは、プロモーションコードフィールド(ID:cusBrand)がAPIに挿入されます。

   ![](assets/extendpandsapi_diff.png)

1. 「**[!UICONTROL Publish]**」ボタンをクリックします。

