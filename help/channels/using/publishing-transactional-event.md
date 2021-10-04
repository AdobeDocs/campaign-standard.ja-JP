---
title: トランザクションイベントの公開
description: トランザクションイベント設定のプレビュー、公開、非公開および削除の方法について説明します。
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

[ 設定 ](../../channels/using/configuring-transactional-event.md) が完了すると、イベントの公開準備が整います。 イベントのプレビュー、公開、非公開、削除の手順を以下に示します。

>[!IMPORTANT]
>
>[ 機能管理者 ](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) --> のみが、イベント設定を公開する適切な権限を持っています。

イベント設定の公開と非公開を含む、トランザクションメッセージの公開プロセス全体を示す表は、[ この節 ](../../channels/using/publishing-transactional-message.md) で参照できます。

公開が完了したら、次の手順に従います。
* 対応するトランザクションメッセージが自動的に作成されます。 [ トランザクションメッセージの編集 ](../../channels/using/editing-transactional-message.md) を参照してください。
* Web サイト開発者が使用する API がデプロイされ、トランザクションイベントを送信できるようになりました。 [ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照してください。

## イベントのプレビューと公開 {#previewing-and-publishing-the-event}

このイベントを使用するには、イベントをプレビューして公開する必要があります。

1. 「 **[!UICONTROL API preview]** 」ボタンをクリックして、Web サイト開発者が公開する前に使用する REST API のシミュレーションを表示します。

   イベントが公開されると、このボタンを使用して実稼動環境で API のプレビューを確認することもできます。 [ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照してください。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API は、選択したチャネルと選択したターゲティングディメンションに応じて変わります。 様々な設定の詳細については、[ この節 ](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations) を参照してください。

1. **[!UICONTROL Publish]** をクリックして公開を開始します。

   ![](assets/message-center_pub.png)

   Web サイト開発者が使用する API がデプロイされ、トランザクションイベントを送信できるようになりました。

1. パブリッシュログは、対応するタブで確認できます。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >イベントを変更するたびに、 **[!UICONTROL Publish]** を再度クリックして、Web サイト開発者が使用する更新済みの REST API を生成する必要があります。

   イベントが公開されると、新しいイベントにリンクされた [ トランザクションメッセージ ](../../channels/using/editing-transactional-message.md) が自動的に作成されます。

1. このトランザクションメッセージには、左側の領域にあるリンクを通じて直接アクセスできます。

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >イベントがトランザクションメッセージをトリガーで送信するには、作成したばかりのメッセージを変更して公開する必要があります。 [](../../channels/using/editing-transactional-message.md) の編集および [ トランザクションメッセージの公開 ](../../channels/using/publishing-transactional-message.md) の節を参照してください。 また、このトリガーイベント ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を Web サイトに [ 統合する必要があります。

1. Adobe Campaignがこのイベント設定に関連するイベントの受信を開始したら、「**[!UICONTROL History]**」セクションの下の「**[!UICONTROL Latest transactional events]**」リンクをクリックして、サードパーティのサービスによって送信され、Adobe Campaignで処理された最新のイベントにアクセスできます。

![](assets/message-center_latest-events.png)

イベントは（JSON 形式で）最新のものから最も古いものへと一覧表示されます。 このリストを使用すると、制御やデバッグの目的で、イベントのコンテンツやステータスなどのデータを確認できます。

## イベントの非公開 {#unpublishing-an-event}

「**[!UICONTROL Unpublish]**」ボタンをクリックすると、イベントの公開をキャンセルできます。このボタンにより、以前に作成したイベントに対応するリソースが REST API から削除されます。

これで、Web サイトを通じてイベントがトリガーされた場合でも、対応するメッセージは送信されなくなり、データベースには保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージを既に公開している場合は、トランザクションメッセージの公開もキャンセルされます。 [ トランザクションメッセージの非公開 ](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) を参照してください。

**[!UICONTROL Publish]** ボタンをクリックして、新しい REST API を生成します。

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## イベントの削除 {#deleting-an-event}

イベントを非公開にした後、またはイベントがまだ公開されていない場合は、イベント設定リストから削除できます。 手順は次のとおりです。

1. 左上隅の **Adobe** ロゴをクリックし、**[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** / **[!UICONTROL Event configuration]** を選択します。
1. 目的のイベント設定にマウスを移動し、**[!UICONTROL Delete element]** ボタンを選択します。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >イベント設定のステータスが **[!UICONTROL Draft]** であることを確認してください。そうしないと、削除できません。 **[!UICONTROL Draft]** ステータスは、まだ公開されていないイベント、または [ 非公開 ](#unpublishing-an-event) のイベントに適用されます。

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>公開済みで既に使用されているイベント設定を削除すると、対応するトランザクションメッセージとその送信およびトラッキングログも削除されます。
