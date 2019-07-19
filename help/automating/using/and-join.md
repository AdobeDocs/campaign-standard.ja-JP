---
title: AND- join
seo-title: AND- join
description: AND- join
seo-description: AND- joinアクティビティを使用すると、ワークフローの複数の実行ブランチを同期できます。
page-status-flag: 常にアクティブ化されていない
uuid: 9b54fd4c-9915-400f- a494-74e52c329b8a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行アクティビティ
discoiquuid: 4b55efa2-652e-4493- bfa7- eaee59b383ca
context-tags: '& join， main'
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# AND-join{#and-join}

## 説明 {#description}

![](assets/and_join.png)

**[!UICONTROL AND-join]** アクティビティでは、ワークフローの複数の実行ブランチを同期できます。

## Context of use {#context-of-use}

**[!UICONTROL AND-join]** このアクティビティでは、すべてのインバウンドトランジションがアクティブ化されると、送信トランジションがトリガーされます（つまり、前のすべてのアクティビティが完了した後）。

## Configuration {#configuration}

1. ワークフローにクエリなど複数のアクティビティをドロップして、少なくとも2つの異なる実行ブランチをフォームに送信します。
1. Drag and drop an **[!UICONTROL AND-join]** activity into your workflow.
1. 同期する2つの異なるブランチの後に接続します。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. アウトバウンドトランジションに保持するメインセットを選択します。セットを選択しない場合、ランダムな母集団がアクティビティから送信されます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

The following example shows two workflow branches before they are joined with the **[!UICONTROL AND-join]** activity. File extraction can only take place when the three inbound transitions of the **[!UICONTROL AND-join]** activity are enabled.

![](assets/wkf_and-join_example.png)

