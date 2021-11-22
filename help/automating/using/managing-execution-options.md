---
title: 実行オプションの管理
description: ワークフロー実行オプションを管理する方法について説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 7%

---

# 実行オプションの管理 {#managing-execution-options}

ワークフローの実行オプションを変更するには、 ![](assets/edit_darkgrey-24px.png) ボタンをクリックしてワークフローのプロパティにアクセスし、 **[!UICONTROL Execution]** 」セクションに入力します。

![](assets/wkf_execution_6.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Default affinity]**:このフィールドを使用すると、特定のマシン上でワークフローまたはワークフローアクティビティを強制的に実行できます。

* **[!UICONTROL History in days]**:履歴をパージする日数を指定します。 履歴には、ワークフローに関連する要素が含まれます。ログ、タスク、イベント（ワークフロー操作にリンクされた技術オブジェクト）、および **[!UICONTROL Transfer file]** アクティビティ。 標準のワークフローテンプレートのデフォルト値は 30 日です。

   履歴のパージは、データベースクリーンアップテクニカルワークフローによって実行され、デフォルトで毎日実行されます ( [テクニカルワークフローのリスト](../../administration/using/technical-workflows.md).)

   >[!IMPORTANT]
   >
   >この **[!UICONTROL History in days]** フィールドが空白の場合、その値は「1」と見なされます。つまり、履歴は 1 日後にパージされます。

* **[!UICONTROL Save SQL queries in the log]**:ワークフローの SQL クエリをログに保存できます。

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**:実行プラン全体をログに記録する場合は、このオプションを選択します。 デフォルトでは無効になっています。

   このオプションについて詳しくは、 [セクション](#diagnostic-mode).

* **[!UICONTROL Keep interim results]**:切り替えの詳細を表示するには、このオプションをオンにします。

   >[!CAUTION]
   >
   >このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。

* **[!UICONTROL Execute in the engine (do not use in production)]**:では、開発環境のテスト用に、ワークフローをローカルで実行できます。

* **[!UICONTROL Severity]**:Adobe Campaignインスタンスでワークフローを実行する際の優先順位を指定できます。 このフィールドは、監視の目的でのみAdobeチームが使用します。

この **[!UICONTROL Error management]** 「 」セクションには、エラー発生時のワークフローの動作を管理するための追加のオプションが用意されています。 これらのオプションについて詳しくは、 [エラー管理](../../automating/using/monitoring-workflow-execution.md#error-management) 」セクションに入力します。

## 診断モード {#diagnostic-mode}

>[!CAUTION]
>
>このオプションは、ワークフローのパフォーマンスに大きく影響を与える可能性があるので、慎重に使用してください。

有効にすると、 **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]** オプション **[!UICONTROL Execution]** クエリに 1 分以上かかる場合、ワークフロープロパティの「 」セクションには実行プラン全体が記録されます。

![](assets/wkf_diagnostic.png)

このオプションを有効にしてワークフローを起動した後、クエリに 1 分以上かかる場合、実行計画が記録されます。 その後、EXPLAIN ANALYZE を使用して実行計画を取得できます。

詳しくは、 [PostgreSQL のドキュメント](https://www.postgresql.org/docs/9.4/using-explain.html).

このクエリにシーケンススキャンがある場合、 **[!UICONTROL Diagnostic mode]** また、は、フィルター式を使用してインデックスを作成するための推奨事項も提供します。

>[!NOTE]
>
> これらの推奨事項は参照用にのみ用意されており、使用事例に応じて慎重に使用する必要があります。

![](assets/wkf_diagnostic_4.png)

ワークフローの実行中に、次の 2 つの条件を満たす必要があります。トリガーレコメンデーション：

* シーケンススキャンでは、クエリの 40%以上の時間がかかります。

* シーケンススキャン後の結果行は、テーブルに存在する合計行の 1 %未満です。

詳細設定メニューで、「 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**:

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**:次の **[!UICONTROL Value]** 」フィールドに値を入力すると、クエリの実行に新しい時刻を設定できます。 クエリの実行がこの値を超えると、実行プランが記録されます。

   ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**:次の **[!UICONTROL Value]** 「 」フィールドで、レコメンデーションを生成するためにシーケンススキャンで実行する必要があるクエリ時間の割合を変更できます。

   ![](assets/wkf_diagnostic_3.png)
