---
title: リソースの作成または拡張
description: リソースを最初から定義する方法を確認します。
page-status-flag: 非活性化の
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: リソースの追加または拡張
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# リソースの作成または拡張{#creating-or-extending-the-resource}

既製のデータモデルに含まれていないデータを操作する必要がある場合は、管理者は新しいリソースを最初から作成したり、既存のリソースの拡張を作成したりできます。

拡張できるのは、次の既製のリソースのみです。

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

1. /から **[!UICONTROL Administration]** 、ボ **[!UICONTROL Development]** タン **[!UICONTROL Custom Resources]**&#x200B;をクリック **[!UICONTROL Create]** します。
1. 実行するアクションを選択します。

   * **[!UICONTROL Create a new resource]**:フィールドとフ **[!UICONTROL Label]** ィールドを入 **[!UICONTROL ID]** 力します。 このフ **[!UICONTROL ID]** ィールドは必須です。 「ラベル」フィールドを空のままにすると、IDから自動的に入力されます。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最大30文字を使用することをお勧めします。

   * **[!UICONTROL Extend an existing resource]**:拡張するリソースを選択します。

      ![](assets/schema_extension_10.png)

1. をクリ **[!UICONTROL Create]** ックしてリソースを作成します。新しいリソースの場合はス **[!UICONTROL Draft]** テータスを、拡張の場合はステ **[!UICONTROL Editing]** ータスを引き継ぎます。

新しいリソースが作成され、設定できるようになります。 リソース設定の詳細については、 [Configuring the resource's data structureを参照してください](../../developing/using/configuring-the-resource-s-data-structure.md)。
