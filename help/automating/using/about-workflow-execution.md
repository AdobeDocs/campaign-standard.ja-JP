---
title: ワークフローの実行について
description: ワークフローの実行に関する詳細を表示します。
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
source-wordcount: '374'
ht-degree: 9%

---


# ワークフローの実行について {#about-workflow-execution}

ワークフローは、必ず手動で開始します。ただし、一度起動した後は、 [スケジューラー](../../automating/using/scheduler.md) アクティビティで指定されている情報に応じて非アクティブのままにすることができます。

>[!CAUTION]
>
> Adobeでは、インスタンス全体で最大のパフォーマンスを維持できるように、ワークフローの実行に優先順位を付け、最大20個の同時ワークフロー実行を実行することをお勧めします。 20個を超える同時ワークフロー実行が計画されている場合があり、デフォルトで順番に実行されます。 チケットをカスタマーケアに送信することで、同時ワークフロー実行の最大数のデフォルト設定を調整できます。

実行に関連するアクション(開始、停止、一時停止など) は **非同期プロセスです** 。コマンドは保存され、サーバが適用可能になると有効になります。

ワークフローでは、各アクティビティの結果は、通常、矢印で表されたトランジションを介して次のアクティビティに送信されます。

トランジションがリンク先のアクティビティにリンクされていない場合、そのは終了されません。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>終了していないトランジションを含むワークフローは、引き続き実行できます。警告メッセージが生成され、ワークフローがトランジションに到達するとワークフローが一時停止しますが、エラーは発生しません。 デザインを完全に終了せずにワークフローを開始し、作業を進めながらワークフローを完了することもできます。

アクティビティが実行されると、トランジションで送信されたレコード数がその上に表示されます。

![](assets/wkf_transition_count.png)

ワークフローの実行中または実行後にトランジションを開いて、送信されたデータが正しいかどうかを確認できます。データとデータ構造を表示できます。

デフォルトでは、ワークフローの最後のトランジションの詳細のみにアクセスできます。 前述のアクティビティの結果にアクセスするには、ワークフローを開始する前に、ワークフロープロパティの **[!UICONTROL Keep interim results]****[!UICONTROL Execution]** セクションでオプションを確認する必要があります。

>[!NOTE]
>
>このオプションは、大量のメモリを消費し、ワークフローの構築と、ワークフローの正しい設定と動作の確保に役立つように設計されています。 実稼働インスタンスでは、このチェックボックスをオフのままにします。

トランジションを開いたときに、その画像を編集したり、にリンクし **[!UICONTROL Label]** たりでき **[!UICONTROL Segment code]** ます。 これを行うには、対応するフィールドを編集し、変更を確認します。

Campaign StandardREST APIを使用して、ワークフローを **開始、**&#x200B;一時停止 **、**&#x200B;再開、 ******** 停止できます。 REST呼び出しの詳細と例については、 [APIドキュメントを参照してください。](../../api/using/controlling-a-workflow.md)
