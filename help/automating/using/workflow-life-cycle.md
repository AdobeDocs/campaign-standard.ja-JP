---
title: ワークフローのライフサイクル
description: ワークフローのライフサイクルについて詳しく見る
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
TQID: 'https://experienceleague.adobe.com/nWv8hOZa2JQgiO2CEnffriIqb6czIA7Gh0AwWCTwRAA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%
---
# ワークフローのライフサイクル {#life-cycle}

ワークフローのライフサイクルには3つの主要なステップがあり、各ステップはステータスと色にリンクされています。

* **編集** （グレー）

  これは、ワークフローの最初の設計フェーズです（[ ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照）。 ワークフローはまだサーバーによって処理されておらず、リスクなしに変更できます。

* **進行中** （青）

  最初の設計フェーズが完了すると、ワークフローを開始し、サーバーが処理します。

* **完了** （緑）

  処理中のタスクがなくなった場合、またはオペレーターがインスタンスを明示的に停止した場合、ワークフローは終了します。

ワークフローを開始すると、他にも2つのステータスが表示される場合があります。

* **警告** （黄色）

  ワークフローを完了できなかったか、![](assets/pause_darkgrey-24px.png)または![](assets/check_pause_darkgrey-24px.png) ボタンを使用して一時停止しました。

* **エラー** （赤）

  ワークフローの実行時にエラーが発生しました。 ワークフローが停止されました。ユーザーはアクションを実行する必要があります。 このエラーの詳細については、![](assets/printpreview_darkgrey-24px.png) ボタンを使用してワークフローログにアクセスしてください（[監視](../../automating/using/monitoring-workflow-execution.md)を参照）。

マーケティング活動のリストを使用すると、すべてのワークフローとそのステータスを表示できます。 詳しくは、「[ マーケティング活動の管理](../../start/using/marketing-activities.md#about-marketing-activities)」を参照してください。

![](assets/wkf_execution_3.png)
