---
title: アプリケーションリソースの購読の拡張
description: アプリケーションリソースに対するサブスクリプションの拡張方法を説明します
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

Adobe Campaignでは、モバイルデバイスから送信されたモバイルプロファイル属性データは、 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** リソースを使用して、アプリケーション購読者から収集するデータを定義できます。 カスタムリソースについて詳しくは、 [このページ](../../developing/using/key-steps-to-add-a-resource.md).

このリソースを拡張して、モバイルデバイスからAdobe Campaignに送信するデータを収集できます。

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Custom resources]** を選択します。
1. クリック **[!UICONTROL Create]** を選択し、 **[!UICONTROL Extend an existing resource]** オプション。
1. を選択します。 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** リソースとクリック **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Adobe Analytics の **[!UICONTROL Fields]** カテゴリ **[!UICONTROL Data structure]** 」タブで、モバイルアプリケーションから取得する顧客データを定義するには、 **[!UICONTROL Add field]** 」ボタンをクリックします。

   >[!NOTE]
   >
   >複数のモバイルアプリケーションを管理している場合は、すべてのアプリケーションで使用されるすべてのフィールドを一覧表示する必要があります。 iOSまたは Android の収集 PII 呼び出しは、各アプリで取り込むフィールドを定義します。

   ![](assets/in_app_personal_data.png)

1. を追加します。 **[!UICONTROL Label]** および **[!UICONTROL ID]** を新しいフィールドに追加します。 フィールドの **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. Adobe Analytics の **[!UICONTROL Link to profiles]** 「 」カテゴリで、Adobe Campaignデータベースのプロファイルをアプリケーションの購読者（E メールなど）にリンクするために使用する紐付けキーを設定します。

   アプリ内メッセージでは、すべてのモバイルアプリに対して 1 つの紐付けキーのみを定義できます。

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** カスタムリソースを公開します。 カスタムリソースのパブリッシュについて詳しくは、 [ページ](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
