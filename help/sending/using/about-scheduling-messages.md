---
title: メッセージのスケジュールについて
description: メッセージをスケジュールする方法を説明します。
page-status-flag: 非活性化の
uuid: 286fcee-65a9-4cb9-b205-9ce5d024675c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: スケジュール・メッセージ
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: 配信，スケジュール，戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# メッセージのスケジュールについて{#about-scheduling-messages}

>[!CAUTION]
>
>配信のスケジュールを変更する場合は、「 **Confirm** 」をクリックする前に「 **Prepare**」ボタンをクリックして配信の準備をし直す必要があります。

メッセージダッシュボードでは、ブ **[!UICONTROL Schedule]** ロックを使用して、メッセージ（電子メール、SMS、またはプッシュ通知）を送信するタイミングを定義できます。

![](assets/delivery_dashboard.png)

このプロ **[!UICONTROL Schedule]** パティを使用すると、電子メール、SMS、またはプッシュ通知の送信オプションを設定できます。

* **[!UICONTROL Messages to be sent once confirmed]**:メッセージは、送信が確認されるとすぐに送信されます。 See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**:メッセージは後で送信されます。 「送信開始 **日」フィー** ルドに連絡日を指定し **** ます。

   送信の準備と確認はできますが、メッセージは選択した日時からのみ送信されます。 送信の準備と確認については、「送信の準備 [」と「送信の確](../../sending/using/preparing-the-send.md) 認」の節を参照 [](../../sending/using/confirming-the-send.md) 。

   このド **[!UICONTROL Time zone of the contact date]** ロップダウンリストを使用すると、送信時刻を考慮するタイムゾーンを変更できます。 例えば、フィールドに「9:00 AM」と入力し、ドロップダウンリストで「Brussels, Copenhagen, Madrid, Paris (GMT+1)」を選択した場合、すべての受信者は午前9:00 AMのパリ時にメッセージを受け取ります。 **[!UICONTROL Start sending from]****[!UICONTROL Time zone of the contact date]** したがって、モスクワにいる受信者(GMT+3)は、モスクワ時間の午前11時にメッセージを受け取ります。

   手動で送信を確認する場合は、このオプションを選択し **[!UICONTROL Request confirmation before sending messages]** ます。 このオプションはデフォルトで有効になっています。

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>配信を複製する場合、すべてのスケジュール設定が削除されます。 新しい連絡日をスケジュールしない限り、重複した配信は送信が確認され次第送信されます。

**関連トピック**：

* [送信時間の最適化](../../sending/using/optimizing-the-sending-time.md)
* [受信者のタイムゾーンでのメッセージの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [送信日の計算](../../sending/using/computing-the-sending-date.md)

