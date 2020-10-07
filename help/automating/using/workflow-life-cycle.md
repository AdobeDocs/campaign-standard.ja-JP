---
title: ワークフローのライフサイクル
description: ワークフローのライフサイクルの詳細
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
source-wordcount: '200'
ht-degree: 3%

---


# ワークフローのライフサイクル {#life-cycle}

ワークフローのライフサイクルには3つの主なステップが含まれ、各ステップはステータスと色にリンクされます。

* **編集** （グレー）

   これは、ワークフローの初期設計段階です(「ワークフローの [作成](../../automating/using/building-a-workflow.md#creating-a-workflow)」を参照)。 ワークフローはまだサーバーで処理されておらず、リスクなく変更できます。

* **処理中** （青）

   初期設計段階が完了すると、ワークフローを開始し、サーバで処理することができます。

* **完了** （緑）

   進行中のタスクがなくなった場合、または演算子がインスタンスを明示的に停止した場合は、ワークフローが完了します。

開始した後は、ワークフローにも次の2つのステータスがあります。

* **警告** （黄色）

   ワークフローを完了できなかったか、または ![](assets/pause_darkgrey-24px.png) ボタンを使用して一時停止してい ![](assets/check_pause_darkgrey-24px.png) ました。

* **エラーあり** （赤）

   ワークフローの実行中にエラーが発生しました。 ワークフローが停止され、ユーザーが操作を実行する必要があります。 このエラーの詳細を確認するには、 ![](assets/printpreview_darkgrey-24px.png) ボタンを使用してワークフローログにアクセスします( [監視を参照](../../automating/using/monitoring-workflow-execution.md))。

マーケティングアクティビティのリストにより、すべてのワークフローとステータスを表示できます。 For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
