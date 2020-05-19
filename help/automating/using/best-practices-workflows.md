---
title: ワークフローのベストプラクティス
description: ワークフローに適用するベストプラクティスを学びます。
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 8%

---


# ワークフローのベストプラクティス{#workflow-best-practices}

Adobe Campaignを使用すると、あらゆる種類のワークフローを設定して、広範なタスクを実行できます。 ただし、ワークフローを設計して実行する場合は、導入が不適切な場合にパフォーマンス、エラー、プラットフォームの問題が発生する可能性があるので、十分に注意する必要があります。 ベストプラクティスとトラブルシューティングのヒントのリストを以下に示します。

>[!NOTE]
>
>ワークフローの設計と実行は、Adobe Campaignの上級ユーザーが実行する必要があります。

## 名前の設定{#naming}

ワークフローのトラブルシューティングを容易にするために、ワークフローに明示的な名前を付け、ラベルを付けることをお勧めします。 ワークフローの説明フィールドに入力し、実行するプロセスを要約して、オペレーターが理解しやすくします。
ワークフローが複数のワークフローに関連するプロセスの一部である場合は、ラベルを入力する際に数値を使用して、明確な順序を指定できます。

次に例を示します。

* 001 – インポート - 受信者のインポート
* 002 – インポート - 売上のインポート
* 003 – インポート - 売上詳細のインポート
* 010 – エクスポート – 配信ログのエクスポート
* 011 – エクスポート – トラッキングログのエクスポート

## ワークフローの複製{#duplicating-workflows}

ワークフローは重複できます。 で、ワークフローの上にマウスポインター **[!UICONTROL Marketing Activities]**&#x200B;を置いて、をクリックし **[!UICONTROL Duplicate element]**&#x200B;ます。 複製後は、ワークフローの変更は複製されたワークフローには引き継がれません。ワークフローのコピーを編集できます。

![](assets/duplicating_workflow.png)

## 実行{#execution}

### ワークフロー数

デフォルトでは、20個を超えるアクティブなワークフローの実行を同時に実行しないことをお勧めします。 その限度に達した後、ワークフローはパフォーマンスに影響を与えないようにキューに入れられます。 同様に、時間の経過と共にワークフローの検出を広めることをお勧めします。
特定のコンテキストでは、20ワークフロー以上の実行が必要になる場合があります。 スケジュールされた実行を待機しているワークフローには適用されません。  その場合は、キャンペーンエキスパートとの使用事例を確認し、アドビカスタマーケアに問い合わせて制限を引き上げる必要があります。

### 頻度

ワークフローは、10分に1回以上自動的に実行することはできません。
アクティビティの繰り返し頻度を10分未満にすることはできません。 繰り返し頻度を0（またはデフォルト値）に設定した場合、このオプションは考慮されず、ワークフローは実行頻度に従って実行されます。

### 一時停止されたワークフロー

7日間以上一時停止または失敗状態になっているワークフローは、ディスク容量を少なくするために停止されます。 ワークフローログにクリーニングタスクが表示されます。

### トランジション

終了していないトランジションを含むワークフローは、引き続き実行できます。 警告メッセージが生成され、トランジションに到達するとワークフローは一時停止しますが、エラーは生成されません。 完成したデザインを使用せずにワークフローを開始し、作業中にワークフローを完了することもできます。

詳しくは、「ワークフローの [実行](../../automating/using/about-workflow-execution.md)」を参照してください。

### タイムゾーン

ワークフローのプロパティを使用すると、すべてのアクティビティでデフォルトで使用される特定のタイムゾーンを定義できます。 デフォルトでは、ワークフローのタイムゾーンは、現在のキャンペーン演算子に対して定義されたタイムゾーンです。


## アクティビティ{#activity}

### ワークフローデザイン

ワークフローが正しく終了するようにするには、を使用し **[!UICONTROL End activity]**&#x200B;ます。 ワークフローの最後のトランジションを単独で残さないようにします。

トランジションの詳細表示にアクセスするには、ワークフロープロパティの「実行」セクションで **[!UICONTROL Keep interim results]** オプションを選択します。

>[!CAUTION]
>
>このオプションは、多くのディスク領域を消費し、ワークフローを構築し、適切な構成と動作を確実に行えるように設計されています。 実稼働インスタンスでは、このチェックボックスをオフのままにします。

![](assets/keep_interim_best_practices.png)


### アクティビティのラベル付け{#activity-labeling}

ワークフローの開発時には、すべてのAdobe Campaignオブジェクトと同様、すべてのアクティビティに対して名前が生成されます。 アクティビティの名前はツールによって生成され、編集することはできませんが、設定時に明示的な名前を付けることをお勧めします。

