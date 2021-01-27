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

Adobe Campaign では、モバイルデバイスから送信されたモバイルプロファイル属性データは、アプリケーション購読者から収集するデータを定義できる「**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**」リソースに保存されます。カスタムリソースの詳細については、[このページ](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

このリソースは、モバイルデバイスからAdobe Campaignに送信するデータを収集するように拡張できます。

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Custom resources]** を選択します。
1. **[!UICONTROL Create]**&#x200B;をクリックし、**[!UICONTROL Extend an existing resource]**&#x200B;オプションを選択します。
1. **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;リソースを選択し、**[!UICONTROL Create]**&#x200B;をクリックします。

   ![](assets/in_app_personal_data_4.png)

1. 「**[!UICONTROL Data structure]**」タブの&#x200B;**[!UICONTROL Fields]**&#x200B;カテゴリーで、**[!UICONTROL Add field]**&#x200B;ボタンをクリックして、モバイルアプリケーションから取得する顧客データを定義します。

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理している場合は、すべてのアプリケーションで使用されるすべてのフィールドを一覧に示す必要があります。 iOSまたはAndroidの収集PII呼び出しは、各アプリで取り込まれるフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. 新し追加いフィールドに対する&#x200B;**[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL ID]**。 フィールドの&#x200B;**[!UICONTROL Type]**&#x200B;を選択します。

   ![](assets/schema_extension_uc9.png)

1. **[!UICONTROL Link to profiles]**&#x200B;カテゴリーで、Adobe Campaignデータベースのプロファイルをアプリケーションのサブスクリプション（電子メールなど）にリンクするために使用する紐付けキーーを設定します。

   アプリ内メッセージで定義できる紐付けキーは、すべてのモバイルアプリに対して1つだけです。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** カスタムリソースを公開します。カスタムリソースのパブリケーションの詳細については、[ページ](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)を参照してください。

