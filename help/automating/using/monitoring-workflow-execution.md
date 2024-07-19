---
title: ワークフローの実行の監視
description: ワークフローの実行を監視する方法について説明します。
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
source-wordcount: '578'
ht-degree: 8%

---

# ワークフローの実行の監視 {#monitoring}

## ワークフローログとタスク {#workflow-log-and-tasks}

![](assets/printpreview_darkgrey-24px.png) アイコンをクリックすると、ワークフローログとタスク メニューが開きます。

ワークフローの履歴は、ワークフローの実行オプションで指定された期間保存されます（[ ワークフローのプロパティ ](../../automating/using/managing-execution-options.md) を参照）。 この期間中は、再起動後も、すべてのメッセージが保存されます。 以前の実行したメッセージを保存しない場合は、「![](assets/delete_darkgrey-24px.png)」ボタンをクリックして履歴をパージする必要があります。

「**[!UICONTROL Log]**」タブには、すべてのアクティビティまたは選択したアクティビティの実行履歴が表示されます。 実行された操作と実行エラーのインデックスを時系列順に作成します。

![](assets/wkf_execution_4.png)

「**[!UICONTROL Tasks]**」タブでは、アクティビティの実行順序の詳細が表示されます。 詳細情報を取得するには、タスクをクリックします。

![](assets/wkf_execution_5.png)

次の 2 つのリストで、

* カウンターをクリックすると、適用されたフィルターに従ったアクティビティの合計数が表示されます。 リスト内の要素数が 30 未満の場合、カウンターはデフォルトで表示されます。
* 「**[!UICONTROL Configure list]**」ボタンを使用すると、表示する情報の選択、列の順序の定義、リストの並べ替えを行うことができます。
* フィルターを使用すると、必要な情報をすばやく見つけることができます。 検索フィールドを使用して、ワークフローアクティビティ名（「クエリ」など）とログで特定のテキストを検索します。

## エラー管理 {#error-management}

エラーが発生すると、ワークフローが一時停止し、エラー発生時に実行中だったアクティビティが赤く点滅します。

ワークフローのステータスが赤に変わり、エラーがログに記録されます。

ワークフローを設定して、一時停止せず、エラーなしで実行を続行できます。 これを行うには、「![](assets/edit_darkgrey-24px.png)」ボタンからワークフローのプロパティに移動し、「**[!UICONTROL Execution]**」セクションの「**エラーの場合**」フィールドで **無視**」オプションを選択します。

この場合、誤ったタスクは中止されます。 このモードは、後で操作を再試行（定期的なアクション）するように設計されたワークフローに特に適しています。

>[!NOTE]
>
>この設定は、各アクティビティに個別に適用できます。これをおこなうには、アクティビティを選択し、クイックアクション ![](assets/edit_darkgrey-24px.png) ールを使用して開きます。 次に、「**実行オプション** タブでエラー管理モードを選択します。 [ アクティビティ実行オプション ](../../automating/using/activity-properties.md) を参照してください。

[ ワークフローのプロパティ ](../../automating/using/managing-execution-options.md) では、エラー管理に関連する追加のオプションを使用できます。

![](assets/wkf_execution_error.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Supervisors]**：ワークフローでエラーが発生した場合に通知（メールおよびアプリ内通知）するユーザーのグループを定義できます。 グループが定義されていない場合は、誰にも通知されません。 Adobe Campaign 通知について詳しくは、[Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)を参照してください。

* **[!UICONTROL In case of error]**：アクティビティでエラーが発生した場合に実行するアクションを指定できます。 これには、次の 2 つのオプションを使用できます。

   * **プロセスを中断**：ワークフローは自動的に中断されます。 ワークフローのステータスが **エラー** になり、関連付けられたカラーが赤に変わります。 問題が解決したら、ワークフローを再開します。
   * **無視**：アクティビティは実行されないので、その結果、後続（同じブランチ内）のアクティビティも実行されません。 これは、繰り返しタスクに役立つ場合があります。 ブランチのスケジューラーがアップストリームに配置されている場合、次の実行日にトリガーする必要があります。

* **[!UICONTROL Consecutive errors]**：ワークフローの実行が自動的に一時停止されるまで許可される連続エラー数を定義できます。

   * 指定した数が **[!UICONTROL 0]** の場合、または指定した数に達しない限り、エラーが発生したアクティビティは無視されます。 その他のワークフローブランチは通常どおりに実行されます。

   * 指定された数に達すると、ワークフロー全体が一時停止し、**[!UICONTROL Erroneous]** になります。 スーパーバイザーが定義されている場合は、メールで自動的に通知されます。  [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)を参照してください。
