---
title: フォローアップメッセージ
description: フォローアップメッセージを作成、管理、送信する方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 2%

---

# フォローアップメッセージ {#follow-up-messages}

フォローアップメッセージは、事前に定義されたマーケティング配信テンプレートで、ワークフロー内で使用して、特定のトランザクションメッセージの受信者に別のコミュニケーションを送信できます。

[ トランザクションメッセージの動作原則 ](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) の節で説明した例を再利用します。買い物かごの放棄に関する電子メールは、商品を買い物かごに追加したが、購入を経ずにサイトを離れた Web サイトユーザーに送信されます。

買い物かごの放棄通知を受け取ったが、3 日後に買い物かごを開封しなかったすべての顧客に、わかりやすいリマインダーを送信する場合。 受信者には、最初に送信された E メールと同じデータに基づいて、フォローアップメッセージが届きます。

## フォローアップメッセージを送信するためのイベントの設定 {#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージを送信するには、まず、既に受信したトランザクションメッセージに対応するイベントを適切に設定する必要があります。

1. 作成したのと同じイベント設定を使用して、イベントトランザクションメッセージを送信します。 [ トランザクションイベントの設定 ](../../channels/using/configuring-transactional-event.md) を参照してください。
1. イベントを設定する場合は、イベントを公開する前に **[!UICONTROL Create follow-up delivery template for this event]** ボックスをオンにします。

   ![](assets/message-center_follow-up-checkbox.png)

1. [イベントをプレビューして公開します](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージとフォローアップ配信テンプレートが自動的に作成されます。 フォローアップメッセージを送信する手順については、[ この節 ](#sending-a-follow-up-message) で詳しく説明します。

## フォローアップメッセージへのアクセス {#accessing-the-follow-up-messages}

ワークフロー内のイベントを処理するには、配信テンプレートが必要です。 ただし、イベントを公開する場合、作成された [ トランザクションメッセージ ](../../channels/using/editing-transactional-message.md) はテンプレートとして使用できません。 したがって、このイベントタイプをサポートし、ワークフローのテンプレートとして使用するために設計された、特定のフォローアップ配信テンプレートを作成する必要があります。

このテンプレートにアクセスするには：

1. 左上隅の **Adobe** ロゴをクリックします。
1. **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** を選択します。
1. 左側のウィンドウで **[!UICONTROL Follow-up messages]** ボックスをオンにします。

   ![](assets/message-center_follow-up-search.png)

フォローアップメッセージのみが表示されます。

>[!IMPORTANT]
>
>トランザクションメッセージにアクセスして編集できるのは、[ 管理 ](../../administration/using/users-management.md#functional-administrators) の役割を持つユーザーだけです。

## フォローアップメッセージの送信 {#sending-a-follow-up-message}

フォローアップ配信テンプレートを作成したら、ワークフローでそのテンプレートを使用してフォローアップメッセージを送信できます。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。

   [ ワークフローの構築 ](../../automating/using/building-a-workflow.md#creating-a-workflow) を参照してください。

1. **[!UICONTROL Scheduler]** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 実行頻度を 1 日に 1 回に設定します。

   スケジューラーアクティビティについては、[ スケジューラー ](../../automating/using/scheduler.md) の節で説明しています。

1. **[!UICONTROL Query]** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。

   「クエリ」アクティビティについては、[ クエリ ](../../automating/using/query.md) の節で説明しています。

1. プロファイルリソース以外のリソースに対してクエリを実行するには、アクティビティの「**[!UICONTROL Properties]**」タブに移動し、「**[!UICONTROL Resource]**」ドロップダウンリストをクリックします。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >デフォルトでは、このアクティビティはプロファイルを検索するように事前設定されています。

1. 対象のイベントを選択して、このイベントのデータにのみアクセスできるようにします。

   ![](assets/message-center_follow-up-query-resource.png)

1. アクティビティの「**[!UICONTROL Target]**」タブに移動し、パレットからワークスペースに **[!UICONTROL Delivery logs (logs)]** 要素をドラッグ&amp;ドロップします。

   ![](assets/message-center_follow-up-delivery-logs.png)

   **[!UICONTROL Exists]** を選択して、E メールを受信したすべての顧客をターゲットにします。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. パレットの **[!UICONTROL Tracking logs (tracking)]** 要素をワークスペースに移動し、**[!UICONTROL Does not exist]** を選択して、電子メールを開封しなかったすべての顧客をターゲットにします。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. ターゲット設定するイベント（この例では **買い物かごの放棄**）をパレットからワークスペースにドラッグ&amp;ドロップします。 次に、3 日前に送信されたすべてのメッセージをターゲットにするルールを定義します。

   ![](assets/message-center_follow-up-created.png)

   つまり、ワークフローの実行の 3 日前にトランザクションメッセージを受け取り、まだ開封していないすべての受信者がターゲットになります。

   **[!UICONTROL Confirm]** をクリックしてクエリを保存します。

1. 「**E メール配信**」アクティビティをワークフローにドラッグ&amp;ドロップします。

   E メール配信アクティビティについては、[E メール配信 ](../../automating/using/email-delivery.md) の節で説明しています。

   ![](assets/message-center_follow-up-workflow.png)

   [SMS 配信 ](../../automating/using/sms-delivery.md) または [ プッシュ通知配信 ](../../automating/using/push-notification-delivery.md) アクティビティを使用することもできます。 この場合、イベント設定を作成する際は、必ず **[!UICONTROL Mobile (SMS)]** チャネルまたは **[!UICONTROL Mobile application]** チャネルを選択してください。 詳しくは、[イベントの作成](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照してください。

1. **E メール配信** アクティビティを開きます。 作成ウィザードで、「 **[!UICONTROL Follow-up messages]** 」ボックスをオンにし、イベントの公開後に作成したフォローアップ配信テンプレートを選択します。

   ![](assets/message-center_follow-up-template.png)

1. フォローアップメッセージのコンテンツでは、パーソナライゼーションフィールドを追加して、イベントのコンテンツを活用できます。

   ![](assets/message-center_follow-up-content.png)

1. イベントの作成時に定義したフィールドを見つけるには、 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** を選択します。 [ トランザクションメッセージのパーソナライズ ](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message) を参照してください。

   ![](assets/message-center_follow-up-personalization.png)

   つまり、イベントの初回送信時に使用した、エンリッチメントされたデータを含む同じコンテンツを活用して、パーソナライズされたわかりやすいリマインダーを作成できます。

1. アクティビティを保存し、ワークフローを開始します。

ワークフローが開始されると、3 日前に買い物かごの放棄通知を受け取ったが、開封しなかったすべての顧客に、同じデータに基づくフォローアップメッセージが届きます。

>[!NOTE]
>
>イベント設定の作成時に **[!UICONTROL Profile]** ターゲティングディメンションを選択した場合は、フォローアップメッセージでAdobe Campaignマーケティングデータベースも利用されます。 [プロファイルトランザクションメッセージ](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)を参照してください。
