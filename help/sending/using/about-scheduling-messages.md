---
title: メッセージのスケジュール設定について
seo-title: メッセージのスケジュール設定について
description: メッセージのスケジュール設定について
seo-description: メッセージのスケジュールを設定する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 286fceee-65a9-4cb9- b205-9ce5d024675c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 削除されたドキュメント
discoiquuid: 9c7fd670- bba9-4f3c-8cb1-87397a1acd27
context-tags: 配信、スケジュール、戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About scheduling messages{#about-scheduling-messages}

>[!CAUTION]
>
>Whenever making changes to a delivery’s schedule, you must re-prepare the delivery by clicking on the **Prepare** button before clicking **Confirm**.

In the message dashboard, the **[!UICONTROL Schedule]** block allows you to define when messages (email, SMS or Push notifications) will be sent.

![](assets/delivery_dashboard.png)

**[!UICONTROL Schedule]** このプロパティを使用すると、電子メール、SMSまたはプッシュ通知の送信オプションを設定できます。

* **[!UICONTROL Messages to be sent once confirmed]**:メッセージは、送信が確定されるとすぐに送信されます。See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**:メッセージが送信されます。Specify the **contact date** in the **Start sending from** field.

   送信を準備して確認することができますが、メッセージは選択した日時からのみ送信されます。Preparing and confirming the send are presented in the [Preparing the send](../../sending/using/preparing-the-send.md) and [Confirming the send](../../sending/using/confirming-the-send.md) sections.

   The **[!UICONTROL Time zone of the contact date]** drop-down list allows you to modify the time zone that will be taken into account for the sending time. **[!UICONTROL Start sending from]** 例えば、フィールドに«9:00AM»と入力し、 **[!UICONTROL Time zone of the contact date]** ドロップダウンリストの«ブリュッセル»、«コペンハーゲン»、«マドリード»、«パリ（GMT+1）»を選択した場合、すべての受信者は、午前9時の午前9時にメッセージを受け取ります。したがって、モスクワ（GMT+3）にある受信者は、午前11時00分の午前11時にメッセージを受け取ります。

   If you would like to manually confirm the send, check the **[!UICONTROL Request confirmation before sending messages]** option. このオプションはデフォルトで有効になっています。

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>配信を複製すると、すべてのスケジュール設定が削除されます。新しい連絡先日をスケジュールしない限り、送信が確定されるとすぐに、複製された配信が送信されます。

**関連トピック**:

* [送信時間の最適化](../../sending/using/optimizing-the-sending-time.md)
* [受信者のタイムゾーンでのメッセージの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [送信日の計算](../../sending/using/computing-the-sending-date.md)

