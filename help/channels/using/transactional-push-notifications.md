---
title: トランザクションプッシュ通知
description: Adobe Campaign Standardでトランザクションプッシュ通知を送信する方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 61988c1d-d538-47b1-94c1-f3fbdf314b65
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 3%

---

# トランザクションプッシュ通知{#transactional-push-notifications}

Adobe Campaignを使用すると、iOSやAndroidのモバイルデバイスでトランザクションプッシュ通知を送信できます。 これらのメッセージは、Experience Cloud Mobile SDK を利用してAdobe Campaignにセットアップしたモバイルアプリケーションで受信されます。

>[!NOTE]
>
>プッシュチャネルはオプションです。 使用許諾契約書を確認してください。標準のプッシュ通知について詳しくは、[ プッシュ通知について ](../../channels/using/about-push-notifications.md) を参照してください。

トランザクションプッシュ通知を送信するには、それに応じてAdobe Campaignを設定する必要があります。 [ モバイルアプリケーションの設定 ](../../administration/using/configuring-a-mobile-application.md) を参照してください。

2 種類のトランザクションプッシュ通知を送信できます。

* [イベントをターゲットにしたトランザクションプッシュ通知](#transactional-push-notifications-targeting-an-event)
* [ プロファイルをターゲットとするトランザクションプッシュ通知 ](#transactional-push-notifications-targeting-a-profile) Adobe Campaign データベースから

## イベントをターゲットにしたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-an-event}

Adobe Campaignを使用すると、モバイルアプリケーションから通知を受け取ることをオプトインしたすべてのユーザーに **匿名のトランザクションプッシュ通知** を送信できます。

この場合、**イベント自体に含まれるデータは、配信ターゲットの定義に使用されます** のみです。 Adobe Campaign統合プロファイルデータベースのデータは利用されません。

### イベントベースのトランザクションプッシュ通知の設定 {#configuring-event-based-transactional-push-notification}

モバイルアプリケーションからの通知の受信をオプトインしたすべてのユーザーにトランザクションプッシュ通知を送信するには、まずイベント自体に含まれるデータをターゲットにするイベントを作成し、設定する必要があります。

>[!NOTE]
>
>引き続き、[ イベント属性 ](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) （イベントからのデータ）と [ イベントエンリッチメント ](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) （Campaign データベースからのデータ）を使用して、イベントベースのトランザクションプッシュ通知のコンテンツをパーソナライズできます。 [ 以下の例 ](#sending-event-based-transactional-push-notification) を参照してください。

イベントには、次の 3 つの要素を含める必要があります。

* **登録トークン**:1 つのモバイルアプリケーションと 1 つのデバイスのユーザー ID Adobe Campaign データベースのプロファイルに対応していない可能性があります。
* **モバイルアプリケーション名** （すべてのデバイス（AndroidおよびiOS）に対応）。 これは、ユーザーのデバイスでプッシュ通知を受け取るために使用される、Adobe Campaignで設定されたモバイルアプリケーションの ID です。 詳しくは、[ モバイルアプリケーションの設定 ](../../administration/using/configuring-a-mobile-application.md) を参照してください。
* **プッシュプラットフォーム** （Androidの場合は「gcm」、iOSの場合は「apns」）。

イベントを設定するには、次の手順に従います。

1. イベント設定を作成する場合は、**[!UICONTROL Push notification]** チャネルと **[!UICONTROL Real-time event]** ターゲティングディメンションを選択します（[ イベントの作成 ](../../channels/using/configuring-transactional-event.md#creating-an-event) を参照）。
1. イベントにフィールドを追加します。 これにより、トランザクションメッセージをパーソナライズできます（[ イベント属性の定義 ](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) を参照）。 この例では、「gateNumber」、「lastname」および「firstname」フィールドを定義します。
1. また、メッセージのコンテンツをエンリッチメントすることもできます。 それには、イベント設定にリンクしたテーブルからフィールドを追加します（「[ イベントのエンリッチメント ](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)」を参照）。

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [ イベントのプレビューと公開 ](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   イベントをプレビューする場合、REST API には、配信のターゲットとして使用される「registrationToken」、「application」および「pushPlatform」属性が含まれています。

   ![](assets/message-center_push_api.png)

   イベントが公開されると、新規イベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成したメッセージを変更して公開できるようになりました（[ この節 ](#sending-event-based-transactional-push-notification) を参照）。

1. イベントを Web サイトに統合します（[ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照）。

### イベントベースのトランザクションプッシュ通知の送信 {#sending-event-based-transactional-push-notification}

例えば、ある航空会社は、モバイルアプリケーションのユーザーを搭乗用の関連ゲートに進めるように招待したいとします。

会社は、1 つのモバイルアプリケーションを使用して、1 つのデバイスを通じて、ユーザーごとに 1 つのトランザクションプッシュ通知（登録トークンで識別）を送信します。

1. 作成されたトランザクションメッセージに移動して編集します。 [ トランザクションメッセージへのアクセス ](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) を参照してください。

   ![](assets/message-center_push_message.png)

1. **[!UICONTROL Content]** ブロックをクリックして、メッセージのタイトルと本文を変更します。

1. パーソナライゼーションフィールドを挿入して、イベントの作成時に定義した要素を追加できます（[ イベント属性の定義 ](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) を参照）。

   ![](assets/message-center_push_content.png)

   これらのフィールドを検索するには、項目の横にある鉛筆をクリックして「**[!UICONTROL Insert personalization field]**」をクリックし、**[!UICONTROL Context]**/**[!UICONTROL Real-time event]**/**[!UICONTROL Event context]** を選択します。

   ![](assets/message-center_push_personalization.png)

   プッシュ通知コンテンツの編集について詳しくは、[ プッシュ通知の準備と送信 ](../../channels/using/preparing-and-sending-a-push-notification.md) を参照してください。

1. Adobe Campaign Database から追加情報を使用する場合は、トランザクションメッセージのコンテンツもエンリッチメントできます（[ イベントのエンリッチメント ](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) を参照）。

1. 変更を保存し、メッセージを公開します。[トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。

1. Adobe Campaign Standard REST API を使用し、Android（gcm）上の 1 つのモバイルアプリケーション（WeFlight）を使用して、イベントを登録トークン（ABCDEF123456789）に送信します。このトークンには、ボーディングデータが含まれます。

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   イベントのトリガーを外部システムに統合する方法について詳しくは、[ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照してください。

登録トークンが存在する場合、対応するユーザーは、次の内容を含むトランザクションプッシュ通知を受け取ります。

*「こんにちは、ジェーン・グリーンさん、搭乗が始まりました。 B18 ゲートに進んでください」*

## プロファイルをターゲットにしたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-a-profile}

トランザクションプッシュ通知 **モバイルアプリケーションを購読しているAdobe Campaign プロファイルに送信** できます。 この配信には、Adobe Campaign データベースから直接取得した受信者の名などの [ パーソナライゼーションフィールド ](../../designing/using/personalization.md#inserting-a-personalization-field) を含めることができます。

この場合、イベントには、（Adobe Campaign データベースからのプロファイルとの紐付けを許可する **いくつかのフィールドが含まれている必要があ** ます。

プロファイルをターゲティングする場合、モバイルアプリケーションとデバイスごとに 1 つのトランザクションプッシュ通知が送信されます。 例えば、Adobe Campaign ユーザーが 2 つのアプリケーションを購読すると、このユーザーに 2 つの通知が届きます。 ユーザーが 2 つの異なるデバイスで同じアプリケーションを購読した場合、このユーザーは各デバイスで通知を受け取ります。

プロファイルが購読しているモバイルアプリケーションは、このプロファイルの「**[!UICONTROL Mobile App Subscriptions]**」タブに表示されます。 このタブにアクセスするには、プロファイルを選択し、右側の「**[!UICONTROL Edit profile properties]**」ボタンをクリックします。

![](assets/push_notif_subscriptions.png)

プロファイルへのアクセスと編集について詳しくは、[ プロファイルについて ](../../audiences/using/about-profiles.md) を参照してください。

### プロファイルベースのトランザクションプッシュ通知の設定 {#configuring-profile-based-transactional-push-notification}

モバイルアプリケーションを購読しているAdobe Campaign プロファイルにトランザクションプッシュ通知を送信するには、まず、Adobe Campaign データベースをターゲットとするイベントを作成し、設定する必要があります。

1. イベント設定を作成する場合は、**[!UICONTROL Push notification]** チャネルと **[!UICONTROL Profile]** ターゲティングディメンションを選択します（[ イベントの作成 ](../../channels/using/configuring-transactional-event.md#creating-an-event) を参照）。

   デフォルトでは、トランザクションプッシュ通知は、受信者が購読しているすべてのモバイルアプリケーションに送信されます。 特定のモバイルアプリケーションにプッシュ通知を送信するには、リストでプッシュ通知を選択します。 その他のモバイルアプリケーションは、メッセージのターゲットとなりますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. トランザクションメッセージをパーソナライズする場合は、イベントにフィールドを追加します（[ イベント属性の定義 ](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) を参照）。

   >[!NOTE]
   >
   >エンリッチメントを作成するには、少なくとも 1 つのフィールドを追加する必要があります。 Adobe Campaign データベースからパーソナライゼーションフィールドを使用できるので、**名** や **姓** など、他のフィールドを作成する必要はありません。

1. エンリッチメントを作成して、イベントを **[!UICONTROL Profile]** リソースにリンクし（[ イベントのエンリッチメント ](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) を参照）、このエンリッチメントを **[!UICONTROL Targeting enrichment]** として選択します。

   >[!IMPORTANT]
   >
   >この手順は、プロファイルベースのイベントに必須です。

1. [ イベントのプレビューと公開 ](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   イベントのプレビュー時、REST API には、**[!UICONTROL Profile]** リソースから取得される登録トークン、アプリケーション名、プッシュプラットフォームを指定する属性が含まれていません。

   イベントが公開されると、新規イベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成したメッセージを変更して公開できるようになりました（[ この節 ](#sending-profile-based-transactional-push-notification) を参照）。

1. イベントを Web サイトに統合します（[ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照）。

### プロファイルベースのトランザクションプッシュ通知の送信 {#sending-profile-based-transactional-push-notification}

例えば、ある航空会社が、モバイルアプリケーションを購読しているすべてのAdobe Campaign ユーザーに、搭乗のための最後の呼び出しを送信したいとします。

1. 作成されたトランザクションメッセージに移動して編集します。 [ トランザクションメッセージへのアクセス ](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) を参照してください。

1. **[!UICONTROL Content]** ブロックをクリックして、メッセージのタイトルと本文を変更します。

   リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズできます。 [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)を参照してください。

   プッシュ通知コンテンツの編集について詳しくは、[ プッシュ通知の準備と送信 ](../../channels/using/preparing-and-sending-a-push-notification.md) を参照してください。

1. 変更を保存し、メッセージを公開します。[トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。
1. Adobe Campaign Standard REST API を使用して、イベントをプロファイルに送信します。

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

イベントのトリガーを外部システムに統合する方法について詳しくは、[ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照してください。

対応するユーザーは、Adobe Campaign データベースから取得されたすべてのパーソナライゼーション要素を含むトランザクションプッシュ通知を受け取ります。

>[!NOTE]
>
>登録トークン、アプリケーション、プッシュプラットフォームのフィールドはありません。 この例では、紐付けはメールフィールドで実行されます。

## トランザクションプッシュ通知でのターゲットマッピングの変更 {#change-target-mapping}

トランザクションプッシュ通知では、特定の [ ターゲットマッピング ](../../administration/using/target-mappings-in-campaign.md) を使用します。このマッピングには、このタイプの配信の送信に必要な技術設定が含まれています。

このターゲットマッピングを変更するには、次の手順に従います。

1. トランザクションメッセージリストから、プッシュ通知を選択します。

1. メッセージダッシュボードで、「**[!UICONTROL Edit properties]**」ボタンをクリックします。

   ![](assets/message-center_push_edit.png)

1. 「**[!UICONTROL Advanced parameters]**」セクションを展開します。

1. 「**[!UICONTROL Select a 'Target mapping' element]**」をクリックします。

   ![](assets/message-center_push_target-mapping.png)

1. リストからターゲットマッピングを選択します。

   >[!NOTE]
   >
   >**プロファイルベース** のトランザクションプッシュ通知を送信する際に最適な配信準備時間とパフォーマンスを得るには、**[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]** ターゲットマッピングを使用します。

   ![](assets/message-center_push_target-mapping_change.png)

1. 変更を確認し、メッセージを公開します。 [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。

   >[!IMPORTANT]
   >
   >変更を有効にするには、メッセージを再度公開する必要があります。そうしないと、以前のターゲットマッピングが引き続き使用されます。


