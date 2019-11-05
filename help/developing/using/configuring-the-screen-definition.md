---
title: 画面定義の設定
description: リソースデータ構造に基づいて新しいAdobe Campaign画面を定義する方法について説明します。
page-status-flag: 非活性化の
uuid: 40848197-b1a0-4018-bfc3-7df64fb83307
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: リソースの追加または拡張
discoiquuid: 9dabb328-ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 画面定義の設定{#configuring-the-screen-definition}

リソースを作成する場合、または既存のリソースに新しいフィールドを追加する場合、インターフェースに表示する方法を定義できます。

この手順は必須ではありません。この手順は、引き続き、ワークフロー、オーディエンスおよびREST APIを使用してリソースにデータを入力し、そのデータにアクセスできるためです。

このタブでは、次 **[!UICONTROL Screen definition]** の操作を実行できます。

* ナビゲーションペインでのカスタムリソースへのアクセスの追加
* リソースを構成する要素のリストを表示する方法をパーソナライズします。
* リソースの各要素の詳細ビューの表示方法を定義します

## ナビゲーションメニューからのアクセスの有効化 {#enabling-access-from-the-navigation-menu}

リソースに専用の画面を設定する場合は、ナビゲーションメニューからその画面を使用できます。

1. リソースのタ **[!UICONTROL Screen definition]** ブから、セクションを展開 **[!UICONTROL Navigation]** します。
1. ナビゲーション **[!UICONTROL Add an entry in the 'Client data' section]** ウィンドウからこのリソースにアクセスできるようにするには、このボックスをオンにします。

   ![](assets/schema_extension_19.png)

リソースは、セクション内のサブエントリとして表示さ **[!UICONTROL Client data]** れます。

## デフォルトのリスト設定の定義 {#defining-the-default-list-configuration}

画面定 **[!UICONTROL List configuration]** 義のセクションでは、リソースの概要にデフォルトで表示される列と情報を定義できます。

1. リソースの **[!UICONTROL Customize the list configuration]** 列の表示方法を定義するには、このボックスをオンにします。
1. 作成したフ **[!UICONTROL Create element]** ィールドからフィールドを選択するには、このボタンを使用します。
1. 作成されたフィールドがリストに表示されます。 ラベルと幅を編集できます。

   ![](assets/schema_extension_20.png)

1. このセクシ **[!UICONTROL Simple search]** ョンで、検索に含め **[!UICONTROL Specify the fields to be taken into account in the search]** るフィールドを定義するには、を選択します。

   >[!CAUTION]
   >
   >この設定は、デフォルトの検索で使用されるフィールドを置き換えます。

1. セクションで、 **[!UICONTROL Advanced filtering]** このボックスにチェッ **[!UICONTROL Add search fields]** クマークを付けて、単純検索フィールドの後にフィールドを追加します。 例えば、作成したフィールドから「日付」フィールドを選択すると、その日付のみを参照する検索を実行できます。
1. 2つの検索タイプのフィールドの順序を変更できます。
1. アドバンス検索では、リンクされたリソースにリンクするフィールドを追加できます。 これらのフィルターは、生成さ **[!UICONTROL Search]** れた画面のメニューに表示されます。

これで、リソースの概要画面が定義されました。

## 詳細画面設定の定義 {#defining-the-detail-screen-configuration}

画面 **[!UICONTROL Detail screen configuration]** 定義のセクションでは、リソースの各要素の詳細画面に表示される列と情報を定義できます。

1. セクション **[!UICONTROL Detail screen configuration]** を展開し、リソースの各 **[!UICONTROL Define a detail screen]** 要素に対応する画面を設定するようにを確認します。 このチェックボックスをオフにすると、このリソースの要素の詳細ビューにアクセスできなくなります。
1. カスタムリソースのすべてのフィールドは、1回のクリックで追加できます。 これを行うには、アイコンをクリック ![](assets/addallfieldsicon.png) するか、ボタンを使用 **[!UICONTROL Add an element]** します。
1. このリソース用に作成された要素から要素を選択し、フィールドタイプを指定します。

   * **[!UICONTROL Input field]**:は編集可能なフィールドです。
   * **[!UICONTROL Value]**:は読み取り専用フィールドです。
   * **[!UICONTROL List]**:は表です。
   * **[!UICONTROL Separator]**:要素をカテゴリに分割します。
   ![](assets/schema_extension_23.png)

1. 追加された要素がリストに表示されます。 ラベルを編集できます。

   ![](assets/schema_extension_22.png)

1. 要素を様々なカ **[!UICONTROL Separator]** テゴリに分割するために必要な数だけ追加します。

   これにより、区切り文字を表示して、ウィンドウを整理しやすくなります。

   ![](assets/schema_extension_25.png)

これで、リソースの詳細画面が設定されました。

## データセクションのアクション {#actions-on-data-section}

これらの設定により、カスタムリソース画面にコントロールバーを表示できます。 次の3つのオプションを使用できます。

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**:このオプションを使用すると、リソースの作成要素をアクティブ化できます。 したがって、ユーザーはレコードを追加できます。

   >[!NOTE]
   >
   >このオプションを有効にするには、まずリソースにリンクされた詳細画面をアクティブにする必要があります。

* **[!UICONTROL Authorize duplicating]**:このオプションを使用すると、カスタムリソースにリンクされた重複レコードをアクティブにできます。
* **[!UICONTROL Authorize deleting]**:このオプションを使用すると、カスタムリソースにリンクされたレコードの削除をアクティブにできます。

