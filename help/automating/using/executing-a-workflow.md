---
title: ワークフローの実行
seo-title: ワークフローの実行
description: ワークフローの実行
seo-description: ワークフローを実行および監視する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: ff02b74e-53e8-49c6- bf8e-0c729eaa7d25
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow- general- operation
discoiquuid: 906c85ea-83b7-4268-86da- cd353f1dc591
context-tags: ワークフロー、概要;ワークフロー、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e33cbfbf6376dabfe81b9bd6f7cce817f35d1b75

---


# Executing a workflow{#executing-a-workflow}

## About workflow execution {#about-workflow-execution}

ワークフローは常に手動で開始されます。However, once started, it can remain inactive, depending on the information specified in a [Scheduler](../../automating/using/scheduler.md) activity.

>[!CAUTION]
>
> アドビでは、ワークフローの実行に優先順位を付け、最大20個の同時ワークフロー実行を実行して、インスタンス全体でパフォーマンスを最大限に発揮させることを推奨しています。20以上の同時ワークフロー実行が計画されており、デフォルトでは順次実行されます。カスタマーケアにチケットを送信することで、同時ワークフロー実行の最大数のデフォルト設定を調整できます。

実行関連アクション（開始、停止、一時停止など）are **asynchronous** processes: the command is saved and will become effective once the server is available to apply it.

ワークフローでは、一般に、各アクティビティの結果は、トランジションを介して次のアクティビティに送信され、矢印で表されます。

宛先アクティビティにリンクされていない場合、トランジションは終了しません。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>停止していないトランジションを含むワークフローは実行できます。警告メッセージが生成され、トランジションに到達するとワークフローが一時停止しますが、エラーは生成されません。デザインを完全に終了せずにワークフローを開始することもできます。これにより、作業を進めることができます。

アクティビティが実行されると、トランジションで送信されたレコードの数がその上に表示されます。

![](assets/wkf_transition_count.png)

トランジションを開いて、ワークフローの実行中または実行後に送信されたデータが正しいことを確認できます。データおよびデータ構造を表示できます。

デフォルトでは、ワークフローの最後の移行の詳細のみにアクセスできます。To be able to access the results of the preceding activities, you need to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties, before starting the workflow.

>[!NOTE]
>
>このオプションには大量のメモリが使用されており、ワークフローの構築や、適切な設定と準備ができるように設計されています。実稼働インスタンスではオフにします。

When a transition is open, you can edit its **[!UICONTROL Label]** or link a **[!UICONTROL Segment code]** to it. これを行うには、対応するフィールドを編集し、変更を確認します。

## Controlling a workflow from the REST API {#controlling-a-workflow-from-the-rest-api}

Using the REST API, you can **start**, **pause**, **resume** and **stop** a workflow.

