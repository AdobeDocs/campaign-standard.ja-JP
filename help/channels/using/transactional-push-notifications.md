---
title: トランザクションプッシュ通知
seo-title: トランザクションプッシュ通知
description: トランザクションプッシュ通知
seo-description: トランザクションプッシュ通知を作成して発行する方法について説明します。
page-status-flag: 非活性化の
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: トランザクションメッセージング
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fad149d30d06f285a89f13e4c8bff20932297695

---


# トランザクションプッシュ通知{#transactional-push-notifications}

Adobe Campaignを使用して、iOSおよびAndroid携帯端末でトランザクションプッシュ通知を送信できます。 これらのメッセージは、Experience Cloud Mobile SDKを利用して、Adobe Campaignで設定したモバイルアプリで受信されます。

>[!NOTE]
>
>プッシュチャネルはオプションです。 使用許諾契約書を確認してください。標準的なプッシュ通知について詳しくは、プッシュ通知を参照 [してください](../../channels/using/about-push-notifications.md)。

次の2種類のトランザクションプッシュ通知を送信できます。

* イベントをターゲットとするトランザクションプッシュ通知。
* Adobe Campaignデータベースからのプロファイルを対象としたトランザクションプッシュ通知。

イベントを作成して発行すると(この節で説明する買い物かごの中断 [)](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)、対応するトランザクションプッシュ通知が自動的に作成されます。

設定手順は、「トランザクションプッ [シュ通知を送信するためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」に記載されています。

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、セキュリティグループに属してい **[!UICONTROL Administrators (all units)]** る必要があります。

## イベントをターゲットとしたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-an-event}

匿名のトランザクションプッシュ通知は、モバイルアプリケーションからの通知の受信をオプトインしているすべてのユーザーに送信できます。

この場合、イベント自体に含まれるデータのみが配信ターゲットの定義に使用されます。 Adobe Campaign統合プロファイルデータベースのデータは使用されません。

### イベントをターゲットにしたトランザクションプッシュ通知の送信 {#sending-a-transactional-push-notification-targeting-an-----------event}

例えば、航空会社がモバイルアプリのユーザーを招待して、搭乗のために関連ゲートに進むことを希望しているとします。

会社は、1つのモバイルアプリケーションを使用して、ユーザー（登録トークンで識別）ごとに1つのトランザクションプッシュ通知を1つのデバイスで送信します。

1. 作成されたトランザクションメッセージに移動して編集します。 イベントトラン [ザクションメッセージを参照してくださ](../../channels/using/event-transactional-messages.md)い。

   ![](assets/message-center_push_message.png)

1. ブロックをク **[!UICONTROL Content]** リックして、メッセージのタイトルと本文を変更します。

   パーソナライゼーションフィールドを挿入して、イベントの作成時に定義した要素を追加できます。

   ![](assets/message-center_push_content.png)

   これらのフィールドを検索するには、項目の横にある鉛筆をクリックし、をクリックし **[!UICONTROL Insert personalization field]** て、// **[!UICONTROL Context]** を選択 **[!UICONTROL Real-time event]** しま **[!UICONTROL Event context]**&#x200B;す。

   ![](assets/message-center_push_personalization.png)

   プッシュ通知コンテンツの編集について詳しくは、プッシュ通知の [作成を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 変更を保存し、メッセージを公開します。 詳しくは、ト [ランザクションメッセージの公開を参照してくださ](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)い。
1. Adobe Campaign Standard REST APIを使用して、搭乗データを含む1つのモバイルアプリケーション(WeFlight)を使用して、登録トークン(ABCDEF123456789)にイベントを送信します。

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

   イベントのトリガーを外部システムに統合する方法について詳しくは、「サイトの統合」を参照 [してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

登録トークンが存在する場合、対応するユーザーは、次のコンテンツを含むトランザクションプッシュ通知を受け取ります。

「ジェーン・グリーンさん、乗船が始まったばかりです！ B18番ゲートに進んでください」

## プロファイルを対象としたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-a-profile}

お使いのモバイルアプリケーションを登録しているAdobe Campaignプロファイルに、トランザクションプッシュ通知を送信できます。 この配信には、受信者の名 [など](../../designing/using/personalization.md#inserting-a-personalization-field) 、パーソナライゼーションフィールドを含めることができます。

この場合、イベントには、Adobe Campaignデータベースのプロファイルとの調整を許可するフィールドが含まれている必要があります。

プロファイルをターゲット設定する場合、モバイルアプリケーションごとおよびデバイスごとに1つのトランザクションプッシュ通知が送信されます。 例えば、Adobe Campaignユーザーが2つのアプリケーションを購読している場合、このユーザーには2つの通知が届きます。 ユーザーが2つの異なるデバイスを使用して同じアプリケーションを購読している場合、このユーザーは各デバイスで通知を受け取ります。

プロファイルがサブスクライブしているモバイルアプリケーションは、このプロファイルの **[!UICONTROL Mobile App Subscriptions]** タブに表示されます。 このタブにアクセスするには、プロファイルを選択し、右側のボ **[!UICONTROL Edit profile properties]** タンをクリックします。

![](assets/push_notif_subscriptions.png)

プロファイルへのアクセスと編集について詳しくは、プロファイルを参照し [てくださ](../../audiences/using/creating-profiles.md)い。

### プロファイルを対象としたトランザクションプッシュ通知の送信 {#sending-a-transactional-push-notification-targeting-a-----------profile}

例えば、航空会社が、モバイルアプリケーションを購読しているすべてのAdobe Campaignユーザーに、搭乗用の最後の通話を送信するとします。

1. 作成されたトランザクションメッセージに移動して編集します。 イベントトラン [ザクションメッセージを参照してくださ](../../channels/using/event-transactional-messages.md)い。

   <!--![](assets/message-center_push_message_profile.png)-->

1. ブロックをク **[!UICONTROL Content]** リックして、メッセージのタイトルと本文を変更します。

   リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズできます。 See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

   <!--![](assets/message-center_push_content_profile.png)-->

   プッシュ通知コンテンツの編集に関する詳細。 プッシュ [通知の作成を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 変更を保存し、メッセージを公開します。 詳しくは、ト [ランザクションメッセージの公開を参照してくださ](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)い。
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

   イベントのトリガーを外部システムに統合する方法について詳しくは、「サイトの統合」を参照 [してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

   >[!NOTE]
   >
   >登録トークン、アプリケーションおよびプッシュプラットフォームフィールドはありません。 この例では、電子メールフィールドを使用して調整が実行されます。

