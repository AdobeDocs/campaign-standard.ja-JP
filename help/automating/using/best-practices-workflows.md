---
title: ワークフローのベストプラクティス
description: ワークフローに適用するベストプラクティスを説明します。
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
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# ワークフローのベストプラクティス{#workflow-best-practices}

Adobe Campaignを使用すると、あらゆるタイプのワークフローを設定して、様々なタスクを実行できます。 ただし、ワークフローをデザインして実行する場合は、実装が悪いとパフォーマンス、エラーおよびプラットフォームの問題が発生する可能性があるので、非常に慎重になる必要があります。 ベストプラクティスとトラブルシューティングのヒントを以下に示します。

>[!NOTE]
>
>ワークフローのデザインと実行は、Adobe Campaignの上級ユーザーが実行する必要があります。

## 命名{#naming}

ワークフローのトラブルシューティングを容易にするために、ワークフローに明示的に名前を付け、ラベルを付けることをお勧めします。 ワークフローの説明フィールドに入力し、実行するプロセスを要約して、オペレーターが理解しやすくします。
ワークフローが複数のワークフローを含むプロセスの一部である場合は、ラベルを入力する際に数値を使用して、明確に並べ替えることができます。

次に例を示します。

* 001 – インポート - 受信者のインポート
* 002 – インポート - 売上のインポート
* 003 – インポート - 売上詳細のインポート
* 010 – エクスポート – 配信ログのエクスポート
* 011 – エクスポート – トラッキングログのエクスポート

## ワークフローの複製{#duplicating-workflows}

ワークフローを複製できます。 で、ワークフ **[!UICONTROL Marketing Activities]**ローの上にカーソルを置いてをクリックしま**[!UICONTROL Duplicate element]**&#x200B;す。 複製後は、ワークフローの変更はワークフローのコピーに引き継がれません。 ワークフローのコピーを編集できます。

![](assets/duplicating_workflow.png)

## 実行{#execution}

### ワークフローの数

デフォルトでは、20を超えるアクティブなワークフロー実行を同時に実行しないことをお勧めします。 この制限に達すると、パフォーマンスに影響を与えないようにワークフローがキューに入れられます。 同様に、時間の経過と共にワークフローのエクセクションを拡大することをお勧めします。
特定のコンテキストでは、20を超えるワークフローを実行する必要がある場合があります。 スケジュールされた実行を待機するワークフローには適用されません。  その場合は、キャンペーンのエキスパートと共に使用事例を確認し、アドビカスタマーケアに連絡して制限を引き上げる必要があります。

### 頻度

ワークフローは、10分に1回以上自動的に実行することはできません。
アクティビティの繰り返し頻度を10分未満にすることはできません。 繰り返し頻度を0（またはデフォルト値）に設定した場合、このオプションは考慮されず、ワークフローは実行頻度に従って実行されます。

### 一時停止されたワークフロー

7日間以上一時停止または失敗状態になっていたワークフローは、使用するディスク容量を減らすために停止されます。 クリーニングタスクがワークフローログに表示されます。

### トランジション

未終了の遷移を含むワークフローは、引き続き実行できます。警告メッセージが生成され、ワークフローは移行に達すると一時停止しますが、エラーは生成されません。 完成したデザインを使用せずにワークフローを開始し、進むにつれてワークフローを完了することもできます。

