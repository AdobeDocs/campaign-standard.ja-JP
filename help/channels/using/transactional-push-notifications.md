---
solution: Campaign Standard
product: campaign
title: トランザクションプッシュ通知
description: Adobe Campaign Standardでトランザクションプッシュ通知を送信する方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: トランザクションメッセージ
role: Business Practitioner
level: Intermediate
exl-id: 61988c1d-d538-47b1-94c1-f3fbdf314b65
source-git-commit: 33d3dc43a64b9670666844a3266e2aa2458a1c40
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 4%

---

# トランザクションプッシュ通知{#transactional-push-notifications}

Adobe Campaignを使用して、iOSおよびAndroidモバイルデバイスでトランザクションプッシュ通知を送信できます。 これらのメッセージは、Mobile SDKを利用して、Adobe Campaignで設定したモバイルアプリケーションでExperience Cloudを受信します。

>[!NOTE]
>
>プッシュチャネルはオプションです。 使用許諾契約書を確認してください。標準のプッシュ通知について詳しくは、[プッシュ通知について](../../channels/using/about-push-notifications.md)を参照してください。

トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。 [モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)を参照してください。

次の2種類のトランザクションプッシュ通知を送信できます。

* [イベントをターゲットとしたトランザクションプッシュ通知](#transactional-push-notifications-targeting-an-event)
* [Adobe Campaignデータベースからのプロファイルをタ](#transactional-push-notifications-targeting-a-profile) ーゲットとするトランザクションプッシュ通知

## イベント{#transactional-push-notifications-targeting-an-event}をターゲットとするトランザクションプッシュ通知

Adobe Campaignを使用して、モバイルアプリケーションからの通知の受信をオプトインしたすべてのユーザー&#x200B;**に、**&#x200B;匿名トランザクションプッシュ通知を送信できます。

この場合、配信ターゲット&#x200B;**の定義には、イベント自体に含まれる**&#x200B;データのみが使用されます。 Adobe Campaign統合プロファイルデータベースのデータは利用されません。

### イベントベースのトランザクションプッシュ通知の設定{#configuring-event-based-transactional-push-notification}

モバイルアプリケーションからの通知の受信をオプトインしたすべてのユーザーにトランザクションプッシュ通知を送信するには、まず、イベント自体に含まれるデータをターゲットにしたイベントを作成および設定する必要があります。

>[!NOTE]
>
>[イベント属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)（イベントのデータ）および[イベントエンリッチメント](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)（Campaignデータベースのデータ）を使用して、イベントベースのトランザクションプッシュ通知のコンテンツをパーソナライズできます。 [以下の例](#sending-event-based-transactional-push-notification)を参照してください。

イベントには、次の3つの要素を含める必要があります。

* **登録トークン**。1つのモバイルアプリケーションと1つのデバイスのユーザーIDです。 これは、Adobe Campaignデータベースのどのプロファイルにも対応していない可能性があります。
* **モバイルアプリケーション名**(すべてのデバイス（AndroidとiOS）に1つ)。 これは、Adobe Campaignで設定され、ユーザーのデバイスでプッシュ通知を受信するために使用されるモバイルアプリケーションのIDです。 詳しくは、[モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)を参照してください。
* **プッシュプラットフォーム**（Androidの場合は「gcm」、iOSの場合は「apns」）。

イベントを設定するには、次の手順に従います。

1. イベント設定を作成する際に、**[!UICONTROL Push notification]**&#x200B;チャネルと&#x200B;**[!UICONTROL Real-time event]**&#x200B;ターゲティングディメンションを選択します（[イベントの作成](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照）。
1. イベントにフィールドを追加します。 これにより、トランザクションメッセージをパーソナライズできます（[イベント属性の定義](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)を参照）。 この例では、「gateNumber」、「lastname」および「firstname」フィールドを定義します。
1. また、メッセージの内容をエンリッチメントすることもできます。 これをおこなうには、イベント設定にリンクしたテーブルからフィールドを追加します（[イベントのエンリッチメント](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)を参照）。

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [イベントをプレビューして公開します](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   イベントをプレビューする際、REST APIには、配信のターゲット設定に使用される「registrationToken」、「application」および「pushPlatform」属性が含まれます。

   ![](assets/message-center_push_api.png)

   イベントが公開されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成したメッセージを変更して公開できます（[この節](#sending-event-based-transactional-push-notification)を参照）。

1. イベントをWebサイトに統合します（[イベントトリガーを統合する](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照）。

### イベントベースのトランザクションプッシュ通知の送信{#sending-event-based-transactional-push-notification}

例えば、航空会社がモバイルアプリのユーザーを招待して、搭乗のために関連するゲートに進みたいとします。

同社は、1台のモバイルアプリケーションを使用して、1人のデバイスを通じて、ユーザーごとに1件のトランザクションプッシュ通知（登録トークンで識別）を送信します。

1. 作成したトランザクションメッセージに移動して編集します。[トランザクションメッセージへのアクセス](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)を参照してください。

   ![](assets/message-center_push_message.png)

1. **[!UICONTROL Content]**&#x200B;ブロックをクリックして、メッセージのタイトルと本文を変更します。

1. パーソナライゼーションフィールドを挿入して、イベントの作成時に定義した要素を追加できます（[イベント属性の定義](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)を参照）。

   ![](assets/message-center_push_content.png)

   これらのフィールドを探すには、項目の横にある鉛筆アイコンをクリックし、**[!UICONTROL Insert personalization field]**&#x200B;をクリックして&#x200B;**[!UICONTROL Context]** / **[!UICONTROL Real-time event]** / **[!UICONTROL Event context]**&#x200B;を選択します。

   ![](assets/message-center_push_personalization.png)

   プッシュ通知コンテンツの編集について詳しくは、「[プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)」を参照してください。

1. また、Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージのコンテンツをエンリッチメントすることもできます（[イベントのエンリッチメント](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)を参照）。

1. 変更を保存し、メッセージを公開します。[トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。

1. Adobe Campaign Standard REST APIを使用して、Android(gcm)上で1つのモバイルアプリケーション(WeFlight)を使用して、以下のボーディングデータを含むイベントを登録トークン(ABCDEF123456789)に送信します。

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

   イベントのトリガーを外部システムに統合する方法について詳しくは、[イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照してください。

登録トークンが存在する場合、対応するユーザーは、次のコンテンツを含むトランザクションプッシュ通知を受け取ります。

*「こんにちは、ジェーン・グリーン、搭乗が始まったばかりです。ゲートB18に進んでください。&quot;*

## プロファイル{#transactional-push-notifications-targeting-a-profile}をターゲットとするトランザクションプッシュ通知

モバイルアプリケーション&#x200B;**を購読したAdobe Campaignプロファイルに、トランザクションプッシュ通知**&#x200B;を送信できます。 この配信には、Adobe Campaignデータベースから直接取得した受信者の名など、[パーソナライゼーションフィールド](../../designing/using/personalization.md#inserting-a-personalization-field)を含めることができます。

この場合、イベントには、Adobe Campaignデータベース&#x200B;**のプロファイルとの紐付けを許可する**&#x200B;フィールドが含まれている必要があります。

プロファイルをターゲティングする場合、モバイルアプリケーションおよびデバイスごとに1つのトランザクションプッシュ通知が送信されます。 例えば、Adobe Campaignユーザーが2つのアプリケーションを購読している場合、このユーザーには2つの通知が届きます。 ユーザーが2つの異なるデバイスを使用して同じアプリを購読した場合、このユーザーは各デバイスで通知を受け取ります。

プロファイルがサブスクライブしたモバイルアプリケーションが、このプロファイルの「**[!UICONTROL Mobile App Subscriptions]**」タブに表示されます。 このタブにアクセスするには、プロファイルを選択し、右側の&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;ボタンをクリックします。

![](assets/push_notif_subscriptions.png)

プロファイルへのアクセスと編集について詳しくは、[プロファイル](../../audiences/using/about-profiles.md)についてを参照してください。

### プロファイルベースのトランザクションプッシュ通知の設定{#configuring-profile-based-transactional-push-notification}

モバイルアプリケーションを購読したAdobe Campaignプロファイルにトランザクションプッシュ通知を送信するには、まずAdobe Campaignデータベースをターゲットとするイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Push notification]**&#x200B;チャネルと&#x200B;**[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを選択します（[イベントの作成](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照）。

   デフォルトでは、受信者が購読しているすべてのモバイルアプリケーションにトランザクションプッシュ通知が送信されます。 特定のモバイルアプリケーションにプッシュ通知を送信するには、リストでその通知を選択します。 その他のモバイルアプリはメッセージのターゲットになりますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. トランザクションメッセージをパーソナライズする場合は、イベントにフィールドを追加します（[イベント属性の定義](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)を参照）。

   >[!NOTE]
   >
   >エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるので、**名**&#x200B;や&#x200B;**姓**&#x200B;など、他のフィールドを作成する必要はありません。

1. イベントを&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクするためにエンリッチメントを作成し（[イベントのエンリッチメント](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)を参照）、このエンリッチメントを&#x200B;**[!UICONTROL Targeting enrichment]**&#x200B;として選択します。

   >[!IMPORTANT]
   >
   >この手順は、プロファイルベースのイベントでは必須です。

1. [イベントをプレビューして公開します](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   イベントをプレビューする際、REST APIには、登録トークン、アプリケーション名、プッシュプラットフォームを指定する属性は含まれません。これらは&#x200B;**[!UICONTROL Profile]**&#x200B;リソースから取得されます。

   イベントが公開されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成したメッセージを変更して公開できます（[この節](#sending-profile-based-transactional-push-notification)を参照）。

1. イベントをWebサイトに統合します（[イベントトリガーを統合する](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照）。

### プロファイルベースのトランザクションプッシュ通知の送信{#sending-profile-based-transactional-push-notification}

例えば、航空会社が、モバイルアプリを購読したすべてのAdobe Campaignユーザーに対して、搭乗用の最後の呼び出しを送信するとします。

1. 作成したトランザクションメッセージに移動して編集します。[トランザクションメッセージへのアクセス](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)を参照してください。

1. **[!UICONTROL Content]**&#x200B;ブロックをクリックして、メッセージのタイトルと本文を変更します。

   リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスしてメッセージをパーソナライズできます。 [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)を参照してください。

   プッシュ通知コンテンツの編集について詳しくは、「[プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)」を参照してください。

1. 変更を保存し、メッセージを公開します。[トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。
1. Adobe Campaign Standard REST APIを使用して、イベントをプロファイルに送信します。

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

イベントのトリガーを外部システムに統合する方法について詳しくは、[イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照してください。

対応するユーザーは、Adobe Campaignデータベースから取得されたすべてのパーソナライゼーション要素を含むトランザクションプッシュ通知を受け取ります。

>[!NOTE]
>
>登録トークン、アプリケーションおよびプッシュプラットフォームフィールドはありません。 この例では、Eメールフィールドに対する紐付けが実行されます。

## トランザクションプッシュ通知でのターゲットマッピングの変更{#change-target-mapping}

トランザクションプッシュ通知は、特定の[ターゲットマッピング](../../administration/using/target-mappings-in-campaign.md)を使用します。このマッピングには、このタイプの配信の送信に必要な技術的設定が含まれます。

このターゲットマッピングを変更するには、次の手順に従います。

1. トランザクションメッセージリストで、プッシュ通知を選択します。

1. メッセージダッシュボードで、「**[!UICONTROL Edit properties]**」ボタンをクリックします。

   ![](assets/message-center_push_edit.png)

1. **[!UICONTROL Advanced parameters]**&#x200B;セクションを展開します。

1. 「**[!UICONTROL Select a 'Target mapping' element]**」をクリックします。

   ![](assets/message-center_push_target-mapping.png)

1. リストからターゲットマッピングを選択します。

   >[!NOTE]
   >
   >**プロファイルベースの**&#x200B;トランザクションプッシュ通知を送信する際の、配信準備の最適な時間とパフォーマンスを得るには、**[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]**&#x200B;ターゲットマッピングを使用します。

   ![](assets/message-center_push_target-mapping_change.png)

1. 変更を確認し、メッセージを公開します。 [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。

   >[!IMPORTANT]
   >
   >変更を有効にするには、メッセージを再度公開する必要があります。そうしないと、以前のターゲットマッピングが引き続き使用されます。


