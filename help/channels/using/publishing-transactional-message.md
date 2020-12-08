---
solution: Campaign Standard
product: campaign
title: イベントトランザクションメッセージ
description: イベントトランザクションメッセージを作成して公開する方法について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 951f358eb7139be8924aadf8461944d4318f03f1
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 76%

---


# トランザクションメッセージライフサイクル{#publishing-transactional-message}

[トランザクションメッセージ](../../channels/using/editing-transactional-message.md)を送信する準備ができたら、それを公開できます。

トランザクションメッセージを公開、一時停止、非公開、削除する手順は、次のとおりです。

>[!IMPORTANT]
>
>[管理](../../administration/using/users-management.md#functional-administrators)ロールを持つユーザーのみが、トランザクションメッセージにアクセスして発行できます。

## トランザクションメッセージの公開プロセス {#transactional-messaging-pub-process}

以下の表に、トランザクションメッセージングの公開プロセス全体を示します。

![](assets/message-center_pub-process.png)

**関連トピック：**
* [トランザクションメッセージの公開](#publishing-a-transactional-message)
* [トランザクションメッセージの一時停止](#suspending-a-transactional-message-publication)
* [トランザクションメッセージの非公開](#unpublishing-a-transactional-message)
* [イベントの公開](../../channels/using/publishing-transactional-event.md)

<!--## Testing a transactional message {#testing-a-transactional-message}

You first need to create a specific test profile that will allow you to properly check the transactional message.

### Defining a specific test profile {#defining-specific-test-profile}

Define a test profile that will be linked to your event, which will allow you to preview your message and send a relevant proof.

1. From the transactional message dashboard, click the **[!UICONTROL Create test profile]** button.

   ![](assets/message-center_test-profile.png)

1. Specify the information to send in JSON format in the **[!UICONTROL Event data used for personalization]** section. This is the content that will be used when previewing the message and when the test profile receives the proof.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >You can also enter the information relating to the profile table. See [Enriching the event](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Once created, the test profile will be pre-specified in the transactional message. Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu. To do this:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section, select the event that you have just created. In this example, select "Cart abandonment (EVTcartAbandonment)".
1. Specify the information to send in JSON format in the **[!UICONTROL Event data]** text box.

   ![](assets/message-center_3.png)

1. Save your changes.
1. Access the message that you created and select the updated test profile.

**Related topics:**

* [Managing test profiles](../../audiences/using/managing-test-profiles.md)
* [Creating audiences](../../audiences/using/creating-audiences.md)

### Sending the proof {#sending-proof}

Once you have created one or more specific test profiles and saved your transactional message, you can send a proof to test it.

![](assets/message-center_10.png)

The steps for sending a proof are detailed in the [Sending proofs](../../sending/using/sending-proofs.md) section.-->

## トランザクションメッセージの公開{#publishing-a-transactional-message}

トランザクションメッセージを編集してテストした後は、その画像を公開できます。 「**[!UICONTROL Publish]**」ボタンをクリックするだけです。

![](assets/message-center_12.png)

これで、「買い物かごの放棄」イベントがトリガーされるとすぐに、受信者のタイトルと姓、買い物かごの URL、最後に参照した製品、または製品のリスト（製品リストを定義した場合）と送信される買い物かごの総数を含むメッセージが自動的に表示されます。

トランザクションメッセージに関するレポートにアクセスするには、「**[!UICONTROL Reports]**」ボタンを使用します。[動的レポート](../../reporting/using/about-dynamic-reports.md)を参照してください。

![](assets/message-center_13.png)

**関連トピック**：
* [トランザクションメッセージの編集](../../channels/using/editing-transactional-message.md)
* [トランザクションメッセージのテスト](../../channels/using/testing-transactional-message.md)
* [イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## トランザクションメッセージ公開の一時停止{#suspending-a-transactional-message-publication}

トランザクションメッセージに含まれるデータを変更する場合など、「**[!UICONTROL Pause]**」ボタンを使用してメッセージの公開を中止できます。したがって、イベントは処理されず、Adobe Campaign データベースのキューに保持されます。

キューに格納されたイベントは、REST APIで定義された期間（[REST APIドキュメント](../../api/using/managing-transactional-messages.md)を参照）またはTriggersコアサービスを使用している場合はトリガーイベントに保持されます([Adobe Experience Cloudトリガーについて](../../integrating/using/about-adobe-experience-cloud-triggers.md)を参照)。

![](assets/message-center_pause.png)

「**[!UICONTROL Resume]**」をクリックすると、キューに格納されているすべてのイベント（期限切れでない場合）が処理されます。テンプレートのパブリケーションが停止されている間に実行されたすべての変更が含まれています。

## トランザクションメッセージの非公開{#unpublishing-a-transactional-message}

「**[!UICONTROL Unpublish]**」をクリックすると、トランザクションメッセージの公開をキャンセルするだけでなく、対応するイベントの公開もキャンセルします。これにより、REST API から、以前に作成したイベントに対応するリソースが削除されます。

![](assets/message-center_unpublish-template.png)

これで、Web サイトを通じてイベントがトリガーされた場合でも、対応するメッセージは送信されなくなり、データベースには保存されません。

>[!NOTE]
>
>メッセージを再度公開するには、対応するイベント設定に戻り、[イベント](../../channels/using/publishing-transactional-event.md)を公開し、[メッセージ](#publishing-a-transactional-message)を公開する必要があります。

一時停止したトランザクションメッセージを非公開にする場合は、再度公開するまで 24 時間待たなければならない場合があります。これは、キューに送信されたすべてのイベントを「**[!UICONTROL Database cleanup]**」ワークフローで消去するためです。

メッセージを一時停止する手順について詳しくは、[トランザクションメッセージ公開の一時停止](#suspending-a-transactional-message-publication)の節を参照してください。

毎日午前 4 時に実行される「**[!UICONTROL Database cleanup]**」ワークフローは、**[!UICONTROL Administration]**／**[!UICONTROL Application settings]**／**[!UICONTROL Workflows]** からアクセスできます。

## トランザクションメッセージの削除{#deleting-a-transactional-message}

トランザクションメッセージが非公開になっている場合、またはトランザクションメッセージがまだ公開されていない場合は、トランザクションメッセージリストから削除できます。手順は次のとおりです。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Transactional messages]** を選択します。
1. 選択したメッセージにマウスを合わせます。
1. 「**[!UICONTROL Delete element]**」ボタンをクリックします。

![](assets/message-center_delete-template.png)

ただし、トランザクションメッセージの削除は、次の特定の状況でのみ実行できます。

* トランザクションメッセージのステータスが「**[!UICONTROL Draft]**」であることを確認してください。そうでない場合、削除できません。この「**[!UICONTROL Draft]**」ステータスは、まだ公開されていないメッセージ、または[非公開にする](#unpublishing-a-transactional-message)（または[一時停止](#suspending-a-transactional-message-publication)されていない）メッセージに適用されます。

* **トランザクションメッセージ**：対応するイベントに別のトランザクションメッセージがリンクされている場合を除き、トランザクションメッセージが非公開の場合は、イベントを正常に削除するために、トランザクションメッセージ設定も非公開にする必要があります。詳しくは、[イベントの非公開](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)を参照してください。

   >[!IMPORTANT]
   >
   >既に通知を送信したトランザクションメッセージを削除すると、その送信およびトラッキングログも削除されます。

* **標準搭載のイベントテンプレート（内部トランザクションメッセージ）**：内部トランザクションメッセージが、対応する内部イベントに関連付けられている唯一のものである場合、削除できません。別のトランザクションメッセージを作成する場合は、まず複製するか、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Transactional message templates]** メニューを使用します。

<!--## Monitoring transactional message delivery {#monitoring-transactional-message-delivery}

Once the message is published and your site integration is done, you can monitor the delivery.

To monitor transactional messaging, you need to access **execution deliveries**. An execution delivery is a non-actionable and non-functional technical message created once a month for each transactional message, and each time a transactional message is edited and published again.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   ![](assets/message-center_access_logs.png)

1. Click the **[!UICONTROL Execution list]** tab.

   ![](assets/message-center_execution_tab.png)

1. Select the execution delivery of your choice.

   ![](assets/message-center_execution_delivery.png)

1. Click again the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   ![](assets/message-center_execution_access_logs.png)

   For each execution delivery, you can consult the delivery logs as you would do for a standard delivery. For more on accessing and using the logs, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

**Related topics**:
* [Publishing a transactional message](#publishing-a-transactional-message)
* [Integrate the event triggering](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

### Profile-based transactional message specificities {#profile-transactional-message-monitoring}

For profile-based transactional messages, you can monitor the following profile information.

Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

![](assets/message-center_marketing_sending_logs.png)

Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Address on denylist]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Related topics**:

* [About typologies and typology rules](../../sending/using/about-typology-rules.md)
* [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)

## Transactional message retry process {#transactional-message-retry-process}

A temporarily undelivered transactional message is subject to automatic retries that are performed until the delivery expires. For more on the delivery duration, see [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters).

When a transactional message fails to be sent, there are two retry systems:

* At the transactional messaging level, a transactional message can fail before the event is assigned to an execution delivery, meaning between the event reception and the delivery preparation. See [Event processing retry process](#event-processing-retry-process).
* At the sending process level, once the event has been assigned to an execution delivery, the transactional message can fail due to a temporary error. See [Message sending retry process](#message-sending-retry-process).

The definition of **execution delivery** can be found in the [Monitoring transactional message delivery](#monitoring-transactional-message-delivery) section.

### Event processing retry process {#event-processing-retry-process}

When an event is triggered, it is assigned to an execution delivery.

If the event cannot be assigned to an execution delivery, the event processing is postponed. Retries are then performed until it is assigned to a new execution delivery.

>[!NOTE]
>
>A postponed event does not appear in the transactional message sending logs, because it is not assigned to an execution delivery yet.

For example, the event could not be assigned to an execution delivery because its content was not correct, there was an issue with access rights or branding, an error was detected on applying typology rules, etc. In this case, you can pause the message, edit it to fix the problem and publish it again. The retry system will then assign it to a new execution delivery.

### Message sending retry process {#message-sending-retry-process}

Once the event has been assigned to an execution delivery, the transactional message can fail due to a temporary error, if the recipient's mailbox is full for example. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>When an event is assigned to an execution delivery, it appears in the sending logs of this execution delivery, and only at this time. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message sending logs.

### Retry process limitations {#limitations}

**Sending logs update**

In the retry process, the sending logs of the new execution delivery are not immediately updated (the update is performed through a scheduled workflow). It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**Failed execution delivery**

You cannot stop an execution delivery. However, if the current execution delivery fails, a new one is created as soon as a new event is received, and all new events are processed by this new execution delivery. No new events are processed by the failed execution delivery.

If some events already assigned to an execution delivery have been postponed as part of the retry process and if that execution delivery fails, the retry system does not assign the postponed events to the new execution delivery, which means that these events are lost. Check the [delivery logs](#monitoring-transactional-message-delivery) to see the recipients that may have been impacted.-->
