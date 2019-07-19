---
title: 受信者のタイムゾーンでのメッセージの送信
seo-title: 受信者のタイムゾーンでのメッセージの送信
description: 受信者のタイムゾーンでのメッセージの送信
seo-description: 受信者のタイムゾーンでメッセージを送信する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 削除されたドキュメント
discoiquuid: daya980ba-8c7c-4673- a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Sending messages at the recipient's time zone{#sending-messages-at-the-recipient-s-time-zone}

日付と時間が重要なキャンペーンを管理する場合、各受信者のローカル時間を考慮する配信をスケジュールできます。電子メール、SMS、またはプッシュ通知は、スケジュールされた時点で、独自のタイムゾーンで送信されます。

>[!NOTE]
>
>To use this functionality, make sure that all profiles targeted by your delivery have a time zone specified in the **[!UICONTROL Address]** section of their properties. For more information on accessing profile properties, refer to this [section](../../audiences/using/editing-profiles.md).

To send a delivery at the recipient's time zone, you can also use the **[!UICONTROL Scheduler]** activity in a workflow. For more on this, refer to this [page](../../automating/using/scheduler.md).

次の例では、バレンタインデーで世界中のすべての顧客にのみ有効なプロモーションコードを送信します。その日の使用に十分な時間を確保するために、すべての顧客は、タイムゾーンに応じて午前8時14分にメッセージを受信する必要があります。

1. **[!UICONTROL Marketing activities]** タブで、配信の作成を開始します（例:電子メール）。To learn more on delivery creation, refer to this [section](../../channels/using/creating-an-email.md).
1. After designing your Valentine's Day email, click **[!UICONTROL Create]** to access the delivery dashboard. For more on email designing, refer to this [page](../../designing/using/example--email-personalization.md).

   ![](assets/send-time_opt_valentine_1.png)

1. From the delivery dashboard, select the **[!UICONTROL Schedule]** block.

   ![](assets/send-time_opt_valentine_2.png)

1. Select the **[!UICONTROL Messages to be sent automatically on the date]** option specified below. **[!UICONTROL Start sending from]** その後、このフィールドで連絡先日を設定します。この場合、2月14日の午前8時14分に、すべての受信者がバレンタインデーでそれを受信します。

   ![](assets/send-time_opt_valentine.png)

1. **[!UICONTROL Time zone of the contact date]** フィールドで、デフォルトで配信するタイムゾーンを選択します。

   If a profile's **[!UICONTROL Time zone]** is left as **[!UICONTROL Default]**, the recipients will receive the delivery depending on the chosen time zone here.

1. **[!UICONTROL Optimize the sending time per recipient]** ドロップダウンメニューから、を選択 **[!UICONTROL Send at the recipient's time zone]**&#x200B;します。これにより、受信者は、タイムゾーンに応じて、2月14日にバレンタインデーの電子メールを受信できます。

   ![](assets/send-time_opt_valentine_3.png)

1. After confirming your schedule for your delivery, click the **[!UICONTROL Prepare]** button then **[!UICONTROL Confirm]** your delivery.

   必ず24時間前に送信を確認してください。そうしないと、その場所によって、実際のバレンタインデーイベントの前に、一部の受信者が配信を受け取ることがあります。

   ![](assets/send-time_opt_valentine_4.png)

すべての受信者がどこにいるかにかかわらず、すべての受信者は、午前8時14分の午前8時にメッセージを受信します。
