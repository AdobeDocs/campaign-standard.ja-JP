---
solution: Campaign Standard
product: campaign
title: トランザクション・メッセージングの実行と監視
description: トランザクションメッセージングの実行について説明し、トランザクションメッセージを監視する方法を確認します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 62%

---


# トランザクションメッセージングの実行と監視{#transactional-messaging-execution}

## トランザクションメッセージ実行配信{#transactional-message-execution-delivery}

メッセージが発行され、サイトの統合が完了すると、イベントがトリガーされると、そのメッセージが実行配信に割り当てられます。

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

**実行配信**&#x200B;は、トランザクションメッセージごとに月に1回作成され、トランザクションメッセージが再び編集され、公開されるたびに作成される、非アクションで機能的な技術メッセージです。

**関連トピック**：
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## トランザクションメッセージングの再試行プロセス{#transactional-message-retry-process}

一時的に配信されないトランザクションメッセージは、配信が期限切れになるまで自動再試行が実行される場合があります。配信期間について詳しくは、[有効期間パラメーター](../../administration/using/configuring-email-channel.md#validity-period-parameters)を参照してください。

トランザクションメッセージの送信に失敗した場合は、2 つの再試行システムがあります。

* トランザクションメッセージングレベルでは、トランザクションメッセージが実行配信に割り当てられる前（イベントの受信と配信の準備の間）に、イベントが失敗する可能性があります。[イベント処理の再試行プロセス](#event-processing-retry-process)を参照してください。
* 送信プロセスレベルでは、イベントが実行配信に割り当てられると、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。詳しくは、[メッセージ送信の再試行プロセス](#message-sending-retry-process)を参照してください。

### イベント処理の再試行プロセス{#event-processing-retry-process}

イベントがトリガーされると、実行配信に割り当てられます。 イベントを実行配信に割り当てられない場合、イベント処理は延期されます。再試行は、新しい実行配信に割り当てられるまで実行されます。

>[!NOTE]
>
>延期されたイベントは、まだ実行配信に割り当てられていないため、トランザクションメッセージ送信ログには表示されません。

例えば、イベントの内容が正しくない、アクセス権やブランディングに問題がある、タイポロジルールの適用時にエラーが検出されたなどの理由で、実行配信にを割り当てることができない場合があります。この場合、メッセージを一時停止し、編集して問題を修正し、再度公開できます。再試行システムは、その後、新しい実行配信に割り当てます。

### メッセージ送信の再試行プロセス{#message-sending-retry-process}

イベントが実行配信に割り当てられると、受信者のメールボックスがいっぱいになった場合など、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。詳しくは、[一時的な配信エラーの後の再試行](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

>[!NOTE]
>
>イベントが実行配信に割り当てられると、そのイベントはこの実行配信の送信ログに今回のみ表示されます。失敗した配信は、ログを送信するトランザクションメッセージの&#x200B;**[!UICONTROL Execution list]**&#x200B;タブに表示されます。

### プロセスの制限を再試行{#limitations}

**ログの更新を送信中**

再試行プロセスでは、新しい実行配信の送信ログは直ちに更新されません（更新はスケジュールされたワークフローを介して実行されます）。つまり、トランザクションイベントが新しい実行配信で処理されている場合でも、メッセージの「**[!UICONTROL Pending]**」ステータスが変わる可能性があります。

**失敗した実行配信**

実行配信を停止することはできません。ただし、現在の実行配信が失敗した場合、新しいイベントを受け取るとすぐに新しいイベントが作成され、すべての新しいイベントがこの新しい実行配信で処理されます。失敗した実行配信で新しいイベントが処理されることはありません。

実行配信に既に割り当てられている一部のイベントが再試行プロセスの一部として延期され、その実行配信に失敗した場合、再試行システムは、延期されたイベントを新しい実行配信に割り当てません。これは、これらのイベントが失われたことを意味します。 [配信ログ](#monitoring-transactional-message-delivery)をチェックして、影響を受けた可能性のある受信者を確認します。

## 監視トランザクションメッセージ{#monitoring-transactional-message-delivery}

トランザクションメッセージを監視するには、対応する[実行配信](#transactional-message-execution-delivery)にアクセスする必要があります。

1. メッセージ配信ログを表示するには、**[!UICONTROL Deployment]** ブロックの右下にあるアイコンをクリックします。

   ![](assets/message-center_access_logs.png)

1. 「**[!UICONTROL Execution list]**」タブをクリックします。

   ![](assets/message-center_execution_tab.png)

1. 選択した実行配信を選択します。

   ![](assets/message-center_execution_delivery.png)

1. **[!UICONTROL Deployment]**&#x200B;ブロックの右下にあるアイコンをもう一度クリックします。

   ![](assets/message-center_execution_access_logs.png)

   各実行配信に対して、標準配信と同様に配信ログを調べることができます。 ログへのアクセスと使用について詳しくは、[配信の監視](../../sending/using/monitoring-a-delivery.md)を参照してください。

### プロファイルベースのトランザクションメッセージの特殊性{#profile-transactional-message-monitoring}

プロファイルベースのトランザクションメッセージの場合、次のプロファイル情報を監視できます。

「**[!UICONTROL Sending logs]**」タブを選択します。**[!UICONTROL Status]** 列内の **[!UICONTROL Sent]** は、プロファイルがオプトインしたことを示します。

![](assets/message-center_marketing_sending_logs.png)

「**[!UICONTROL Exclusions logs]**」タブを選択すると、メッセージターゲットから除外された表示受信者(ブロックリスト上のアドレスなど)が表示されます。

![](assets/message-center_marketing_exclusion_logs.png)

オプトアウトしたプロファイルの場合、**[!UICONTROL Address on denylist]** タイポロジルールは対応する受信者を除外します。

このルールは、**[!UICONTROL Profile]** テーブルに基づくすべてのトランザクションメッセージに適用される特定のタイポロジの一部です。

![](assets/message-center_marketing_typology.png)

**関連トピック**：

* [タイポロジとタイポロジルールについて](../../sending/using/about-typology-rules.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
