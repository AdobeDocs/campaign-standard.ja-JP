---
title: アプリケーションリソースへの購読の拡張
description: null
page-status-flag: 非活性化の
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: 使用事例
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# アプリケーションリソースへの購読の拡張{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-to-add-a-resource.md).

このリソースを拡張して、モバイルデバイスからAdobe Campaignに送信するデータを収集できます。

1. アドバンスメニューで、Adobe Campaignロゴを使用して/を選 **[!UICONTROL Administration]** 択し、 **[!UICONTROL Development]**&#x200B;次に選択しま **[!UICONTROL Custom resources]**&#x200B;す。
1. をクリック **[!UICONTROL Create]** し、オプションを選択 **[!UICONTROL Extend an existing resource]** します。
1. リソースを選択 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   ![](assets/in_app_personal_data_4.png)

1. タブのカ **[!UICONTROL Fields]** テゴリで、ボ **[!UICONTROL Data structure]** タンをクリックして、モバイルアプリケーションから取得する顧客データを定義し **[!UICONTROL Add field]** ます。

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理している場合は、すべてのアプリケーションで使用されるすべてのフィールドを一覧表示する必要があります。 iOSまたはAndroidのcollect PII呼び出しは、各アプリケーションで取り込まれるフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. 新しいフィ **[!UICONTROL Label]** ールドにお **[!UICONTROL ID]** よびを追加します。 フィールドの値を選択しま **[!UICONTROL Type]**&#x200B;す。

   ![](assets/schema_extension_uc9.png)

1. カテゴリ **[!UICONTROL Link to profiles]** で、Adobe Campaignデータベースのプロファイルを電子メールなどのアプリケーションの購読者にリンクするために使用する調整キーを設定します。

   アプリ内メッセージで定義できる調整キーは、すべてのモバイルアプリに対して1つだけです。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** カスタムリソースを公開します。 カスタムリソースの発行の詳細については、このページを参照して [ください](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

