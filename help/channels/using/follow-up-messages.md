---
title: フォローアップメッセージ
description: フォローアップメッセージを作成、管理、送信する方法について説明します。
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

フォローアップメッセージは、ワークフローで特定のトランザクションメッセージの受信者に別の通信を送信するために使用できる、事前定義されたマーケティング配信テンプレートです。

[&#x200B; トランザクションメッセージの動作原理 &#x200B;](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) の節で説明した例を再利用しましょう。買い物かごに製品を追加したが、購入を続行せずにサイトを離れた web サイトのユーザーに、買い物かごの放棄メールが送信されます。

買い物かごの放棄の通知を受信したが、3 日後に開いていなかったすべての顧客にフレンドリなリマインダーを送信します。 最初に送信されたメールと同じデータに基づくフォローアップメッセージが届きます。

## フォローアップメッセージを送信するためのイベントの設定 {#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージを送信するには、まず、既に受信したトランザクションメッセージに対応するイベントを適切に設定する必要があります。

1. イベント トランザクションメッセージを送信するために作成したのと同じイベント設定を使用します。 [&#x200B; トランザクションイベントの設定 &#x200B;](../../channels/using/configuring-transactional-event.md) を参照してください。
1. イベントを設定する場合は、イベントを公開する前に **[!UICONTROL Create follow-up delivery template for this event]** のチェックボックスをオンにします。

   ![](assets/message-center_follow-up-checkbox.png)

1. [&#x200B; イベントのプレビューと公開 &#x200B;](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージとフォローアップ配信テンプレートが自動的に作成されます。 フォローアップメッセージを送信する手順については、[&#x200B; この節 &#x200B;](#sending-a-follow-up-message) を参照してください。

## フォローアップメッセージへのアクセス {#accessing-the-follow-up-messages}

ワークフロー内のイベントを処理するには、配信テンプレートが必要です。 ただし、イベントを公開する場合、作成された [&#x200B; トランザクションメッセージ &#x200B;](../../channels/using/editing-transactional-message.md) はテンプレートとして使用できません。 したがって、このイベントタイプをサポートし、ワークフロー内のテンプレートとして使用するように設計された、特定のフォローアップ配信テンプレートを作成する必要があります。

このテンプレートにアクセスするには：

1. 左上隅の **Adobe** ロゴをクリックします。
1. **[!UICONTROL Resources]**/**[!UICONTROL Templates]**/**[!UICONTROL Delivery templates]** を選択します。
1. 左側のペインの「**[!UICONTROL Follow-up messages]**」ボックスを選択します。

   ![](assets/message-center_follow-up-search.png)

フォローアップメッセージのみが表示されます。

>[!IMPORTANT]
>
>トランザクションメッセージにアクセスして編集できるのは、[&#x200B; 管理 &#x200B;](../../administration/using/users-management.md#functional-administrators) の役割を持つユーザーのみです。

## フォローアップメッセージの送信 {#sending-a-follow-up-message}

フォローアップ配信テンプレートを作成したら、ワークフローでそのテンプレートを使用して、フォローアップメッセージを送信できます。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。

   [&#x200B; ワークフローの作成 &#x200B;](../../automating/using/building-a-workflow.md#creating-a-workflow) を参照してください。

1. **[!UICONTROL Scheduler]** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 実行頻度を 1 日 1 回に設定します。

   スケジューラーアクティビティは、「[&#x200B; スケジューラー &#x200B;](../../automating/using/scheduler.md) セクションに表示されます。

1. **[!UICONTROL Query]** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。

   クエリ アクティビティは、「[&#x200B; クエリ &#x200B;](../../automating/using/query.md)」セクションに表示されます。

1. プロファイルリソース以外のリソースに対してクエリを実行するには、アクティビティの「**[!UICONTROL Properties]**」タブに移動し、「**[!UICONTROL Resource]**」ドロップダウンリストをクリックします。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >デフォルトでは、このアクティビティはプロファイルを検索するように事前設定されています。

1. このイベントのデータにのみアクセスするように、ターゲットにするイベントを選択します。

   ![](assets/message-center_follow-up-query-resource.png)

1. アクティビティの「**[!UICONTROL Target]**」タブに移動し、パレットからワークスペースに **[!UICONTROL Delivery logs (logs)]** 要素をドラッグ&amp;ドロップします。

   ![](assets/message-center_follow-up-delivery-logs.png)

   「**[!UICONTROL Exists]**」を選択すると、メールを受信したすべての顧客がターゲットになります。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. パレットの **[!UICONTROL Tracking logs (tracking)]** 要素をワークスペースに移動し、「**[!UICONTROL Does not exist]**」を選択して、メールを開いていなかったすべての顧客をターゲットにします。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. ターゲットにするイベント（この例では **買い物かごの放棄**）を、パレットからワークスペースにドラッグ&amp;ドロップします。 次に、3 日前に送信されたすべてのメッセージをターゲットにするルールを定義します。

   ![](assets/message-center_follow-up-created.png)

   つまり、ワークフローの実行の 3 日前にトランザクションメッセージを受信し、まだそのメッセージを開いていないすべての受信者がターゲットになります。

   「**[!UICONTROL Confirm]**」をクリックして、クエリを保存します。

1. **メール配信** アクティビティをワークフローにドラッグ&amp;ドロップします。

   メール配信アクティビティは、「[&#x200B; メール配信 &#x200B;](../../automating/using/email-delivery.md) セクションに表示されます。

   ![](assets/message-center_follow-up-workflow.png)

   [SMS 配信 &#x200B;](../../automating/using/sms-delivery.md) または [&#x200B; プッシュ通知配信 &#x200B;](../../automating/using/push-notification-delivery.md) アクティビティを使用することもできます。 この場合、イベント設定を作成する際には、必ず **[!UICONTROL Mobile (SMS)]** チャネルまたは **[!UICONTROL Mobile application]** チャネルを選択してください。 詳しくは、[イベントの作成](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照してください。

1. **メール配信** アクティビティを開きます。 作成ウィザードで、「**[!UICONTROL Follow-up messages]**」チェックボックスをオンにして、イベントの公開後に作成したフォローアップ配信テンプレートを選択します。

   ![](assets/message-center_follow-up-template.png)

1. フォローアップメッセージのコンテンツでは、パーソナライゼーションフィールドを追加することでイベントのコンテンツを活用できます。

   ![](assets/message-center_follow-up-content.png)

1. **[!UICONTROL Context]**/**[!UICONTROL Real-time event]**/**[!UICONTROL Event context]** を選択して、イベントの作成時に定義したフィールドを見つけます。 [&#x200B; トランザクションメッセージのパーソナライズ &#x200B;](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message) を参照してください。

   ![](assets/message-center_follow-up-personalization.png)

   つまり、イベントが初めて送信されたときに使用されたエンリッチメントされたデータを含む同じコンテンツを活用して、パーソナライズされたフレンドリなリマインダーを作成できます。

1. アクティビティを保存し、ワークフローを開始します。

ワークフローが開始されると、3 日前に買い物かごの放棄の通知を受け取ったが開かなかった顧客はすべて、同じデータに基づくフォローアップメッセージを受け取ります。

>[!NOTE]
>
>イベント設定の作成時に **[!UICONTROL Profile]** ターゲティングディメンションを選択した場合、フォローアップメッセージにはAdobe Campaign マーケティングデータベースも使用されます。 [プロファイルトランザクションメッセージ](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)を参照してください。
