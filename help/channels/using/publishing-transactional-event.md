---
title: トランザクションイベントの公開
description: トランザクションイベント設定をプレビュー、公開、非公開、削除する方法について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 6bcd8dcd-d710-4ca3-937d-bf4339f36069
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 6%

---

# トランザクションイベントの公開 {#publishing-transactional-event}

[ 設定 ](../../channels/using/configuring-transactional-event.md) が完了すると、イベントを公開する準備が整います。 イベントのプレビュー、公開、非公開、削除の手順は次のとおりです。

>[!IMPORTANT]
>
>イベント設定を公開する適切な権限を持つのは [ 機能管理者 ](../../administration/using/users-management.md#functional-administrators) のみです。<!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->

イベント設定の公開や非公開を含む、トランザクションメッセージの公開プロセス全体を示すグラフを [ この節 ](../../channels/using/publishing-transactional-message.md) で利用できます。

公開が完了したら、次の操作を行います。
* 対応するトランザクションメッセージが自動的に作成されます。 [ トランザクションメッセージの編集 ](../../channels/using/editing-transactional-message.md) を参照してください。
* Web サイトの開発者が使用する API がデプロイされ、トランザクションイベントを送信できるようになりました。 [ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照してください。

## イベントのプレビューと公開 {#previewing-and-publishing-the-event}

イベントを使用するには、まずプレビューして公開する必要があります。

1. 「**[!UICONTROL API preview]**」ボタンをクリックして、web サイト開発者が公開前に使用する REST API のシミュレーションを表示します。

   イベントが公開されると、このボタンを使用して、実稼動環境で API のプレビューを確認することもできます。 [ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照してください。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API は、選択したチャネルと選択したターゲティングディメンションに応じて異なります。 様々な設定について詳しくは、[ この節 ](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations) を参照してください。

1. 「**[!UICONTROL Publish]**」をクリックして公開を開始します。

   ![](assets/message-center_pub.png)

   Web サイトの開発者が使用する API がデプロイされ、トランザクションイベントを送信できるようになりました。

1. 公開ログは、対応するタブに表示されます。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >イベントを変更するたびに、**[!UICONTROL Publish]** を再度クリックして、web サイト開発者が使用する更新された REST API を生成する必要があります。

   イベントが公開されると、新しいイベントにリンクされた [ トランザクションメッセージ ](../../channels/using/editing-transactional-message.md) が自動的に作成されます。

1. 左側の領域にあるリンクを介して、このトランザクションメッセージに直接アクセスできます。

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >イベントがトランザクションメッセージの送信をトリガーにするには、作成したメッセージを変更して公開する必要があります。 [ トランザクションメッセージの編集 ](../../channels/using/editing-transactional-message.md) および [ 公開 ](../../channels/using/publishing-transactional-message.md) を参照してください。 また、web サイトに [ このトリガーイベントを組み込む ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) 必要があります。

1. Adobe Campaignがこのイベント設定に関連するイベントの受信を開始したら、「**[!UICONTROL History]**」セクションの下にある「**[!UICONTROL Latest transactional events]**」リンクをクリックして、サードパーティのサービスから送信され、Adobe Campaignによって処理される最新のイベントにアクセスできます。

![](assets/message-center_latest-events.png)

イベント（JSON 形式）は、最新のイベントから古いイベントへと表示されます。 このリストを使用すると、制御やデバッグの目的で、イベントのコンテンツやステータスなどのデータを確認できます。

## イベントの非公開 {#unpublishing-an-event}

「**[!UICONTROL Unpublish]**」ボタンをクリックすると、イベントの公開をキャンセルできます。これにより、以前に作成したイベントに対応するリソースが REST API から削除されます。

これで、Web サイトを通じてイベントがトリガーされた場合でも、対応するメッセージは送信されなくなり、データベースには保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージが既にパブリッシュされている場合、トランザクションメッセージのパブリッシュもキャンセルされます。 [ トランザクションメッセージの非公開 ](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) を参照してください。

「**[!UICONTROL Publish]**」ボタンをクリックして、新しい REST API を生成します。

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## イベントの削除 {#deleting-an-event}

イベントが非公開になっているか、まだ公開されていない場合は、イベント設定リストから削除できます。 手順は次のとおりです。

1. 左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、**&#x200B;[!UICONTROL Marketing plans]&#x200B;**/**&#x200B;[!UICONTROL Transactional messages]&#x200B;**/**&#x200B;[!UICONTROL Event configuration]&#x200B;**を選択します。**
1. 選択したイベント設定にマウスポインターを置いて、「**[!UICONTROL Delete element]**」ボタンを選択します。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >イベント設定のステータスが **[!UICONTROL Draft]** であることを確認します。そうでない場合、イベント設定を削除することはできません。 **[!UICONTROL Draft]** のステータスは、まだ公開されていないイベントまたは [ 非公開 ](#unpublishing-an-event) に適用されます。

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>公開済みで既に使用されているイベント設定を削除すると、対応するトランザクションメッセージとその送信およびトラッキングログも削除されます。
