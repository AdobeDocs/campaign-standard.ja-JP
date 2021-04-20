---
solution: Campaign Standard
product: campaign
title: リソースの作成または拡張
description: リソースを最初から定義する方法を見つけます。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 12%

---


# リソースの作成または拡張{#creating-or-extending-the-resource}

組み込みのデータモデルに含まれないデータを操作する必要がある場合は、管理者は、新しいリソースを最初から作成するか、既存のリソースの拡張を作成することができます。

拡張できる組み込みリソースは次のとおりです。

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

1. **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**&#x200B;から、**[!UICONTROL Create]**&#x200B;ボタンをクリックします。
1. 実行するアクションを選択します。

   * **[!UICONTROL Create a new resource]**:と **[!UICONTROL Label]** フィー **[!UICONTROL ID]** ルドを入力します。「**[!UICONTROL ID]**」フィールドは必須です。「ラベル」フィールドを空のままにすると、IDから自動的に入力されます。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最大 30 文字です。

   * **[!UICONTROL Extend an existing resource]**:拡張するリソースを選択します。

      ![](assets/schema_extension_10.png)

1. **[!UICONTROL Create]**&#x200B;をクリックしてリソースを作成します。新しいリソースの場合は&#x200B;**[!UICONTROL Draft]**&#x200B;ステータス、拡張の場合は&#x200B;**[!UICONTROL Editing]**&#x200B;ステータスになります。

新しいリソースが作成され、設定できるようになります。 リソースの設定について詳しくは、[リソースのデータ構造の設定](../../developing/using/configuring-the-resource-s-data-structure.md)を参照してください。
