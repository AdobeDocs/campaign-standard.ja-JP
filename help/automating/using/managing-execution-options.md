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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 13%

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

* **[!UICONTROL Keep interim results]**:トランジションの詳細を表示できるようにするには、このオプションを選択します。

   >[!CAUTION]
   >
   >このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。

* **[!UICONTROL Execute in the engine (do not use in production)]**:開発環境のテスト用に、ワークフローをローカルで実行できます。

* **[!UICONTROL Severity]**:adobe campaignインスタンスでワークフローを実行する際の優先度を指定できます。 このフィールドは、監視の目的でのみAdobeチームが使用します。

この **[!UICONTROL Error management]** 節では、エラーが発生した場合のワークフローの動作を管理するための追加のオプションを提供します。 これらのオプションの詳細については、「 [エラー管理](../../automating/using/monitoring-workflow-execution.md#error-management) 」の節を参照してください。
