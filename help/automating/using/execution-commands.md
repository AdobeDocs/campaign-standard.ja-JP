---
title: 実行コマンド
description: ワークフロー実行コマンドの使用方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 5%

---

# 実行コマンド {#execution-commands}

アクションバーのアイコンを使用して、ワークフローの実行を開始、追跡、変更できます。 [アクションバー](../../automating/using/workflow-interface.md#action-bar)を参照してください。

![](assets/wkf_execution_2.png)

利用可能なアクションを次に示します。

**開始**

![](assets/play_darkgrey-24px.png)ボタンは、ワークフローの実行を開始し、**処理中**（青）ステータスを取ります。 ワークフローが一時停止していた場合は再開され、それ以外の場合は開始され、最初のアクティビティが有効化されます。

>[!NOTE]
>
>開始は非同期プロセスです。リクエストは保存され、ワークフローの実行エンジンによってただちに処理されます。

**一時停止**

![](assets/pause_darkgrey-24px.png)ボタンは実行を一時停止します。 ワークフローは、「**警告**（黄色）」ステータスになります。 再開されるまで、新しいアクティビティはアクティブ化されませんが、進行中の操作は中断されません。

**停止**

![](assets/stop_darkgrey-24px.png)ボタンは、実行中のワークフローを停止し、**完了**（緑）ステータスになります。 処理中の操作は可能な場合は中断され、進行中のインポートまたはSQLクエリは即座にキャンセルされます。 停止した場所と同じ場所からワークフローを再開することはできません。

**再起動**

![](assets/pauseplay_darkgrey-24px.png)ボタンを押すと、ワークフローが停止し、再開されます。 ほとんどの場合は、これによりすばやく再起動できます。 また、![](assets/play_darkgrey-24px.png)ボタンは停止が有効な場合にのみ使用できるので、停止が一定時間かかった場合に再起動を自動化する場合にも便利です。

ワークフロー内の1つ以上のアクティビティを選択した場合、実行できる他のアクションは次のとおりです。

**即時実行**

「![](assets/pending_darkgrey-24px.png)」ボタンを押すと、選択中のアクティビティがただちに開始されます。

**通常の実行**

![](assets/check_darkgrey-24px.png)ボタンは、一時停止したアクティビティまたは非アクティブ化されたアクティビティを再アクティブ化します。

**実行中断**

![](assets/check_pause_darkgrey-24px.png)ボタンは、選択したアクティビティでワークフローを一時停止します。このタスクとそれに続くタスク（同じ分岐内）はどれも実行されません。

**実行なし**

![](assets/checkdisable.png)ボタンは、選択したアクティビティを非アクティブ化します。

>[!NOTE]
>
>クイックアクションを使用すると、1つの特定のアクティビティに関する様々なアクションにアクセスし、アクティビティを選択したときに表示できます。
