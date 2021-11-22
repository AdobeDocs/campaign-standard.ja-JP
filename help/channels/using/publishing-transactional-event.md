---
title: トランザクションイベントの公開
description: トランザクションイベント設定のプレビュー、公開、非公開および削除方法について説明します。
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

1 回 [設定](../../channels/using/configuring-transactional-event.md) が完了したら、イベントを公開する準備が整います。 イベントのプレビュー、公開、非公開、削除の手順を以下に示します。

>[!IMPORTANT]
>
>のみ [機能管理者](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->イベント設定を公開するための適切な権限を持っている。

イベント設定の公開と非公開を含む、トランザクションメッセージの公開プロセス全体を示すグラフは、 [この節](../../channels/using/publishing-transactional-message.md).

公開が完了したら、次の手順に従います。
* 対応するトランザクションメッセージが自動的に作成されます。 詳しくは、 [トランザクションメッセージの編集](../../channels/using/editing-transactional-message.md).
* Web サイト開発者が使用する API がデプロイされ、トランザクションイベントを送信できるようになりました。 詳しくは、 [イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## イベントのプレビューと公開 {#previewing-and-publishing-the-event}

イベントを使用する前に、イベントをプレビューして公開する必要があります。

1. 次をクリック： **[!UICONTROL API preview]** ボタンをクリックして、Web サイト開発者が使用する REST API のシミュレーションを表示します。

   イベントが公開されると、このボタンを使用して、実稼働環境で API のプレビューを確認することもできます。 詳しくは、 [イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API は、選択したチャネルと選択したターゲティングディメンションに応じて変わります。 様々な設定について詳しくは、 [この節](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. クリック **[!UICONTROL Publish]** 公開を開始します。

   ![](assets/message-center_pub.png)

   Web サイト開発者が使用する API がデプロイされ、トランザクションイベントを送信できるようになりました。

1. パブリッシュログは、対応するタブで表示できます。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >イベントを変更するたびに、 **[!UICONTROL Publish]** を再度生成して、web サイト開発者が使用する更新された REST API を生成します。

   イベントが公開されると、 [トランザクションメッセージ](../../channels/using/editing-transactional-message.md) 新しいイベントにリンクすると、自動的に作成されます。

1. このトランザクションメッセージには、左側の領域にあるリンクを通じて直接アクセスできます。

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >イベントがトランザクションメッセージをトリガーで送信するには、作成したばかりのメッセージを変更して公開する必要があります。 詳しくは、 [編集中](../../channels/using/editing-transactional-message.md) および [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md) セクション。 また、 [このトリガーイベントを統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を web サイトに追加します。

1. Adobe Campaignがこのイベント設定に関連するイベントの受信を開始したら、 **[!UICONTROL Latest transactional events]** 下のリンク **[!UICONTROL History]** セクションを参照して、サードパーティのサービスによって送信され、Adobe Campaignで処理された最新のイベントにアクセスします。

![](assets/message-center_latest-events.png)

イベントは（JSON 形式で）最新のものから最も古いものへと一覧表示されます。 このリストを使用すると、制御やデバッグの目的で、イベントのコンテンツやステータスなどのデータを確認できます。

## イベントの非公開 {#unpublishing-an-event}

この **[!UICONTROL Unpublish]** ボタンをクリックすると、イベントの公開をキャンセルできます。これにより、以前に作成したイベントに対応するリソースが REST API から削除されます。

これで、Web サイトを通じてイベントがトリガーされた場合でも、対応するメッセージは送信されなくなり、データベースには保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージを既に公開している場合は、トランザクションメッセージの公開もキャンセルされます。 詳しくは、 [トランザクションメッセージの非公開](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

次をクリック： **[!UICONTROL Publish]** ボタンをクリックして新しい REST API を生成します。

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## イベントの削除 {#deleting-an-event}

イベントを非公開にした後、またはイベントがまだ公開されていない場合は、イベント設定リストから削除できます。 手順は次のとおりです。

1. 次をクリック： **Adobe** ロゴ（左上隅）に移動し、「 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. 目的のイベント設定にマウスを移動し、 **[!UICONTROL Delete element]** 」ボタンをクリックします。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >イベント設定に **[!UICONTROL Draft]** ステータスに設定されていない場合、削除できません。 この **[!UICONTROL Draft]** ステータスは、まだ公開されていないイベントまたはまだ公開されていないイベントに適用されます [非公開](#unpublishing-an-event).

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>公開済みで既に使用されているイベント設定を削除すると、対応するトランザクションメッセージと、その送信およびトラッキングログも削除されます。
