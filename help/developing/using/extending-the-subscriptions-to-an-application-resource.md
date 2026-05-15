---
title: アプリケーションリソースの購読の拡張
description: サブスクリプションをアプリケーションリソースに拡張する方法について説明します
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
TQID: https://experienceleague.adobe.com/LtTykn3J6LjivrUr-xkhsZMgaVg-uQ2PHqA6wcJipo8
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 233
ht-degree: 24%

---

# アプリケーションリソースの購読の拡張{#extending-the-subscriptions-to-an-application-resource}

Adobe Campaign では、モバイルデバイスから送信されたモバイルプロファイル属性データは、アプリケーション購読者から収集するデータを定義できる「**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**」リソースに保存されます。 カスタムリソースについて詳しくは、[このページ ](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

このリソースは、モバイルデバイスからAdobe Campaignに送信するデータを収集するように拡張できます。

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Custom resources]** を選択します。
1. **[!UICONTROL Create]**&#x200B;をクリックし、**[!UICONTROL Extend an existing resource]** オプションを選択します。
1. **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** リソースを選択し、**[!UICONTROL Create]**&#x200B;をクリックします。

   ![](assets/in_app_personal_data_4.png)

1. 「**[!UICONTROL Data structure]**」タブの「**[!UICONTROL Fields]**」カテゴリで、「**[!UICONTROL Add field]**」ボタンをクリックして、モバイルアプリケーションから取得する顧客データを定義します。

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理する場合は、すべてのアプリケーションで使用されるすべてのフィールドをリストする必要があります。 IOSまたはAndroid collect PII呼び出しは、各アプリケーションによってキャプチャされるフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. 新しいフィールドに&#x200B;**[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL ID]**&#x200B;を追加します。 フィールドの&#x200B;**[!UICONTROL Type]**&#x200B;を選択します。

   ![](assets/schema_extension_uc9.png)

1. **[!UICONTROL Link to profiles]** カテゴリで、Adobe Campaign データベースのプロファイルを、電子メールなどのアプリケーションのサブスクライバーにリンクするために使用する紐付けキーを設定します。

   アプリ内メッセージでは、すべてのモバイルアプリケーションに対して1つの紐付けキーしか定義できないことに注意してください。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]**&#x200B;を作成し、カスタムリソースを公開します。 カスタムリソース公開について詳しくは、この[ ページ ](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)を参照してください。
