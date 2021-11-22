---
title: ワークフローのライフサイクル
description: ワークフローのライフサイクルの詳細を説明します
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# ワークフローのライフサイクル {#life-cycle}

ワークフローのライフサイクルには、3 つの主なステップが含まれ、各ステップはステータスと色にリンクされます。

* **編集中** （グレー）

   これは、ワークフローの最初のデザインフェーズです ( [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)) をクリックします。 ワークフローはまだサーバーで処理されておらず、安全に変更できます。

* **処理中** （青）

   最初のデザインフェーズが完了したら、ワークフローを開始し、サーバーによって処理できます。

* **完了** （緑）

   進行中のタスクがなくなった後、またはオペレーターがインスタンスを明示的に停止した後、ワークフローは終了します。

ワークフローを開始すると、その他に 2 つのステータスも表示されます。

* **警告** （黄色）

   ワークフローを完了できなかったか、 ![](assets/pause_darkgrey-24px.png) または ![](assets/check_pause_darkgrey-24px.png) ボタン

* **エラー** （赤）

   ワークフローの実行中にエラーが発生しました。 ワークフローが停止し、ユーザーはアクションを実行する必要があります。 このエラーの詳細については、 ![](assets/printpreview_darkgrey-24px.png) ボタンを使用して、ワークフローログにアクセスします ( [監視](../../automating/using/monitoring-workflow-execution.md)) をクリックします。

マーケティングアクティビティのリストを使用すると、すべてのワークフローとそのステータスを表示できます。 詳しくは、 [マーケティングアクティビティの管理](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
