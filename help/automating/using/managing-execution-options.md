---
title: 実行オプションの管理
description: ワークフローの実行オプションを管理する方法を説明します。
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8ebded956ef52bb742160d62ebbd8095c390d51c
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 2%

---


# 実行オプションの管理 {#managing-execution-options}

ワークフローの実行オプションを変更するには、 ![](assets/edit_darkgrey-24px.png) ボタンを使用してワークフローのプロパティにアクセスし、セク **[!UICONTROL Execution]** ションを選択します。

![](assets/wkf_execution_6.png)

選択できるオプションは次のとおりです。

* **[!UICONTROL Default affinity]**:このフィールドを使用すると、特定のマシン上でワークフローまたはワークフローアクティビティを強制的に実行できます。

* **[!UICONTROL History in days]**:履歴を削除する必要がある日数を指定します。 履歴には、ワークフローに関連する要素が含まれます。ログ、タスク、イベント（ワークフロー操作にリンクされた技術オブジェクト）、および **[!UICONTROL Transfer file]** アクティビティがダウンロードしたファイル。 デフォルト値は、あらかじめ用意されたワークフローテンプレートの30日です。

   履歴の削除は、Database cleanup technical workflowが実行します。これは、デフォルトで毎日実行されます(テクニカルワークフローの [リストを参照](../../administration/using/technical-workflows.md))。

   >[!IMPORTANT]
   >
   >この **[!UICONTROL History in days]** フィールドを空白のままにすると、その値は「1」と見なされ、1日後に履歴が削除されます。

* **[!UICONTROL Save SQL queries in the log]**:ワークフローのSQLクエリをログに保存できます。

* **[!UICONTROL Keep interim results]**:トランジションの詳細を表示できるようにするには、このオプションを選択します。 警告：このオプションを選択すると、ワークフローの実行が大幅に遅くなる可能性があります。

* **[!UICONTROL Execute in the engine (do not use in production)]**:開発環境のテスト用に、ワークフローをローカルで実行できます。

* **[!UICONTROL Severity]**:adobe campaignインスタンスでワークフローを実行する際の優先度を指定できます。 このフィールドは、監視の目的でのみAdobeチームが使用します。

この **[!UICONTROL Error management]** 節では、エラーが発生した場合のワークフローの動作を管理するための追加のオプションを提供します。 これらのオプションの詳細については、「 [エラー管理](../../automating/using/monitoring-workflow-execution.md#error-management) 」の節を参照してください。
