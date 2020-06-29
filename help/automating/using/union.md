---
title: 和集合
description: 和集合アクティビティを使用すると、複数のアクティビティの結果を1つのターゲットに再グループ化できます。
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 1%

---


# 和集合{#union}

## 説明 {#description}

![](assets/union.png)

この **[!UICONTROL Union]** アクティビティを使用すると、複数のアクティビティの結果を1つのターゲットに再グループ化できます。

>[!NOTE]
>
>セットは必ずしも同一である必要はありません。

## 使用状況 {#context-of-use}

この **[!UICONTROL Union]** アクティビティは、セグメント化の実行、オーディエンスの定義、またはメッセージターゲットの準備などの際に、インバウンドトランジションからの訪問者を組み合わせるために使用されます。

**関連トピック：**

* [使用例： 2つの洗練されたオーディエンスの和集合](../../automating/using/union-on-two-refined-audiences.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Union]** アクティビティをドラッグ&amp;ドロップします。
1. クエリなど、その前にある他のアクティビティに接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 受入母集団 **[!UICONTROL Reconciliation type]** 間の対決からの重複の処理方法を定義するには、を選択します。

   * **[!UICONTROL Keys only]**: これはデフォルトのモードです。 アクティビティは、異なる受信トランジションの要素が同じキーを持つ場合、1つの要素のみを保持します。 このオプションは、受入母集団が同一の場合にのみ使用できます。
   * **[!UICONTROL All shared columns]**: データは、受信トランジションと共通するすべての列に基づいて調整されます。 したがって、重複の場合に保持するプライマリセットを選択する必要があります。 このオプションは、受信訪問者のターゲティングディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**: データの調整を適用する列のリストを定義する場合は、このオプションを選択します。 最初に（ソース・データを含む）プライマリ・セットを選択し、次に結合に使用する列を選択する必要があります。

1. すべての受信トランジションに追加のデータのみを保持する場合は、この **[!UICONTROL Use common additional data only]** チェックボックスをオンにします。
1. 最終的な母集団のサイズを制限する場合は、この **[!UICONTROL Limit size of generated population]** ボックスをオンにします。 サイズは、 **[!UICONTROL Maximum number of records]** フィールドで指定できます。
1. 必要に応じて、アクティビティの [トランジションを管理し](../../automating/using/activity-properties.md) 、計算された母集団の高度なオプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、18 ～ 27才のAdobe Campaignデータベースと34 ～ 40才のプロファイルを再グループ化する2つのクエリアクティビティの結果を示しています。 結果には、設定時に指定した2つのクエリのすべてのプロファイル、または該当する場合は最大レコード数が含まれます。

![](assets/wkf_union_example.png)