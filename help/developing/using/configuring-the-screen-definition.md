---
title: 画面定義の設定
description: リソースデータ構造に基づいて新規の Adobe Campaign 画面を定義する方法について説明します。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: cusResource,main
feature: Data Model
role: Developer
level: Experienced
exl-id: dc45f487-7502-478d-a2b3-51669cc6b225
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 100%

---

# 画面定義の設定{#configuring-the-screen-definition}

リソースを作成する場合、または既存のリソースに新たなフィールドを追加する場合、これらをインターフェイスでどのように表示するかを定義できます。

ワークフロー、オーディエンスおよび REST API を使用して、リソースに値を設定し、そのデータにアクセスできるので、この手順は必須ではありません。

「**[!UICONTROL Screen definition]**」タブでは、次の操作が可能です。

* ナビゲーションペインでカスタムリソースにアクセスを追加する
* リソースを構成する要素のリストを表示する形式をパーソナライズする
* リソースの各要素の詳細ビューを表示する形式を定義する

## ナビゲーションメニューからアクセスを有効にする {#enabling-access-from-the-navigation-menu}

リソースに専用の画面を割り当てる必要がある場合、ナビゲーションメニューからアクセス可能にできます。

1. リソースの「**[!UICONTROL Screen definition]**」タブから「**[!UICONTROL Navigation]**&#x200B;セクションを展開します。
1. 「**[!UICONTROL Add an entry in the 'Client data' section]**」ボックスをオンにして、ナビゲーションペインからリソースにアクセスできるようにします。

   ![](assets/schema_extension_19.png)

リソースは、「**[!UICONTROL Client data]**」セクション内のサブエントリとして表示されます。

## デフォルトのリスト設定を定義する {#defining-the-default-list-configuration}

画面定義の「**[!UICONTROL List configuration]**」セクションでは、リソースの概要にデフォルトで表示される列と情報を定義できます。

1. リソースの列を表示する形式を定義するには、「**[!UICONTROL Customize the list configuration]**」ボックスをオンにします。
1. 「**[!UICONTROL Create element]**」ボタンを使用して、作成したフィールドの 1 つを選択します。
1. 作成されたフィールドがリストに表示されます。ラベルと幅を編集できます。

   ![](assets/schema_extension_20.png)

1. 「**[!UICONTROL Simple search]**」セクションで「**[!UICONTROL Specify the fields to be taken into account in the search]**」をオンにして、検索の対象にするフィールドを定義します。

   >[!IMPORTANT]
   >
   >この設定により、デフォルト検索で使用するフィールドが置き換えられます。

1. 「**[!UICONTROL Advanced filtering]**」セクションで「**[!UICONTROL Add search fields]**」をオンにして、単純検索フィールド以外のフィールドを追加します。例えば、作成したフィールドから「日付」フィールドを選択すると、ユーザーは該当する日付だけを参照する検索を実行できます。
1. 2 つのタイプの検索で対象とするフィールドの順序を変更することができます。
1. 詳細検索では、リンクされたリソースに結び付けるフィールドを追加できます。これらのフィルターは、生成された画面の&#x200B;**[!UICONTROL Search]**&#x200B;メニューに表示されます。

これでリソースの概要画面が定義されました。

## 詳細画面の設定を定義する {#defining-the-detail-screen-configuration}

画面定義の「**[!UICONTROL Detail screen configuration]**」セクションでは、リソースの各要素に対する詳細画面に表示する列と情報を定義することができます。

1. 「**[!UICONTROL Detail screen configuration]**」セクションを展開し、「**[!UICONTROL Define a detail screen]**」をオンにして、リソースの各要素に対応する画面を設定します。このボックスをオフにすると、このリソースの要素を示す詳細表示にはアクセスできなくなります。
1. 1 回のクリックで、カスタムリソースのすべてのフィールドを追加できます。これをおこなうには、![](assets/addallfieldsicon.png) アイコンをクリックするか、「**[!UICONTROL Add an element]**」ボタンを使用します。
1. このリソース用として作成された要素の 1 つを選択し、フィールドタイプを指定します。

   * **[!UICONTROL Input field]**：編集可能なフィールドです。
   * **[!UICONTROL Value]**：読み取り専用フィールドです。
   * **[!UICONTROL List]**：テーブルです。
   * **[!UICONTROL Separator]**：要素を複数のカテゴリーに分割します。

   ![](assets/schema_extension_23.png)

1. 追加された要素がリストに表示されます。ラベルを編集できます。

   ![](assets/schema_extension_22.png)

1. 要素を各カテゴリーに分割する場合に使用する&#x200B;**[!UICONTROL Separator]**&#x200B;を必要なだけ追加します。

   これにより区切り記号を使用して、ウィンドウを読みやすく表示できます。

   ![](assets/schema_extension_25.png)

これでリソースの詳細画面が設定されました。

## 「データへのアクション」セクション  {#actions-on-data-section}

以下の設定により、カスタムリソース画面にコントロールバーを表示できます。次の 3 つのオプションを使用できます。

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**：リソース要素の作成を有効にできます。これによりユーザーは、さらに別のレコードを追加できます。

   >[!NOTE]
   >
   >このオプションを使用可能にするには、まず、リソースにリンクされた詳細画面を有効にする必要があります。

* **[!UICONTROL Authorize duplicating]**：カスタムリソースにリンクされたレコードの複製を有効にできます。
* **[!UICONTROL Authorize deleting]**：カスタムリソースにリンクされたレコードの削除を有効にできます。
