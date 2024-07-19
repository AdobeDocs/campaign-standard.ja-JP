---
title: ワークフローの実行について
description: ワークフローの実行についての詳細情報
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

ワークフローは、必ず手動で開始します。ただし、開始後は、「スケジューラー [ アクティビティで指定された情報によっては、非アクティブなままになる可能性が ](../../automating/using/scheduler.md) ります。

>[!IMPORTANT]
>
> Adobeでは、20 を超えるアクティブなワークフローの実行を同時に実行せず、ワークフローの実行を時間の経過と共に優先順位を付けて分散することをお勧めします。 詳しくは、[ このページ ](../../automating/using/best-practices-workflows.md) に記載されているベストプラクティスを参照してください。

実行関連のアクション（開始、停止、一時停止など） は **非同期** プロセスです。コマンドは保存され、サーバーが適用できるようになると有効になります。

ワークフローでは、通常、各アクティビティの結果は、トランジションを介して次のアクティビティに送信されます（矢印で表されます）。

宛先アクティビティにリンクされていないトランジションは終了しません。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>終了していないトランジションを含むワークフローは引き続き実行できます。警告メッセージが生成され、トランジションに到達するとワークフローが一時停止しますが、エラーは生成されません。 デザインを完全に完成させずにワークフローを開始し、進みながら完了することもできます。

アクティビティが実行されると、トランジションで送信されたレコード数がアクティビティの上に表示されます。

![](assets/wkf_transition_count.png)

ワークフローの実行中または実行後にトランジションを開いて、送信されたデータが正しいかどうかを確認できます。データとデータ構造を表示できます。

デフォルトでは、ワークフローの最後のトランジションの詳細にのみアクセスできます。 上記のアクティビティの結果にアクセスできるようにするには、ワークフローを開始する前に、ワークフロープロパティの「**[!UICONTROL Execution]**」セクションで「**[!UICONTROL Keep interim results]**」オプションをオンにする必要があります。

>[!NOTE]
>
>このオプションは多くのメモリを消費し、ワークフローの構築と、正しく設定され動作することを保証するように設計されています。 実稼働インスタンスでは、このチェックボックスをオフのままにします。

トランジションが開いている場合は、トランジションの **[!UICONTROL Label]** を編集するか、トランジションにトランジシ **[!UICONTROL Segment code]** ンをリンクします。 これを行うには、対応するフィールドを編集し、変更を確認します。

Campaign Standardの REST API を使用すると、ワークフローを **開始**、**一時停止**、**再開** および **停止** できます。 REST 呼び出しの詳細と例については、[API ドキュメント ](../../api/using/controlling-a-workflow.md) を参照してください。
