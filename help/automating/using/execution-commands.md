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
ht-degree: 20%

---

# 実行コマンド {#execution-commands}

アクションバーのアイコンを使用して、ワークフローの実行を開始、追跡、変更できます。 詳しくは、 [アクションバー](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

利用可能なアクションを次に示します。

**開始**

The ![](assets/play_darkgrey-24px.png) ボタンは、ワークフローの実行を開始し、ワークフローを処理します **処理中** （青）ステータス。 ワークフローが一時停止していた場合は再開されます。それ以外の場合は、ワークフローが開始され、初期のアクティビティが有効化されます。

>[!NOTE]
>
>開始は非同期プロセスです。リクエストは保存され、ワークフローの実行エンジンでただちに処理されます。

**一時停止**

The ![](assets/pause_darkgrey-24px.png) ボタンを押すと、実行が一時停止されます。 ワークフローでは、 **警告** （黄色）ステータス。 ワークフローが再開されるまでは新しいアクティビティは有効化されません。ただし、進行中の操作は中断されません。

**停止**

The ![](assets/stop_darkgrey-24px.png) ボタンを押すと、実行中のワークフローが停止し、ワークフローが **完了** （緑）ステータス。 処理中の操作が可能な場合は中断され、進行中のインポートまたは SQL クエリは直ちにキャンセルされます。 ワークフローを停止した場所から再開することはできません。

**再起動**

The ![](assets/pauseplay_darkgrey-24px.png) ボタンをクリックすると、ワークフローが停止した後で再起動します。 ほとんどの場合は、これにより迅速に再起動できます。 また、停止がある程度の時間を要すると、再起動を自動化する場合にも便利です。 ![](assets/play_darkgrey-24px.png) ボタンは、停止が有効な場合にのみ使用できます。

ワークフロー内の 1 つまたは複数のアクティビティを選択した場合、次のような他のアクションを実行できます。

**即時実行**

The ![](assets/pending_darkgrey-24px.png) ボタンは、選択した保留中のアクティビティをただちに開始します。

**通常の実行**

The ![](assets/check_darkgrey-24px.png) ボタンは、一時停止したアクティビティまたは非アクティブなアクティビティを再アクティブ化します。

**実行が中断されました**

The ![](assets/check_pause_darkgrey-24px.png) ボタンは、選択したアクティビティでワークフローを一時停止します。このタスクとそれに続くタスク（同じ分岐内）はどれも実行されません。

**実行なし**

The ![](assets/checkdisable.png) 「 」ボタンをクリックすると、選択したアクティビティが非アクティブになります。

>[!NOTE]
>
>クイックアクションを使用すると、1 つの特定のアクティビティに関する様々なアクションにアクセスし、アクティビティを選択したときに表示できます。
