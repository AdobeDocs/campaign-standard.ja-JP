---
title: リソースの作成または拡張
description: リソースを最初から定義する方法を見つけます。
page-status-flag: never-activated
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# リソースの作成または拡張{#creating-or-extending-the-resource}

組み込みデータモデルに含まれていないデータを操作する必要がある場合、管理者は、新しいリソースを最初から作成したり、既存のリソースの拡張を作成したりできます。

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

1. //か **[!UICONTROL Administration]** ら、 **[!UICONTROL Development]** ボタン **[!UICONTROL Custom Resources]**&#x200B;をクリック **[!UICONTROL Create]** します。
1. 実行するアクションを選択します。

   * **[!UICONTROL Create a new resource]**:およびフィールド **[!UICONTROL Label]** を入力 **[!UICONTROL ID]** します。 このフィ **[!UICONTROL ID]** ールドは必須です。 「ラベル」フィールドを空のままにすると、IDから自動的にラベルが入力されます。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最大30文字を使用します。

   * **[!UICONTROL Extend an existing resource]**:拡張するリソースを選択します。

      ![](assets/schema_extension_10.png)

1. をクリ **[!UICONTROL Create]** ックしてリソースを作成します。新しいリソースの場 **[!UICONTROL Draft]** 合はステータス、拡張の場合はス **[!UICONTROL Editing]** テータスになります。

新しいリソースが作成され、設定できるようになります。 リソースの設定の詳細については、 [Configuring the resource&#39;s data structureを参照してください](../../developing/using/configuring-the-resource-s-data-structure.md)。
