---
title: 受信者のタイムゾーンでのメッセージの送信
seo-title: 受信者のタイムゾーンでのメッセージの送信
description: 受信者のタイムゾーンでのメッセージの送信
seo-description: 受信者のタイムゾーンでメッセージを送信する方法を説明します。
page-status-flag: 未活性化の
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: スケジューリングメッセージ
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 781904d58f520987e978ad5d1cdc9e34871ca876

---


# 受信者のタイムゾーンでのメッセージの送信{#sending-messages-at-the-recipient-s-time-zone}

日付と時刻が重要なキャンペーンを管理する場合は、各受信者の現地時刻を考慮に入れた配信をスケジュールできます。スケジュールした時点で、メール、SMS、またはプッシュ通知がそれぞれのタイムゾーンで受信されます。

>[!NOTE]
>
>この機能を使用するには、配信対象のすべてのプロファイルに、プロパティのセクションで指定されたタイムゾーンが設定されてい **[!UICONTROL Address]** ることを確認してください。 プロファイルプロパティへのアクセスの詳細については、このセクションを参照して [くださ](../../audiences/using/editing-profiles.md)い。

受信者のタイムゾーンで配信を送信するには、ワークフローでアクティビティを使 **[!UICONTROL Scheduler]** 用することもできます。 詳細は、このページを参照してく [ださい](../../automating/using/scheduler.md)。

次の例では、バレンタインデーにのみ有効な販促コードを世界中のすべてのお客様に送信します。 日中に使用するのに十分な時間を割くには、2月14日の午前8時に、お客様のタイムゾーンに応じてメッセージを受け取る必要があります。

1. タブで、 **[!UICONTROL Marketing activities]** 配信の作成を開始します。この場合は、Eメールを作成します。 配信の作成の詳細については、このセクションを参照してく [ださい](../../channels/using/creating-an-email.md)。
1. バレンタインデーの電子メールをデザインした後、をクリックして配信ダ **[!UICONTROL Create]** ッシュボードにアクセスします。 電子メールの設計の詳細については、このページを参照して [ください](../../designing/using/personalization.md#example-email-personalization)。

   ![](assets/send-time_opt_valentine_1.png)

1. 搬送ダッシュボードで、ブロックを選択 **[!UICONTROL Schedule]** します。

   ![](assets/send-time_opt_valentine_2.png)

1. 以下で指定したオ **[!UICONTROL Messages to be sent automatically on the date]** プションを選択します。 次に、フィ **[!UICONTROL Start sending from]** ールドに連絡日を設定します。この場合は、2月14日の午前8時に連絡日を設定し、すべての受信者がバレンタインデーに連絡を受け取るようにします。

   ![](assets/send-time_opt_valentine.png)

1. フィールド **[!UICONTROL Time zone of the contact date]** で、デフォルトで配信を送信するタイムゾーンを選択します。

   プロファイルをとして残し **[!UICONTROL Time zone]** た場合は、こ **[!UICONTROL Default]**&#x200B;こで選択したタイムゾーンに応じて、受信者が配信を受け取ります。

1. ドロップダウ **[!UICONTROL Optimize the sending time per recipient]** ンメニューからを選択しま **[!UICONTROL Send at the recipient's time zone]**&#x200B;す。 これにより、受信者は2月14日にバレンタインデーのメールを受け取ることができます。

   ![](assets/send-time_opt_valentine_3.png)

1. 配信のスケジュールを確認したら、ボタンをクリックしてから配 **[!UICONTROL Prepare]** 信をクリ **[!UICONTROL Confirm]** ックします。

   少なくとも24時間前に送信を確認してください。 それ以外の場所によっては、実際のバレンタインデーイベントの前に配達を受け取る受信者もいる場合があります。

   ![](assets/send-time_opt_valentine_4.png)

どこにいようと、2月14日の午前8時に、現地時間にメッセージが届きます。
