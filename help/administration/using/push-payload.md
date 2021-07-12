---
solution: Campaign Standard
product: campaign
title: Campaign Standardプッシュ通知のペイロード構造について
description: このドキュメントは、モバイルアプリケーションで受け取るペイロードの構造を説明することを目的としています。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: インスタンス設定
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 5%

---

# プッシュ通知のペイロード構造について {#push-payload}

Adobe Campaignでは、iOSおよびAndroidモバイルデバイスで、パーソナライズおよびセグメント化されたプッシュ通知をモバイルアプリケーション（モバイルアプリ）に送信できます。

モバイルアプリで受信されるすべてのプッシュ通知には、アラートプッシュ通知が送信された場合にプッシュ通知を表示するためにアプリが使用する情報が含まれ、特にサイレントプッシュ通知が送信された場合に、さらに何らかの計算をおこなう可能性が高い。

この情報は、プッシュ通知が受信されたことを示すイベントハンドラーで、モバイルアプリコードによって受信されます。 Adobe Campaign Standardからプッシュ通知を送信する場合、モバイルアプリで受信する情報には、Campaign Standardが提供する機能を活用するために使用できる、Campaign Standard固有の情報が含まれる場合があります。 さらに、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントでは、Adobe Campaign Standardからアプリにプッシュ通知が正常に送信された場合にモバイルアプリで受信されるペイロードの構造を説明します。

>[!NOTE]
>
>ペイロード構造は、モバイルアプリのタイプ（iOSアプリ、FCM対応のAndroidアプリ）によって異なります。

## プッシュペイロード構造 {#push-payload-structure}

この節では、様々なモバイルプラットフォームのサンプルペイロードの構造と、そのペイロードに含まれる主な属性について説明します。 これは、プッシュ通知が受信されたことを示す、イベントハンドラーのモバイルアプリコードで受信されたペイロードの構造です。

ペイロード属性とその値は、プッシュ通知の詳細設定オプションで提供される設定に基づいて異なります。 また、この節では、Campaign Standardでのオプションの設定時にペイロードがどのように変更されるかを明確にするために、Campaign StandardUIでのこれらの設定とペイロードの属性のマッピングも示します。

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

**iOS APNSテスターで使用するJSONサン [プルペイロード](https://pushtry.com/)**

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

ペイロードの最も重要なセクションは、aps辞書です。この辞書には、Appleが定義したキーが含まれ、通知を受け取るシステムがユーザーに警告する方法を決定するために使用されます。 この節には、プッシュ通知の動作を策定するためにモバイルアプリで使用される事前定義済みのキーが含まれています。

aps内の属性の詳細については、Apple開発者向けドキュメントを参照してください。[リモート通知ペイロード](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)を作成しています。

### Androidアプリの場合 {#payload-structure-android}

**Adobe CampaignからAndroidアプリに送信されるペイロードサンプル**

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

**Google FCMテスターを使用するJSONサン [プルペイロード](https://pushtry.com/)**

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

ペイロードには、カスタムのキー/値のペアを含むすべてのプッシュ通知配信コンテンツを含むデータメッセージが含まれ、必要に応じて、または他のビジネスロジックを追加するために、クライアントアプリはメッセージを処理する必要があります。

Androidペイロードの側面を理解するには、[メッセージングの概念とオプション(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options)を参照してください。

>[!NOTE]
>
>2018年1月に、Androidペイロードでの通知メッセージのサポートが削除され、ユーザーがアプリを操作することなく、アプリを起動し、モバイルアプリに制御を渡すことができるようになりました。

### ペイロード設定とCampaign Standard属性のマッピング {#mapping-payload}

| キャンペーンの設定 | iOSの影響を受ける属性 | Androidの影響を受けた属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージタイトル<br>メッセージ本文 | アラート→タイトル<br>アラート→本文 | title <br>body | このデータには、アラートメッセージの詳細が含まれています。<br>タイトルキーと本文キーは、アラートの内容を示します。 |
| サウンドの再生 | 音 | 音 | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンにバッジを付けるために使用される整数値。 |
| ディープリンクの追加 | uri | 該当なし | ディープリンクを使用すると、（Web ブラウザーページを開くのではなく）ユーザーをアプリケーション内のコンテンツに直接移動させることができます。 |
| カテゴリ | カテゴリー | カテゴリー | リモート通知でカスタムアクションを表示する。 <br>カテゴリキーは、そのカテゴリのアクションをアラートインターフェイスのボタンとして表示するのに役立ちます。 |
| カスタムフィールド | custom_field1、custom_field2 ... | custom_field1、custom_field2 ... | アプリに送信する任意のカスタムデータ。 |
| リッチメディアコンテンツURL（画像、gif、オーディオおよびビデオファイル）<br>（iOS 10以降にのみ適用） | media-attachment-url | 該当なし | 通知にリッチコンテンツを追加するためのメディアファイルのURL。 <br>このURLに値を指定すると、mutable-contentフラグが自動的にペイロードに送信されます。<br> （iOS 10以降にのみ適用） |
| 可変コンテンツ<br>（iOS 10以降にのみ適用） | mutable-content | 該当なし | アプリのNotification Service Extensionは、可変コンテンツキーを使用してすべてのリモート通知を「傍受」し、リクエストペイロードの内容を処理/操作できるようにします。これは、通知のカスタマイズに使用できます。 この機能の使用例には、複数のメディアのダウンロードと表示、プッシュペイロードに存在する暗号化されたデータの復号化などがあります。 詳しくは、[リモート通知のペイロードの変更](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)を参照してください。 <br>（iOS 10以降にのみ適用） |
| 利用可能なコンテンツ | content-available | 該当なし | このオプションを選択すると、バックグラウンド/休止状態のiOSアプリを起動できます。 起動すると、アプリがバックグラウンドで実行され、プッシュ通知データペイロードを受け取る適切なイベントハンドラーが制御を受け取り、カスタムプッシュ通知の作成や表示など、データを使用して任意の計算を実行できます。 詳しくは、[通知配信を使用してアプリを起動](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)を参照してください。 |
| リッチメディアコンテンツURL（画像ファイル）<br>（Androidの場合のみ適用） | 該当なし | media-attachment-url | 通知にリッチコンテンツを追加する画像ファイルのURL。 |
| 該当なし | _mId<br>_dId | _mId <br>_dId | broadlogIdとdeliveryIdの値。<br>これらの属性は、アプリがトラッキングポストバックを呼び出して、プッシュ通知がクリックまたは開かれたタイミングを追跡する場合に必要です。この情報は、ユーザーの介入なしに、アプリサーバーによって内部的に計算および送信されます。<br>ポストバックに関する情報は、このページを参照し [てください](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)。 |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーによって送信されるペイロード情報は、プッシュ通知が受信されたことを示すイベントハンドラー内のモバイルアプリコードによって受信されます。 このイベントは、作業中のモバイルプラットフォームや、アプリがフォアグラウンドで実行されているかバックグラウンドで実行されているかによって異なります。 次のドキュメントは、使用事例に基づいて、処理するイベントハンドラーを特定するのに役立ちます。

* iOSアプリケーション：**[リモート通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)のリモート通知**&#x200B;セクションの処理
* Androidアプリケーション：[Androidクライアントアプリでのメッセージの受信](https://firebase.google.com/docs/cloud-messaging/android/receive)

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
