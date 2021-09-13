---
title: ワークフローの実行の監視
description: ワークフローの実行を監視する方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 6%

---

# ワークフローの実行の監視 {#monitoring}

## ワークフローログとタスク {#workflow-log-and-tasks}

![](assets/printpreview_darkgrey-24px.png)アイコンをクリックすると、ワークフローログとタスクのメニューが開きます。

ワークフローの履歴は、ワークフローの実行オプションで指定された期間保存されます（[ワークフローのプロパティ](../../automating/using/managing-execution-options.md)を参照）。 この期間中は、再起動後も、すべてのメッセージが保存されます。 以前の実行のメッセージを保存しない場合は、「![](assets/delete_darkgrey-24px.png)」ボタンをクリックして履歴をパージする必要があります。

**[!UICONTROL Log]**&#x200B;タブには、すべてのアクティビティまたは選択したアクティビティの実行履歴が表示されます。 実行された操作と実行エラーのインデックスを時系列順に作成します。

![](assets/wkf_execution_4.png)

「 **[!UICONTROL Tasks]** 」タブでは、アクティビティの実行順序の詳細を説明します。 タスクをクリックして詳細を表示します。

![](assets/wkf_execution_5.png)

次の2つのリストで、

* カウンターをクリックし、適用したフィルターに従ったアクティビティの合計数を確認します。 リスト内の要素数が30未満の場合は、カウンターがデフォルトで表示されます。
* **[!UICONTROL Configure list]**&#x200B;ボタンを使用すると、表示される情報の選択、列の順序の定義、リストの並べ替えを行うことができます。
* フィルターを使用すると、必要な情報をすばやく見つけることができます。 検索フィールドを使用して、ワークフローアクティビティ名内の特定のテキストを検索します(例：&quot;query&quot;)とログを参照してください。

## エラー管理 {#error-management}

エラーが発生すると、ワークフローが一時停止し、エラーが発生したときに実行中だったアクティビティが赤く点滅します。

ワークフローのステータスが赤に変わり、エラーがログに記録されます。

一時停止せず、エラーなく実行を続行するようにワークフローを設定できます。 それには、![](assets/edit_darkgrey-24px.png)ボタンを使用してワークフローのプロパティに移動し、「**[!UICONTROL Execution]**」セクションの「**エラーの場合**」フィールドで「**無視**」オプションを選択します。

この場合、エラーのあるタスクは中止されます。 このモードは、後で操作を再試行するように設計されたワークフロー（定期的なアクション）に特に適しています。

>[!NOTE]
>
>この設定は、各アクティビティに個別に適用できます。これをおこなうには、アクティビティを選択し、クイックアクション![](assets/edit_darkgrey-24px.png)を使用して開きます。 次に、「**実行オプション**」タブでエラー管理モードを選択します。 [アクティビティ実行オプション](../../automating/using/activity-properties.md)を参照してください。

[ワークフローのプロパティ](../../automating/using/managing-execution-options.md)には、エラー管理に関する追加のオプションが用意されています。

![](assets/wkf_execution_error.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Supervisors]**:ワークフローでエラーが発生した場合に通知するユーザーのグループ（電子メールおよびアプリ内通知）を定義できます。グループが定義されていない場合、通知は送信されません。 Adobe Campaignの通知について詳しくは、[Adobe Campaignの通知](../../administration/using/sending-internal-notifications.md)を参照してください。

* **[!UICONTROL In case of error]**:「 」では、アクティビティでエラーが発生した場合に実行するアクションを指定できます。これには、次の2つのオプションを使用できます。

   * **プロセスの休止**:ワークフローは自動的に休止されます。次に、ワークフローのステータスが「**エラー**」になり、関連付けられた色が赤に変わります。 問題が解決したら、ワークフローを再起動します。
   * **無視**:アクティビティは実行されず、その結果、後続のアクティビティも（同じ分岐内で）実行されません。これは、繰り返しタスクに役立つ場合があります。 上流で分岐にスケジューラーが設定されている場合、これは次の実行日にトリガーする必要があります。

* **[!UICONTROL Consecutive errors]** :では、ワークフローの実行が自動的に中断されるまでに承認される連続したエラーの数を定義できます。

   * 指定した数が&#x200B;**[!UICONTROL 0]**&#x200B;の場合、または指定した数に達しない限り、エラーが発生したアクティビティは無視されます。 その他のワークフローブランチは、通常どおり実行されます。

   * 指定した数に達すると、ワークフロー全体が休止され、**[!UICONTROL Erroneous]**&#x200B;になります。 スーパーバイザーを定義している場合、スーパーバイザーには自動的にEメールが送信されます。  [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)を参照してください。
