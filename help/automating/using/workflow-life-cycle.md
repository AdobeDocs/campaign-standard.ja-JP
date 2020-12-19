---
solution: Campaign Standard
product: campaign
title: ワークフローのライフサイクル
description: ワークフローのライフサイクルの詳細
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---


# ワークフローのライフサイクル {#life-cycle}

ワークフローのライフサイクルには3つの主なステップが含まれ、各ステップはステータスと色にリンクされます。

* **編集** （グレー）

   これは、ワークフローの初期設計段階です（[ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照）。 ワークフローはまだサーバーで処理されておらず、リスクなく変更できます。

* **処理中** （青）

   初期設計段階が完了すると、ワークフローを開始し、サーバで処理することができます。

* **完了** （緑）

   進行中のタスクがなくなった場合、または演算子がインスタンスを明示的に停止した場合は、ワークフローが完了します。

開始した後は、ワークフローにも次の2つのステータスがあります。

* **警告** （黄色）

   ワークフローを完了できなかったか、![](assets/pause_darkgrey-24px.png)または![](assets/check_pause_darkgrey-24px.png)ボタンを使用して一時停止しました。

* **エラーあり** （赤）

   ワークフローの実行中にエラーが発生しました。 ワークフローが停止され、ユーザーが操作を実行する必要があります。 このエラーの詳細を調べるには、![](assets/printpreview_darkgrey-24px.png)ボタンを使用してワークフローログにアクセスします（[監視](../../automating/using/monitoring-workflow-execution.md)を参照）。

マーケティングアクティビティのリストにより、すべてのワークフローとステータスを表示できます。 詳しくは、「[マーケティングアクティビティの管理](../../start/using/marketing-activities.md#about-marketing-activities)」を参照してください。

![](assets/wkf_execution_3.png)
