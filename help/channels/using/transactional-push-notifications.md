---
title: トランザクションプッシュ通知
seo-title: トランザクションプッシュ通知
description: トランザクションプッシュ通知
seo-description: トランザクションプッシュ通知を作成して公開する方法を説明します。
page-status-flag: 未活性化の
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: トランザクション·メッセージング
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# トランザクションプッシュ通知{#transactional-push-notifications}

Adobe Campaignを使用して、iOSおよびAndroidモバイルデバイスでトランザクションプッシュ通知を送信できます。 これらのメッセージは、Adobe Campaignで設定したモバイルアプリケーションで、Experience Cloud Mobile SDKを利用して受信されます。

>[!NOTE]
>
>プッシュチャネルはオプションです。 使用許諾契約を確認してください。 標準のプッシュ通知の詳細は、「プッシュ通知」を参照し [てください](../../channels/using/about-push-notifications.md)。

2種類のトランザクションプッシュ通知を送信できます。

* イベントを対象としたトランザクションプッシュ通知。
* Adobe Campaignデータベースのプロファイルを対象としたトランザクションプッシュ通知。

イベントを作成して公開すると(このセクションで説明するカートの破棄 [)、対応するトランザクション](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)Push通知が自動的に作成されます。

構成手順は、「トランザクションプッシュ通 [知を送信するイベントの構成」セクションで説明します](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

イベントがトランザクション·メッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクション·メッセージにアクセスするには、管理権限を持っているか、(mcExec)セキュリ **[!UICONTROL Message Center agents]** ティ·グループに表示されている必要があります。

## イベントを対象としたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-an-event}

匿名トランザクションプッシュ通知を、モバイルアプリケーションから通知を受け取るようにオプトインしたすべてのユーザーに送信できます。

この場合、配信ターゲットの定義には、イベント自体に含まれるデータのみが使用されます。 Adobe Campaign統合プロファイルデータベースのデータは利用されません。

### イベントを対象としたトランザクションプッシュ通知の送信 {#sending-a-transactional-push-notification-targeting-an-----------event}

例えば、航空会社は、モバイルアプリケーションのユーザーを招待して、搭乗のために関連ゲートに進みたいと考えています。

同社は、1台のデバイスを通じて、1つのモバイルアプリケーションを使用して、1人のユーザー（登録トークンで識別）に1つのトランザクションプッシュ通知を送信します。

1. 作成されたトランザクションメッセージを編集するために移動します。 「イベント·ト [ランザクション·メッセージ](../../channels/using/event-transactional-messages.md)」を参照。

   ![](assets/message-center_push_message.png)

1. メッセージの **[!UICONTROL Content]** タイトルと本文を変更するには、ブロックをクリックします。

   個人用設定フィールドを挿入して、イベントの作成時に定義した要素を追加できます。

   ![](assets/message-center_push_content.png)

   これらのフィールドを検索するには、項目の横にある鉛筆をクリックし、をクリックし **[!UICONTROL Insert personalization field]** て「&gt;」を選 **[!UICONTROL Transactional event]** 択しま **[!UICONTROL Event context]**&#x200B;す。

   ![](assets/message-center_push_personalization.png)

   プッシュ通知コンテンツの編集の詳細は、「プッシュ通知の作 [成」を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 変更を保存し、メッセージを発行します。 「トランザク [ション·メッセージの発行」を参照](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。
1. Adobe Campaign Standard REST APIを使用して、搭乗データを含むAndroid(gcm)上の1つのモバイルアプリケーション(WeFlight)を使用して、登録トークン(ABCDEF123456789)にイベントを送信します。

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

   イベントのトリガを外部システムに統合する方法の詳細については、「サイトの統合」を参照 [してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

登録トークンが存在する場合、対応するユーザは、次の内容を含むトランザクションプッシュ通知を受け取ります。

「こんにちは、ジェーン·グリーンさん、乗船が始まったばかりです！ B18番ゲートに進んで下さい」

## プロファイルを対象としたトランザクションプッシュ通知 {#transactional-push-notifications-targeting-a-profile}

トランザクションプッシュ通知は、モバイルアプリケーションを購読しているAdobe Campaignプロファイルに送信できます。 この配信には、受信者の名 [など](../../designing/using/personalization.md#inserting-a-personalization-field) 、個人用設定フィールドを含めることができます。

この場合、イベントには、Adobe Campaignデータベースのプロファイルとの調整を許可するフィールドがいくつか含まれている必要があります。

プロファイルをターゲットにする場合、モバイルアプリケーションとデバイスごとに1つのトランザクションプッシュ通知が送信されます。 たとえば、Adobe Campaignユーザーが2つのアプリケーションを購読している場合、このユーザーは2つの通知を受け取ります。 ユーザーが2つの異なるデバイスを持つ同じアプリケーションにサブスクライブした場合、このユーザーは各デバイスで通知を受け取ります。

プロファイルが購読しているモバイルアプリケーションが、このプロファイルのタ **[!UICONTROL Mobile App Subscriptions]** ブに一覧表示されます。 このタブにアクセスするには、プロファイルを選択し、右側のボ **[!UICONTROL Edit profile properties]** タンをクリックします。

![](assets/push_notif_subscriptions.png)

プロファイルへのアクセスと編集の詳細は、「プロファイル」を参照して [ください](../../audiences/using/creating-profiles.md)。

### プロファイルを対象としたトランザクションプッシュ通知の送信 {#sending-a-transactional-push-notification-targeting-a-----------profile}

たとえば、航空会社が、モバイルアプリケーションを購読しているすべてのAdobe Campaignユーザーに、最後の乗船用の電話を送信したいとします。

1. 作成されたトランザクションメッセージを編集するために移動します。 「イベント·ト [ランザクション·メッセージ](../../channels/using/event-transactional-messages.md)」を参照。

   ![](assets/message-center_push_message_profile.png)

1. メッセージの **[!UICONTROL Content]** タイトルと本文を変更するには、ブロックをクリックします。

   リアルタイムイベントに基づく構成とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをカスタマイズできます。 「個人用設 [定フィールドの挿入」を参照してくださ](../../designing/using/personalization.md#inserting-a-personalization-field)い。

   ![](assets/message-center_push_content_profile.png)

   プッシュ通知コンテンツの編集の詳細を表示します。 「プッシュ通 [知の作成」を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 変更を保存し、メッセージを発行します。 「トランザク [ション·メッセージの発行」を参照](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。
1. Adobe Campaign Standard REST APIを使用して、プロファイルにイベントを送信します。

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   イベントのトリガを外部システムに統合する方法の詳細については、「サイトの統合」を参照 [してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

   >[!NOTE]
   >
   >登録トークン、アプリケーション、およびプッシュプラットフォームの各フィールドはありません。 この例では、調整は電子メールフィールドを使用して実行されます。

