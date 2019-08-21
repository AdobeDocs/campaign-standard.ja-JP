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
source-git-commit: fd44c6e6d0f6a4ca75b01c99fbae6d9072dd7736

---


# ワークフローのベストプラクティス{#workflow-best-practices}

Adobe Campaignでは、タスクの大規模なスコープを実行するためのすべてのタイプのワークフローを設定できます。ただし、ワークフローを設計して実行するときは、不正な実装として細心の注意を払う必要があるので、パフォーマンス、エラー、プラットフォームの問題につながる可能性があります。ベストプラクティスとトラブルシューティングのヒントの一覧を参照できます。

>[!NOTE]
>
>ワークフローデザインと実行は、Adobe Campaignの上級ユーザーが実行する必要があります。

## 命名{#naming}

ワークフローのトラブルシューティングを行うには、ワークフローに名前を付けてラベルを付けることをお勧めします。ワークフローの説明フィールドに入力して、演算子が簡単に理解できるようにプロセスを要約します。
ワークフローが複数のワークフローを含むプロセスの一部である場合は、ラベルを入力して、明確に並べることができます。

次に例を示します。

* 001-インポート-受信者を読み込み
* 002-インポート-販売の読み込み
* 003-インポート-販売の詳細をインポート
* 010-エクスポート-配信ログの書き出し
* 011-エクスポート-トラッキングログの書き出し

## ワークフローの複製{#duplicating-workflows}

ワークフローを複製できます。で **[!UICONTROL Marketing Activities]**、ワークフローの上にマウスポインターを置いて、をクリック **[!UICONTROL Duplicate element]**&#x200B;します。複製が完了すると、ワークフローの変更はワークフローのコピーまで持ち越されません。ワークフローのコピーを編集できます。

![](assets/duplicating_workflow.png)

## 実行{#execution}

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

詳しくは、「ワークフロー [の実行](../../automating/using//executing-a-workflow.md)」を参照してください。

## アクティビティ{#activity}

### ワークフローデザイン

ワークフローが正しく終了するようにするには、を使用 **[!UICONTROL End activity]**&#x200B;してください。ワークフローの最後のトランジションはそのままにしておいてください。

トランジションの詳細ビューにアクセスするには、ワークフローのプロパティの「実行」セクションで **[!UICONTROL Keep interim results]** オプションを確認します。

>[!CAUTION]
>
>このオプションは、多くのディスクスペースを消費し、ワークフローを構築して適切な設定と動作を実現するように設計されています。実稼働インスタンスではオフにします。

![](assets/keep_interim_best_practices.png)


### ワークリングアクティビティ{#activity-labeling}

ワークフローの開発時に、すべてのAdobe Campaignオブジェクトのように、すべてのアクティビティに対して名前が生成されます。アクティビティの名前はツールによって生成され、編集できませんが、設定時に明示的な名前でラベル付けすることをお勧めします。

### アクティビティの複製{#activity-duplicating}

既存のアクティビティを複製するには、コピー&amp;ペーストを使用できます。このようにして、当初定義されていた設定を維持します。詳しくは、ワークフローアクティビティ [の複製](../../automating/using/workflow-interface.md)を参照してください。

### スケジューラーアクティビティ{#acheduler-activity}

ワークフローを作成するときは、ブランチごとに1つ **[!UICONTROL Scheduler activity]** だけ使用します。ワークフローの同じブランチに複数のスケジューラー（相互にリンクされている）がある場合、実行するタスクの数は指数的に乗算され、データベースにかなり負荷がかかります。

クリック **[!UICONTROL Preview next executions]**&#x200B;して、ワークフローの次の10回の実行をプレビューできます。

![](assets/preview_scheduler.png)

詳しくは [、スケジューラーアクティビティ](../../automating/using/scheduler.md)を参照してください。

## パラメーターを使用したワークフローの呼び出し{#workflow-with-parameters}

ワークフローの呼び出し時に定義されているパラメーターと同じ名前と数が使用されていることを確認してください（ワークフローの呼び出し時にパラメーター [の定義を参照](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)してください）。パラメーターのタイプも、期待される値と一致する必要があります。

すべてのパラメーターがで宣言されていることを確認 **[!UICONTROL External signal activity]**&#x200B;してください。そうしないと、アクティビティの実行時にエラーが発生します。

詳しくは、「外部パラメーターを使用したワークフロー [の呼び出し](../../automating/using/calling-a-workflow-with-external-parameters.md)」を参照してください。

## パッケージの書き出し{#exporting-packages}

パッケージをエクスポートするには、エクスポートされたリソースにデフォルトIDを含めることはできません。そのため、エクスポート可能なリソースのIDは、Adobe Campaign Standardの標準として提供されているテンプレートとは異なる名前を使用して変更する必要があります。
詳しくは、パッケージ [の管理](../../automating/using/managing-packages.md)を参照してください。

## リストの書き出し{#exporting-lists}

書き出しリストオプションを使用すると、デフォルトで最大100,000行を書き出し、 **NMS_ ExportlistLimitオプションで定義**&#x200B;できます。このオプションは、&gt;&gt;の下 **[!UICONTROL Administration]** の機能管理者によって管理でき **[!UICONTROL Application settings]****[!UICONTROL Options]**ます。
詳しくは、「リスト [の書き出し](../../automating/using/exporting-lists.md)」を参照してください。

## トラブルシューティング{#workflow-troubleshooting}

Adobe Campaignには、ワークフローの問題をよりよく把握するための様々なログが用意されています。

### ワークフローログの使用{#using-workflow-logs}

ワークフローログにアクセスして、アクティビティの実行を監視できます。このインデックスは、実行時に実行される操作および実行エラーを時系列で表します。「ログ」タブは、選択したすべてのアクティビティの実行の履歴に含まれます。
「タスク」タブでは、アクティビティの実行シーケンスの詳細が表示されます。アクティビティに関する詳細情報を取得するには、タスクをクリックします。
詳しくは [、「監視ワークフローの実行](../../automating/using/executing-a-workflow.md#monitoring)」を参照してください。

#### データ管理アクティビティのトラブルシューティング{#troubleshooting-data-management-activities}

SQLクエリは、「ログ」タブで分析できます。

1. ワークフローワークスペースで、をクリック **[!UICONTROL Edit properties]**&#x200B;します。
1. In **[!UICONTROL General]** &gt; **[!UICONTROL Execution]**， check and **[!UICONTROL Save SQL queries in the log]****[!UICONTROL Execute in the engine]** options and click **[!UICONTROL Confirm]**.

**ログにSQLクエリを表示するには:**
1. **[!UICONTROL Log and Tasks]**&#x200B;をクリックします。
1. **[!UICONTROL Logs]** タブで **[!UICONTROL Search]** パネルを開きます。
1. チェック **[!UICONTROL Display SQL logs only]**&#x200B;してください。

クエリーがログの **[!UICONTROL Message]** 列に表示されます。

### 配信ログの使用{#using-delivery-logs}

配信ログを使用すると、配信の成功を監視できます。除外ログは、送信の準備中に除外されたメッセージを返します。ログを送信すると、各プロファイルの配信ステータスが提供されます。
詳しくは、配信エラー [について](../../sending/using/understanding-delivery-failures.md)を参照してください。

### 配信に関するアラートの使用{#delivery-alerting}

配信の警告機能は、ユーザーグループが配信の実行に関する情報を含む通知を自動的に受信できるアラート管理システムです。
詳しくは [、配信の警告](../../sending/using/receiving-alerts-when-failures-happen.md)を参照してください。

**関連トピック:**

* [エラー管理](../../automating/using/executing-a-workflow.md#error-management)
