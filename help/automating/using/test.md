---
title: テスト
seo-title: テスト
description: テスト
seo-description: テストアクティビティでは、テスト結果に基づくトランジションを有効にします。
page-status-flag: 常にアクティブ化されていない
uuid: 1562ec7a-253a-4f4f- b66a- c2948b57775a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行アクティビティ
discoiquuid: 2650bf1f-0bce-4049- a226-2369f6666b95
context-tags: jstest、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# テスト{#test}

## 説明 {#description}

![](assets/test.png)

**[!UICONTROL Test]** アクティビティによって、テスト結果に基づくトランジションが有効になります。

## Context of use {#context-of-use}

**テスト** アクティビティは、関連する条件を満たす最初のトランジションをアクティブにします。

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

Conditions can be based on **functions**, or on **variables**, for example events variables that have been declared into the workflow's **[!UICONTROL External signal]** activity.

**関連トピック:**

* [関数のリスト](../../automating/using/list-of-functions.md)
* [外部パラメーターでのワークフローの呼び出し](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Test]** activity into the workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 各条件の属性を定義します。

   **[!UICONTROL Condition]** フィールドを編集する際には、2つのボタンを使用して、イベント変数と関数を組み合わせた式の変数と関数を呼び出すことができます。

   * ![](assets/extsignal_picker.png):ワークフローで使用可能なすべての変数のイベント変数を選択します（外部パラメーターによるワークフロー [のカスタマイズを参照）](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)。

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png):編集式を使用して、変数と関数を組み合わせることができます。For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

