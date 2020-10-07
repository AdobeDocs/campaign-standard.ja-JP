---
title: メッセージのスケジュールについて
description: メッセージのスケジュールを設定する方法を説明します。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 100%

---


# メッセージのスケジュールについて{#about-scheduling-messages}

>[!CAUTION]
>
>配信のスケジュールを変更する場合は、必ず「**Prepare**」ボタンをクリックして配信を準備し直してから、「**Confirm**」をクリックする必要があります。

メッセージダッシュボードの **[!UICONTROL Schedule]** ブロックを使用すると、メッセージ（E メール、SMS、プッシュ通知）を送信するタイミングを定義できます。

![](assets/delivery_dashboard.png)

**[!UICONTROL Schedule]** プロパティを使用すると、E メール、SMS、プッシュ通知の送信オプションを設定できます。

* **[!UICONTROL Messages to be sent once confirmed]**：メッセージは、送信が確認されるとすぐに送信されます。[送信の確認](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**：メッセージは、後で送信されます。「**Start sending from**」フィールドに&#x200B;**連絡日時**&#x200B;を指定します。

   送信の準備と確認はできますが、メッセージは選択した日時まで送信されません。送信の準備と確認は、[送信の準備](../../sending/using/preparing-the-send.md)および[送信の確認](../../sending/using/confirming-the-send.md)の節に記載されています。

   **[!UICONTROL Time zone of the contact date]** ドロップダウンリストを使用すると、送信時間のタイムゾーンを変更できます。例えば、「**[!UICONTROL Start sending from]**」フィールドに「9:00 AM」と入力して **[!UICONTROL Time zone of the contact date]** ドロップダウンリストで「Brussels, Copenhagen, Madrid, Paris (GMT+1)」を選択した場合、すべての受信者はパリ時間の午前 9 時にメッセージを受信します。したがって、モスクワの受信者はモスクワ時間（GMT+3）の午前 11 時にメッセージを受信します。

   手動で送信を確認する場合は、「**[!UICONTROL Request confirmation before sending messages]**」オプションをオンにします。このオプションは、デフォルトでは有効になっています。

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>配信を複製すると、すべてのスケジュール設定が削除されます。新しい連絡日付をスケジュール設定しない限り、重複した配信は、送信が確認されるとすぐに送信されます。

**関連トピック**：

* [送信時間の最適化](../../sending/using/optimizing-the-sending-time.md)
* [受信者のタイムゾーンでのメッセージの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [送信日の計算](../../sending/using/computing-the-sending-date.md)

