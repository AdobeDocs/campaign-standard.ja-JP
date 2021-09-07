---
solution: Campaign Standard
product: campaign
title: 実行オプションの管理
description: ワークフロー実行オプションの管理方法について説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: 8092eda6241e83a9bb4c23d8955cd12b6509432a
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 7%

---

# 実行オプションの管理 {#managing-execution-options}

ワークフローの実行オプションを変更するには、![](assets/edit_darkgrey-24px.png)ボタンを使用してワークフローのプロパティにアクセスし、「**[!UICONTROL Execution]**」セクションを選択します。

![](assets/wkf_execution_6.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Default affinity]**:このフィールドを使用すると、特定のマシンでワークフローまたはワークフローアクティビティを強制的に実行できます。

* **[!UICONTROL History in days]**:履歴をパージする日数を指定します。履歴には、ワークフローに関連する要素が含まれます。ログ、タスク、イベント（ワークフロー操作にリンクされたテクニカルオブジェクト）、および&#x200B;**[!UICONTROL Transfer file]**&#x200B;アクティビティでダウンロードされたファイル。 デフォルト値は、標準のワークフローテンプレートの場合は30日です。

   履歴のパージは、デフォルトで毎日実行されるデータベースクリーンアップテクニカルワークフローによって実行されます（[テクニカルワークフローのリスト](../../administration/using/technical-workflows.md)を参照）。

   >[!IMPORTANT]
   >
   >**[!UICONTROL History in days]**&#x200B;フィールドが空白の場合、その値は「1」と見なされ、1日後に履歴がパージされます。

* **[!UICONTROL Save SQL queries in the log]**:ワークフローのSQLクエリをログに保存できます。

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**:実行計画全体をログに記録する場合は、このオプションを選択します。デフォルトでは無効になっています。

   このオプションの詳細については、[](#diagnostic-mode)を参照してください。

* **[!UICONTROL Keep interim results]**:切り替えの詳細を表示するには、このオプションをオンにします。

   >[!CAUTION]
   >
   >このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。

* **[!UICONTROL Execute in the engine (do not use in production)]**:では、開発環境のテスト用に、ワークフローをローカルで実行できます。

* **[!UICONTROL Severity]**:Adobe Campaignインスタンスでワークフローを実行する際の優先順位を指定できます。このフィールドは、監視の目的でのみAdobeチームによって使用されます。

**[!UICONTROL Error management]**&#x200B;セクションには、エラーが発生した場合のワークフローの動作を管理するための追加のオプションが用意されています。 これらのオプションについて詳しくは、[エラー管理](../../automating/using/monitoring-workflow-execution.md#error-management)の節で説明しています。

## 診断モード {#diagnostic-mode}

>[!CAUTION]
>
>このオプションは、ワークフローのパフォーマンスに大きく影響する可能性があるので、慎重に使用してください。

有効にすると、クエリに1分以上かかる場合に、ワークフロープロパティの&#x200B;**[!UICONTROL Execution]**&#x200B;セクションの&#x200B;**[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**&#x200B;オプションによって実行計画全体がログに記録されます。

![](assets/wkf_diagnostic.png)

このオプションを有効にしてワークフローを起動した後、クエリに1分以上かかる場合、実行計画が記録されます。 その後、EXPLAIN ANALYZEを使用して実行計画を取得できます。

詳しくは、[PostgreSQLのドキュメント](https://www.postgresql.org/docs/9.4/using-explain.html)を参照してください。

このクエリでシーケンススキャンをおこなう場合、**[!UICONTROL Diagnostic mode]**&#x200B;は、フィルター式を使用してインデックスを作成することも推奨します。

>[!NOTE]
>
> これらの推奨事項は参照用にのみ使用され、使用事例に応じて慎重に使用する必要があります。

![](assets/wkf_diagnostic_4.png)

ワークフローの実行中に、次の2つの条件を満たす必要があります。レコメンデーションのトリガー

* シーケンススキャンでは、クエリの40%以上の時間がかかります。

* シーケンススキャン後の結果行が、テーブルに存在する合計行の1 %未満である。

詳細設定メニューで&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;を選択して、このオプションを管理できます。

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**:「 」フィールド **[!UICONTROL Value]** から、クエリの実行に新しい時刻を設定できます。クエリの実行がこの値を超えると、実行計画が記録されます。

   ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**:「 」フィ **[!UICONTROL Value]** ールドで、レコメンデーションを生成するためにシーケンススキャンで実行する必要があるクエリ時間の割合を変更できます。

   ![](assets/wkf_diagnostic_3.png)
