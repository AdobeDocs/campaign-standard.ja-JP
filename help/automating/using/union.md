---
title: Union
seo-title: Union
description: Union
seo-description: Unionアクティビティを使用すると、複数のアクティビティの結果を単一のターゲットに再グループ化できます。
page-status-flag: 常にアクティブ化されていない
uuid: ffc3ce9-2212-4403-8754- cfbb28ba6e26
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: 99a8c3a5-7d90-4dbb- aa37-1d0a84719cf6
context-tags: union， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Union{#union}

## 説明 {#description}

![](assets/union.png)

**[!UICONTROL Union]** アクティビティを使用すると、複数のアクティビティの結果を単一のターゲットに再グループ化できます。

>[!NOTE]
>
>セットは必ずしも均一である必要はありません。

## Context of use {#context-of-use}

**[!UICONTROL Union]** アクティビティは、セグメント化の実行、オーディエンスの定義、メッセージターゲットの準備などの際に、訪問者をインバウンドトランジションから結合するために使用します。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Union]** activity into your workflow.
1. クエリなどの他のアクティビティに接続します。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]** to define how duplicates are from the confrontation between inbound populations are handled:

   * **[!UICONTROL Keys only]**:これがデフォルトのモードです。このアクティビティでは、異なるインバウンドトランジションの要素が同じキーを持つ場合にのみ、1つの要素を保持します。このオプションは、受信母集団が均等な場合にのみ使用できます。
   * **[!UICONTROL All shared columns]**:データは、インバウンドトランジションと共通のすべての列に基づいて調整されます。そのため、複製の場合に保持するプライマリセットを選択する必要があります。このオプションは、受信者の母集団のディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**:データの紐付けを適用する列のリストを定義するには、このオプションを選択します。最初に、プライマリセット（ソースデータを含む）を選択し、結合に使用する列を選択する必要があります。

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. The size can be specified in the **[!UICONTROL Maximum number of records]** field.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the calculated population.
1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

次の例は、18才から27才までのAdobe Campaignデータベースからプロファイルを再グループ化する2つのクエリーアクティビティの結果を示しています。結果には、2つのクエリーのすべてのプロファイルまたは設定時に指定した最大レコード数が含まれます。

![](assets/wkf_union_example.png)