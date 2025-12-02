---
title: 和集合
description: 「和集合」アクティビティを使用すると、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: union,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3189745c-dcc9-4719-b080-85ffa3bb66be
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 97%

---

# 和集合{#union}

## 説明 {#description}

![](assets/union.png)

「**[!UICONTROL Union]**」アクティビティを使用すると、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。

>[!NOTE]
>
>セットは、同質である必要はありません。

## 使用コンテキスト {#context-of-use}

「**[!UICONTROL Union]**」アクティビティは、セグメント化の実行、オーディエンスの定義、またはメッセージターゲットの準備などの際に、インバウンドトランジションからの母集団を組み合わせるために使用します。

**関連トピック：**

* [ユースケース：2 つの絞り込まれたオーディエンスの和集合](../../automating/using/union-on-two-refined-audiences.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Union]**」アクティビティをドラッグ＆ドロップします。
1. そのアクティビティを、事前に実行する他のアクティビティ（クエリなど）に接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. インバウンド母集団間の矛盾から生じた重複の処理方法を定義するには、**[!UICONTROL Reconciliation type]** を選択します。

   * **[!UICONTROL Keys only]**：これはデフォルトのモードです。アクティビティは、異なるインバウンドトランジションの要素が同じキーを持つ場合、1 つの要素のみを保持します。このオプションは、インバウンド母集団が同質である場合にのみ使用できます。
   * **[!UICONTROL All shared columns]**：データは、インバウンドトランジションと共通するすべての列に基づいて紐付けされます。したがって、重複の場合に保持するプライマリセットを選択する必要があります。このオプションは、インバウンド母集団のターゲティングディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**：このオプションを選択し、データの紐付けが適用される列のリストを定義します。最初に（ソースデータを含む）プライマリセットを選択し、次に結合に使用する列を選択する必要があります。

1. すべてのインバウンドトランジションにある追加データのみを保持する場合は、「**[!UICONTROL Use common additional data only]**」チェックボックスをオンにします。
1. 最終的な母集団のサイズを制限する場合は、「**[!UICONTROL Limit size of generated population]**」チェックボックスをオンにします。サイズは「**[!UICONTROL Maximum number of records]**」フィールドで指定できます。
1. 必要に応じて、アクティビティの[トランジション](../../automating/using/activity-properties.md)を管理し、計算された母集団の詳細オプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

次の例は、Adobe Campaign データベースの 18～27 歳のプロファイルと 34～40 歳のプロファイルを再グループ化するための 2 つのクエリアクティビティの結果を示しています。結果には、設定時に指定した 2 つのクエリのすべてのプロファイル、または該当する場合は最大レコード数が含まれます。

![](assets/wkf_union_example.png)