[APIドキュメントのREST呼び出しの詳細と例を確認できます。](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#controlling-a-workflow)

## Life cycle {#life-cycle}

ワークフローのライフサイクルには3つの主要ステップがあり、各ステップがステータスと色にリンクされています。

* **編集** （グレー）

   This is the initial design phase of a workflow (refer to [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). ワークフローはサーバーによってまだ処理されておらず、リスクなしで変更できます。

* **進行中** （青）

   初期設計段階が完了すると、ワークフローを開始し、サーバーによって処理できます。

* **終了（** 緑）

   ワークフローは、進行中のタスクがなく、または演算子がインスタンスを明示的に停止したときに終了します。

開始したワークフローには、次の2つのステータスがあります。

* **警告** （黄色）

   The workflow could not finish or was paused using the ![](assets/pause_darkgrey-24px.png) or ![](assets/check_pause_darkgrey-24px.png) buttons.

* **エラー** （赤）

   ワークフローが実行されたときにエラーが発生しました。ワークフローが停止し、ユーザーがアクションを実行する必要がありました。To find out more about this error, use the ![](assets/printpreview_darkgrey-24px.png) button to access the workflow log (refer to [Monitoring](../../automating/using/executing-a-workflow.md#monitoring)).

マーケティングアクティビティのリストでは、すべてのワークフローとそのステータスを表示できます。For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Execution commands {#execution-commands}

アクションバーのアイコンを使用すると、ワークフローの実行を開始、追跡および変更できます。[アクションバー](../../automating/using/workflow-interface.md#action-bar)を参照してください。

![](assets/wkf_execution_2.png)

使用できるアクションは次のとおりです。

**Start**

![](assets/play_darkgrey-24px.png) ボタンでワークフローの実行が開始され、 **進行中** （青）のステータスが表示されます。ワークフローが一時停止された場合、そのワークフローは再開され、それ以外の場合は開始され、最初のアクティビティがアクティブ化されます。

>[!NOTE]
>
>開始は、非同期プロセスです。リクエストが保存され、ワークフロー実行エンジンによってできるだけ早く処理されます。

**一時停止**

![](assets/pause_darkgrey-24px.png) ボタンは実行を一時停止します。The workflow takes on the **Warning** (yellow) status. 新しいアクティビティは再開されるまでアクティブ化されませんが、処理中の操作は休止されません。

**Stop**

![](assets/stop_darkgrey-24px.png) ボタンによって実行中のワークフローが停止し、 **完了** （緑）のステータスになります。処理中の操作は可能であれば中断され、実行中のインポートまたはSQLクエリーは直ちにキャンセルされます。停止した場所と同じ場所から再開することはできません。

**再開**

![](assets/pauseplay_darkgrey-24px.png) このボタンを使用するには、停止してからワークフローを再起動します。ほとんどの場合、迅速に再起動できます。It can also be useful to automate restarting once stopping takes a certain amount of time, because the ![](assets/play_darkgrey-24px.png) button is only available when the stop is effective.

ワークフロー内の1つまたは複数のアクティビティが選択されている場合、次のような他のアクションが実行できます。

**即時実行**

![](assets/pending_darkgrey-24px.png) ボタンは、可能な限り早く選択されている保留中のアクティビティを開始します。

**通常の実行**

The ![](assets/check_darkgrey-24px.png) button reactivates any paused or deactivated activities.

**実行が停止されました**

The ![](assets/check_pause_darkgrey-24px.png) button pauses the workflow at the selected activity: this task as well as all those that follow it (in the same branch) are not executed.

**実行なし**

![](assets/checkdisable.png) ボタンは選択した任意のアクティビティを非アクティブにします。

>[!NOTE]
>
>クイックアクションを使用すると、特定のアクティビティに関する様々なアクションにアクセスし、アクティビティが選択されているときに表示されます。

## Monitoring {#monitoring}

The ![](assets/printpreview_darkgrey-24px.png) icon opens the workflow log and task menu.

The workflow history is saved for the duration specified in the workflow execution options (refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties)). この間、再起動後もすべてのメッセージが保存されます。If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.

**[!UICONTROL Log]** タブには、すべてのアクティビティまたは選択したアクティビティの実行履歴が含まれます。このインデックスは、実行時に実行される操作および実行エラーを時系列で表します。

![](assets/wkf_execution_4.png)

The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. タスクをクリックして詳細情報を取得します。

![](assets/wkf_execution_5.png)

次の2つのリストにあります。

* カウンターをクリックすると、適用されたフィルターに従ってアクティビティの総数が表示されます。リスト内の要素数が30未満の場合、カウンターはデフォルトで表示されます。
* **[!UICONTROL Configure list]** このボタンでは、表示される情報の選択、列の順番の定義、リストの並べ替えを行うことができます。
* フィルターを使用すると、必要な情報を見つけることができます。検索フィールドを使用して、ワークフローアクティビティ名の特定のテキストを検索します（例:"query"）とログ。

## Error management {#error-management}

エラーが発生すると、ワークフローが一時停止され、エラーが発生したときに実行されたアクティビティが実行されます。

ワークフローのステータスが赤くなり、エラーがログに記録されます。

このワークフローを設定して、エラーなく一時停止して実行を続行することができます。To do this, go to the workflow properties via the ![](assets/edit_darkgrey-24px.png) button and, in the **[!UICONTROL Execution]** section, select the **Ignore** option in the **In case of error** field.

この場合、誤ったタスクが中止されます。このモードは、後で操作を再試行するよう設計されたワークフローに特に適しています（定期的なアクション）。

>[!NOTE]
>
>この設定は、アクティビティごとに個別に適用できます。To do this, select an activity and open it using the quick action ![](assets/edit_darkgrey-24px.png). Then select the error management mode in the **Execution options** tab. [アクティビティの実行オプション](../../automating/using/executing-a-workflow.md#activity-execution-options)を参照してください。

The **[!UICONTROL Execution]** section of the workflow properties also allows you to define a number of **[!UICONTROL Consecutive errors]** that are authorized before the workflow execution is automatically suspended. この数値に達しない限り、誤った要素は無視され、他のワークフローのブランチは通常どおり実行されます。この数に達すると、ワークフローが停止し、ワークフローのスーパーバイザーに自動的に通知が送信されます（電子メールおよびアプリ内通知）。[ワークフロープロパティ](../../automating/using/executing-a-workflow.md#workflow-properties) および [Adobe Campaign通知](../../administration/using/sending-internal-notifications.md)を参照してください。

スーパーバイザーは、ワークフローの実行プロパティで定義することもできます。

## Workflow properties {#workflow-properties}

To modify a workflow's execution options, use the ![](assets/edit_darkgrey-24px.png) button to access the workflow properties and select the **[!UICONTROL Execution]** section.

**[!UICONTROL Default affinity]** このフィールドを使用すると、特定のマシン上でワークフローまたはワークフローアクティビティを強制的に実行できます。

**[!UICONTROL History in days]** フィールド内で、履歴を削除する必要がある時間を指定します。

You can choose to check the **[!UICONTROL Save SQL queries in the log]** and **[!UICONTROL Execute in the engine (do not use in production)]** options if necessary.

Check the **[!UICONTROL Keep interim results]** option if you would like to be able to view the detail of transitions. 警告:このオプションを選択すると、ワークフローの実行が大幅に遅くなる可能性があります。

**[!UICONTROL Severity]** このフィールドでは、Adobe Campaignインスタンスでワークフローを実行するための優先順位を指定できます。重要なワークフローが最初に実行されます。

The **[!UICONTROL Supervisors]** field is where you can define the group of people to notify (email and in-app notification) if the workflow encounters an error. グループが定義されていない場合、誰も通知されません。For more on Adobe Campaign notifications, refer to [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

**[!UICONTROL In case of error]** このフィールドでは、アクティビティでエラーが発生した場合に実行するアクションを指定できます。これには、次の2つのオプションがあります。

* **プロセス**&#x200B;の休止:ワークフローが自動的に停止されます。The workflow status is then **Erroneous** and the color associated turns red. 問題が解決したら、ワークフローを再起動します。
* **無視**:アクティビティは実行されず、その結果として（同じブランチ内の）アクティビティのいずれも実行されません。これは、繰り返し実行する場合に便利です。ブランチがアップストリームを配置している場合、これは次の実行日でトリガーする必要があります。

   By selecting this option, you can also define a number of **[!UICONTROL Consecutive errors]** that are authorized:

   * If the number specified is **[!UICONTROL 0]**, or as long as the number specified is not reached, activities that encounter errors are ignored. 他のワークフローのブランチは通常どおり実行されます。
   * If the number specified is reached, the whole of the workflow is suspended and becomes **[!UICONTROL Erroneous]**. スーパーバイザーが定義されている場合、ユーザーは電子メールで自動的に通知されます。

![](assets/wkf_execution_6.png)

## Activity properties {#activity-properties}

### General properties of an activity {#general-properties-of-an-activity}

Each activity has a **[!UICONTROL Properties]** tab. このタブでは、アクティビティの一般的なパラメーター、特にラベルとIDを変更できます。このタブの設定はオプションです。

### Managing an activity's outbound transitions {#managing-an-activity-s-outbound-transitions}

デフォルトでは、一部のアクティビティにはアウトバウンドトランジションがありません。**[!UICONTROL Transitions]** タブまたはアクティビティ **[!UICONTROL Properties]** のタブから1つを追加して、同じワークフローの訪問者に他のプロセスを適用できます。

アクティビティによっては、次のタイプのアウトバウンドトランジションを追加できます。

* 標準トランジション:アクティビティによって計算される母集団
* 母集団のないトランジション:このタイプのアウトバウンドトランジションを追加してワークフローを続行し、システム上の不要なスペースを使用しない母集団を含まないようにすることができます。
* 拒否:訪問者が拒否されました。例えば、アクティビティの受信データが不正解または不完全だったため処理できないとします。
* 補数:訪問者がアクティビティの実行後に残ります。例えば、セグメンテーションアクティビティが、受信母集団の割合のみを保存するように設定されている場合などです。

If applicable, specify a **[!UICONTROL Segment code]** for the activity's outbound transition. このセグメントコードを使用すると、ターゲット母集団からのサブセットの位置を特定し、後でメッセージパーソナライゼーションの目的で提供することができます。

### Activity execution options {#activity-execution-options}

In the activity's properties screen, there is an **[!UICONTROL Advanced options]** tab that lets you define the activity's execution mode and behavior in case of errors.

To access these options, select an activity in a workflow, then open it using the ![](assets/edit_darkgrey-24px.png) button from the action bar.

![](assets/wkf_advanced_parameters.png)

**[!UICONTROL Execution]** このフィールドでは、タスクの開始時に実行するアクションを定義できます。これには次の3つのオプションがあります。

* **標準**:アクティビティは通常どおり実行されます。
* **Enable but do not execute**:アクティビティが一時停止され、その結果として後続のプロセスが実行されます。これは、タスクを開始したときに表示される場合に便利です。
* **有効**&#x200B;にしない:アクティビティは実行されず、結果として、（同じブランチ内の）すべてのアクティビティが実行されません。

**[!UICONTROL In case of error]** このフィールドでは、アクティビティでエラーが発生した場合に実行するアクションを指定できます。これには、次の2つのオプションがあります。

* **プロセス**&#x200B;の休止:ワークフローが自動的に停止されます。The workflow status is then **Erroneous** and the color associated turns red. 問題が解決したら、ワークフローを再起動します。
* **無視**:アクティビティは実行されず、その結果として（同じブランチ内の）アクティビティのいずれも実行されません。これは、繰り返し実行する場合に便利です。ブランチがアップストリームを配置している場合、これは次の実行日でトリガーする必要があります。

**[!UICONTROL Behavior]** このフィールドでは、非同期タスクを使用する場合に従う手順を定義できます。これには、次の2つのオプションがあります。

* **認証され**&#x200B;た複数のタスク:複数のタスクは、最初のタスクが完了していない場合でも同時に実行できます。
* **現在のタスクは優先**&#x200B;されます。タスクが進行中の場合は、優先されます。タスクがまだ進行中である限り、他のタスクは実行されません。

**[!UICONTROL Max. execution duration]** このフィールドでは、"30s"や"1h"などの期間を指定できます。指定された期間の経過後にアクティビティが終了しない場合は、アラートがトリガーされます。これは、ワークフローの機能には影響しません。

**[!UICONTROL Affinity]** このフィールドを使用すると、特定のマシン上でワークフローまたはワークフローアクティビティを強制的に実行できます。これを行うには、該当するワークフローまたはアクティビティに対して1つまたは複数の親和性を指定する必要があります。

**[!UICONTROL Time zone]** このフィールドでは、アクティビティのタイムゾーンを選択できます。Adobe Campaignでは、同じインスタンス上の複数の国の時間差を管理できます。適用された設定は、インスタンスの作成時に設定されます。

**「コメント」** フィールドは、メモを追加するための無料フィールドです。
