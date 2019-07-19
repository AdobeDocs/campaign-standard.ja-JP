---
title: Wait
seo-title: Wait
description: Wait
seo-description: ワークフローの一部の実行を一時停止する待機アクティビティ。
page-status-flag: 常にアクティブ化されていない
uuid: 396a3de1-6ffa-4385- ac9f-15fdeae5a366
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行アクティビティ
discoiquuid: 377821e6-69f8-41cc- a1ad-8a2f5ed4d409
context-tags: wait， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Wait{#wait}

## 説明 {#description}

![](assets/wait.png)

The **[!UICONTROL Wait]** activity momentarily suspends executing a part of a workflow. 数秒から数か月に及ぶ遅延の後、アウトバウンドトランジションがアクティブになり、後で配置したアクティビティが実行されます。

## Context of use {#context-of-use}

**[!UICONTROL Wait]** アクティビティは、実行される2つのアクティビティ間の特定の時間を受け渡すために使用されます。例えば、電子メール配信アクティビティから数日待ってから、フォローアップ操作（リマインダーの電子メール、オーディエンスの作成など）を実行するまでに生成された開封およびクリックを分析することができます。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Wait]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Duration]** of the wait between when the inbound and outbound transitions of the activity are activated.

   手動で期間を入力することも、フィールド内の選択可能なセレクターを使用することもできます。

   ![](assets/wait_duration.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

The following example illustrates the **[!UICONTROL Wait]** activity in a typical use case. イベントへの電子メールの招待状が送信されます。送信後24時間後に、電子メール配信ログが分析され、リマインダーの電子メールが受信者に送信されますが、サインアップしなかったユーザーに送信されます。

ワークフローは次のように表示されます。

![](assets/wait_example_workflow.png)

* A first **[!UICONTROL Query]** targets the profiles that will be sent the email invitation.
* An **[!UICONTROL Email delivery]** sends the invitation for the first time to the profiles selected.
* **[!UICONTROL Wait]** 24hのアクティビティでは、招待の送信時と残りのワークフローの間で一時停止が行われます。
* A second **[!UICONTROL Query]** targets the profiles that received the first email but did not click on the subscription link inside.
* A second **[!UICONTROL Email delivery]** sends a reminder of the invitation to the people selected.

