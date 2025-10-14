---
title: リソースの作成または拡張
description: リソースをゼロから定義する方法を説明します。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 11%

---

# リソースの作成または拡張{#creating-or-extending-the-resource}

ビルトインデータモデルに含まれていないデータを操作する必要がある場合、管理者は新しいリソースをゼロから作成したり、既存のリソースの拡張機能を作成したりできます。

拡張できるのは、次の組み込みリソースのみです。

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

リソースを作成または拡張するには：

1. **[!UICONTROL Administration]**/**[!UICONTROL Development]**/**[!UICONTROL Custom Resources]** から、「**[!UICONTROL Create]**」ボタンをクリックします。
1. 実行するアクションを選択します。

   * **[!UICONTROL Create a new resource]**:「**[!UICONTROL Label]**」フィールドと「**[!UICONTROL ID]**」フィールドを入力します。 「**[!UICONTROL ID]**」フィールドは必須です。「ラベル」フィールドを空のままにすると、ID から自動的に入力されます。

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >最大 30 文字です。

   * **[!UICONTROL Extend an existing resource]**：拡張するリソースを選択します。

     ![](assets/schema_extension_10.png)

1. 「**[!UICONTROL Create]**」をクリックしてリソースを作成します。これにより、新しいリソースの場合は **[!UICONTROL Draft]** ステータスが取得され、拡張機能の場合は **[!UICONTROL Editing]** ステータスが取得されます。

新しいリソースが作成され、設定できるようになります。 リソースの設定について詳しくは、[&#x200B; リソースのデータ構造の設定 &#x200B;](../../developing/using/configuring-the-resource-s-data-structure.md) を参照してください。
