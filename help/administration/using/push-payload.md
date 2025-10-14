---
title: Campaign Standardプッシュ通知のペイロード構造について
description: モバイルアプリケーションで受信されるペイロードの構造について説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 3%

---

# プッシュ通知のペイロード構造について {#push-payload}

Adobe Campaignでは、iOSやAndroidのモバイルデバイスで、パーソナライズされセグメント化されたプッシュ通知をモバイルアプリケーション（モバイルアプリ）に送信できます。

モバイルアプリで受信されるすべてのプッシュ通知には、アラート プッシュ通知が送信された場合にプッシュ通知の表示に使用される情報と、特にサイレントプッシュ通知が送信された場合に追加の計算が行われる可能性が高い情報があります。

この情報は、プッシュ通知が受信されたことを示すイベントハンドラーでモバイルアプリコードによって受信されます。 Adobe Campaign Standardからプッシュ通知を送信する場合、モバイルアプリで受信する情報にはCampaign Standard固有の情報も含まれる場合があり、Campaign Standardが提供する機能を活用するために使用されることがあります。 さらに、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントでは、プッシュ通知がAdobe Campaign Standardからアプリに正常に送信されたときにモバイルアプリで受信されるペイロードの構造について説明します。

>[!NOTE]
>
>ペイロード構造はモバイルアプリのタイプ（iOS アプリ、FCM 対応Android アプリなど）によって異なります。

## プッシュペイロード構造 {#push-payload-structure}

この節では、様々なモバイルプラットフォーム向けのサンプルペイロードの構造を詳しく説明し、その中に含まれる主な属性について説明します。 これは、プッシュ通知が受信されたことを示す、イベントハンドラーのモバイルアプリコードで受信されたペイロードの構造です。

ペイロード属性とその値は、プッシュ通知の詳細オプションで指定された設定に応じて異なります。 また、この節では、Campaign Standardでのオプション設定時にペイロードがどのように変化するかを明確にするために、Campaign StandardUI のこれらの設定とペイロードの属性の間のマッピングも示します。

### iOS モバイルアプリの場合 {#payload-structure-ios}

**Adobe CampaignからiOS アプリに送信されるサンプルペイロード：**

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