### アクティビティの複製{#activity-duplicating}

既存のアクティビティを重複するには、コピー&amp;ペーストを使用します。 これにより、最初に定義した設定を保持できます。 詳しくは、「ワークフローアクティビティの [複製](../../automating/using/workflow-interface.md)」を参照してください。

### スケジューラーアクティビティ{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. ワークフローの同じ分岐に、相互にリンクされた複数のスケジューラーがある場合、実行タスクの数が指数関数的に増大するので、データベースに膨大な負荷がかかりかねません。

をクリックして、次に10回実行するワークフローをプレビューでき **[!UICONTROL Preview next executions]**&#x200B;ます。

![](assets/preview_scheduler.png)

詳しくは、「 [スケジューラーアクティビティ](../../automating/using/scheduler.md)」を参照してください。

## パラメーターを使用したワークフローの呼び出し{#workflow-with-parameters}

名前とパラメーター数が、ワークフローの呼び出し時に定義された名前と数と一致することを確認します(ワークフローの呼び出し時にパラメーターを [定義するを参照](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。 また、パラメーターの型は、期待される値と一致する必要があります。

内ですべてのパラメーターが宣言されていることを確認し **[!UICONTROL External signal activity]**&#x200B;ます。 それ以外の場合は、アクティビティの実行時にエラーが発生します。

詳しくは、「外部パラメーターを使用したワークフローの [呼び出し](../../automating/using/calling-a-workflow-with-external-parameters.md)」を参照してください。

## パッケージのエクスポート{#exporting-packages}

パッケージを書き出すには、書き出すリソースにデフォルトのIDを含めないでください。 したがって、書き出し可能なリソースのIDは、Adobe Campaign標準で提供されているテンプレートとは異なる名前を使用して変更する必要があります。
詳しくは、「パッケージの [管理](../../automating/using/managing-packages.md)」を参照してください。

## リストの書き出し{#exporting-lists}

書き出しリストオプションを使用すると、デフォルトで100,000行まで書き出すことができ、 **Nms_ExportListLimitオプションで定義できます**。 このオプションは、機能管理者の **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** >で管理でき **[!UICONTROL Options]**ます。
詳しくは、「 [リストの書き出し](../../automating/using/exporting-lists.md)」を参照してください。

## トラブルシューティング{#workflow-troubleshooting}

Adobe Campaignオファー様々なログを使用して、ワークフローの問題をより深く理解できます。

### ワークフローログの使用{#using-workflow-logs}

ワークフローログにアクセスして、アクティビティの実行を監視できます。 実行された操作と実行エラーのインデックスを時系列順に作成します。 「ログ」タブは、選択したすべてのアクティビティまたは一部の実行の履歴で構成されます。
「タスク」タブでは、アクティビティの実行順序の詳細が示されます。 タスクの詳細を表示するには、アクティビティをクリックします。
詳細については、「 [監視ワークフローの実行](../../automating/using/monitoring-workflow-execution.md)」を参照してください。

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

SQLクエリは「ログ」タブで分析できます。

1. ワークフローワークスペースで、をクリックし **[!UICONTROL Edit properties]**&#x200B;ます。
1. / **[!UICONTROL General]** で、との **[!UICONTROL Execution]**&#x200B;オプションをチェックし、をクリックし **[!UICONTROL Save SQL queries in the log]****[!UICONTROL Execute in the engine]****[!UICONTROL Confirm]**&#x200B;ます。

**ログにSQLクエリを表示するには：**
1. クリック **[!UICONTROL Log and Tasks]** .
1. タブで、 **[!UICONTROL Logs]** パネルを開き **[!UICONTROL Search]** ます。
1. 確認 **[!UICONTROL Display SQL logs only]**.

クエリがログの **[!UICONTROL Message]** 列に表示されます。

### 配信ログの使用{#using-delivery-logs}

配信ログを使用して、配信の成功を監視できます。 除外ログは、送信の準備中に除外されたメッセージを返します。 送信ログは、各プロファイルの配信のステータスを提供します。
詳細については、「配信エラーについて [](../../sending/using/understanding-delivery-failures.md)」を参照してください。

### 配信アラートの使用{#delivery-alerting}

配信アラート機能は、アラート管理システムです。この機能を使用すると、配信のグループは、ユーザーの実行に関する情報を含む通知を自動的に受信できます。
詳細については、「 [配信アラート](../../sending/using/receiving-alerts-when-failures-happen.md)」を参照してください。

**関連トピック：**

* [エラー管理](../../automating/using/monitoring-workflow-execution.md)
