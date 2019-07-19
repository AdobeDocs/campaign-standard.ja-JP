---
title: 画面定義の設定
seo-title: 画面定義の設定
description: 画面定義の設定
seo-description: リソースデータ構造に基づいて新しいAdobe Campaign画面を定義する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 40848197- b1a0-4018- bfc3-7df64fb83307
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: 追加または拡張するリソース
discoiquuid: 9dabb328- ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b3291f7c0cbede6a3180ad4a4ab8a365720f5031

---


# Configuring the screen definition{#configuring-the-screen-definition}

リソースを作成するとき、または既存のリソースに新しいフィールドを追加するときに、インターフェイスに表示する方法を定義できます。

ワークフロー、オーディエンス、REST APIを使用してデータを入力し、そのデータにアクセスすることができるので、この手順は必須ではありません。

**[!UICONTROL Screen definition]** タブでは、次のことができます。

* ナビゲーションペインのカスタムリソースへのアクセス権の追加
* リソースを構成する要素のリストが表示されるようにカスタマイズ
* リソースの各要素の詳細ビューの表示方法の定義

## Enabling access from the navigation menu {#enabling-access-from-the-navigation-menu}

リソースに専用の画面が表示されるようにするには、ナビゲーションメニューから使用できるようにします。

1. From the **[!UICONTROL Screen definition]** tab of the resource, unfold the **[!UICONTROL Navigation]** section.
1. **[!UICONTROL Add an entry in the 'Client data' section]** このリソースへのアクセスをナビゲーションペインから許可するには、チェックボックスをオンにします。

   ![](assets/schema_extension_19.png)

The resource will appear as a sub-entry within the **[!UICONTROL Client data]** section.

## Defining the default list configuration {#defining-the-default-list-configuration}

The **[!UICONTROL List configuration]** section of the screen definition lets you define the columns and information that will be displayed by default in the overview of a resource.

1. Check the **[!UICONTROL Customize the list configuration]** box to define the way the columns of the resource are displayed.
1. Use the **[!UICONTROL Create element]** button to select a field from those that you have created.
1. 作成されたフィールドがリストに表示されます。ラベルとその幅は編集できます。

   ![](assets/schema_extension_20.png)

1. **[!UICONTROL Simple search]** セクションで、検索 **[!UICONTROL Specify the fields to be taken into account in the search]** に含めるフィールドを定義します。

   >[!CAUTION]
   >
   >この設定は、デフォルトの検索で使用されるフィールドに置き換えられます。

1. **[!UICONTROL Advanced filtering]** このセクションで **[!UICONTROL Add search fields]** は、チェックボックスをオンにして、単純検索フィールド以外のフィールドを追加します。例えば、作成したフィールドから「日付」フィールドを選択した場合、ユーザーは日付のみを参照する検索を実行できます。
1. 2つの検索タイプのフィールドの順序を変更できます。
1. アドバンス検索では、リンクされたリソースにリンクするフィールドを追加できます。These filters appear in the **[!UICONTROL Search]** menu of the generated screen.

リソースの概要画面が定義されるようになりました。

## Defining the detail screen configuration {#defining-the-detail-screen-configuration}

The **[!UICONTROL Detail screen configuration]** section of the screen definition lets you define the columns and information that will be displayed in the detail screen of each element of the resource.

1. **[!UICONTROL Detail screen configuration]** セクションを展開して **[!UICONTROL Define a detail screen]** 、リソースの各要素に対応する画面を設定します。このボックスを選択しない場合、このリソースの要素の詳細ビューにアクセスできません。
1. カスタムリソースからすべてのフィールドをワンクリックで追加できます。To do this, click the ![](assets/addallfieldsicon.png) icon or use the **[!UICONTROL Add an element]** button.
1. このリソース用に作成した要素から要素を選択し、フィールドタイプを指定します。

   * **[!UICONTROL Input field]**:は編集可能なフィールドです。
   * **[!UICONTROL Value]**:は読み取り専用フィールドです。
   * **[!UICONTROL List]**:はテーブルです。
   * **[!UICONTROL Separator]**:エレメントをカテゴリに分割します。
   ![](assets/schema_extension_23.png)

1. 追加された要素がリストに表示されます。ラベルは編集できます。

   ![](assets/schema_extension_22.png)

1. Add as many **[!UICONTROL Separator]** as needed to split your elements into different categories.

   これにより、区切りを表示してウィンドウをより適切に整理できます。

   ![](assets/schema_extension_25.png)

リソースの詳細画面が設定されるようになりました。

## Actions on data section {#actions-on-data-section}

これらの設定により、カスタムリソース画面にコントロールバーを表示できます。次の3つのオプションがあります。

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**:このオプションを使用すると、リソースの要素を作成できます。したがって、ユーザーは追加のレコードを追加できます。

   >[!NOTE]
   >
   >このオプションを使用できるようにするには、リソースにリンクされている詳細画面をアクティブにする必要があります。

* **[!UICONTROL Authorize duplicating]**:このオプションを使用すると、カスタムリソースにリンクされている重複レコードをアクティブ化できます。
* **[!UICONTROL Authorize deleting]**:このオプションを使用すると、カスタムリソースにリンクされているレコードを削除できます。

