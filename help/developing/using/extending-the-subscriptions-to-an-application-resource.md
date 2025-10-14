---
title: アプリケーションリソースの購読の拡張
description: アプリケーションリソースの購読を拡張する方法を説明します
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 10%

---

# アプリケーションリソースの購読の拡張{#extending-the-subscriptions-to-an-application-resource}

Adobe Campaignでは、モバイルデバイスから送信されたモバイルプロファイル属性データが **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** リソースに保存されるので、アプリケーションの購読者から収集するデータを定義できます。 カスタムリソースについて詳しくは、[&#x200B; このページ &#x200B;](../../developing/using/key-steps-to-add-a-resource.md) を参照してください。

このリソースは、モバイルデバイスからAdobe Campaignに送信するデータを収集するように拡張できます。

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Custom resources]** を選択します。
1. 「**[!UICONTROL Create]**」をクリックし、「**[!UICONTROL Extend an existing resource]**」オプションを選択します。
1. **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** リソースを選択し、「**[!UICONTROL Create]**」をクリックします。

   ![](assets/in_app_personal_data_4.png)

1. 「**[!UICONTROL Data structure]**」タブの「**[!UICONTROL Fields]**」カテゴリで、「**[!UICONTROL Add field]**」ボタンをクリックして、モバイルアプリケーションから取得する顧客データを定義します。

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理している場合は、すべてのアプリケーションで使用されているすべてのフィールドがリストされている必要があります。 iOSまたはAndroidの Collect PII 呼び出しは、各アプリケーションでキャプチャされるフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. 新しいフィールドに **[!UICONTROL Label]** と **[!UICONTROL ID]** を追加します。 フィールドの **[!UICONTROL Type]** を選択します。

   ![](assets/schema_extension_uc9.png)

1. **[!UICONTROL Link to profiles]** カテゴリで、Adobe Campaign データベースからアプリケーションのサブスクライバーにプロファイルをリンクするために使用する紐付けキー（メールなど）を設定します。

   アプリ内メッセージの場合、すべてのモバイルアプリケーションに対して 1 つの紐付けキーのみを定義できます。

   ![](assets/in_app_personal_data_3.png)

1. カスタムリソースを **[!UICONTROL Save]** 開して公開します。 カスタムリソースの公開について詳しくは、この [&#x200B; ページ &#x200B;](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource) を参照してください。
