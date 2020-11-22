---
solution: Campaign Standard
product: campaign
title: トランザクションプッシュ通知
description: トランザクションプッシュ通知を作成して発行する方法について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 13%

---


# トランザクションプッシュ通知{#transactional-push-notifications}

Adobe Campaignを使用して、iOSおよびAndroidモバイルデバイスでトランザクションプッシュ通知を送信できます。 これらのメッセージは、Experience CloudMobile SDKを利用して、Adobe Campaignで設定したモバイルアプリケーションで受信されます。

>[!NOTE]
>
>プッシュチャネルはオプションです。 使用許諾契約書を確認してください。標準的なプッシュ通知について詳しくは、 [プッシュ通知を参照してください](../../channels/using/about-push-notifications.md)。

2種類のトランザクションプッシュ通知を送信できます。

* イベントを対象としたトランザクションプッシュ通知。
* Adobe Campaignデータベースのプロファイルをターゲットにしたトランザクションプッシュ通知。

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、**[!UICONTROL Administrators (all units)]**&#x200B;セキュリティグループに属している必要があります。

## イベントを対象としたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-an-event}

匿名トランザクションプッシュ通知は、モバイルアプリケーションからの通知の受信を選択しているすべてのユーザーに送信できます。

この場合、配信ターゲットの定義には、イベント自体に含まれるデータのみが使用されます。 Adobe Campaign統合プロファイル・データベースのデータは使用されません。

### イベントを対象としたトランザクションプッシュ通知の送信 {#sending-a-transactional-push-notification-targeting-an-----------event}

例えば、航空会社の会社が、搭乗のために関連ゲートに進むようモバイルアプリのユーザーを招待したいとします。

会社は、1台のモバイルアプリケーションを介して、1人のユーザー（登録トークンで識別）につき1つのトランザクションプッシュ通知を送信します。

1. 作成したトランザクションメッセージに移動して編集します。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   パーソナライゼーションフィールドを挿入して、イベントの作成時に定義した要素を追加できます。

   ![](assets/message-center_push_content.png)

   これらのフィールドを探すには、アイテムの横にある鉛筆をクリックし、をクリックし **[!UICONTROL Insert personalization field]** てから、 **[!UICONTROL Context]** / **[!UICONTROL Real-time event]** /を選択し **[!UICONTROL Event context]**&#x200B;ます。

   ![](assets/message-center_push_personalization.png)

   プッシュ通知の内容の編集について詳しくは、プッシュ通知の [作成を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 変更を保存し、メッセージを公開します。[トランザクションメッセージの公開](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)を参照してください。

1. Adobe Campaign StandardREST APIを使用して、搭載データを含むAndroid(gcm)上のモバイルアプリケーション(WeFlight)を使用して、イベントを登録トークン(ABCDEF123456789)に送信します。

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

   イベントのトリガー機能を外部システムに統合する方法について詳しくは、 [サイト統合を参照してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

登録トークンが存在する場合、対応するユーザーは、次のコンテンツを含むトランザクションプッシュ通知を受け取ります。

「やあ、ジェーン・グリーンさん、乗船が始まったばかりです！ B18番ゲートに進んでください」

## プロファイルを対象としたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-a-profile}

モバイルアプリケーションを購読しているAdobe Campaignプロファイルに、トランザクションプッシュ通知を送信できます。 この配信には、受信者の名など [のパーソナライゼーション](../../designing/using/personalization.md#inserting-a-personalization-field) ・フィールドを含めることができます。

この場合、イベントには、Adobe Campaignデータベースのプロファイルとの調整を許可するフィールドがいくつか含まれている必要があります。

プロファイルをターゲット設定する場合、モバイルアプリケーションごとおよびデバイスごとに1つのトランザクションプッシュ通知が送信されます。 例えば、Adobe Campaignユーザーが2つのアプリをサブスクライブしている場合、このユーザーには2つの通知が届きます。 ユーザーが2つの異なるデバイスを使用して同じアプリケーションをサブスクライブしている場合、このユーザーは各デバイスで通知を受け取ります。

プロファイルがサブスクライブしたモバイルプロファイルは、このアプリケーションの **[!UICONTROL Mobile App Subscriptions]** タブに表示されます。 このタブにアクセスするには、プロファイルを選択し、右側の **[!UICONTROL Edit profile properties]** ボタンをクリックします。

![](assets/push_notif_subscriptions.png)

プロファイルへのアクセスと編集について詳しくは、 [プロファイルを参照してください](../../audiences/using/creating-profiles.md)。

### プロファイルを対象としたトランザクションプッシュ通知の送信 {#sending-a-transactional-push-notification-targeting-a-----------profile}

例えば、航空会社の会社は、モバイルアプリを購読しているすべてのAdobe Campaignユーザーに、搭乗のための最後の通話を送信したいと考えています。

1. 作成したトランザクションメッセージに移動して編集します。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズできます。 [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)を参照してください。

   プッシュ通知コンテンツの編集に関する詳細。 プッシュ通知の [作成を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 変更を保存し、メッセージを公開します。[トランザクションメッセージの公開](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)を参照してください。
1. Adobe Campaign StandardREST APIを使用して、プロファイルにイベントを送信します。

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   イベントのトリガー機能を外部システムに統合する方法について詳しくは、 [サイト統合を参照してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

   >[!NOTE]
   >
   >登録トークン、アプリケーション、プッシュプラットフォームのフィールドはありません。 この例では、電子メールフィールドを使用して調整が実行されます。
