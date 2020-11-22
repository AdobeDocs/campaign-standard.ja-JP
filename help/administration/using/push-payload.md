---
solution: Campaign Standard
product: campaign
title: Campaign Standardプッシュ通知のペイロード構造について
description: このドキュメントは、モバイルアプリケーションで受け取るペイロードの構造を記述するためのものです。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 5%

---


# プッシュ通知のペイロード構造について {#push-payload}

Adobe Campaignを使用すると、iOSおよびAndroidモバイルデバイス上で、パーソナライズされたセグメント化されたプッシュ通知をモバイルアプリ（モバイルアプリ）に送信できます。

モバイルアプリで受信されるすべてのプッシュ通知には、アプリが使用する情報が含まれています。この情報は、アラートのプッシュ通知が送信された場合にプッシュ通知を表示する際に使用され、特にサイレントプッシュ通知が送信された場合にも、多くの場合はそれ以上の計算を行います。

この情報は、プッシュ通知が受信されたことを示すイベントハンドラーで、モバイルアプリコードによって受け取られます。 Adobe Campaign Standardからプッシュ通知を送信する際、モバイルアプリで受信される情報には、Campaign Standardが提供する機能の活用に使用できるCampaign Standard固有の情報が含まれている場合があります。 また、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントは、プッシュ通知がAdobe Campaign Standardからアプリに正常に送信された場合にモバイルアプリで受信されるペイロードの構造を説明します。

>[!NOTE]
>
>ペイロード構造は、モバイルアプリ（iOSアプリ、FCM対応のAndroidアプリなど）のタイプによって異なります。

## プッシュペイロード構造 {#push-payload-structure}

この節では、様々なモバイルプラットフォームのサンプルペイロードの構造を説明し、それに含まれる主要属性について説明します。 これは、プッシュ通知が受信されたことを示すイベントハンドラー内のモバイルアプリコードで受信されたペイロードの構造です。

ペイロード属性とその値は、プッシュ通知のアドバンスオプションで提供される設定によって異なります。 また、Campaign Standardでのオプションの設定でペイロードがどのように変化するかを明確にするため、Campaign StandardUIのこれらの設定とペイロードの属性とのマッピングも示します。

### iOSモバイルアプリの場合 {#payload-structure-ios}

**Adobe CampaignからiOSアプリに送信されたペイロードのサンプル：**

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

**iOS APNS Testerで使用するJSONサンプルペイ [ロード](https://pushtry.com/)**

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

### Campaign Standard設定とペイロード属性のマッピング {#mapping-payload}

| キャンペーン設定 | iOSの影響を受けた属性 | Androidの影響を受けた属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージタイトル <br>メッセージ本文 | 警告→タイトル <br> 警告→本文 | 表題 <br>本文 | このデータには、アラートメッセージの詳細が含まれています。<br>タイトルとボディキーは、アラートの内容を提供します。 |
| サウンドの再生 | 音 | 音 | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンを示すために使用する整数値。 |
| ディープリンクの追加 | uri | ナトリウム | ディープリンクを使用すると、（Web ブラウザーページを開くのではなく）ユーザーをアプリケーション内のコンテンツに直接移動させることができます。 |
| カテゴリ | category | category | リモート通知でカスタムアクションを表示する。 <br>カテゴリキーは、そのカテゴリのアクションをアラートインターフェイスのボタンとして表示するのに役立ちます。 |
| カスタムフィールド | custom_field1、custom_field2... | custom_field1、custom_field2... | アプリに送信する任意のカスタムデータ。 |
| リッチメディアコンテンツURL（画像、gif、オーディオ、ビデオファイル）<br>（iOS 10以降にのみ適用） | media-attachment-url | ナトリウム | 通知にリッチコンテンツを追加するメディアファイルのURL。 <br>このURLの値を指定すると、可変コンテンツフラグがペイロードに自動的に送信されます。 <br> （iOS 10以降にのみ適用可能） |
| 可変コンテンツ <br> （iOS 10以降にのみ適用可能） | 可変内容 | ナトリウム | アプリのNotification Service Extensionは、可変コンテンツキーを使用してすべてのリモート通知を「傍受」し、要求ペイロードの内容を処理または操作できるようにします。これを使用して通知をカスタマイズできます。 この機能の使用例としては、複数のメディアのダウンロードと表示、プッシュペイロードに存在する暗号化されたデータの復号化などがあります。 詳細は、「リモート通知のペイロードの [変更](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)」を参照してください。 <br>（iOS 10以降にのみ適用可能） |
| 利用可能なコンテンツ | コンテンツを利用できる | ナトリウム | このオプションを選択すると、バックグラウンド/一時停止状態のiOSアプリのスリープを解除できます。 スリープを解除すると、アプリがバックグラウンドで実行され、プッシュ通知データのペイロードを受け取る適切なイベントハンドラーが制御を取得し、データを使用して任意の計算を行うことができます。カスタムプッシュ通知の作成や表示に限りません。 詳しくは、 [「アプリの起動と通知配信](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)」を参照してください。 |
| リッチメディアコンテンツのURL（画像ファイル）<br>（Androidのみに適用） | ナトリウム | media-attachment-url | 通知にリッチコンテンツを追加する画像ファイルのURL。 |
| ナトリウム | _mId<br>_dId | _mId <br>_dId | broadlogIdとdeliveryIdの値。<br>これらの属性は、アプリが追跡ポストバックを呼び出して、プッシュ通知がクリックまたは開かれた日時を追跡する場合に必要です。 この情報は計算され、ユーザーの介入なしでアプリサーバーによって内部的に送信されます。<br>ポストバックに関する情報は、この [ページに記載されています](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)。 |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーによって送信されるペイロード情報は、プッシュ通知が受信されたことを示すイベントハンドラーで、モバイルアプリコードによって受信されます。 このイベントは、対象となるモバイルプラットフォームによって異なり、また、アプリがフォアグラウンドで実行されているかバックグラウンドで実行されているかによって異なります。 次のドキュメントは、使用事例に基づいて、処理するイベントハンドラを特定する際に役立ちます。

* iOSアプリケーション： **「** リモート通知 [」の「リモート通知の処理](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)」の節を参照してください。
* Androidアプリケーション： [Androidクライアントアプリでのメッセージの受信](https://firebase.google.com/docs/cloud-messaging/android/receive)

**iOSモバイルアプリのサンプル**

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

**AndroidモバイルFCMアプリのサンプル**

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
