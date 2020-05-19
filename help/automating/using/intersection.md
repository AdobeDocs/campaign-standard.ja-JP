---
title: 積集合
description: 積集合アクティビティでは、アクティビティ内の異なる受信訪問者に共通の要素のみを保持できます。
page-status-flag: never-activated
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 1%

---


# 積集合{#intersection}

## 説明 {#description}

![](assets/intersection.png)

この **[!UICONTROL Intersection]** アクティビティでは、アクティビティ内の異なる受信訪問者に共通の要素のみを保持できます。

## 使用状況 {#context-of-use}

この **[!UICONTROL Intersection]** アクティビティは、通常、受信トランジションからの訪問者に対して追加のフィルタリングを行うのに使用されます。

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Intersection]** アクティビティをドラッグ&amp;ドロップします。
1. クエリなど、その前にある他のアクティビティに接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 以下を選択し **[!UICONTROL Reconciliation type]**&#x200B;ます。

   * **[!UICONTROL Keys only]**: デフォルトモード アクティビティは、異なる受信トランジションの要素が同じキーを持つ場合、1つの要素のみを保持します。
   * **[!UICONTROL All shared columns]**: データは、受信トランジションと共通の列に基づいて調整されます。 したがって、比較の基準となるプライマリセットを選択する必要があります。 このオプションは、受信訪問者のターゲティングディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**: データの調整を適用する列のリストを定義するには、このオプションを選択します。 最初にプライマリセット（ソースデータを含むセット）を選択し、次に結合に使用するフィールドを指定する必要があります。

1. すべての受信トランジションに追加のデータのみを保持する場合は、この **[!UICONTROL Use common additional data only]** チェックボックスをオンにします。
1. 必要に応じて、アクティビティの [トランジションを管理し](../../automating/using/activity-properties.md) 、アウトバウンド母集団のアドバンスオプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、2つのクエリアクティビティ間の共通部分を示しています。 ここでは、Adobe Campaignデータベースを調べ、18 ～ 27才のプロファイルと、それぞれ電子メールアドレスが指定されたプロファイルを取得するために使用されています。

![](assets/wkf_intersection_example.png)

