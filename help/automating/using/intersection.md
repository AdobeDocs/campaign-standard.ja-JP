---
title: 積集合
description: 交差アクティビティでは、アクティビティ内の異なる受入母集団に共通の要素のみを保持できます。
page-status-flag: 非活性化の
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲティング活動
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 積集合{#intersection}

## 説明 {#description}

![](assets/intersection.png)

アクテ **[!UICONTROL Intersection]** ィビティでは、アクティビティ内の異なる受信訪問者に共通の要素のみを保持できます。

## 使用状況 {#context-of-use}

通常、 **[!UICONTROL Intersection]** アクティビティは、受信遷移からの訪問者に対して追加のフィルタリングを実行するために使用されます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Intersection]** にドラッグ&amp;ドロップします。
1. クエリーなど、その前の他のアクティビティに接続します。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 以下を選択しま **[!UICONTROL Reconciliation type]**&#x200B;す。

   * **[!UICONTROL Keys only]**:デフォルトモード。 アクティビティは、異なる受信遷移の要素が同じキーを持つ場合に、1つの要素のみを保持します。
   * **[!UICONTROL All shared columns]**:データは、受信遷移と共通の列に基づいて調整されます。 したがって、比較の基になる主セットを選択する必要があります。 このオプションは、インバウンド母集団のターゲットディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**:データ調整を適用する列のリストを定義するには、このオプションを選択します。 最初にプライマリセット（ソースデータを含むセット）を選択し、結合に使用するフィールドを指定する必要があります。

1. すべての受 **[!UICONTROL Use common additional data only]** 信遷移に含まれる追加データのみを保持する場合は、このボックスをオンにします。
1. 必要に応じて、アクティビティの遷移を管理し [て](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) 、アウトバウンド母集団のアドバンスオプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、2つのクエリーアクティビティの共通部分を示しています。 ここでは、Adobe Campaignデータベースを調べ、18 ～ 27才のプロファイルと、それぞれ電子メールアドレスが指定されたプロファイルを取得するために使用されています。

![](assets/wkf_intersection_example.png)

