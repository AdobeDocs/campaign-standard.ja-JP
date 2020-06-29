---
title: 紐付け
description: 「調整」アクティビティを使用すると、識別できないデータを既存のリソースにリンクできます。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 1%

---


# 紐付け{#reconciliation}

## 説明 {#description}

![](assets/reconciliation.png)

この **[!UICONTROL Reconciliation]** アクティビティを使用すると、識別できないデータを既存のリソースにリンクできます。

## 使用状況 {#context-of-use}

この **[!UICONTROL Reconciliation]** アクティビティは基本的にデータ管理目的で使用され、次の2つの異なる使用例を意味します。

* リレーションの追加： 「 **[!UICONTROL Links]** 」タブを使用すると、受信データと他の複数のAdobe Campaignデータベースディメンションの間にリンクを追加できます。

   例えば、購入データを含むファイルには、購入者だけでなく購入した製品も識別する情報を含めることができます。 したがって、( **購入以外の**)次の2つの追加のディメンションが、ファイルデータに関係します。 「 **製品** 」ディメンションと「 **プロファイル** 」ディメンション。 次に、これらと **Purchases** （購入）ディメンションの間のリレーションを作成する必要があります（次の例を参照）。

   リレーションを定義する場合、リンクディメンションの外部キーを参照するために、列がインバウンドデータに追加されます。

   >[!NOTE]
   >
   >この操作は、リンクされたディメンションのデータが既にデータベースに存在することを意味します。 例えば、購入した製品を示す購入ファイルをインポートする場合、購入した製品を示すファイルは、その時点で、どの顧客が購入したかなどを示すときに、その製品とクライアントがデータベースに既に存在している必要があります。

* データID: 「 **[!UICONTROL Identification]** 」タブを使用すると、受信データをAdobe Campaignデータベース内の既存のディメンションの列に単純にリンクできます。 アクティビティ後、データは、定義されたディメンションに属していると識別されます。

   たとえば、保存オーディエンス、データベースの更新などを実行できます。

例えば、非標準のデータをデータベースに読み込むために、データの読み込みアクティビティの後に **[!UICONTROL Reconciliation]** アクティビティを配置できます。

**関連トピック：**

* [使用例： 関係を使用したデータ調整](../../automating/using/reconciliation-using-relations.md)
* [使用例： 調整を使用したデータ更新](../../automating/using/data-update-reconciliation.md)
* [使用例： ファイルオーディエンスとデータベースとの調整](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

1. Adobe Campaignから直接ターゲティングディメンションを受け取らない母集団を含むトランジションに従って、ワークフローに **[!UICONTROL Reconciliation]** アクティビティをドラッグ&amp;ドロップします。 詳しくは、「 [ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)」を参照してください。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 受信データと他のデータベースディメンションの間にリンクを定義する場合は、 **[!UICONTROL Links]** タブに移動します。

   必要な数追加の関係。 各リレーションに対して、最初にリンクされた寸法を選択し、次にリンクの詳細で、対応するフィールドを指定します。

1. 受信データを識別するだけの場合は、 **[!UICONTROL Identification]** タブに移動し、 **[!UICONTROL Identify the document from the working data]** ボックスをオンにします。

   受信データを調整するターゲティングディメンションを選択します。

   受信トランジションレコードを選択したターゲティングディメンションレコードにリンクするための追加調整条件。 複数の条件を指定した場合、すべてのデータ間のリンクが機能するために、すべての条件を検証する必要があります。

   次の **[!UICONTROL Processing unidentified source lines]** モードを選択します。

   * **[!UICONTROL Ignore them]**: 識別可能なデータのみが、アクティビティのアウトバウンドトランジションに保持されます。
   * **[!UICONTROL Keep in the outbound population]**: 受信トランジションからのすべてのデータは、アクティビティの送信トランジションに保持されます。

1. アクティビティの設定を確認し、ワークフローを保存します。
