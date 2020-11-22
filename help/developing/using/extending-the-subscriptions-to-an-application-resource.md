---
solution: Campaign Standard
product: campaign
title: アプリケーションリソースへのサブスクリプションの拡張
description: null
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# アプリケーションリソースへのサブスクリプションの拡張{#extending-the-subscriptions-to-an-application-resource}

Adobe Campaign では、モバイルデバイスから送信されたモバイルプロファイル属性データは、アプリケーション購読者から収集するデータを定義できる「**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**」リソースに保存されます。For more information on custom resources, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

このリソースは、モバイルデバイスからAdobe Campaignに送信するデータを収集するように拡張できます。

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Custom resources]** を選択します。
1. をクリック **[!UICONTROL Create]** し、 **[!UICONTROL Extend an existing resource]** オプションを選択します。
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. タブの **[!UICONTROL Fields]** カテゴリで、ボタンをクリックして、モバイルアプリから取得する顧客データを定義し **[!UICONTROL Data structure]****[!UICONTROL Add field]** ます。

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理している場合は、すべてのアプリケーションで使用されるすべてのフィールドを一覧に示す必要があります。 iOSまたはAndroidの収集PII呼び出しは、各アプリで取り込まれるフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. 新しいフィ追加ールドに対するaおよびa **[!UICONTROL Label]****[!UICONTROL ID]** を指定します。 フィールドの名前を選択し **[!UICONTROL Type]**&#x200B;ます。

   ![](assets/schema_extension_uc9.png)

1. カテゴリで、紐付けキーデータベースのプロファイルを電子メールなどのAdobe Campaignのサブスクライバーにリンクするために使用するを設定します。 **[!UICONTROL Link to profiles]**

   アプリ内メッセージで定義できる紐付けキーは、すべてのモバイルアプリに対して1つだけです。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** カスタムリソースを公開します。 カスタムリソースの発行の詳細については、この [ページを参照してください](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

