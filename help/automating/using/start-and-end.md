---
title: 開始と終了
seo-title: 開始と終了
description: 開始と終了
seo-description: 開始および終了アクティビティでは、ワークフローの開始と終了を明確にマークできます。
page-status-flag: 常にアクティブ化されていない
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行アクティビティ
discoiquuid: a0a8a725-8ede-4626-9798- b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# Start and end{#start-and-end}

## 説明 {#description}

![](assets/start.png)

![](assets/end.png)

**[!UICONTROL Start]****[!UICONTROL End]** また、ワークフローの開始と終了を明確に示すことができます。

## Context of use {#context-of-use}

ワークフローの実行は、インバウンドトランジションのないアクティビティで開始され、進行中のタスクがなくても停止します。Nevertheless, you can add **[!UICONTROL Start]** and **[!UICONTROL End]** activities to clearly mark the starting and ending points of a workflow. これは、比較的複雑なワークフローに特に便利です。

It is a best practice to use an **[!UICONTROL End]** activity instead of leaving the last transition of a workflow on its own to ensure that the workflow properly ends.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Start]** or **[!UICONTROL End]** activity into your workflow.
1. Put the **[!UICONTROL Start]** activity in front of other activities such as queries, and the **[!UICONTROL End]** activity after a series of activities.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. **終了** オブジェクトを設定して、完了していないすべてのワークフローの実行中のタスクを中断することができます。これを行うには、対応するオプションを選択します。
1. アクティビティの設定を確認し、ワークフローを保存します。

## Triggering another workflow {#triggering-another-workflow}

Using the **[!UICONTROL External signal]** tab of an **[!UICONTROL End]** activity, you can trigger another workflow. [「外部信号](../../automating/using/external-signal.md) 」セクションを参照してください。

## Example {#example}

The following example shows how a complex workflow is executed with a **[!UICONTROL Start]** activity and several **[!UICONTROL End]** activities. **[!UICONTROL Stop all tasks in progress]** 最初 **[!UICONTROL End]** のアクティビティがチェックされました。Once the corresponding task is finished, the entire workflow will be stopped: it will have the same effect as if the ![](assets/stop_darkgrey-24px.png) button had been selected (refer to the [Action bar](../../automating/using/workflow-interface.md#action-bar) section).

![](assets/wkf_start_end_example.png)