**[iOS APNS テスターで使用する JSON サンプルペイロード &#x200B;](https://pushtry.com/)**

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

ペイロードの最も重要なセクションは aps ディクショナリです。このディクショナリには、Appleで定義されたキーが含まれており、通知を受け取ったシステムがユーザーに警告する方法（あるとしても）を決定するために使用されています。 この節には、プッシュ通知の動作を作成するためにモバイルアプリで使用される、事前定義済みのキーが含まれています。

Aps 内の属性について詳しくは、Apple開発者向けドキュメント [&#x200B; リモート通知ペイロードの作成 &#x200B;](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1) を参照してください。

### Android アプリケーションの場合 {#payload-structure-android}

**Adobe CampaignからAndroid アプリに送信されるサンプルペイロード**

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

**1&rbrace;Google FCM テスターを使用するための JSON サンプルペイロード [&#128279;](https://pushtry.com/)**

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

ペイロードには、カスタムのキーと値のペアを含むすべてのプッシュ通知配信コンテンツを含むデータメッセージが含まれています。クライアントアプリは、必要に応じてプッシュ通知を作成および表示したり、その他のビジネスロジックを追加したりするためにメッセージを処理する必要があります。

Android ペイロードの側面を理解するには、[&#x200B; メッセージングの概念とオプション（fcm） &#x200B;](https://firebase.google.com/docs/cloud-messaging/concept-options) を参照してください。

>[!NOTE]
>
>Android ペイロードでの通知メッセージのサポートは、ユーザーがアプリとやり取りしなくてもアプリをウェイクアップしてモバイルアプリに制御を渡すことができるように、2018 年 1 月に削除されました。

### Campaign Standard設定とペイロード属性のマッピング {#mapping-payload}

| Campaign 設定 | iOSの影響を受ける属性 | Androidの影響を受ける属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージタイトル <br> メッセージ本文 | アラート → タイトル <br> アラート →本文 | title <br>body | このデータには、アラートメッセージの詳細が含まれます。<br> タイトルキーと本文キーは、アラートの内容を提供します。 |
| サウンドを再生 | サウンド | サウンド | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンのバッジを付けるために使用される整数値。 |
| ディープリンクを追加 | uri | 該当なし | ディープリンクを使用すると、（Web ブラウザーページを開くのではなく）ユーザーをアプリケーション内のコンテンツに直接移動させることができます。 |
| カテゴリ | カテゴリー | カテゴリー | リモート通知でカスタムアクションを表示する。 <br> カテゴリキーを使用すると、そのカテゴリのアクションをアラートインターフェイスのボタンとしてシステムに表示できます。 |
| カスタムフィールド | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | アプリに送信するカスタムデータ。 |
| リッチメディアコンテンツ URL （画像、gif、オーディオおよびビデオファイル） <br> （iOS 10 以降にのみ適用） | media-attachment-url | 該当なし | 通知にリッチコンテンツを追加するためのメディアファイルの URL。 <br> この URL に値を指定すると、可変コンテンツフラグがペイロードに自動的に送信されます。 <br> （iOS 10 以降にのみ適用） |
| 可変コンテンツ <br> （iOS 10 以降にのみ適用） | 可変コンテンツ | 該当なし | アプリの通知サービス拡張機能は、可変コンテンツキーを使用してすべてのリモート通知を「インターセプト」し、リクエストペイロードの内容を処理/操作できます。この内容を使用して通知をカスタマイズできます。 この機能のユースケースには、複数のメディアのダウンロードと表示、プッシュペイロードに存在する暗号化データの復号化が含まれます。 詳しくは、[&#x200B; リモート通知のペイロードの変更 &#x200B;](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html) を参照してください。 <br> （iOS 10 以降にのみ適用） |
| Content Available | content-available | 該当なし | このオプションを選択すると、iOS アプリがバックグラウンド/休止状態の間に、アプリをウェイクアップできます。 ウェイクアップとは、アプリがバックグラウンドで実行され、プッシュ通知データペイロードの受信を担当する適切なイベントハンドラーがコントロールを取得し、そのデータを使用して、カスタムプッシュ通知の作成や表示など、任意の計算を実行できることを意味します。 詳しくは、[&#x200B; 通知配信でアプリを起動 &#x200B;](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html) を参照してください。 |
| リッチメディアコンテンツ URL （画像ファイル） <br> （Android にのみ適用） | 該当なし | media-attachment-url | 通知にリッチコンテンツを追加するための画像ファイルの URL。 |
| 該当なし | _mId<br>_dId | _mId <br>_dId | broadlogId と deliveryId の値。<br> これらの属性は、アプリがプッシュ通知がクリック/開かれたときに追跡するトラッキングポストバックを呼び出す場合に必要です。 この情報は、ユーザーの操作なしでアプリサーバーによって内部で計算および送信されます。<br> ポストバックに関する情報は、この [&#x200B; ページ &#x200B;](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback) を参照してください。 |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーが送信するペイロード情報は、プッシュ通知を受信したことを示すイベントハンドラーでモバイルアプリコードによって受信されます。 このイベントは、作業中のモバイルプラットフォームや、アプリがフォアグラウンドまたはバックグラウンドで実行されているかどうかによって異なります。 ユースケースに基づいて処理するイベントハンドラーを特定するには、次のドキュメントを参照してください。

* iOS アプリケーション：「リモート通知 **の** リモート通知の処理 [&#x200B; セクション &#x200B;](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)
* Android アプリケーション：[Android クライアントアプリでのメッセージの受信 &#x200B;](https://firebase.google.com/docs/cloud-messaging/android/receive)

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

**Android Mobile FCM アプリのサンプル**

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
