---
title: 和集合
description: Unionアクティビティでは、複数のアクティビティの結果を1つのターゲットに再グループ化できます。
page-status-flag: 非活性化の
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲティング活動
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 和集合{#union}

## 説明 {#description}

![](assets/union.png)

アクティビテ **[!UICONTROL Union]** ィを使用すると、複数のアクティビティの結果を1つのターゲットに再グループ化できます。

>[!NOTE]
>
>セットは必ずしも同一である必要はありません。

## 使用状況 {#context-of-use}

アクティビティ **[!UICONTROL Union]** は、セグメント化の実行、オーディエンスの定義、例えばメッセージターゲットの準備などの際に、インバウンド遷移からの訪問者を組み合わせるために使用されます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Union]** にドラッグ&amp;ドロップします。
1. クエリーなど、その前の他のアクティビティに接続します。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 「」を選択 **[!UICONTROL Reconciliation type]** し、インバウンド母集団間の対決からの重複の処理方法を定義します。

   * **[!UICONTROL Keys only]**:これはデフォルトのモードです。 アクティビティは、異なる受信遷移の要素が同じキーを持つ場合に、1つの要素のみを保持します。 このオプションは、受入母集団が均一である場合にのみ使用できます。
   * **[!UICONTROL All shared columns]**:データは、受信遷移と共通するすべての列に基づいて調整されます。 したがって、重複した場合に保持するプライマリ・セットを選択する必要があります。 このオプションは、インバウンド母集団のターゲットディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**:データ調整を適用する列のリストを定義する場合は、このオプションを選択します。 最初に（ソースデータを含む）プライマリ・セットを選択し、次に結合に使用する列を選択する必要があります。

1. すべての受 **[!UICONTROL Use common additional data only]** 信遷移に含まれる追加データのみを保持する場合は、このボックスをオンにします。
1. 最終的な母集団のサイズを制限する場合は、このボックスをオンにし **[!UICONTROL Limit size of generated population]** ます。 サイズはフィールドで指定でき **[!UICONTROL Maximum number of records]** ます。
1. 必要に応じて、アクティビティの遷移を管理し [て](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) 、計算された母集団のアドバンスオプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、18 ～ 27才のAdobe Campaignデータベースから、34 ～ 40才のプロファイルを再グループ化する2つのクエリアクティビティの結果を示しています。 結果には、2つのクエリーのすべてのプロファイル、または設定時に指定した最大レコード数（該当する場合）が含まれます。

![](assets/wkf_union_example.png)