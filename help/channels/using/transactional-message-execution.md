---
title: トランザクションメッセージの実行と監視
description: トランザクションメッセージの実行と、トランザクションメッセージの監視方法について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 4cea7207-469c-46c5-9921-ae2f8f12d141
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 61%

---

# トランザクションメッセージの実行と監視 {#transactional-messaging-execution}

## トランザクションメッセージ実行配信 {#transactional-message-execution-delivery}

メッセージが公開され、サイト統合が完了すると、イベントがトリガーされると、イベントが実行配信に割り当てられます。

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

**実行配信** は、トランザクションメッセージごとに月に 1 回、トランザクションメッセージが再度編集および公開されるたびに作成される、アクションを起こさず機能しないテクニカルメッセージです。

**関連トピック**：
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## トランザクションメッセージの再試行プロセス {#transactional-message-retry-process}

一時的に配信されないトランザクションメッセージは、配信が期限切れになるまで自動再試行が実行される場合があります。配信期間について詳しくは、[有効期間パラメーター](../../administration/using/configuring-email-channel.md#validity-period-parameters)を参照してください。

トランザクションメッセージの送信に失敗した場合は、2 つの再試行システムがあります。

* トランザクションメッセージングレベルでは、トランザクションメッセージが実行配信に割り当てられる前（イベントの受信と配信の準備の間）に、イベントが失敗する可能性があります。[イベント処理の再試行プロセス](#event-processing-retry-process)を参照してください。
* 送信プロセスレベルでは、イベントが実行配信に割り当てられると、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。詳しくは、[メッセージ送信の再試行プロセス](#message-sending-retry-process)を参照してください。

### イベント処理の再試行プロセス {#event-processing-retry-process}

イベントがトリガーされると、実行配信に割り当てられます。 イベントを実行配信に割り当てられない場合、イベント処理は延期されます。再試行は、新しい実行配信に割り当てられるまで実行されます。

>[!NOTE]
>
>延期されたイベントは、まだ実行配信に割り当てられていないため、トランザクションメッセージ送信ログには表示されません。

例えば、イベントの内容が正しくない、アクセス権やブランディングに問題がある、タイポロジルールの適用時にエラーが検出されたなどの理由で、実行配信にを割り当てることができない場合があります。この場合、メッセージを一時停止し、編集して問題を修正し、再度公開できます。再試行システムは、その後、新しい実行配信に割り当てます。

### メッセージ送信の再試行プロセス {#message-sending-retry-process}

イベントが実行配信に割り当てられると、受信者のメールボックスがいっぱいになった場合など、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。詳しくは、[一時的な配信エラーの後の再試行](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

>[!NOTE]
>
>イベントが実行配信に割り当てられると、そのイベントはこの実行配信の送信ログに今回のみ表示されます。失敗した配信は、トランザクションメッセージ送信ログの「**[!UICONTROL Execution list]**」タブに表示されます。

### 再試行プロセスの制限 {#limitations}

**ログの更新を送信中**

再試行プロセスでは、新しい実行配信の送信ログは直ちに更新されません（更新はスケジュールされたワークフローを介して実行されます）。つまり、トランザクションイベントが新しい実行配信で処理されている場合でも、メッセージの「**[!UICONTROL Pending]**」ステータスが変わる可能性があります。

**失敗した実行配信**

実行配信を停止することはできません。ただし、現在の実行配信が失敗した場合、新しいイベントを受け取るとすぐに新しいイベントが作成され、すべての新しいイベントがこの新しい実行配信で処理されます。失敗した実行配信で新しいイベントが処理されることはありません。

実行配信に既に割り当てられている一部のイベントが再試行プロセスの一環として延期され、その実行配信が失敗した場合、再試行システムは延期されたイベントを新しい実行配信に割り当てません。つまり、これらのイベントは失われます。 [ 配信ログ ](#monitoring-transactional-message-delivery) を調べて、影響を受けた可能性のある受信者を確認します。

## トランザクションメッセージの監視 {#monitoring-transactional-message-delivery}

トランザクションメッセージを監視するには、対応する [ 実行配信 ](#transactional-message-execution-delivery) にアクセスする必要があります。

1. メッセージ配信ログを表示するには、**[!UICONTROL Deployment]** ブロックの右下にあるアイコンをクリックします。

   ![](assets/message-center_access_logs.png)

1. 「**[!UICONTROL Execution list]**」タブをクリックします。

   ![](assets/message-center_execution_tab.png)

1. 任意の実行配信を選択します。

   ![](assets/message-center_execution_delivery.png)

1. **[!UICONTROL Deployment]** ブロックの右下にあるアイコンをもう一度クリックします。

   ![](assets/message-center_execution_access_logs.png)

   各実行配信について、標準の配信の場合と同様に配信ログを確認できます。 ログへのアクセスと使用について詳しくは、[ 配信の監視 ](../../sending/using/monitoring-a-delivery.md) を参照してください。

### プロファイルベースのトランザクションメッセージの特異性 {#profile-transactional-message-monitoring}

プロファイルベースのトランザクションメッセージの場合は、次のプロファイル情報を監視できます。

「**[!UICONTROL Sending logs]**」タブを選択します。**[!UICONTROL Status]** 列内の **[!UICONTROL Sent]** は、プロファイルがオプトインしたことを示します。

![](assets/message-center_marketing_sending_logs.png)

「**[!UICONTROL Exclusions logs]**」タブを選択して、メッセージターゲットから除外された受信者（ブロックリスト上のアドレスなど）を表示します。

![](assets/message-center_marketing_exclusion_logs.png)

オプトアウトしたプロファイルの場合、**[!UICONTROL Address on denylist]** タイポロジルールは対応する受信者を除外します。

このルールは、**[!UICONTROL Profile]** テーブルに基づくすべてのトランザクションメッセージに適用される特定のタイポロジの一部です。

![](assets/message-center_marketing_typology.png)

**関連トピック**：

* [タイポロジとタイポロジルールについて](../../sending/using/about-typology-rules.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
