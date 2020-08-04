---
title: テスト
description: 「Test」アクティビティは、テスト結果に基づくトランジションを有効にします。
page-status-flag: never-activated
uuid: 1562ec7a-253a-4f4f-b66a-c2948b57775a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 2650bf1f-0bce-4049-a226-2369f6666b95
context-tags: jstest,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---


# テスト{#test}

## 説明 {#description}

![](assets/test.png)

「**[!UICONTROL Test]**」アクティビティは、テスト結果に基づくトランジションを有効にします。

## 使用状況{#context-of-use}

「**Test**」アクティビティは、自身に関連付けられている条件を最初に満たしたトランジションを有効化します。

条件が 1 つも満たされず、「**Use default transition**」オプションが有効化されている場合、デフォルトのトランジションが有効化されます。

![](assets/wkf_test_activity_example.png)

条件は、**関数**&#x200B;または&#x200B;**変数**（ワークフローの「**[!UICONTROL External signal]**」アクティビティに宣言されたイベント変数など）に基づくことができます。

**関連トピック：**

* [関数のリスト](../../automating/using/list-of-functions.md)
* [外部パラメーターを使用したワークフローの呼び出し](../../automating/using/calling-a-workflow-with-external-parameters.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Test]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 各条件の属性を定義します。

   「**[!UICONTROL Condition]**」フィールドの編集時に、2 つのボタンを使用してイベント変数を呼び出し、変数と関数を組み合わせた式を編集できます。

   * ![](assets/extsignal_picker.png)：ワークフローで使用可能なすべての変数の中からイベント変数を選択します（[外部パラメーターを使用したワークフローのカスタマイズ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)を参照）。

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png)：変数と関数を組み合わせた式を編集します。式エディターについて詳しくは、[この節](../../automating/using/advanced-expression-editing.md)を参照してください。

      ![](assets/wkf_test_activity_variables_expression.png)