詳しくは、「ワークフローの実行」を参 [照してください](../../automating/using//executing-a-workflow.md)。

### タイムゾーン

ワークフロープロパティを使用すると、すべてのアクティビティでデフォルトで使用される特定のタイムゾーンを定義できます。 デフォルトでは、ワークフローのタイムゾーンは現在のキャンペーン演算子に対して定義されています。


## アクティビティ{#activity}

### ワークフローデザイン

ワークフローが正しく終了するようにするには、を使用しま **[!UICONTROL End activity]**す。 ワークフローの最後の移行をそのままにするのは避けてください。

遷移の詳細ビューにアクセスするには、ワークフロープロパティの「実 **[!UICONTROL Keep interim results]**行」セクションにあるオプションをオンにします。

>[!CAUTION]
>
>このオプションは、多くのディスク領域を消費し、ワークフローを構築し、適切な構成と動作を保証するために設計されています。 実稼働インスタンスでは、このチェックボックスをオフのままにします。

![](assets/keep_interim_best_practices.png)


### ラベル付け活動{#activity-labeling}

ワークフローの開発時に、すべてのAdobe Campaignオブジェクトと同様に、すべてのアクティビティに名前が生成されます。 アクティビティの名前はツールによって生成され、編集することはできませんが、設定時に明示的な名前を付けることをお勧めします。

### アクティビティの複製{#activity-duplicating}

既存のアクティビティを複製するには、コピー&amp;ペーストを使用します。 これにより、元々定義された設定を保持できます。 詳しくは、ワークフローアクティビティの複 [製を参照してくださ](../../automating/using/workflow-interface.md)い。

### スケジューラーアクティビティ{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]**per branch. ワークフローの同じ分岐に、相互にリンクされた複数のスケジューラーがある場合、実行タスクの数が指数関数的に増大するので、データベースに膨大な負荷がかかりかねません。

次に10回実行するワークフローをプレビューするには、をクリックしま **[!UICONTROL Preview next executions]**す。

![](assets/preview_scheduler.png)

詳しくは、「スケジューラーアクティビティ」 [を参照してくださ](../../automating/using/scheduler.md)い。

## パラメーターを使用したワークフローの呼び出し{#workflow-with-parameters}

パラメーターの名前と数が、ワークフローの呼び出し時に定義されたものと同じであることを確認します(ワークフ [ローの呼び出し時のパラメーターの定義](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。 パラメーターの型も、期待される値と一致している必要があります。

内ですべてのパラメーターが宣言されていることを確認しま **[!UICONTROL External signal activity]**す。 それ以外の場合は、アクティビティの実行時にエラーが発生します。

詳しくは、「外部パラメーターを使用し [たワークフローの呼び出し」を参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md)い。

## パッケージのエクスポート{#exporting-packages}

パッケージを書き出す場合、書き出すリソースにデフォルトのIDを含めないでください。 したがって、書き出し可能なリソースのIDは、Adobe Campaign Standardで標準として提供されているテンプレートとは異なる名前を使用して変更する必要があります。
詳しくは、「パッケージの管理」を [参照してくださ](../../automating/using/managing-packages.md)い。

## リストの書き出し{#exporting-lists}

書き出しリストオプションを使用すると、デフォルトで最大100,000行まで書き出すことができ、 **Nms_ExportListLimitオプションで定義できます**。 このオプションは、機能管理者が//で管理 **[!UICONTROL Administration]**でき**[!UICONTROL Application settings]** ます **[!UICONTROL Options]**。
詳しくは、リストの書き出しを参[照してください](../../automating/using/exporting-lists.md)。

## トラブルシューティング{#workflow-troubleshooting}

Adobe Campaignでは、ワークフローの問題をより深く理解するために様々なログを提供しています。

### ワークフローログの使用{#using-workflow-logs}

ワークフローログにアクセスして、アクティビティの実行を監視できます。 実行された操作と実行エラーを時系列順にインデックスします。 「ログ」タブは、選択したすべてのアクティビティまたは一部のアクティビティの実行履歴で構成されます。
「タスク」タブでは、アクティビティの実行順序の詳細が表示されます。 アクティビティの詳細を取得するには、タスクをクリックします。
詳細については、「監視ワークフローの実 [行」を参照してください](../../automating/using/executing-a-workflow.md#monitoring)。

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

SQLクエリは「ログ」タブで分析できます。

1. ワークフローワークスペースで、をクリックしま **[!UICONTROL Edit properties]**す。
1. /で、 **[!UICONTROL General]**とオ**[!UICONTROL Execution]**&#x200B;プションを **[!UICONTROL Save SQL queries in the log]**確認し**[!UICONTROL Execute in the engine]** てをクリックしま **[!UICONTROL Confirm]**す。

**SQLクエリをログに表示するには：**
1. クリック **[!UICONTROL Log and Tasks]**.
1. タブで、 **[!UICONTROL Logs]**パネルを開き**[!UICONTROL Search]** ます。
1. 確認 **[!UICONTROL Display SQL logs only]**.

クエリーがログの列に **[!UICONTROL Message]**表示されます。

### 配信ログの使用{#using-delivery-logs}

配信ログを使用して、配信の成功を監視できます。 除外ログは、送信の準備中に除外されたメッセージを返します。 送信ログは、各プロファイルの配信のステータスを提供します。
詳しくは、「配信エラーにつ [いて](../../sending/using/understanding-delivery-failures.md)」を参照。

### 配信アラートの使用{#delivery-alerting}

配信アラート機能は、ユーザーのグループが配信の実行に関する情報を含む通知を自動的に受け取れるようにするアラート管理システムです。
詳しくは、「配信アラート」を参 [照してください](../../sending/using/receiving-alerts-when-failures-happen.md)。

**関連トピック：**

* [エラー管理](../../automating/using/executing-a-workflow.md#error-management)
