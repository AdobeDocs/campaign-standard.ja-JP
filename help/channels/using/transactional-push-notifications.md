---
solution: Campaign Standard
product: campaign
title: トランザクションプッシュ通知
description: トランザクションプッシュを作成して公開する方法を説明します。         notification.
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 13%

---


# トランザクションプッシュ通知{#transactional-push-notifications}

Adobe Campaignを使用して、iOSおよびAndroidモバイルデバイスでトランザクションプッシュ通知を送信できます。 これらのメッセージは、Experience CloudMobile SDKを利用して、Adobe Campaignで設定したモバイルアプリケーションで受信されます。

>[!NOTE]
>
>プッシュチャネルはオプションです。 使用許諾契約書を確認してください。標準的なプッシュ通知について詳しくは、[プッシュ通知](../../channels/using/about-push-notifications.md)を参照してください。

2種類のトランザクションプッシュ通知を送信できます。

* イベントを対象としたトランザクションプッシュ通知。
* Adobe Campaignデータベースのプロファイルをターゲットにしたトランザクションプッシュ通知。

イベントを作成して公開すると（買い物かごの放棄について[このセクション](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)で説明します）、対応するトランザクションプッシュ通知が自動的に作成されます。

設定手順については、「[トランザクションプッシュ通知を送信するためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)」の節を参照してください。

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、**[!UICONTROL Administrators (all units)]**&#x200B;セキュリティグループに属している必要があります。

## イベント{#transactional-push-notifications-targeting-an-event}を対象としたトランザクションプッシュ通知

匿名トランザクションプッシュ通知は、モバイルアプリケーションからの通知の受信を選択しているすべてのユーザーに送信できます。

この場合、配信ターゲットの定義には、イベント自体に含まれるデータのみが使用されます。 Adobe Campaign統合プロファイル・データベースのデータは使用されません。

### イベント{#sending-a-transactional-push-notification-targeting-an-----------event}を対象としたトランザクションプッシュ通知の送信

例えば、航空会社の会社が、搭乗のために関連ゲートに進むようモバイルアプリのユーザーを招待したいとします。

会社は、1台のモバイルアプリケーションを介して、1人のユーザー（登録トークンで識別）につき1つのトランザクションプッシュ通知を送信します。

1. 作成したトランザクションメッセージに移動して編集します。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

   ![](assets/message-center_push_message.png)

1. **[!UICONTROL Content]**&#x200B;ブロックをクリックして、メッセージのタイトルと本文を変更します。

   パーソナライゼーションフィールドを挿入して、イベントの作成時に定義した要素を追加できます。

   ![](assets/message-center_push_content.png)

   これらのフィールドを探すには、項目の横の鉛筆をクリックし、**[!UICONTROL Insert personalization field]**&#x200B;をクリックして&#x200B;**[!UICONTROL Context]**/**[!UICONTROL Real-time event]**/**[!UICONTROL Event context]**&#x200B;を選択します。

   ![](assets/message-center_push_personalization.png)

   プッシュ通知の内容の編集について詳しくは、[プッシュ通知の作成](../../channels/using/preparing-and-sending-a-push-notification.md)を参照してください。

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

   イベントのトリガーを外部システムに組み込む方法について詳しくは、[サイト統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)を参照してください。

登録トークンが存在する場合、対応するユーザーは、次のコンテンツを含むトランザクションプッシュ通知を受け取ります。

「やあ、ジェーン・グリーンさん、乗船が始まったばかりです！ B18番ゲートに進んでください」

## プロファイル{#transactional-push-notifications-targeting-a-profile}を対象としたトランザクションプッシュ通知

モバイルアプリケーションを購読しているAdobe Campaignプロファイルに、トランザクションプッシュ通知を送信できます。 この配信には、受信者の名など、[パーソナライゼーション](../../designing/using/personalization.md#inserting-a-personalization-field)フィールドを含めることができます。

この場合、イベントには、Adobe Campaignデータベースのプロファイルとの調整を許可するフィールドがいくつか含まれている必要があります。

プロファイルをターゲット設定する場合、モバイルアプリケーションごとおよびデバイスごとに1つのトランザクションプッシュ通知が送信されます。 例えば、Adobe Campaignユーザーが2つのアプリをサブスクライブしている場合、このユーザーには2つの通知が届きます。 ユーザーが2つの異なるデバイスを使用して同じアプリケーションをサブスクライブしている場合、このユーザーは各デバイスで通知を受け取ります。

プロファイルがサブスクライブしたモバイルアプリケーションは、このプロファイルの&#x200B;**[!UICONTROL Mobile App Subscriptions]**&#x200B;タブに一覧表示されます。 このタブにアクセスするには、プロファイルを選択し、右側の&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;ボタンをクリックします。

![](assets/push_notif_subscriptions.png)

プロファイルへのアクセスと編集について詳しくは、[プロファイル](../../audiences/using/creating-profiles.md)を参照してください。

### プロファイル{#sending-a-transactional-push-notification-targeting-a-----------profile}を対象としたトランザクションプッシュ通知の送信

例えば、航空会社の会社は、モバイルアプリを購読しているすべてのAdobe Campaignユーザーに、搭乗のための最後の通話を送信したいと考えています。

1. 作成したトランザクションメッセージに移動して編集します。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

1. **[!UICONTROL Content]**&#x200B;ブロックをクリックして、メッセージのタイトルと本文を変更します。

   リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズできます。 [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)を参照してください。

   プッシュ通知コンテンツの編集に関する詳細。 「[プッシュ通知の作成](../../channels/using/preparing-and-sending-a-push-notification.md)」を参照してください。

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

   イベントのトリガーを外部システムに組み込む方法について詳しくは、[サイト統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)を参照してください。

   >[!NOTE]
   >
   >登録トークン、アプリケーション、プッシュプラットフォームのフィールドはありません。 この例では、電子メールフィールドを使用して調整が実行されます。
