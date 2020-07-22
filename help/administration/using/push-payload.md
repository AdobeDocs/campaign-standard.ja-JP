---
title: Campaign Standardプッシュ通知のペイロード構造について
description: This document is intended to describe the structure of the payload received in mobile applications.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 91cb524e104fbaa7f3334578d82b3878cc15fc9b
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 2%

---


# Understanding push notifications payload structure {#push-payload}

Adobe Campaignを使用すると、iOSおよびAndroidモバイルデバイス上で、パーソナライズされたセグメント化されたプッシュ通知をモバイルアプリ（モバイルアプリ）に送信できます。

Every push notification that is received on a mobile app carries some information which is used by the app to display the push notification if an Alert push notification is sent, and most likely to also do some further computation, especially if a silent push notification is sent.

この情報は、プッシュ通知が受信されたことを示すイベントハンドラーで、モバイルアプリコードによって受け取られます。 Adobe Campaign Standardからプッシュ通知を送信する際、モバイルアプリで受信される情報には、Campaign Standardが提供する機能の活用に使用できるCampaign Standard固有の情報が含まれている場合があります。 また、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントは、プッシュ通知がAdobe Campaign Standardからアプリに正常に送信された場合にモバイルアプリで受信されるペイロードの構造を説明します。

>[!NOTE]
>
>ペイロード構造は、モバイルアプリ（iOSアプリ、FCM対応のAndroidアプリなど）のタイプによって異なります。

## プッシュペイロード構造 {#push-payload-structure}

この節では、様々なモバイルプラットフォームのサンプルペイロードの構造を説明し、それに含まれる主要属性について説明します。 これは、プッシュ通知が受信されたことを示すイベントハンドラー内のモバイルアプリコードで受信されたペイロードの構造です。

ペイロード属性とその値は、プッシュ通知のアドバンスオプションで提供される設定によって異なります。 また、Campaign Standardでのオプションの設定でペイロードがどのように変化するかを明確にするため、Campaign StandardUIのこれらの設定とペイロードの属性とのマッピングも示します。

### For iOS Mobile App {#payload-structure-ios}

**Sample Payload sent from Adobe Campaign to iOS app:**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**iOS APNS Testerで使用するJSONサンプルペイ[ロード](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

ペイロードの最も重要な部分はapsディクショナリです。このディクショナリにはAppleが定義したキーが含まれ、通知を受信するシステムがユーザーに警告する方法を決定するために使用されます。 この節には、プッシュ通知の動作を策定するためにモバイルアプリで使用される定義済みのキーが含まれます。

app内の属性に関する詳細は、Apple開発者ドキュメントを参照してください。 [リモート通知ペイロードの作成](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)。

### Androidアプリの場合 {#payload-structure-android}

**Adobe CampaignからAndroidアプリに送信されるペイロードのサンプル**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**[Google FCMテスターを使用するJSONサンプルペイロード](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

ペイロードには、カスタムのキー/値のペアを含むすべてのプッシュ通知配信コンテンツを含むデータメッセージが含まれ、必要に応じて、クライアントアプリは、プッシュ通知を作成して表示するメッセージを処理する必要があります。

androidペイロードの側面を理解するには、「 [メッセージングの概念とオプション(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options)」を参照してください。

>[!NOTE]
>
>Androidペイロードでの通知メッセージのサポートが、2018年1月に削除され、アプリのスリープを解除し、アプリとの対話を行うことなくモバイルアプリに制御を渡せるようになりました。

### Mapping between Campaign Standard Configurations and Payload Attributes {#mapping-payload}

| キャンペーン設定 | iOSの影響を受けた属性 | Androidの影響を受けた属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージタイトル <br>メッセージ本文 | 警告→タイトル <br> 警告→本文 | 表題 <br>本文 | このデータには、アラートメッセージの詳細が含まれています。<br>タイトルとボディキーは、アラートの内容を提供します。 |
| サウンドを再生 | 音 | 音 | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンを示すために使用する整数値。 |
| 追加欠陥 | uri | ナトリウム | ディープリンクを使用すると、（Webブラウザーページを開く代わりに）アプリケーション内のコンテンツにユーザーを直接移動できます。 |
| カテゴリ | category | category | リモート通知でカスタムアクションを表示する。 <br>The category key helps the system display the actions for that category as buttons in the alert interface. |
| Custom fields | custom_field1、custom_field2... | custom_field1、custom_field2... | アプリに送信する任意のカスタムデータ。 |
| リッチメディアコンテンツURL（画像、gif、オーディオ、ビデオファイル）<br>（iOS 10以降にのみ適用） | media-attachment-url | ナトリウム | 通知にリッチコンテンツを追加するメディアファイルのURL。 <br>このURLの値を指定すると、可変コンテンツフラグがペイロードに自動的に送信されます。 <br> （iOS 10以降にのみ適用可能） |
| 可変コンテンツ <br> （iOS 10以降にのみ適用可能） | 可変内容 | ナトリウム | The Notification Service Extension in your app will &quot;intercept&quot; all remote notifications with the mutable-content key and will allow you to handle/manipulate the contents of the request payload, which can then be used to customize the notification. Use cases of this feature include downloading and displaying multiple media, decrypting any encrypted data present in the push payload. More information can be found in [Modify the payload of a Remote Notification](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>（iOS 10以降にのみ適用可能） |
| Content Available | content-available | ナトリウム | Selecting this option enables waking up of an iOS app while it is in background/suspended state. Waking up implies that the app runs in the background and the appropriate event handler responsible for receiving the push notification data payload gets a control and can use the data to do any computation, including but not limited to building custom push notification and displaying the same. More information can be found in [Wake up App with Notification delivery](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| Rich media content URL (image files)<br>(Only applicable forAndroid) | ナトリウム | media-attachment-url | 通知にリッチコンテンツを追加する画像ファイルのURL。 |
| ナトリウム | _mId<br>_dId | _mId <br>_dId | broadlogIdとdeliveryIdの値。<br>これらの属性は、アプリが追跡ポストバックを呼び出して、プッシュ通知がクリックまたは開かれた日時を追跡する場合に必要です。 この情報は計算され、ユーザーの介入なしでアプリサーバーによって内部的に送信されます。<br>ポストバックに関する情報は、この [ページに記載されています](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)。 |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーによって送信されるペイロード情報は、プッシュ通知が受信されたことを示すイベントハンドラーで、モバイルアプリコードによって受信されます。 このイベントは、対象となるモバイルプラットフォームによって異なり、また、アプリがフォアグラウンドで実行されているかバックグラウンドで実行されているかによって異なります。 次のドキュメントは、使用事例に基づいて、処理するイベントハンドラを特定する際に役立ちます。

* iOSアプリケーション： **「** リモート通知 [」の「リモート通知の処理](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)」の節を参照してください。
* Androidアプリケーション： [Androidクライアントアプリでのメッセージの受信](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Sample for iOS Mobile App**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Sample for Android Mobile FCM App**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
