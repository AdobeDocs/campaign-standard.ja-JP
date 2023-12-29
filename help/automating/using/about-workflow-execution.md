---
title: ワークフローの実行について
description: ワークフローの実行の詳細を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 10%

---

# ワークフローの実行について {#about-workflow-execution}

ワークフローは、必ず手動で開始します。ただし、開始した後も、 [スケジューラ](../../automating/using/scheduler.md) アクティビティ。

>[!IMPORTANT]
>
> Adobeでは、20 個を超えるアクティブなワークフローを同時に実行しないようにし、時間の経過と共にワークフローの実行を優先し、広げることをお勧めします。 詳しくは、 [このページ](../../automating/using/best-practices-workflows.md).

実行に関連するアクション（開始、停止、一時停止など） が **非同期** プロセス：コマンドは保存され、サーバーがコマンドを適用できるようになると有効になります。

ワークフローでは、通常、各アクティビティの結果は、矢印で表されるトランジションを介して後続のアクティビティに送信されます。

トランジションが宛先アクティビティにリンクされていない場合、トランジションは終了されません。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>未終了のトランジションを含むワークフローは、引き続き実行できます。その場合、警告メッセージが生成され、トランジションに到達するとワークフローは一時停止しますが、エラーは発生しません。 デザインを完全に完了せずにワークフローを開始し、作業を進めながらワークフローを完了することもできます。

アクティビティを実行すると、トランジションで送信されたレコードの数がその上に表示されます。

![](assets/wkf_transition_count.png)

ワークフローの実行中または実行後にトランジションを開いて、送信されたデータが正しいかどうかを確認できます。データとデータ構造を表示できます。

デフォルトでは、ワークフローの最後のトランジションの詳細のみにアクセスできます。 前のアクティビティの結果にアクセスするには、 **[!UICONTROL Keep interim results]** オプションを **[!UICONTROL Execution]** 」セクションを開き、ワークフローを開始する前にクリックします。

>[!NOTE]
>
>このオプションは、大量のメモリを消費します。ワークフローの構築と、ワークフローの設定と動作の正確化を支援するように設計されています。 実稼働インスタンスでは、このチェックボックスをオフのままにします。

トランジションを開いている場合は、トランジションを編集できます **[!UICONTROL Label]** または **[!UICONTROL Segment code]** それに対して これをおこなうには、対応するフィールドを編集し、変更を確定します。

Campaign StandardREST API を使用すると、 **開始**, **pause**, **再開** および **停止** ワークフロー。 REST 呼び出しの詳細と例については、 [API ドキュメント。](../../api/using/controlling-a-workflow.md)
