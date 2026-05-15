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
TQID: https://experienceleague.adobe.com/glqcq7zaJ3-cRhOyU8whLUMKBGL-6TVkuGs53Lpce9o
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 559
ht-degree: 77%

---

# 紐付け{#reconciliation}

## 説明 {#description}

![](assets/reconciliation.png)

「**[!UICONTROL Reconciliation]**」アクティビティを使用すると、識別されていないデータを既存のリソースにリンクできます。

## Context of use {#context-of-use}

「**[!UICONTROL Reconciliation]**」アクティビティは、次の 2 つの使用例が示すように、基本的にデータ管理のために使用されます。

* リレーションの追加：「**[!UICONTROL Links]**」タブを使用すると、インバウンドデータとその他の複数の Adobe Campaign データベースディメンションの間にリンクを追加できます。

  例えば、購入データを含むファイルには、購入者だけでなく購入した商品も識別する情報を含めることができます。 したがって、**Purchases** に加えて、**Products** と **Profiles** の 2 つの追加のディメンションが、ファイルデータに関係します。 次に、これらと&#x200B;**Purchases** ディメンションの間のリレーションを作成する必要があります（次の例を参照）。

  リレーションを定義する場合、リンクされたディメンションの外部キーを参照するために、列がインバウンドデータに追加されます。

  >[!NOTE]
  >
  >この操作は、リンクされたディメンションのデータが既にデータベースに存在することを意味します。 例えば、購入された商品、購入時間、商品を購入したクライアントなどを示す購入ファイルをインポートする場合、商品とクライアントはデータベースに既に存在している必要があります。

* データの識別：「**[!UICONTROL Identification]**」タブを使用すると、インバウンドデータを Adobe Campaign データベース内の既存のディメンションの列に容易にリンクできます。 アクティビティ後、データは、定義されたディメンションに属していると識別されます。

  オーディエンスの保存、データベースの更新などを実行できます。

例えば、**[!UICONTROL Reconciliation]** アクティビティは、非標準データをデータベースに読み込むために、データ読み込みアクティビティの後に配置できます。

**Enrichment** アクティビティでは、ワークフローで処理する追加データを定義できます（複数セットからのデータを組み合わせたり、一時的なリソースへのリンクを作成したりするには、**Enrichment** アクティビティを使用します）。**紐付け** アクティビティでは、未識別データを既存のリソースにリンクできます。 紐付け操作は、リンクされたディメンションのデータが既にデータベース内にあることを意味します。 ユースケースは、[このセクション &#x200B;](#use-cases-reconciliation)で利用できます。


## 設定 {#configuration}

1. Adobe Campaign から直接ターゲティングディメンションを受け取らない母集団を含むトランジションに従って、ワークフローに「**[!UICONTROL Reconciliation]**」アクティビティをドラッグ＆ドロップします。 詳しくは、[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)を参照してください。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. インバウンドデータとその他のデータベースディメンションの間にリンクを定義する場合は、「**[!UICONTROL Links]**」タブに移動します。

   必要な数のリレーションを追加します。 各リレーションに対して、リンクされたディメンションを選択し、次にリンクの詳細で対応するフィールドを指定します。

1. インバウンドデータを識別する場合は、「**[!UICONTROL Identification]**」タブに移動し、「**[!UICONTROL Identify the document from the working data]**」チェックボックスをオンにします。

   インバウンドデータを紐付けするターゲティングディメンションを選択します。

   インバウンドトランジションレコードを選択したターゲティングディメンションレコードにリンクするための紐付け条件を追加します。 複数の条件を指定する場合、すべてのデータ間のリンクが機能するために、すべての条件を検証する必要があります。

   **[!UICONTROL Processing unidentified source lines]** モードを選択します。

   * **[!UICONTROL Ignore them]**：識別可能なデータのみが、アクティビティのアウトバウンドトランジションに保持されます。
   * **[!UICONTROL Keep in the outbound population]**：インバウンドトランジションからのすべてのデータは、アクティビティのアウトバウンドトランジションに保持されます。

1. アクティビティの設定を確認し、ワークフローを保存します。


## ユースケース{#use-cases-reconciliation}

このアクティビティを使用する方法は、次のユースケースで説明します。

* [ユースケース：リレーションを使用したデータ紐付け](../../automating/using/reconciliation-using-relations.md)
* [ユースケース：紐付けを使用したデータ更新](../../automating/using/data-update-reconciliation.md)
* [ユースケース：ファイルオーディエンスとデータベースの紐付け](../../automating/using/reconcile-file-audience-with-database.md)