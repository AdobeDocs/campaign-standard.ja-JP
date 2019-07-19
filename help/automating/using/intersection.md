---
title: 交差
seo-title: 交差
description: 交差
seo-description: 交差アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを維持できます。
page-status-flag: 常にアクティブ化されていない
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: 7a107d6b- edc3-44c3- bbb7- ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Intersection{#intersection}

## 説明 {#description}

![](assets/intersection.png)

**[!UICONTROL Intersection]** アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを維持できます。

## Context of use {#context-of-use}

**[!UICONTROL Intersection]** アクティビティは、通常、インバウンドトランジションからの訪問者に対して追加のフィルターを実行するために使用します。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Intersection]** activity into your workflow.
1. クエリなどの他のアクティビティに接続します。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**:デフォルトモード。このアクティビティでは、異なるインバウンドトランジションの要素が同じキーを持つ場合にのみ、1つの要素を保持します。
   * **[!UICONTROL All shared columns]**:データは、インバウンドトランジションと共通の列に基づいて調整されます。そのため、比較のベースとなるプライマリセットを選択する必要があります。このオプションは、受信者の母集団のディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**:データの紐付けを適用する列のリストを定義するには、このオプションを選択します。最初に、プライマリセット（ソースデータを含む）を選択し、結合に使用するフィールドを指定します。

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

次の例では、2つのクエリーアクティビティ間の共通部分を示しています。ここでは、Adobe Campaignデータベースを調べ、それぞれ18~27才のプロファイルを取得し、電子メールアドレスを提供するプロファイルを取得します。

![](assets/wkf_intersection_example.png)

