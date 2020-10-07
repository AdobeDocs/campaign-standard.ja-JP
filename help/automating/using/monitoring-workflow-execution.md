---
title: 監視ワークフローの実行
description: ワークフローの実行を監視する方法を説明します。
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
source-wordcount: '577'
ht-degree: 5%

---


# 監視ワークフローの実行 {#monitoring}

## ワークフローログとタスク {#workflow-log-and-tasks}

ワークフローログとタスクメニューが ![](assets/printpreview_darkgrey-24px.png) 開きます。

ワークフローの履歴は、ワークフローの実行オプションで指定された期間、保存されます( [ワークフローのプロパティを参照](../../automating/using/managing-execution-options.md))。 この間、再起動後も、すべてのメッセージが保存されます。 以前の実行のメッセージを保存したくない場合は、ボタンをクリックして履歴を削除する必要があり ![](assets/delete_darkgrey-24px.png) ます。

この **[!UICONTROL Log]** タブには、すべてのアクティビティまたは選択したアクティビティの実行履歴が含まれます。 実行された操作と実行エラーのインデックスを時系列順に作成します。

![](assets/wkf_execution_4.png)

The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. タスクをクリックして詳細を表示します。

![](assets/wkf_execution_5.png)

次の2つのリストで、

* カウンターをクリックすると、適用したフィルターに従ったアクティビティの合計数が表示されます。 リスト内の要素数が30未満の場合は、デフォルトでカウンターが表示されます。
* この **[!UICONTROL Configure list]** ボタンを使用すると、表示する情報の選択、列の順序の定義、リストの並べ替えを行うことができます。
* フィルターを使用すると、必要な情報をより迅速に見つけることができます。 検索フィールドを使用して、ワークフローアクティビティ名の特定のテキストを検索します(例：「クエリ」)とログを参照してください。

## エラー管理 {#error-management}

エラーが発生すると、ワークフローは一時停止され、エラーが発生したときに実行されていたアクティビティが赤く点滅します。

ワークフローのステータスが赤に変わり、エラーがログに記録されます。

ワークフローを設定して、一時停止を行わず、エラーなく実行を続行できます。 これを行うには、 ![](assets/edit_darkgrey-24px.png) ボタンからワークフローのプロパティに移動し、「エラーの場合 **[!UICONTROL Execution]** 」フィールドの「 **無視** 」オプションを **** 選択します。

この場合、エラーのあるタスクは中止されます。 このモードは、後で操作を再試行する（定期的な操作）ように設計されたワークフローに特に適しています。

>[!NOTE]
>
>この設定は、各アクティビティに個別に適用できます。これを行うには、アクティビティを選択し、クイックアクションを使用して開き ![](assets/edit_darkgrey-24px.png)ます。 次に、「 **実行オプション** 」タブでエラー管理モードを選択します。 「 [アクティビティ実行オプション](../../automating/using/activity-properties.md)」を参照してください。

ワークフ [ローのプロパティに](../../automating/using/managing-execution-options.md)、エラー管理に関連する追加のオプションが使用できます。

![](assets/wkf_execution_error.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Supervisors]**:ワークフローでエラーが発生した場合に通知するユーザーのグループ（電子メールおよびアプリ内通知）を定義できます。 グループが定義されていない場合、誰も通知されません。 Adobe Campaign通知について詳しくは、 [Adobe Campaign通知を参照してください](../../administration/using/sending-internal-notifications.md)。

* **[!UICONTROL In case of error]**:アクティビティでエラーが発生した場合に実行するアクションを指定できます。 これには、次の2つのオプションがあります。

   * **プロセスの休止**:ワークフローは自動的に中断されます。 次に、ワークフローのステータスが「 **エラー** 」になり、関連付けられた色が赤に変わります。 問題が解決したら、ワークフローを再起動します。
   * **無視**:アクティビティは実行されず、その結果、（同じブランチ内の）その後に続くアクティビティも実行されません。 これは、定期的なタスクに役立つ場合があります。 ブランチのスケジューラーがアップストリームに配置されている場合は、次の実行日にトリガーされます。

* **[!UICONTROL Consecutive errors]** :ワークフローの実行が自動的に中断される前に承認される連続する複数のエラーを定義できます。

   * 指定した数値がである場合 **[!UICONTROL 0]**、または指定した数値に達しない限り、エラーが発生したアクティビティは無視されます。 他のワークフローブランチは、通常どおり実行されます。

   * 指定した数に達すると、ワークフロー全体が中断され、ワークフロー全体になり **[!UICONTROL Erroneous]**&#x200B;ます。 スーパーバイザを定義した場合は、電子メールで自動的に通知されます。  [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)を参照してください。
