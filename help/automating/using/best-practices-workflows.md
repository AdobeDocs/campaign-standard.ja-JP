---
title: ワークフローのベストプラクティス
seo-title: ワークフローのベストプラクティス
description: ワークフローのベストプラクティス
seo-description: ワークフローに適用するベストプラクティスについて説明します。
page-status-flag: 常にアクティブ化されていない
uuid: ff02b74e-53e8-49c6- bf8e-0c729eaa7d25
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow- general- operation
context-tags: ワークフロー、概要;ワークフロー、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e02ca92032c298fe1b5dbc7094de201d0a106be5

---


# Workflow best practices{#workflow-best-practices}

Adobe Campaignでは、タスクの大規模なスコープを実行するためのすべてのタイプのワークフローを設定できます。ただし、ワークフローを設計して実行するときは、不正な実装として細心の注意を払う必要があるので、パフォーマンス、エラー、プラットフォームの問題につながる可能性があります。ベストプラクティスとトラブルシューティングのヒントの一覧を参照できます。

>[!NOTE]
>
>ワークフローデザインと実行は、Adobe Campaignの上級ユーザーが実行する必要があります。

## Naming{#naming}

ワークフローのトラブルシューティングを行うには、ワークフローに名前を付けてラベルを付けることをお勧めします。ワークフローの説明フィールドに入力して、演算子が簡単に理解できるようにプロセスを要約します。
ワークフローが複数のワークフローを含むプロセスの一部である場合は、ラベルを入力して、明確に並べることができます。

次に例を示します。

* 001-インポート-受信者を読み込み
* 002-インポート-販売の読み込み
* 003-インポート-販売の詳細をインポート
* 010-エクスポート-配信ログの書き出し
* 011-エクスポート-トラッキングログの書き出し

## Duplicating workflows{#duplicating-workflows}

ワークフローを複製できます。In the **[!UICONTROL Marketing Activities]**, hover over the workflow and click **[!UICONTROL Duplicate element]**. 複製が完了すると、ワークフローの変更はワークフローのコピーまで持ち越されません。ワークフローのコピーを編集できます。

![](assets/duplicating_workflow.png)

## Execution{#execution}

### ワークフロー数

デフォルトでは、アクティブなワークフロー実行を同時に実行しないことをお勧めします。その制限をヒットすると、ワークフローはパフォーマンスに影響を与えないようにキューに入れられます。同様に、時間の経過とともにワークフローのエクスションを広げることをお勧めします。
特定の状況では、20以上のワークフローを実行する必要があります。スケジュールされた実行を待機するワークフローには適用されません。その場合は、キャンペーンエキスパートによる使用事例を確認し、アドビカスタマーケアに連絡して制限を増やす必要があります。

### 頻度

ワークフローは、10分ごとに自動的に実行することはできません。
アクティビティの繰り返し頻度は10分以内にする必要があります。繰り返し頻度が0（デフォルト値）に設定されている場合、このオプションは考慮されず、ワークフローは実行頻度に従って実行されます。

### 一時停止したワークフロー

7日以上の状態で一時停止または失敗したワークフローは、ディスク容量を節約するために停止します。クリーニングタスクがワークフローログに表示されます。

### トランジション

停止していないトランジションを含むワークフローは実行できます。これにより、警告メッセージが生成され、ワークフローが一時停止しますが、トランジションに到達すると、エラーが発生しません。また、デザインを完了せずにワークフローを開始し、進めることもできます。

For more information, refer to [Executing workflows](../../automating/using//executing-a-workflow.md).

## Activity{#activity}

### ワークフローデザイン

To ensure that the workflow ends properly, use an **[!UICONTROL End activity]**. ワークフローの最後のトランジションはそのままにしておいてください。

To access the detail view of the transitions, check the **[!UICONTROL Keep interim results]** option in the Execution section of the workflow properties.

>[!CAUTION]
>
>このオプションは、多くのディスクスペースを消費し、ワークフローを構築して適切な設定と動作を実現するように設計されています。実稼働インスタンスではオフにします。

![](assets/keep_interim_best_practices.png)


### Labelling activities{#activity-labeling}

ワークフローの開発時に、すべてのAdobe Campaignオブジェクトのように、すべてのアクティビティに対して名前が生成されます。アクティビティの名前はツールによって生成され、編集できませんが、設定時に明示的な名前でラベル付けすることをお勧めします。

### Duplicating activities{#activity-duplicating}

既存のアクティビティを複製するには、コピー&amp;ペーストを使用できます。このようにして、当初定義されていた設定を維持します。For more information, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md).

### Scheduler activity{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. ワークフローの同じブランチに複数のスケジューラー（相互にリンクされている）がある場合、実行するタスクの数は指数的に乗算され、データベースにかなり負荷がかかります。

You can preview the next ten executions of your workflows by clicking **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

For more information, refer to [Scheduler activity](../../automating/using/scheduler.md).

## Calling workflow with parameters{#workflow-with-parameters}

Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). パラメーターのタイプも、期待される値と一致する必要があります。

Make sure that all the parameters have been declared in the **[!UICONTROL External signal activity]**. そうしないと、アクティビティの実行時にエラーが発生します。

For more information, see [Calling a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exporting packages{#exporting-packages}

パッケージをエクスポートするには、エクスポートされたリソースにデフォルトIDを含めることはできません。そのため、エクスポート可能なリソースのIDは、Adobe Campaign Standardの標準として提供されているテンプレートとは異なる名前を使用して変更する必要があります。
For more information, see [Managing packages](../../automating/using/managing-packages.md).

## Exporting lists{#exporting-lists}

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit option**. This option can be managed by the functional administrator, under **Administration** &gt; **Application settings** &gt; **Options**.
For more information, see [Exporting lists](../../automating/using/exporting-lists.md).

## Troubleshooting{#workflow-troubleshooting}

Adobe Campaignには、ワークフローの問題をよりよく把握するための様々なログが用意されています。

### Using workflow logs{#using-workflow-logs}

ワークフローログにアクセスして、アクティビティの実行を監視できます。このインデックスは、実行時に実行される操作および実行エラーを時系列で表します。
For more information, refer to [Monitoring workflow execution](../../automating/using/executing-a-workflow.md#monitoring).

### Using delivery logs{#using-delivery-logs}

配信ログを使用すると、配信の成功を監視できます。除外ログは、送信の準備中に除外されたメッセージを返します。ログを送信すると、各プロファイルの配信ステータスが提供されます。
For more information, refer to [Understanding delivery failures](../../sending/using/understanding-delivery-failures.md).

### Using delivery alerting{#delivery-alerting}

配信の警告機能は、ユーザーグループが配信の実行に関する情報を含む通知を自動的に受信できるアラート管理システムです。
For more information, refer to [Delivery alerting](../../sending/using/receiving-alerts-when-failures-happen.md).
