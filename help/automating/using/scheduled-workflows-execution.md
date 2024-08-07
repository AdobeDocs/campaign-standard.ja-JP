---
title: スケジュールされたワークフローの重複実行
description: スケジュールされたワークフローが重複して実行されるのを防ぐ方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d9820a4-3c44-45f5-815e-4ed48a96276d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# スケジュールされたワークフローの重複実行{#preventing-overlapping-execution-of-scheduled-workflows}

## スケジュールされたワークフローの実行について

これにCampaign Standardして、ワークフローエンジンは、ワークフローインスタンスが 1 つのプロセスによってのみ実行されることを保証します。 インポート、長時間実行されているクエリ、データベースへの書き込みなどのアクティビティをブロックすると、実行中に他のタスクを実行できなくなります。

一方、ノンブロッキングアクティビティでは、他のタスク（通常は **[!UICONTROL Scheduler]** アクティビティなどのイベントを待機しているアクティビティ）の実行はブロックされません。

これにより、同じワークフローの以前の実行がまだ終了していない場合でも、スケジュールベースのワークフローの実行が開始され、予期しないデータの問題が発生する可能性があります。

したがって、複数のアクティビティを含むスケジュール済みワークフローを設計する場合、ワークフローが完了するまでスケジュールを再設定しないようにする必要があります。 これを行うには、以前の実行の 1 つ以上のタスクがまだ保留中の場合に実行を防ぐために、ワークフローを設定する必要があります。

## ワークフローの設定

以前のワークフロー実行で作成した 1 つ以上のタスクがまだ保留中かどうかを確認するには、**[!UICONTROL Query]** と **[!UICONTROL Test]** アクティビティを使用する必要があります。

1. **[!UICONTROL Query]** アクティビティを **[!UICONTROL Scheduler]** アクティビティの後に追加してから、次のように設定してください。

1. アクティビティのリソースを **[!UICONTROL WorkflowTaskDetail]** に変更します。つまり、ワークフローの現在のタスクをターゲットにします。

   ![](assets/scheduled-wkf-resource.png)

1. 以下のルールでクエリを設定します。

   ![](assets/scheduled-wkf-query.png)

   * 最初のルールでは、現在のタスク（query2）と、現在のワークフローに属する次のスケジュールタスク（schedule2）が除外されます。

     >[!NOTE]
     >
     >**[!UICONTROL Scheduler]** アクティビティが開始されると、直ちに別のスケジュールタスクを追加して、次のスケジュールされた時間に実行し、ワークフローを開始します。 したがって、以前の実行で保留中のタスクを検索する際は、クエリとスケジュールの両方のタスクをフィルタリングすることが重要です。

   * 2 つ目のルールは、ワークフローの以前の実行で作成されたタスクがまだアクティブ（保留中）かどうかを決定します。これは、実行ステータス 0 に対応します。

1. **[!UICONTROL Test]** アクティビティを追加して、**[!UICONTROL Query]** アクティビティから返される保留中のタスクの数を確認します。 これを行うには、2 つのアウトバウンドトランジションを設定します。

   ![](assets/scheduled-wkf-test.png)

   * 保留中のタスクがない場合、最初のトランジションはワークフローの実行を続行します。
   * 保留中のタスクがある場合、2 番目のトランジションではワークフローの実行がキャンセルされます。

   ![](assets/scheduled-wkf-workflow.png)

必要に応じて、残りのワークフローを設定できるようになりました。 タスクが保留中であるためにワークフローの実行がキャンセルされた場合、ワークフローがスケジュールに従って再度実行されると、次の手順を実行する可能性があります。 これにより、以前の実行からアクティブな（保留中の）タスクがない場合にのみ、ワークフローの実行が続行されます。
