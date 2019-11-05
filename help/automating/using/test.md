---
title: テスト
description: Testアクティビティは、テスト結果に基づく移行を有効にします。
page-status-flag: 非活性化の
uuid: 1562ec7a-253a-4f4f-b66a-c2948b5775a
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 2650bf1f-0bce-4049-a226-2369f666b95
context-tags: jstest,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# テスト{#test}

## 説明 {#description}

![](assets/test.png)

The **[!UICONTROL Test]** activity enables a transition based on a test result.

## 使用状況 {#context-of-use}

A **Test** activity activates the first transition that satisfies the condition associated to it.

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

条件は、関数に基づいて **、または変数**（例えば、ワークフローのアクティビティに宣言されたイベント変数）に基づいて設定で ******[!UICONTROL External signal]** きます。

**関連トピック：**

* [関数のリスト](../../automating/using/list-of-functions.md)
* [外部パラメーターを使用したワークフローの呼び出し](../../automating/using/calling-a-workflow-with-external-parameters.md)

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Test]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 各条件の属性を定義します。

   フィールドを編集する **[!UICONTROL Condition]** 際に、2つのボタンを使用して、イベント変数を呼び出し、変数と関数を組み合わせた式を編集できます。

   * ![](assets/extsignal_picker.png):ワークフローで使用可能なすべての変数の中からevents変数を選択します(「外部パラメーターを使用したワ [ークフローのカスタマイズ」を参照](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters))。

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png):変数と関数を組み合わせた式を編集します。 For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

