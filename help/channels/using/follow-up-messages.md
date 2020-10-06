---
title: フォローアップメッセージ
description: フォローアップメッセージを作成して公開する方法を説明します。
page-status-flag: never-activated
uuid: d2a17da2-e935-420a-8531-78ed6a1fe68b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 9615e369-754f-4f6a-a1b1-14462f946666
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 5%

---


# フォローアップメッセージ{#follow-up-messages}

特定のトランザクションメッセージを受け取った顧客にフォローアップメッセージを送信できます。 これを行うには、対応するイベントをターゲットにしたワークフローを設定する必要があります。

「 [トランザクションメッセージングの動作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) 」の節で説明した例を再利用します。買い物かごに商品を追加したが、購入を経験せずにサイトを離れたユーザーに、買い物かごの放棄の電子メールが送信されます。

買い物かごの放棄の通知を受け取ったが、3日後に買い物かごを開かなかったすべての顧客に、わかりやすいリマインダーを送信したい。

関係する各顧客は、最初に送信された電子メールで使用されたのと同じデータに基づくフォローアップメッセージを受け取ります。

## フォローアップメッセージへのアクセス {#accessing-the-follow-up-messages}

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) above), the corresponding transactional message and follow-up message are created automatically.

The configuration steps are presented in the [Configuring an event to send a follow-up message](../../administration/using/configuring-transactional-messaging.md#configuring-an-event-to-send-a-follow-up-message) section.

ワークフロー内のイベントを処理するには、配信テンプレートが必要です。 ただし、イベントを公開する場合、作成された [トランザクションメッセージ](../../channels/using/event-transactional-messages.md) はテンプレートとして使用できません。 したがって、このイベントタイプをサポートし、ワークフローのテンプレートとして使用するために、特定のフォローアップ配信テンプレートを作成する必要があります。

このテンプレートにアクセスするには：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 左側のペインの **[!UICONTROL Follow-up messages]** ボックスをチェックします。

   ![](assets/message-center_follow-up-search.png)

フォローアップメッセージのみが表示されます。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、**[!UICONTROL Administrators (all units)]**&#x200B;セキュリティグループに属している必要があります。

## フォローアップメッセージの送信 {#sending-a-follow-up-message}

作成したフォローアップ配信テンプレートをワークフローで使用して、フォローアップメッセージを送信できます。

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。

   [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow and open it. 実行頻度を1日に1回に設定します。

   スケジューラーアクティビティは、 [スケジューラー](../../automating/using/scheduler.md) ・セクションに表示されます。

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. プロファイルリソース以外のリソースに対してクエリを実行するには、アクティビティの **[!UICONTROL Properties]** タブに移動し、ドロップダウン **[!UICONTROL Resource]** リストをクリックします。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >デフォルトでは、このアクティビティはプロファイルを検索するように事前設定されています。

1. ターゲットするイベントを選択して、このイベントのデータにのみアクセスできるようにします。

   ![](assets/message-center_follow-up-query-resource.png)

1. アクティビティの **[!UICONTROL Target]** タブに移動し、パレットから **[!UICONTROL Delivery logs (logs)]** 要素をワークスペースにドラッグ&amp;ドロップします。

   ![](assets/message-center_follow-up-delivery-logs.png)

   電子メール **[!UICONTROL Exists]** を受信したすべての顧客をターゲットする場合に選択します。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 要素をパレットからワークスペースに移動し、電子メールを開かなかったすべての顧客をターゲット **[!UICONTROL Tracking logs (tracking)]****[!UICONTROL Does not exist]** するように選択します。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. ターゲットにするイベント(この例では&#x200B;**買い物かごの放棄** )をパレットからワークスペースにドラッグ&amp;ドロップします。 次に、3日前に送信されたすべてのメッセージをターゲットするルールを定義します。

   ![](assets/message-center_follow-up-created.png)

   つまり、ワークフローの実行の3日前にトランザクションメッセージを受け取り、まだワークフローを開いていないすべての受信者がターゲットになります。

   Click **[!UICONTROL Confirm]** to save the query.

1. Drag and drop an **Email delivery** activity into your workflow.

   電子メール配信アクティビティは、「 [電子メール配信](../../automating/using/email-delivery.md) 」セクションに表示されます。

   ![](assets/message-center_follow-up-workflow.png)

   また、 [SMS配信](../../automating/using/sms-delivery.md) 、 [モバイルアプリ配信](../../automating/using/push-notification-delivery.md) アクティビティを使用することもできます。 この場合、イベント設定を作成する際に、 **[!UICONTROL Mobile (SMS)]** または **[!UICONTROL Mobile application]** チャネルを選択していることを確認してください。 詳しくは、[イベントの作成](../../administration/using/configuring-transactional-messaging.md#creating-an-event)を参照してください。

1. Open the **Email delivery** activity. 作成ウィザードで、 **[!UICONTROL Follow-up messages]** ボックスをオンにし、イベントの発行後に作成されたフォローアップ配信テンプレートを選択します。

   ![](assets/message-center_follow-up-template.png)

1. フォローアップメッセージの内容では、パーソナライゼーションフィールドを追加することで、イベントの内容を活用できます。

   ![](assets/message-center_follow-up-content.png)

1. イベントの作成時に定義したフィールドを探すには、 **[!UICONTROL Context]** / **[!UICONTROL Real-time event]** /を選択し **[!UICONTROL Event context]**&#x200B;ます。 See [Personalizing a transactional message](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   つまり、イベントの初回送信時に使用したリッチデータを含む同じコンテンツを利用して、パーソナライズされたフレンドリリマインダーを作成できます。

1. アクティビティと開始をワークフローに保存します。

ワークフローが開始されると、3日前に買い物かごの放棄通知を受け取ったが開かなかったすべての顧客に、同じデータに基づくフォローアップメッセージが表示されます。

>[!NOTE]
>
>イベント設定の作成時に **[!UICONTROL Profile]** ターゲティングディメンションを選択した場合は、Adobe Campaignのマーケティングデータベースもフォローアップメッセージとして使用されます。 [プロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md)を参照してください。
