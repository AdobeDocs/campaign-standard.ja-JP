---
title: リソースの作成または拡張
description: リソースをゼロから定義する方法。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
TQID: https://experienceleague.adobe.com/hdn9Hj-zHdqoD2fKbv5Rl-GcV5EpH-L8p95e7W0ouzA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 11%

---

# リソースの作成または拡張{#creating-or-extending-the-resource}

組み込みデータモデルに含まれていないデータに対する作業が必要な場合は、管理者はゼロから新しいリソースを作成するか、既存のリソースの拡張機能を作成できます。

拡張できるのは、次のビルトインリソースのみです。

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

1. **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**&#x200B;から、**[!UICONTROL Create]** ボタンをクリックします。
1. 実行するアクションを選択します。

   * **[!UICONTROL Create a new resource]**: **[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL ID]** フィールドを入力します。 「**[!UICONTROL ID]**」フィールドは必須です。 「ラベル」フィールドを空のままにすると、IDから自動的に入力されます。

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >最大 30 文字です。

   * **[!UICONTROL Extend an existing resource]**：拡張するリソースを選択します。

     ![](assets/schema_extension_10.png)

1. 「**[!UICONTROL Create]**」をクリックしてリソースを作成し、新しいリソースの場合は「**[!UICONTROL Draft]**」ステータス、拡張の場合は「**[!UICONTROL Editing]**」ステータスになります。

新しいリソースが作成され、設定できるようになります。 リソース設定について詳しくは、[ リソースのデータ構造の設定](../../developing/using/configuring-the-resource-s-data-structure.md)を参照してください。
