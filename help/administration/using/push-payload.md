---
title: Campaign Standardプッシュ通知のペイロード構造について
description: モバイルアプリケーションで受け取るペイロードの構造について説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 5%

---

# プッシュ通知のペイロード構造について {#push-payload}

Adobe Campaignでは、iOSおよび Android モバイルデバイスで、パーソナライズおよびセグメント化されたプッシュ通知をモバイルアプリケーション（モバイルアプリ）に送信できます。

モバイルアプリで受信されるすべてのプッシュ通知には、アプリがプッシュ通知を表示するために使用する情報が含まれます。アラートプッシュ通知が送信された場合は、ほとんどの場合はさらに計算をおこないます。

この情報は、プッシュ通知が受信されたことを示すイベントハンドラーで、モバイルアプリコードによって受信されます。 Adobe Campaign Standardからプッシュ通知を送信する際、モバイルアプリで受信する情報には、Campaign Standard固有の情報も含まれ、Campaign Standardが提供する機能を活用するために使用できます。 さらに、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントでは、Adobe Campaign Standardからアプリにプッシュ通知が正常に送信された場合にモバイルアプリで受け取られるペイロードの構造を説明します。

>[!NOTE]
>
>ペイロード構造は、モバイルアプリのタイプ (iOSアプリ、FCM 対応 Android アプリ ) によって異なります。

## ペイロード構造をプッシュ {#push-payload-structure}

この節では、様々なモバイルプラットフォーム向けのサンプルペイロードの構造と、それに含まれる主要な属性について説明します。 これは、プッシュ通知が受信されたことを示す、イベントハンドラー内のモバイルアプリコードで受け取ったペイロードの構造です。

ペイロード属性とその値は、プッシュ通知の詳細オプションで提供される設定に基づいて異なります。 また、この節では、Campaign StandardUI でのこれらの設定とペイロードの属性のマッピングを示し、Campaign Standardでのオプションの設定時にペイロードがどのように変更されるかを明確にします。

### iOS Mobile アプリの場合 {#payload-structure-ios}

**Adobe CampaignからiOSアプリに送信されたサンプルペイロード：**

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

**で使用する JSON サンプルペイロード [iOS APNS Tester](https://pushtry.com/)**

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

ペイロードの最も重要な節は、aps 辞書です。この辞書は、Appleで定義されたキーを含み、通知を受け取るシステムがユーザーに警告する方法を決定するために使用されます（すべての場合）。 このセクションには、プッシュ通知の動作を定式化するためにモバイルアプリで使用される事前定義済みのキーが含まれています。

aps 内の属性の詳細については、 Apple開発者向けドキュメントを参照してください。 [リモート通知ペイロードの作成](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### Android アプリの場合 {#payload-structure-android}

**Adobe Campaignから Android アプリに送信されるサンプルペイロード**

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

**使用する JSON サンプルペイロード [Google FCM テスター](https://pushtry.com/)**

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

ペイロードには、カスタムのキーと値のペアを含むすべてのプッシュ通知配信コンテンツを含むデータメッセージが含まれ、必要に応じて、プッシュ通知を作成して表示するメッセージを処理するか、他のビジネスロジックを追加します。

Android ペイロードの側面を理解するには、を参照してください。 [メッセージの概念とオプション (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>2018 年 1 月に、Android ペイロードでの通知メッセージのサポートが削除され、ユーザーがアプリを操作する必要なく、アプリを起動し、モバイルアプリに制御を渡せるようになりました。

### Campaign Standard設定とペイロード属性のマッピング {#mapping-payload}

| キャンペーン設定 | iOSの影響を受けた属性 | Android の影響を受ける属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージのタイトル <br>メッセージ本文 | アラート→タイトル <br> 警告→本文 | タイトル <br>本文 | このデータには、アラートメッセージの詳細が含まれています。<br>タイトルキーと本文キーは、アラートの内容を提供します。 |
| サウンドの再生 | 音 | 音 | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンにバッジを付けるために使用される整数値。 |
| ディープリンクの追加 | uri | 該当なし | ディープリンクを使用すると、（Web ブラウザーページを開くのではなく）ユーザーをアプリケーション内のコンテンツに直接移動させることができます。 |
| カテゴリ | カテゴリー | カテゴリー | リモート通知でカスタムアクションを表示する。 <br>カテゴリキーは、そのカテゴリのアクションをアラートインターフェイスのボタンとして表示するのに役立ちます。 |
| カスタムフィールド | custom_field1、custom_field2 ... | custom_field1、custom_field2 ... | アプリに送信する任意のカスタムデータです。 |
| リッチメディアコンテンツの URL（画像、gif、オーディオおよびビデオファイル）<br>(iOS 10 以降にのみ適用 ) | media-attachment-url | 該当なし | 通知にリッチコンテンツを追加するためのメディアファイルの URL。 <br>この URL に値を指定すると、mutable-content フラグが自動的にペイロードに送信されます。 <br> (iOS 10 以降にのみ適用 ) |
| 可変コンテンツ <br> (iOS 10 以降にのみ適用 ) | mutable-content | 該当なし | アプリの通知サービス拡張は、可変コンテンツキーを使用してすべてのリモート通知を「傍受」し、要求ペイロードの内容を処理または操作できるようにします。これは、通知のカスタマイズに使用できます。 この機能の使用例には、複数のメディアのダウンロードと表示、プッシュペイロードに存在する暗号化されたデータの復号化などがあります。 詳しくは、 [リモート通知のペイロードを変更する](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(iOS 10 以降にのみ適用 ) |
| 利用可能なコンテンツ | content-available | 該当なし | このオプションを選択すると、バックグラウンド/休止状態のiOSアプリをスリープ解除できます。 起動すると、アプリがバックグラウンドで実行され、プッシュ通知データペイロードの受信に対応する適切なイベントハンドラーがコントロールを取得し、データを使用してカスタムプッシュ通知の作成や表示などの計算を実行できます。 詳しくは、 [通知配信でアプリを起動](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| リッチメディアコンテンツの URL（画像ファイル）<br>（Android にのみ適用） | 該当なし | media-attachment-url | 通知にリッチコンテンツを追加する画像ファイルの URL。 |
| 該当なし | _mId<br>_dId | _mId <br>_dId | broadlogId と deliveryId の値。<br>これらの属性は、アプリがトラッキングポストバックを呼び出して、プッシュ通知がいつクリックまたは開かれたかを追跡する場合に必要です。 この情報は、ユーザーの介入なしにアプリサーバーによって計算され、内部的に送信されます。<br>ポストバックに関する情報は、次を参照してください。 [ページ](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーによって送信されたペイロード情報は、プッシュ通知が受信されたことを示すイベントハンドラーでモバイルアプリコードによって受信されます。 このイベントは、作業対象のモバイルプラットフォームと、アプリがフォアグラウンドで実行されているかバックグラウンドで実行されているかによって異なります。 次のドキュメントは、使用例に基づいて、処理するイベントハンドラーを識別するのに役立ちます。

* iOSアプリケーション： **リモート通知の処理** のセクション [リモート通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Android アプリケーション： [Android クライアントアプリでのメッセージの受信](https://firebase.google.com/docs/cloud-messaging/android/receive)

**iOS Mobile アプリのサンプル**

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
