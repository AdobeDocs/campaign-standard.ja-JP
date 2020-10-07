---
title: 実行コマンド
description: ワークフローの実行コマンドを使用する方法を説明します。
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 5%

---


# 実行コマンド {#execution-commands}

アクションバーのアイコンを使用すると、ワークフローの実行の開始、追跡、変更を行うことができます。 「 [アクションバー](../../automating/using/workflow-interface.md#action-bar)」を参照してください。

![](assets/wkf_execution_2.png)

利用可能なアクションを次に示します。

**開始**

ワークフローを実行する ![](assets/play_darkgrey-24px.png) ボタン開始。次に、 **処理中** （青）のステータスになります。 ワークフローが一時停止された場合は再開され、それ以外の場合は開始され、最初のアクティビティがアクティブ化されます。

>[!NOTE]
>
>開始は非同期プロセスです。要求は保存され、ワークフローの実行エンジンによって可能な限り早く処理されます。

**一時停止**

この ![](assets/pause_darkgrey-24px.png) ボタンを押すと実行が一時停止します。 ワークフローは、 **警告** （黄色）ステータスになります。 新しいアクティビティは、再開されるまでアクティブ化されませんが、進行中の操作は中断されません。

**停止**

この ![](assets/stop_darkgrey-24px.png) ボタンを押すと、実行中のワークフローが停止し、「 **完了** （緑色）」のステータスになります。 進行中の操作は可能な場合は中断され、進行中のインポートまたはSQLクエリは直ちに取り消されます。 ワークフローを停止した場所と同じ場所から再開することはできません。

**再起動**

この ![](assets/pauseplay_darkgrey-24px.png) ボタンは、ワークフローを停止してから再開する操作です。 ほとんどの場合、これにより、より迅速に再起動できます。 また、停止が有効な場合にのみ ![](assets/play_darkgrey-24px.png) ボタンを使用できるので、停止が一定時間かかると再起動を自動化すると便利です。

ワークフロー内の1つまたは複数のアクティビティを選択した場合、実行できる他の操作は次のとおりです。

**即時実行**

この ![](assets/pending_darkgrey-24px.png) ボタンは、可能な限り早く選択された保留中のアクティビティを開始します。

**通常の実行**

この ![](assets/check_darkgrey-24px.png) ボタンは、一時停止中または非アクティブなアクティビティを再度アクティブにします。

**実行が中断されました**

この ![](assets/check_pause_darkgrey-24px.png) ボタンを押すと、選択したアクティビティでワークフローが一時停止されます。このタスクとそれに続く（同じブランチ内の）すべての操作は実行されません。

**実行なし**

この ![](assets/checkdisable.png) ボタンは選択したアクティビティを非アクティブにします。

>[!NOTE]
>
>クイックアクションを使用すると、特定のアクティビティに関する様々なアクションにアクセスし、アクティビティを選択したときに表示されます。
