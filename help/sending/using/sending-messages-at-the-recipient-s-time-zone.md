---
title: 受信者のタイムゾーンでのメッセージの送信
description: 受信者のタイムゾーンでメッセージを送信する方法を説明します。
page-status-flag: 非活性化の
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: スケジュール・メッセージ
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 受信者のタイムゾーンでのメッセージの送信{#sending-messages-at-the-recipient-s-time-zone}

日時が重要なキャンペーンを管理する場合は、各受信者のローカル時間を考慮に入れて配信をスケジュールできます。電子メール、SMS、またはプッシュ通知は、スケジュールした日時に、それぞれ独自のタイムゾーンで受信されます。

>[!NOTE]
>
>この機能を使用するには、配信の対象となるすべてのプロファイルのプロパティのセクションでタイムゾーンが指定されている **[!UICONTROL Address]** ことを確認します。 プロファイルプロパティへのアクセスの詳細については、この節を参照して [くださ](../../audiences/using/editing-profiles.md)い。

受信者のタイムゾーンで配信を送信する場合は、ワークフローでアクティビティを **[!UICONTROL Scheduler]** 使用することもできます。 詳しくは、この[ページ](../../automating/using/scheduler.md)を参照してください。

次の例では、バレンタインデーでのみ有効なプロモーションコードを世界中のすべての顧客に送信します。 1日の間に十分な時間を割くために、すべての顧客は、2月14日の午前8時に、自分のタイムゾーンに応じてメッセージを受け取る必要があります。

1. この場合 **[!UICONTROL Marketing activities]** は、タブで配信の作成を開始します。 配信の作成の詳細については、この節を参照してく [ださい](../../channels/using/creating-an-email.md)。
1. バレンタインデーの電子メールをデザインしたら、をクリックして配 **[!UICONTROL Create]** 信ダッシュボードにアクセスします。 For more on email designing, refer to this [page](../../designing/using/personalization.md#example-email-personalization).

   ![](assets/send-time_opt_valentine_1.png)

1. 配信ダッシュボードで、ブロックを選択 **[!UICONTROL Schedule]** します。

   ![](assets/send-time_opt_valentine_2.png)

1. 以下で指定した **[!UICONTROL Messages to be sent automatically on the date]** オプションを選択します。 次に、このフ **[!UICONTROL Start sending from]** ィールドで、2月14日の午前8時に連絡日を設定し、すべての受信者がバレンタインデーに受け取るようにします。

   ![](assets/send-time_opt_valentine.png)

1. このフィー **[!UICONTROL Time zone of the contact date]** ルドで、配信をデフォルトで送信するタイムゾーンを選択します。

   プロファイルを「」のままにし **[!UICONTROL Time zone]** た場合、受信者は **[!UICONTROL Default]**&#x200B;ここで選択したタイムゾーンに応じて配信を受け取ります。

1. ドロップダウ **[!UICONTROL Optimize the sending time per recipient]** ンメニューから、を選択しま **[!UICONTROL Send at the recipient's time zone]**&#x200B;す。 これにより、受信者はタイムゾーンに応じて2月14日にバレンタインデーの電子メールを受け取ることができます。

   ![](assets/send-time_opt_valentine_3.png)

1. 配信のスケジュールを確認したら、ボタンをクリックし **[!UICONTROL Prepare]** てから配 **[!UICONTROL Confirm]** 信を行います。

   少なくとも24時間前に送信を確認してください。 そうでないと、場所によっては、実際のバレンタインデーイベントの前に配信を受け取る受信者もいます。

   ![](assets/send-time_opt_valentine_4.png)

場所に関係なく、2月14日の午前8時に、すべての受信者にメッセージが届きます。
