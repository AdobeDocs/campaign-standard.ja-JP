---
solution: Campaign Standard
product: campaign
title: フォローアップメッセージ
description: フォローアップメッセージを作成して公開する方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 5%

---


# フォローアップメッセージ{#follow-up-messages}

特定のトランザクションメッセージを受け取った顧客にフォローアップメッセージを送信できます。 これを行うには、対応するイベントをターゲットにしたワークフローを設定する必要があります。

「[トランザクションメッセージングの動作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)」の節で説明した例を再利用します。買い物かごに商品を追加したが、購入を経験せずにサイトを離れたユーザーに、買い物かごの放棄の電子メールが送信されます。

買い物かごの放棄の通知を受け取ったが、3日後に買い物かごを開かなかったすべての顧客に、わかりやすいリマインダーを送信したい。

関係する各顧客は、最初に送信された電子メールで使用されたのと同じデータに基づくフォローアップメッセージを受け取ります。

## フォローアップメッセージへのアクセス{#accessing-the-follow-up-messages}

イベントを作成して公開すると（上記の[例](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)に従って買い物かごの放棄が行われた場合）、対応するトランザクションメッセージとフォローアップメッセージが自動的に作成されます。

設定手順は、「[イベントの設定」の「フォローアップメッセージ](../../administration/using/configuring-transactional-messaging.md#configuring-an-event-to-send-a-follow-up-message)を送信するための設定」の節に記載されています。

ワークフロー内のイベントを処理するには、配信テンプレートが必要です。 ただし、イベントを公開する場合、作成された[トランザクションメッセージ](../../channels/using/event-transactional-messages.md)はテンプレートとして使用できません。 したがって、このイベントタイプをサポートし、ワークフローのテンプレートとして使用するために、特定のフォローアップ配信テンプレートを作成する必要があります。

このテンプレートにアクセスするには：

1. 左上隅の&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;ロゴをクリックします。
1. **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;を選択します。
1. 左側のウィンドウの&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;ボックスをチェックします。

   ![](assets/message-center_follow-up-search.png)

フォローアップメッセージのみが表示されます。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、**[!UICONTROL Administrators (all units)]**&#x200B;セキュリティグループに属している必要があります。

## フォローアップメッセージ{#sending-a-follow-up-message}を送信中

作成したフォローアップ配信テンプレートをワークフローで使用して、フォローアップメッセージを送信できます。

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。

   [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。

1. **[!UICONTROL Scheduler]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 実行頻度を1日に1回に設定します。

   スケジューラーアクティビティは、[スケジューラー](../../automating/using/scheduler.md)セクションに表示されます。

1. **[!UICONTROL Query]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。

   クエリアクティビティは、[クエリ](../../automating/using/query.md)セクションに表示されます。

1. プロファイルリソース以外のリソースに対してクエリを実行するには、アクティビティの&#x200B;**[!UICONTROL Properties]**&#x200B;タブに移動し、**[!UICONTROL Resource]**&#x200B;ドロップダウンリストをクリックします。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >デフォルトでは、このアクティビティはプロファイルを検索するように事前設定されています。

1. ターゲットするイベントを選択して、このイベントのデータにのみアクセスできるようにします。

   ![](assets/message-center_follow-up-query-resource.png)

1. アクティビティの「**[!UICONTROL Target]**」タブに移動し、**[!UICONTROL Delivery logs (logs)]**&#x200B;要素をパレットからワークスペースにドラッグ&amp;ドロップします。

   ![](assets/message-center_follow-up-delivery-logs.png)

   **[!UICONTROL Exists]**&#x200B;を選択すると、電子メールを受信したすべての顧客がターゲットされます。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. **[!UICONTROL Tracking logs (tracking)]**&#x200B;要素をパレットからワークスペースに移動し、**[!UICONTROL Does not exist]**&#x200B;を選択して、電子メールを開かなかったすべての顧客をターゲットします。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. ターゲットにするイベント（この例では&#x200B;**買い物かごの放棄**）をパレットからワークスペースにドラッグ&amp;ドロップします。 次に、3日前に送信されたすべてのメッセージをターゲットするルールを定義します。

   ![](assets/message-center_follow-up-created.png)

   つまり、ワークフローの実行の3日前にトランザクションメッセージを受け取り、まだワークフローを開いていないすべての受信者がターゲットになります。

   **[!UICONTROL Confirm]**&#x200B;をクリックしてクエリを保存します。

1. **電子メール配信**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップします。

   電子メール配信アクティビティは、[電子メール配信](../../automating/using/email-delivery.md)セクションに表示されます。

   ![](assets/message-center_follow-up-workflow.png)

   [SMS配信](../../automating/using/sms-delivery.md)または[モバイルアプリ配信](../../automating/using/push-notification-delivery.md)アクティビティを使用することもできます。 この場合、イベント設定を作成する際に、**[!UICONTROL Mobile (SMS)]**&#x200B;または&#x200B;**[!UICONTROL Mobile application]**&#x200B;チャネルを選択していることを確認してください。 詳しくは、[イベントの作成](../../administration/using/configuring-transactional-messaging.md#creating-an-event)を参照してください。

1. **電子メール配信**&#x200B;アクティビティを開きます。 作成ウィザードで、**[!UICONTROL Follow-up messages]**&#x200B;ボックスをオンにし、イベントの発行後に作成されたフォローアップ配信テンプレートを選択します。

   ![](assets/message-center_follow-up-template.png)

1. フォローアップメッセージの内容では、パーソナライゼーションフィールドを追加することで、イベントの内容を活用できます。

   ![](assets/message-center_follow-up-content.png)

1. イベントの作成時に定義したフィールドを探すには、**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**&#x200B;を選択します。 [トランザクションメッセージの個人設定](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)を参照してください。

   ![](assets/message-center_follow-up-personalization.png)

   つまり、イベントの初回送信時に使用したリッチデータを含む同じコンテンツを利用して、パーソナライズされたフレンドリリマインダーを作成できます。

1. アクティビティと開始をワークフローに保存します。

ワークフローが開始されると、3日前に買い物かごの放棄通知を受け取ったが開かなかったすべての顧客に、同じデータに基づくフォローアップメッセージが表示されます。

>[!NOTE]
>
>イベント設定の作成時に&#x200B;**[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを選択した場合は、Adobe Campaignのマーケティングデータベースもフォローアップメッセージとして使用されます。 [プロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md)を参照してください。
