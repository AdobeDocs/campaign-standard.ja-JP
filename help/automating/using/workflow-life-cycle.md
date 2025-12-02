---
title: ワークフローのライフサイクル
description: ワークフローのライフサイクルの詳細情報
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# ワークフローのライフサイクル {#life-cycle}

ワークフローのライフサイクルには 3 つの主なステップが含まれ、各ステップはステータスとカラーにリンクされています。

* **編集中** （灰色）

  これは、ワークフローの初期デザインフェーズです（[&#x200B; ワークフローの作成 &#x200B;](../../automating/using/building-a-workflow.md#creating-a-workflow) を参照）。 ワークフローはまだサーバーで処理されず、リスクを伴わずに変更できます。

* **処理中** （青）

  初期デザインフェーズが完了したら、ワークフローを開始し、サーバーで処理することができます。

* **完了** （緑）

  ワークフローは、進行中のタスクがなくなるか、オペレーターがインスタンスを明示的に停止すると終了します。

開始されると、ワークフローには他に 2 つのステータスが含まれる場合もあります。

* **警告** （黄色）

  ワークフローを完了できなかったか、「![](assets/pause_darkgrey-24px.png)」または「![](assets/check_pause_darkgrey-24px.png)」ボタンを使用して一時停止しました。

* **エラー** （赤）

  ワークフローの実行時にエラーが発生しました。 ワークフローが停止されました。ユーザーはアクションを実行する必要があります。 このエラーの詳細については、「![](assets/printpreview_darkgrey-24px.png)」ボタンを使用してワークフローログにアクセスしてください（[&#x200B; モニタリング &#x200B;](../../automating/using/monitoring-workflow-execution.md) を参照）。

マーケティングアクティビティのリストを使用すると、すべてのワークフローとそのステータスを表示できます。 詳しくは、[&#x200B; マーケティングアクティビティの管理 &#x200B;](../../start/using/marketing-activities.md#about-marketing-activities) を参照してください。

![](assets/wkf_execution_3.png)
