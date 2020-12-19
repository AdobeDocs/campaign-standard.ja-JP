---
solution: Campaign Standard
product: campaign
title: 紐付け
description: 「Reconciliation」アクティビティを使用すると、識別されていないデータを既存のリソースにリンクできます。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 紐付け{#reconciliation}

## 説明{#description}

![](assets/reconciliation.png)

「**[!UICONTROL Reconciliation]**」アクティビティを使用すると、識別されていないデータを既存のリソースにリンクできます。

## 使用状況 {#context-of-use}

「**[!UICONTROL Reconciliation]**」アクティビティは、次の 2 つの使用例が示すように、基本的にデータ管理のために使用されます。

* リレーションの追加：「**[!UICONTROL Links]**」タブを使用すると、インバウンドデータとその他の複数の Adobe Campaign データベースディメンションの間にリンクを追加できます。

   例えば、購入データを含むファイルには、購入者だけでなく購入した商品も識別する情報を含めることができます。したがって、**Purchases** に加えて、**Products** と **Profiles** の 2 つの追加のディメンションが、ファイルデータに関係します。次に、これらと&#x200B;**Purchases** ディメンションの間のリレーションを作成する必要があります（次の例を参照）。

   リレーションを定義する場合、リンクされたディメンションの外部キーを参照するために、列がインバウンドデータに追加されます。

   >[!NOTE]
   >
   >この操作は、リンクされたディメンションのデータが既にデータベースに存在することを意味します。例えば、購入された商品、購入時間、商品を購入したクライアントなどを示す購入ファイルをインポートする場合、商品とクライアントはデータベースに既に存在している必要があります。

* データの識別：「**[!UICONTROL Identification]**」タブを使用すると、インバウンドデータを Adobe Campaign データベース内の既存のディメンションの列に容易にリンクできます。アクティビティ後、データは、定義されたディメンションに属していると識別されます。

   オーディエンスの保存、データベースの更新などを実行できます。

例えば、非標準のデータをデータベースにインポートするために、データの読み込みアクティビティの後に「**[!UICONTROL Reconciliation]**」アクティビティを配置できます。

**関連トピック：**

* [使用例：関係を使用したデータ調整](../../automating/using/reconciliation-using-relations.md)
* [使用例：調整を使用したデータ更新](../../automating/using/data-update-reconciliation.md)
* [使用例：ファイルオーディエンスとデータベースとの調整](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

1. Adobe Campaign から直接ターゲティングディメンションを受け取らない母集団を含むトランジションに従って、ワークフローに「**[!UICONTROL Reconciliation]**」アクティビティをドラッグ＆ドロップします。詳しくは、[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)を参照してください。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. インバウンドデータとその他のデータベースディメンションの間にリンクを定義する場合は、「**[!UICONTROL Links]**」タブに移動します。

   必要な数のリレーションを追加します。各リレーションに対して、リンクされたディメンションを選択し、次にリンクの詳細で対応するフィールドを指定します。

1. インバウンドデータを識別する場合は、「**[!UICONTROL Identification]**」タブに移動し、「**[!UICONTROL Identify the document from the working data]**」チェックボックスをオンにします。

   インバウンドデータを紐付けするターゲティングディメンションを選択します。

   インバウンドトランジションレコードを選択したターゲティングディメンションレコードにリンクするための紐付け条件を追加します。複数の条件を指定する場合、すべてのデータ間のリンクが機能するために、すべての条件を検証する必要があります。

   **[!UICONTROL Processing unidentified source lines]** モードを選択します。

   * **[!UICONTROL Ignore them]**：識別可能なデータのみが、アクティビティのアウトバウンドトランジションに保持されます。
   * **[!UICONTROL Keep in the outbound population]**：インバウンドトランジションからのすべてのデータは、アクティビティのアウトバウンドトランジションに保持されます。

1. アクティビティの設定を確認し、ワークフローを保存します。
