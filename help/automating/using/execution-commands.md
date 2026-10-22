---
title: 実行コマンド
description: ワークフロー実行コマンドの使用方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
TQID: 'https://experienceleague.adobe.com/jDS-3Rz--h6N17JfbijrtOaj8jVDPDW9HiOoiLwPHSY'
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
source-wordcount: '317'
ht-degree: 20%
---
# 実行コマンド {#execution-commands}

アクションバーのアイコンを使用すると、ワークフローの実行を開始、追跡、変更できます。 [&#x200B; アクションバー](../../automating/using/workflow-interface.md#action-bar)を参照してください。

![](assets/wkf_execution_2.png)

利用可能なアクションを次に示します。

**開始**

![](assets/play_darkgrey-24px.png) ボタンはワークフローの実行を開始し、**進行中** （青）ステータスになります。 ワークフローが一時停止していた場合は再開されます。それ以外の場合は、ワークフローが開始され、初期のアクティビティが有効化されます。

>[!NOTE]
>
>開始は非同期プロセスです。リクエストは保存され、ワークフロー実行エンジンによってできるだけ早く処理されます。

**一時停止**

![](assets/pause_darkgrey-24px.png) ボタンは実行を一時停止します。 ワークフローは、**警告** （黄色）ステータスになります。 ワークフローが再開されるまでは新しいアクティビティは有効化されません。ただし、進行中の操作は中断されません。

**停止**

![](assets/stop_darkgrey-24px.png) ボタンは、実行中のワークフローを停止します。そのワークフローは、**完了** （緑）のステータスになります。 処理中の操作は、可能であれば中断され、処理中のSQL クエリのインポートやSQL クエリは直ちにキャンセルされます。 ワークフローを停止した場所から再開することはできません。

**再起動**

![](assets/pauseplay_darkgrey-24px.png) ボタンには、ワークフローを停止してから再起動することが含まれます。 ほとんどの場合、これにより、より迅速に再起動できます。 また、![](assets/play_darkgrey-24px.png) ボタンは停止が効果的な場合にのみ使用できるため、停止に一定の時間がかかった場合は自動的に再起動すると便利です。

ワークフロー内の1つまたは複数のアクティビティを選択すると、次のような他のアクションを実行できます。

**即時の実行**

![](assets/pending_darkgrey-24px.png) ボタンは、選択された保留中のアクティビティをできるだけ早く開始します。

**通常の実行**

![](assets/check_darkgrey-24px.png) ボタンは、一時停止または非アクティブ化されたアクティビティを再アクティブ化します。

**実行が中断されました**

![](assets/check_pause_darkgrey-24px.png) ボタンは、選択したアクティビティでワークフローを一時停止します。このタスクと、それに続くすべてのタスク（同じブランチ内）は実行されません。

**実行なし**

![](assets/checkdisable.png) ボタンは、選択したアクティビティをすべて無効にします。

>[!NOTE]
>
>クイックアクションを使用すると、1つの特定のアクティビティに関するさまざまなアクションにアクセスし、アクティビティが選択されたときに表示されます。
