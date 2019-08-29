---
title: リソースの作成または拡張
seo-title: リソースの作成または拡張
description: リソースの作成または拡張
seo-description: リソースを最初から定義する方法を見つけます。
page-status-flag: 決して活性化されていない
uuid: 7c26b63d-9587-472b-804f- cde5c45dfb3c
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 現像
content-type: 参照
topic-tags: 追加または拡張されたリソース
discoiquuid: 8dc45c37-6908-407e-8e41-4a ba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 50620788c05b76cc2f69c19c26f968ca15a02048

---


# リソースの作成または拡張{#creating-or-extending-the-resource}

管理者は、最初から新しいリソースを作成するか、最新のデータモデルの一部ではないデータに対して作業が必要な場合は、既存のリソースの拡張を作成できます。

拡張できるのは、次のすぐに使用できるリソースのみです。

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

1. **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt;で **[!UICONTROL Custom Resources]**、ボタン **[!UICONTROL Create]** をクリックします。
1. 実行するアクションを選択します。

   * **[!UICONTROL Create a new resource]**:および **[!UICONTROL Label]****[!UICONTROL ID]** フィールドを入力します。**[!UICONTROL ID]** フィールドは必須です。「ラベル」フィールドを空のままにすると、自動的にIDから完了します。

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >最大30文字の使用を推奨します。

   * **[!UICONTROL Extend an existing resource]**:拡張するリソースを選択します。

      ![](assets/schema_extension_10.png)

1. リソース **[!UICONTROL Create]** を作成するときにクリックします。リソースは、 **[!UICONTROL Draft]** 新しいリソースの場合、または拡張子の場合 **[!UICONTROL Editing]** はステータスになります。

新しいリソースが作成され、構成できるようになります。リソース構成の詳細については、「 [リソースのデータ構造の構成」を](../../developing/using/configuring-the-resource-s-data-structure.md)参照してください。
