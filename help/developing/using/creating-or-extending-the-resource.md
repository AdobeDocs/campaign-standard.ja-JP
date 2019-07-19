---
title: リソースの作成または拡張
seo-title: リソースの作成または拡張
description: リソースの作成または拡張
seo-description: リソースを最初から定義する方法を確認します。
page-status-flag: 常にアクティブ化されていない
uuid: 7c26b63d-9587-472b-804f- cde5c45dfb3c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: 追加または拡張するリソース
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Creating or extending the resource{#creating-or-extending-the-resource}

管理者は、あらかじめ用意されたデータモデルに含まれていないデータに対して作業が必要な場合、新規リソースを最初から作成することも、既存のリソースの拡張を作成することもできます。

拡張できるのは、次の機能を備えたリソースのみです。

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

リソースを作成または拡張するには:

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, click the **[!UICONTROL Create]** button.
1. 実行するアクションを選択します。

   * **[!UICONTROL Create a new resource]**:フィールド **[!UICONTROL Label]** と **[!UICONTROL ID]** フィールドを入力します。**[!UICONTROL ID]** フィールドは必須です。「ラベル」フィールドを空のままにすると、IDから自動的に完了します。

      ![](assets/schema_extension_2.png)

   * **[!UICONTROL Extend an existing resource]**:拡張するリソースを選択します。

      ![](assets/schema_extension_10.png)

1. Click **[!UICONTROL Create]** to create the resource, which will then take on the **[!UICONTROL Draft]** status in case of new resource or the **[!UICONTROL Editing]** status in case of extension.

新しいリソースが作成され、設定できるようになりました。For more on resource configuration, refer to [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).
