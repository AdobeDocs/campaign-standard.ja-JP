---
title: アプリケーションリソースの購読の拡張
seo-title: アプリケーションリソースの購読の拡張
description: アプリケーションリソースの購読の拡張
seo-description: null
page-status-flag: 常にアクティブ化されていない
uuid: 8879b427- b31b-4311- bf54-258a91b1fb78
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: use- case——拡張リソース
discoiquuid: 59fa74e-86fc-42d3-90da- f48580b5ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Extending the subscriptions to an application resource{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-of-adding-a-resource.md).

このリソースを拡張して、モバイルデバイスからAdobe Campaignに送信するデータを収集できます。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. Click **[!UICONTROL Create]** and choose the **[!UICONTROL Extend an existing resource]** option.
1. **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** リソースを選択して、をクリック **[!UICONTROL Create]**&#x200B;します。

   ![](assets/in_app_personal_data_4.png)

1. In the **[!UICONTROL Fields]** category of the **[!UICONTROL Data structure]** tab, define the customer data that you want to retrieve from your mobile application by clicking the **[!UICONTROL Add field]** button.

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理している場合は、すべてのアプリケーションで使用されているすべてのフィールドを一覧表示する必要があります。iOSまたはAndroidの呼び出しでは、各アプリケーションによってキャプチャされるフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. Add a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to your new field. Select your field's **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. **[!UICONTROL Link to profiles]** カテゴリ内で、Adobe Campaignデータベースから、電子メールなどのアプリケーションの購読者にプロファイルをリンクするために使用する紐付けキーを設定します。

   アプリ内メッセージでは、すべてのモバイルアプリケーションに対して1つの紐付けキーしか定義できません。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** カスタムリソースを公開します。For more information on custom resource publication, refer to this [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

