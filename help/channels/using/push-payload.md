---
title: Campaign Standardプッシュ通知のペイロード構造について
description: このドキュメントは、モバイルアプリケーションで受け取るペイロードの構造を記述することを目的としています。
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
source-git-commit: 302159577f5a7d917ba253994ff23c4980d518e5

---


# Campaign Standardプッシュ通知のペイロード構造について {#push-payload}

Adobe Campaignを使用すると、iOSおよびAndroidのモバイルデバイス上で、パーソナライズされたセグメント化されたプッシュ通知をモバイルアプリ（モバイルアプリ）に送信できます。

モバイルアプリで受信されるすべてのプッシュ通知は、アプリが使用する情報を持ちます。この情報は、アラートのプッシュ通知が送信された場合にプッシュ通知を表示するために使用され、特にサイレントプッシュ通知が送信された場合にも、多くの場合は計算を行います。

この情報は、プッシュ通知を受信したことを示すイベントハンドラーで、モバイルアプリコードによって受信されます。 Adobe Campaign標準からプッシュ通知を送信する場合、モバイルアプリで受信される情報には、Campaign Standard固有の情報も含まれ、Campaign Standardが提供する機能の活用に使用される場合があります。 さらに、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントは、プッシュ通知がApp Standardからアプリに正常に送信された場合にモバイルアプリで受信されるペイロードの構造をAdobe Campaignします。

>[!NOTE]
>
>ペイロードの構造は、モバイルアプリのタイプ（iOSアプリ、FCM対応のAndroidアプリなど）によって異なります。

## プッシュペイロード構造 {#push-payload-structure}

この節では、様々なモバイルプラットフォームのサンプルペイロードの構造と、それに含まれる主要な属性について説明します。 これは、プッシュ通知が受信されたことを示すイベントハンドラーのモバイルアプリコードで受信されたペイロードの構造です。

ペイロード属性とその値は、プッシュ通知のアドバンスオプションで提供される設定によって異なります。 また、この節では、Campaign StandardUIのこれらの設定とペイロードの属性との間のマッピングも提供し、Campaign Standardでのオプションの設定でペイロードがどのように変化するかを明確に示します。

### iOSモバイルアプリの場合 {#payload-structure-ios}

**ペイロードのサンプルがAdobe CampaignからiOSアプリに送信されました：**

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

**iOS APNSテスターで使用するJSONサンプルペ[イロード](https://pushtry.com/)**

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

ペイロードの最も重要なセクションはapsディクショナリです。この中にはAppleで定義されたキーが含まれ、通知を受信するシステムがユーザーに警告する方法を決定するために使用されます。 この節には、プッシュ通知の動作を策定するためにモバイルアプリで使用される、事前定義されたキーが含まれています。

aps内の属性に関する詳細は、Apple Developer Docsを参照してください。リモー [ト通知ペイロードの作成](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)。

### Androidアプリの場合 {#payload-structure-android}

**ペイロードのサンプルをAdobe CampaignからAndroidアプリに送信**

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

ペイロードには、カスタムのキーと値のペアを含むすべてのプッシュ通知配信のコンテンツを含むデータメッセージが含まれ、クライアントアプリは、必要に応じて、プッシュ通知を作成し表示するメッセージを処理するか、他のビジネスロジックを追加する必要があります。

Androidペイロードの側面を理解するには、「メッセージングの概 [念とオプション(fcm)」を参照してくださ](https://firebase.google.com/docs/cloud-messaging/concept-options)い。

>[!NOTE]
>
>Androidペイロードでの通知メッセージのサポートが2018年1月に削除され、アプリのスリープを解除し、ユーザーがアプリを操作することなくモバイルアプリに制御を渡せるようになりました。

### ペイロード設定とCampaign Standard属性のマッピング {#mapping-payload}

| キャンペーン設定 | iOSの影響を受けた属性 | Androidの影響を受けた属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージタイト <br>ルメッセージ本文 | 警告→タイトルの警 <br> 告→本文 | 表題 <br>本文 | このデータには、アラートメッセージの詳細が含まれています。<br>タイトルとボディキーは、アラートの内容を提供します。 |
| サウンドを再生 | サウンド | サウンド | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンのマークに使用する整数値。 |
| 追加検問 | uri | NA | ディープリンクを使用すると、Webブラウザーページを開く代わりに、アプリケーション内のコンテンツにユーザーを直接移動できます。 |
| カテゴリ | category | category | リモート通知でカスタムアクションを表示する。 <br>カテゴリキーは、そのアクションのアクションをアラートインターフェイスのカテゴリとして表示するのに役立ちます。 |
| カスタムフィールド | custom_field1、custom_field2 ... | custom_field1、custom_field2 ... | アプリに送信する任意のカスタムデータ。 |
| リッチメディアコンテンツのURL（画像、GIF、オーディオ、ビデオファイル）<br>（iOS 10以降にのみ適用） | media-attachment-url | NA | 通知にリッチコンテンツを追加するメディアファイルのURL。 <br>このURLの値を指定すると、可変コンテンツフラグがペイロードに自動的に送信されます。 <br> （iOS 10以降にのみ適用） |
| 可変コン <br> テンツ（iOS 10以降にのみ適用） | 可変コンテンツ | NA | アプリのNotification Service Extensionは、可変コンテンツキーを使用してすべてのリモート通知を「傍受」し、要求ペイロードの内容を処理/操作できるようにします。これにより、通知のカスタマイズに使用できます。 この機能の使用例としては、複数のメディアのダウンロードと表示、プッシュペイロードに存在する暗号化されたデータの復号化などがあります。 詳しくは、「リモート通知のペイロ [ードの変更」を参照してください](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)。 <br>（iOS 10以降にのみ適用） |
| 利用可能なコンテンツ | コンテンツを利用できる | NA | このオプションを選択すると、バックグラウンド/休止状態のiOSアプリのスリープ解除が有効になります。 スリープ状態を解除すると、アプリがバックグラウンドで実行され、プッシュ通知データのペイロードを受け取る適切なイベントハンドラーが制御を取得し、データを使用して任意の計算を行うことができます。 詳しくは、通知機能付きのアプリの起 [動を参照してください](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)。 |
| リッチメディアコンテンツのURL（画像ファイル）<br>（Androidのみに適用） | NA | media-attachment-url | 通知にリッチコンテンツを追加する画像ファイルのURL。 |
| NA | _mId<br>_dId | _mId <br>_dId | broadlogIdとdeliveryIdの値。<br>プッシュ通知がいつクリックまたは開かれたかを追跡するために、アプリが追跡ポストバックを呼び出す場合、これらの属性は必須です。 この情報は、ユーザーの介入なしに、アプリサーバーによって内部的に計算され、送信されます。<br>ポストバックに関する情報は、このページで確認で [きます](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)。 |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーから送信されるペイロード情報は、プッシュ通知が受信されたことを示すイベントハンドラーで、モバイルアプリコードによって受信されます。 このイベントは、作業対象のモバイルプラットフォームによって異なり、また、アプリがフォアグラウンドで実行されているかバックグラウンドで実行されているかによって異なります。 以下のドキュメントは、使用事例に基づいて処理するイベントハンドラを特定するのに役立ちます。

* iOSアプリケーション：「リモー **ト通知の処理** 」セクシ [ョンを参照します](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)。
* Androidアプリケーション：Androidクライ [アントアプリでのメッセージの受信](https://firebase.google.com/docs/cloud-messaging/android/receive)

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
