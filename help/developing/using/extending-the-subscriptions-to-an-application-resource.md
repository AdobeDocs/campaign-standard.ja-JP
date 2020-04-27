---
title: アプリケーションリソースへのサブスクリプションの拡張
description: null
page-status-flag: never-activated
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# アプリケーションリソースへのサブスクリプションの拡張{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers. For more information on custom resources, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

このリソースは、モバイルデバイスからデバイスに送信するデータを収集するために拡張できます。Adobe Campaign

1. 詳細メニューのAdobe Campaignロゴから/を選 **[!UICONTROL Administration]** 択し、 **[!UICONTROL Development]**&#x200B;を選択しま **[!UICONTROL Custom resources]**&#x200B;す。
1. をクリック **[!UICONTROL Create]** し、オプションを選 **[!UICONTROL Extend an existing resource]** 択します。
1. リソースを選択 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   ![](assets/in_app_personal_data_4.png)

1. タブの **[!UICONTROL Fields]** カテゴリ **[!UICONTROL Data structure]** で、ボタンをクリックして、モバイルアプリから取得する顧客データを定義し **[!UICONTROL Add field]** ます。

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理している場合は、すべてのアプリケーションで使用されるすべてのフィールドを一覧表示する必要があります。 iOSまたはAndroidの収集PII呼び出しは、各アプリケーションで取り込まれるフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. 新しいフ追加ィールドに対す **[!UICONTROL Label]****[!UICONTROL ID]** るaおよびa。 フィールドのを選択しま **[!UICONTROL Type]**&#x200B;す。

   ![](assets/schema_extension_uc9.png)

1. カテゴリで、 **[!UICONTROL Link to profiles]** Adobe Campaignデータベースのプロファイルを電子メールなどのアプリケーションの購読者にリンクするために使用する紐付けキーを設定します。

   アプリ内メッセージでは、すべてのモバイルアプリに対して1つの紐付けキーのみを定義できます。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** カスタムリソースを公開します。 カスタムリソースの発行の詳細については、このページを参照して [ください](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

