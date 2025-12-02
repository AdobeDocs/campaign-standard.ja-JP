---
title: 紐付け
description: 紐付けアクティビティを使用すると、識別されていないデータを既存のリソースにリンクできます。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ed2e3793-6164-48af-9043-42dc43fa8ed4
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 78%

---

# 紐付け{#reconciliation}

## 説明 {#description}

![](assets/reconciliation.png)

「**[!UICONTROL Reconciliation]**」アクティビティを使用すると、識別されていないデータを既存のリソースにリンクできます。

## 使用コンテキスト {#context-of-use}

「**[!UICONTROL Reconciliation]**」アクティビティは、次の 2 つの使用例が示すように、基本的にデータ管理のために使用されます。

* リレーションの追加：「**[!UICONTROL Links]**」タブを使用すると、インバウンドデータとその他の複数の Adobe Campaign データベースディメンションの間にリンクを追加できます。

  例えば、購入データを含むファイルには、購入者だけでなく購入した商品も識別する情報を含めることができます。したがって、**Purchases** に加えて、**Products** と **Profiles** の 2 つの追加のディメンションが、ファイルデータに関係します。次に、これらと&#x200B;**Purchases** ディメンションの間のリレーションを作成する必要があります（次の例を参照）。

  リレーションを定義する場合、リンクされたディメンションの外部キーを参照するために、列がインバウンドデータに追加されます。

  >[!NOTE]
  >
  >この操作は、リンクされたディメンションのデータが既にデータベースに存在することを意味します。例えば、購入された商品、購入時間、商品を購入したクライアントなどを示す購入ファイルをインポートする場合、商品とクライアントはデータベースに既に存在している必要があります。

* データの識別：「**[!UICONTROL Identification]**」タブを使用すると、インバウンドデータを Adobe Campaign データベース内の既存のディメンションの列に容易にリンクできます。アクティビティ後、データは、定義されたディメンションに属していると識別されます。

  オーディエンスの保存、データベースの更新などを実行できます。

例えば、**[!UICONTROL Reconciliation]** アクティビティを「データを読み込み」アクティビティの後に配置して、非標準のデータをデータベースに読み込むことができます。

**エンリッチメント** アクティビティでは、ワークフローで処理する追加データを定義できますが（**エンリッチメント** アクティビティを使用すると、複数のセットからのデータを組み合わせたり、一時的なリソースへのリンクを作成したりできます）、**紐付け** アクティビティを使用すると、未識別データを既存のリソースにリンクできます。 紐付け操作は、リンクされたディメンションのデータが既にデータベースに存在することを意味します。 ユースケースについては、[ この節 ](#use-cases-reconciliation) を参照してください。


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


## ユースケース{#use-cases-reconciliation}

このアクティビティを次のユースケースで使用する方法を説明します。

* [ユースケース：関係を使用したデータの紐付け](../../automating/using/reconciliation-using-relations.md)
* [ユースケース：紐付けを使用したデータの更新](../../automating/using/data-update-reconciliation.md)
* [ユースケース：ファイルオーディエンスとデータベースの紐付け](../../automating/using/reconcile-file-audience-with-database.md)