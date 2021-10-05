---
title: Campaign Standardプッシュ通知のペイロード構造について
description: このドキュメントは、モバイルアプリケーションで受け取るペイロードの構造を説明することを目的としています。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 5%

---

# プッシュ通知のペイロード構造について {#push-payload}

Adobe Campaignでは、iOS および Android モバイルデバイスに対して、パーソナライズおよびセグメント化されたプッシュ通知をモバイルアプリケーション（モバイルアプリ）に送信できます。

モバイルアプリで受信されるすべてのプッシュ通知は、アラートのプッシュ通知が送信された場合にプッシュ通知を表示するためにアプリで使用される情報を持ち、特に無音のプッシュ通知が送信された場合に、さらに何らかの計算を行う可能性が高い。

この情報は、プッシュ通知が受信されたことを示すイベントハンドラー内のモバイルアプリコードで受信されます。 Adobe Campaign Standardからプッシュ通知を送信する際、モバイルアプリで受信する情報には、Campaign Standard固有の情報も含まれ、Campaign Standardが提供する機能を活用するために使用される場合があります。 さらに、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントでは、プッシュ通知がAdobe Campaign Standardからアプリに正常に送信された場合にモバイルアプリで受信されるペイロードの構造を説明します。

>[!NOTE]
>
>ペイロード構造は、モバイルアプリのタイプ（iOS アプリ、FCM 対応の Android アプリ）によって異なります。

## プッシュペイロード構造 {#push-payload-structure}

この節では、様々なモバイルプラットフォームのサンプルペイロードの構造と、そのペイロードに含まれる主要な属性について説明します。 これは、プッシュ通知が受信されたことを示すイベントハンドラーのモバイルアプリコードで受信されたペイロードの構造です。

ペイロード属性とその値は、プッシュ通知の詳細オプションで提供される設定に基づいて異なります。 また、この節では、Campaign StandardUI でのこれらの設定とCampaign Standardの属性のマッピングを示し、ペイロードの設定時にペイロードがどのように変わるかを明確にします。

### iOS モバイルアプリの場合 {#payload-structure-ios}

**Adobe Campaignから iOS アプリに送信されたペイロードのサンプル：**

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

**iOS APNS テスターで使用する JSON サン [プルペイロード](https://pushtry.com/)**

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

ペイロードの最も重要なセクションは、Apple 定義のキーを含む aps 辞書です。通知を受け取るシステムがユーザーに警告する方法を決定するのに使用されます。 この節には、プッシュ通知の動作を策定するためにモバイルアプリで使用される事前定義済みのキーが含まれています。

aps 内の属性の詳細については、Apple 開発者向けドキュメントを参照してください。[ リモート通知ペイロード ](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1) の作成。

### Android アプリの場合 {#payload-structure-android}

**Adobe Campaignから Android アプリに送信されるペイロードのサンプル**

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

**Google FCM テスターを使用する JSON サン [プルペイロード](https://pushtry.com/)**

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

ペイロードには、カスタムのキーと値のペアを含むすべてのプッシュ通知配信コンテンツを含むデータメッセージが含まれ、必要に応じて、または他のビジネスロジックを追加するために、クライアントアプリはメッセージを処理する必要があります。

Android ペイロードの側面を理解するには、[ メッセージングの概念とオプション (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options) を参照してください。

>[!NOTE]
>
>2018 年 1 月に、Android ペイロードでの通知メッセージのサポートが削除され、ユーザーがアプリを操作する必要なく、アプリを起動し、モバイルアプリに制御を渡すことができるようになりました。

### Campaign Standard設定とペイロード属性のマッピング {#mapping-payload}

| キャンペーンの設定 | iOS の影響を受けた属性 | Android の影響を受けた属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージタイトル <br> メッセージ本文 | alert → title <br> alert → body | title <br>body | このデータには、アラートメッセージの詳細が含まれています。<br>タイトルキーと本文キーは、アラートの内容を示します。 |
| サウンドの再生 | sound | sound | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンにバッジを付けるために使用される整数値です。 |
| ディープリンクの追加 | uri | 該当なし | ディープリンクを使用すると、（Web ブラウザーページを開くのではなく）ユーザーをアプリケーション内のコンテンツに直接移動させることができます。 |
| カテゴリ | カテゴリー | カテゴリー | リモート通知でカスタムアクションを表示する。 <br>カテゴリキーは、そのカテゴリのアクションをアラートインターフェイスのボタンとして表示するのに役立ちます。 |
| カスタムフィールド | custom_field1、custom_field2 ... | custom_field1、custom_field2 ... | アプリに送信する任意のカスタムデータ。 |
| リッチメディアコンテンツ URL（画像、gif、オーディオおよびビデオファイル）<br>（iOS 10 以降にのみ適用） | media-attachment-url | 該当なし | 通知にリッチコンテンツを追加するメディアファイルの URL。 <br>この URL に値を指定すると、mutable-content フラグが自動的にペイロードに送信されます。<br> （iOS 10 以降にのみ適用） |
| 可変コンテンツ <br> （iOS 10 以降にのみ適用） | mutable-content | 該当なし | アプリの Notification Service Extension は、可変コンテンツキーを使用してすべてのリモート通知を「傍受」し、要求ペイロードの内容を処理/操作できるようにします。これを使用して通知をカスタマイズできます。 この機能の使用例には、複数のメディアのダウンロードと表示、プッシュペイロードに存在する暗号化されたデータの復号化などがあります。 詳しくは、[ リモート通知のペイロードの変更 ](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html) を参照してください。 <br>（iOS 10 以降にのみ適用） |
| 利用可能なコンテンツ | content-available | 該当なし | このオプションを選択すると、バックグラウンド/休止状態の iOS アプリを起動できます。 起動すると、アプリがバックグラウンドで実行され、プッシュ通知データペイロードを受け取る適切なイベントハンドラーが制御を取得し、カスタムプッシュ通知の作成や表示など、データを使用して任意の計算を実行できます。 詳しくは、[ 通知配信を使用したアプリの起動 ](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html) を参照してください。 |
| リッチメディアコンテンツ URL（画像ファイル）<br>（Android のみ適用） | 該当なし | media-attachment-url | 通知にリッチコンテンツを追加する画像ファイルの URL。 |
| 該当なし | _mId<br>_dId | _mId <br>_dId | broadlogId と deliveryId の値。<br>これらの属性は、プッシュ通知がクリックまたは開封されたタイミングを追跡するためにアプリがトラッキングポストバックを呼び出す場合に必要です。この情報は、ユーザーの介入なしに、アプリサーバーによって計算され、内部的に送信されます。<br>ポストバックに関する情報は、このページを参照し [てください](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)。 |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーによって送信されるペイロード情報は、プッシュ通知が受信されたことを示すイベントハンドラー内のモバイルアプリコードによって受信されます。 このイベントは、作業中のモバイルプラットフォームや、アプリがフォアグラウンドで実行されているかバックグラウンドで実行されているかによって異なります。 次のドキュメントは、使用事例に基づいて、処理するイベントハンドラーを特定するのに役立ちます。

* iOS アプリケーション：**[ リモート通知 ](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html) のリモート通知** セクションの処理
* Android アプリケーション：[Android クライアントアプリでのメッセージの受信 ](https://firebase.google.com/docs/cloud-messaging/android/receive)

**iOS モバイルアプリのサンプル**

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

**Android モバイル FCM アプリのサンプル**

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
