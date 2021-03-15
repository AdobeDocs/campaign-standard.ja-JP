---
solution: Campaign Standard
product: campaign
title: '"手順 2：拡張機能の公開"'
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: データモデル
role: 開発者
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 27%

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

