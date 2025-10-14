---
title: 実行オプションの管理
description: ワークフロー実行オプションを管理する方法を説明します。
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
source-wordcount: '525'
ht-degree: 8%

---

# 実行オプションの管理 {#managing-execution-options}

ワークフローの実行オプションを変更するには、「![](assets/edit_darkgrey-24px.png)」ボタンを使用してワークフローのプロパティにアクセスし、「**[!UICONTROL Execution]**」セクションを選択します。

![](assets/wkf_execution_6.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Default affinity]**：このフィールドを使用すると、特定のマシン上でワークフローまたはワークフローアクティビティを強制的に実行できます。

* **[!UICONTROL History in days]**：履歴をパージする必要があるまでの日数を指定します。 履歴には、ログ、タスク、イベント（ワークフロー操作にリンクされた技術的なオブジェクト）、**[!UICONTROL Transfer file]** アクティビティによってダウンロードされたファイルなど、ワークフローに関連する要素が含まれます。 標準のワークフローテンプレートのデフォルト値は 30 日です。

  履歴のパージは、デフォルトで毎日実行されるデータベースクリーンアップテクニカルワークフローによって実行されます（[&#x200B; テクニカルワークフローのリスト &#x200B;](../../administration/using/technical-workflows.md) を参照）。

  >[!IMPORTANT]
  >
  >**[!UICONTROL History in days]** フィールドが空白のままの場合、その値は「1」と見なされます。つまり、履歴は 1 日後にパージされます。

* **[!UICONTROL Save SQL queries in the log]**：ワークフローからの SQL クエリをログに保存できます。

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**：実行計画全体をログに記録する場合は、このオプションをオンにします。 この機能は、デフォルトでは無効になっています。

  このオプションについて詳しくは、この [&#x200B; 節 &#x200B;](#diagnostic-mode) を参照してください。

* **[!UICONTROL Keep interim results]**：トランジションの詳細を表示する場合は、このオプションをオンにします。

  >[!CAUTION]
  >
  >このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。

* **[!UICONTROL Execute in the engine (do not use in production)]**：開発環境のテストを目的として、ワークフローをローカルで実行できます。

* **[!UICONTROL Severity]**:Adobe Campaign インスタンスでワークフローを実行するための優先度レベルを指定できます。 このフィールドは、Adobeチームがモニタリング目的でのみ使用します。

**[!UICONTROL Error management]** の節では、エラーが発生した場合のワークフローの動作を管理できる追加のオプションを提供します。 これらのオプションについて詳しくは、[&#x200B; エラー管理 &#x200B;](../../automating/using/monitoring-workflow-execution.md#error-management) の節を参照してください。

## 診断モード {#diagnostic-mode}

>[!CAUTION]
>
>このオプションは、ワークフローのパフォーマンスに大きな影響を与える可能性があるので、慎重に使用してください。

有効にすると、クエリに 1 分以上かかる場合に、ワークフロープロパティの **[!UICONTROL Execution]** セクションにある「**[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**」オプションが実行プラン全体をログに記録します。

![](assets/wkf_diagnostic.png)

このオプションを有効にしてワークフローを起動した後、クエリの処理に 1 分以上かかる場合は、実行プランがログに記録されます。 その後、EXPLAIN ANALYZE を使用して実行プランを取得できます。

詳しくは、[PostgreSQL のドキュメント &#x200B;](https://www.postgresql.org/docs/9.4/using-explain.html) を参照してください。

このクエリにシーケンススキャンがある場合、**[!UICONTROL Diagnostic mode]** は、フィルター式を使用してインデックスを作成するための推奨事項も提供します。

>[!NOTE]
>
> これらの推奨事項は参照目的でのみ使用されており、使用例に応じて慎重に使用する必要があります。

![](assets/wkf_diagnostic_4.png)

レコメンデーションをトリガーするには、ワークフローの実行中に次の 2 つの条件を満たす必要があります。

* シーケンススキャンは、クエリの 40% 以上の時間がかかります。

* シーケンススキャン後の結果の行が、テーブルに存在する行の合計の 1% 未満である。

詳細メニューで **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** を選択して、オプションを管理できます。

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**: 「**[!UICONTROL Value]**」フィールドから、クエリ実行の新しい時間を設定できます。 クエリの実行がこの値を超えると、実行プランがログに記録されます。

  ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**: 「**[!UICONTROL Value]**」フィールドでは、シーケンス・スキャンで生成されるレコメンデーションに要する問合せ時間の割合を変更できます。

  ![](assets/wkf_diagnostic_3.png)
