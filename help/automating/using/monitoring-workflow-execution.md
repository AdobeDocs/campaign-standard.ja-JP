---
solution: Campaign Standard
product: campaign
title: 監視ワークフローの実行
description: ワークフローの実行を監視する方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 6%

---


# 監視ワークフローの実行 {#monitoring}

## ワークフローログとタスク{#workflow-log-and-tasks}

![](assets/printpreview_darkgrey-24px.png)アイコンをクリックすると、ワークフローログとタスクメニューが開きます。

ワークフローの履歴は、ワークフローの実行オプションで指定された期間（[ワークフローのプロパティ](../../automating/using/managing-execution-options.md)を参照）保存されます。 この間、再起動後も、すべてのメッセージが保存されます。 以前の実行のメッセージを保存したくない場合は、![](assets/delete_darkgrey-24px.png)ボタンをクリックして履歴を削除する必要があります。

**[!UICONTROL Log]**&#x200B;タブには、すべてのアクティビティまたは選択したアクティビティの実行履歴が含まれます。 実行された操作と実行エラーのインデックスを時系列順に作成します。

![](assets/wkf_execution_4.png)

**[!UICONTROL Tasks]**&#x200B;タブは、アクティビティの実行順序の詳細を示します。 タスクをクリックして詳細を表示します。

![](assets/wkf_execution_5.png)

次の2つのリストで、

* カウンターをクリックすると、適用したフィルターに従ったアクティビティの合計数が表示されます。 リスト内の要素数が30未満の場合は、デフォルトでカウンターが表示されます。
* **[!UICONTROL Configure list]**&#x200B;ボタンを使用すると、表示する情報の選択、列の順序の定義、リストの並べ替えを行うことができます。
* フィルターを使用すると、必要な情報をより迅速に見つけることができます。 検索フィールドを使用して、ワークフローアクティビティ名の特定のテキストを検索します(例：「クエリ」)とログを参照してください。

## エラー管理 {#error-management}

エラーが発生すると、ワークフローは一時停止され、エラーが発生したときに実行されていたアクティビティが赤く点滅します。

ワークフローのステータスが赤に変わり、エラーがログに記録されます。

ワークフローを設定して、一時停止を行わず、エラーなく実行を続行できます。 これを行うには、![](assets/edit_darkgrey-24px.png)ボタンを介してワークフローのプロパティに移動し、**[!UICONTROL Execution]**&#x200B;セクションで、**「エラーの場合**」フィールドの&#x200B;**無視**&#x200B;オプションを選択します。

この場合、エラーのあるタスクは中止されます。 このモードは、後で操作を再試行する（定期的な操作）ように設計されたワークフローに特に適しています。

>[!NOTE]
>
>この設定は、各アクティビティに個別に適用できます。これを行うには、アクティビティを選択し、![](assets/edit_darkgrey-24px.png)クイックアクションを使用して開きます。 次に、「**実行オプション**」タブでエラー管理モードを選択します。 「[アクティビティ実行オプション](../../automating/using/activity-properties.md)」を参照してください。

[ワークフローのプロパティ](../../automating/using/managing-execution-options.md)には、エラー管理に関連する追加のオプションが用意されています。

![](assets/wkf_execution_error.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Supervisors]**:ワークフローでエラーが発生した場合に通知するユーザーのグループ（電子メールおよびアプリ内通知）を定義できます。グループが定義されていない場合、誰も通知されません。 Adobe Campaign通知について詳しくは、[Adobe Campaign通知](../../administration/using/sending-internal-notifications.md)を参照してください。

* **[!UICONTROL In case of error]**:アクティビティでエラーが発生した場合に実行するアクションを指定できます。これには、次の2つのオプションがあります。

   * **プロセスの休止**:ワークフローは自動的に中断されます。次に、ワークフローのステータスが&#x200B;**エラー**&#x200B;になり、関連付けられた色が赤に変わります。 問題が解決したら、ワークフローを再起動します。
   * **無視**:アクティビティは実行されず、その結果、（同じブランチ内の）その後に続くアクティビティも実行されません。これは、定期的なタスクに役立つ場合があります。 ブランチのスケジューラーがアップストリームに配置されている場合は、次の実行日にトリガーされます。

* **[!UICONTROL Consecutive errors]** :ワークフローの実行が自動的に中断される前に承認される連続する複数のエラーを定義できます。

   * 指定した数が&#x200B;**[!UICONTROL 0]**&#x200B;の場合、または指定した数に達しない限り、エラーが発生したアクティビティは無視されます。 他のワークフローブランチは、通常どおり実行されます。

   * 指定された数に達すると、ワークフロー全体が中断され、**[!UICONTROL Erroneous]**&#x200B;になります。 スーパーバイザを定義した場合は、電子メールで自動的に通知されます。  [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)を参照してください。
