---
solution: Campaign Standard
product: campaign
title: 実行コマンド
description: ワークフローの実行コマンドを使用する方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: ワークフロー
role: Data Architect
level: 初心者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 5%

---


# 実行コマンド {#execution-commands}

アクションバーのアイコンを使用すると、ワークフローの実行の開始、追跡、変更を行うことができます。 [アクションバー](../../automating/using/workflow-interface.md#action-bar)を参照してください。

![](assets/wkf_execution_2.png)

利用可能なアクションを次に示します。

**開始**

ワークフローを実行する![](assets/play_darkgrey-24px.png)ボタン開始。これは、**進行中** （青）の状態になります。 ワークフローが一時停止された場合は再開され、それ以外の場合は開始され、最初のアクティビティがアクティブ化されます。

>[!NOTE]
>
>開始は非同期プロセスです。要求は保存され、ワークフローの実行エンジンによって可能な限り早く処理されます。

**一時停止**

![](assets/pause_darkgrey-24px.png)ボタンは実行を一時停止します。 ワークフローは、**警告** （黄色）のステータスになります。 新しいアクティビティは、再開されるまでアクティブ化されませんが、進行中の操作は中断されません。

**停止**

![](assets/stop_darkgrey-24px.png)ボタンを押すと、実行中のワークフローが停止し、**完了** （緑）のステータスが適用されます。 進行中の操作は可能な場合は中断され、進行中のインポートまたはSQLクエリは直ちに取り消されます。 ワークフローを停止した場所と同じ場所から再開することはできません。

**再起動**

![](assets/pauseplay_darkgrey-24px.png)ボタンは、停止してからワークフローを再開します。 ほとんどの場合、これにより、より迅速に再起動できます。 また、![](assets/play_darkgrey-24px.png)ボタンは停止が有効な場合にのみ使用できるので、停止が一定時間かかると再起動を自動化すると便利です。

ワークフロー内の1つまたは複数のアクティビティを選択した場合、実行できる他の操作は次のとおりです。

**即時実行**

![](assets/pending_darkgrey-24px.png)ボタンは、可能な限り早く選択された保留中のアクティビティを開始します。

**通常の実行**

![](assets/check_darkgrey-24px.png)ボタンは、一時停止中または非アクティブなアクティビティを再度アクティブにします。

**実行が中断されました**

![](assets/check_pause_darkgrey-24px.png)ボタンは、選択したアクティビティでワークフローを一時停止します。このタスクとそれに続く（同じブランチ内の）すべての操作は実行されません。

**実行なし**

![](assets/checkdisable.png)ボタンは選択したアクティビティを非アクティブにします。

>[!NOTE]
>
>クイックアクションを使用すると、特定のアクティビティに関する様々なアクションにアクセスし、アクティビティを選択したときに表示されます。
