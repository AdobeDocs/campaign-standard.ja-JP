---
title: 受信者のタイムゾーンでのメッセージの送信
description: 受信者のタイムゾーンでのメッセージの送信について説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Proofs
role: User
level: Intermediate
exl-id: 48f222bd-9c2f-4eeb-a12b-bbfc62119024
TQID: https://experienceleague.adobe.com/0ZBuZihQqaowNG6y5gzkh5Vpz86e6pjmTRd5bNDPGxg
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 381
ht-degree: 69%

---

# 受信者のタイムゾーンでのメッセージの送信{#sending-messages-at-the-recipient-s-time-zone}

日時が重要なキャンペーンを管理する場合は、各受信者の現地時間を考慮して配信をスケジュールできます。受信者は、スケジュールした時間に、自分のタイムゾーンで電子メール、SMS、プッシュ通知を受け取ります。

>[!NOTE]
>
>この機能を使用するには、配信先となるすべてのプロファイルのタイムゾーンがプロパティの[**[!UICONTROL Address]**]セクションで指定されていることを確認してください。 プロファイルプロパティへのアクセスについて詳しくは、[こちらの節](../../audiences/using/editing-profiles.md)を参照してください。

受信者のタイムゾーンで配信を送信する場合は、ワークフローで「**[!UICONTROL Scheduler]**」アクティビティを使用することもできます。 詳しくは、この[ページ](../../automating/using/scheduler.md)を参照してください。

次の例では、バレンタインデーでのみ有効なプロモーションコードを世界中のすべての顧客に送信します。 日中に使用するのに十分な時間を確保するには、すべての顧客が2月14日の午前8:00時に、タイムゾーンに応じてメッセージを受け取る必要があります。

1. 「**[!UICONTROL Marketing activities]**」タブで、配信（この例ではメール）の作成を開始します。 配信の作成について詳しくは、[こちらの節](../../channels/using/creating-an-email.md)を参照してください。
1. バレンタインデーのメールをデザインしたら、「**[!UICONTROL Create]**」をクリックして配信ダッシュボードにアクセスします。 メールのデザインについて詳しくは、[こちらのページ](../../designing/using/personalization.md#example-email-personalization)を参照してください。

   ![](assets/send-time_opt_valentine_1.png)

1. 配信ダッシュボードで、「**[!UICONTROL Schedule]**」ブロックを選択します。

   ![](assets/send-time_opt_valentine_2.png)

1. 以下に示した「**[!UICONTROL Messages to be sent automatically on the date]**」オプションを選択します。 次に、**[!UICONTROL Start sending from]** フィールドで、連絡日を設定します。この場合は、2月14日の午前8:00時に、バレンタインデーにすべての受信者が受信するように設定します。

   ![](assets/send-time_opt_valentine.png)

1. 「**[!UICONTROL Time zone of the contact date]**」フィールドで、デフォルトの送信タイムゾーンを選択します。

   プロファイルの「**[!UICONTROL Time zone]**」を「**[!UICONTROL Default]**」のままにしておくと、受信者はここで選択されたタイムゾーンで配信を受け取ります。

1. ドロップダウンメニュー&#x200B;**[!UICONTROL Optimize the sending time per recipient]**&#x200B;から、「**[!UICONTROL Send at the recipient's time zone]**」を選択します。 これで、受信者は自分のタイムゾーンの 2 月 14 日にバレンタインデーのメールを受け取ることができます。

   ![](assets/send-time_opt_valentine_3.png)

1. 配信のスケジュールを確認したら、まず「**[!UICONTROL Prepare]**」ボタンをクリックし、次に「**[!UICONTROL Confirm]**」をクリックして配信を確定します。

   少なくとも 24 時間前に送信を確定してください。 24 時間以前に送信を確定しないと、受信者の所在地によっては、実際のバレンタインデーイベントの前に配信が届く場合もあります。

   ![](assets/send-time_opt_valentine_4.png)

受信者の所在地に関係なく、すべての受信者は2月14日の現地時間の午前8:00にメッセージを受け取ります。
