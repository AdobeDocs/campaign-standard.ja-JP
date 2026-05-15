---
title: Campaign Standard プッシュ通知ペイロード構造について
description: モバイルアプリケーションで受信したペイロードの構造について説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
TQID: https://experienceleague.adobe.com/KSJ-umygCpPr5pjkpiAcbHh-zb1HjK-vZJJLCXz3c5A
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1150
ht-degree: 5%

---

# プッシュ通知のペイロード構造について {#push-payload}

Adobe Campaignを使用すると、iOSおよびAndroidのモバイルデバイスで、パーソナライズされたセグメント化されたプッシュ通知をモバイルアプリケーション（モバイルアプリ）に送信できます。

モバイルアプリで受信されるすべてのプッシュ通知には、アプリが使用する一部の情報が含まれます。プッシュ通知が送信された場合にプッシュ通知を表示し、特にサイレントプッシュ通知が送信された場合に、さらに何らかの処理を行う可能性が最も高くなります。

この情報は、プッシュ通知を受信したことを示すイベントハンドラーで、モバイルアプリコードによって受信されます。 Adobe Campaign Standardからプッシュ通知を送信する場合、モバイルアプリで受信した情報には、Campaign Standardが提供する一部の機能を活用するために使用できるCampaign Standard固有の情報も含まれている場合があります。 さらに、ペイロードには、モバイルアプリで使用できるカスタムデータを含めることができます。

このドキュメントでは、Adobe Campaign Standardからアプリにプッシュ通知が正常に送信されたときに、モバイルアプリで受信されるペイロードの構造について説明します。

>[!NOTE]
>
>ペイロードの構造は、モバイルアプリの種類（iOS アプリ、FCM対応のAndroid アプリ）によって異なります。

## プッシュペイロード構造 {#push-payload-structure}

この節では、様々なモバイルプラットフォームのサンプルペイロードの構造を詳しく説明し、その中に含まれる主な属性について説明します。 これは、イベントハンドラーでモバイルアプリコードで受信したペイロードの構造で、プッシュ通知を受信したことを示します。

ペイロード属性とその値は、プッシュ通知の詳細オプションで提供される設定によって異なります。 この節では、Campaign Standard UIでのこれらの設定とペイロード内の属性のマッピングも提供して、Campaign Standardでオプションを設定する際にペイロードがどのように変化するかを明確にします。

### IOS モバイルアプリの場合 {#payload-structure-ios}

**サンプル ペイロードがAdobe CampaignからiOS アプリに送信されました：**

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

[iOS APNS Tester](https://pushtry.com/)**で使用する** JSON サンプルペイロード

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

ペイロードの最も重要なセクションはaps ディクショナリで、これはApple定義のキーを含み、通知を受け取るシステムがユーザーに警告する方法を判断するために使用されます。 このセクションには、プッシュ通知の動作を作成するためにモバイルアプリで使用される定義済みキーが含まれています。

Apps内の属性について詳しくは、Apple開発者ドキュメントを参照してください。[ リモート通知ペイロードの作成](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)。

### Android アプリの場合 {#payload-structure-android}

**サンプルのペイロードをAdobe CampaignからAndroid アプリに送信**

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

**Google FCM テスター[を使用するためのJSON サンプルペイロード ](https://pushtry.com/)**

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

ペイロードには、カスタムキーと値のペアを含むすべてのプッシュ通知配信コンテンツを含むデータメッセージが含まれており、クライアントアプリは、必要に応じてプッシュ通知を作成および表示するか、他のビジネスロジックを追加するためにメッセージを処理する必要があります。

Android ペイロードの側面を理解するには、[ メッセージングの概念とオプション（fcm） ](https://firebase.google.com/docs/cloud-messaging/concept-options)を参照してください。

>[!NOTE]
>
>Android ペイロードでの通知メッセージのサポートは2018年1月の時点で削除され、ユーザーがアプリを操作しなくてもアプリを起動してモバイルアプリに制御を渡せるようになりました。

### Campaign Standard設定とペイロード属性のマッピング {#mapping-payload}

| キャンペーン設定 | IOSの影響を受ける属性 | Androidの影響を受ける属性 | 説明 |
|:-:|:-:|:-:|:-:|
| メッセージ タイトル <br> メッセージ本文 | タイトル <br>→アラート→本文 | タイトル <br>body | このデータには、アラートメッセージの詳細が含まれます。<br> タイトル キーと本文キーは、アラートの内容を提供します。 |
| サウンドを再生 | サウンド | サウンド | アラートで再生するカスタムサウンド。 |
| バッジの値 | バッジ | バッジ | アプリのアイコンのバッジに使用する整数値。 |
| ディープリンクを追加 | uri | NA | ディープリンクを使用すると、（Web ブラウザーページを開くのではなく）ユーザーをアプリケーション内のコンテンツに直接移動させることができます。 |
| カテゴリ | カテゴリー | カテゴリー | リモート通知でカスタムアクションを表示する。 <br> カテゴリーキーを使用すると、そのカテゴリのアクションを警告インターフェイスのボタンとしてシステムに表示できます。 |
| カスタムフィールド | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | アプリに送信するカスタムデータ。 |
| リッチメディアコンテンツ URL （画像、GIF、オーディオおよびビデオファイル） <br> （iOS 10以降にのみ適用） | media-attachment-url | NA | 通知にリッチコンテンツを追加するためのメディアファイルのURL。 <br>このURLに値を指定すると、可変コンテンツフラグが自動的にペイロードに送信されます。<br> （iOS 10以降にのみ適用） |
| 可変コンテンツ <br> （iOS 10以降にのみ適用） | mutable-content | NA | アプリの通知サービス拡張機能は、可変コンテンツキーを使用してすべてのリモート通知を「インターセプト」し、リクエストペイロードのコンテンツを処理/操作できるようにします。これにより、通知をカスタマイズできます。 この機能のユースケースには、複数のメディアのダウンロードと表示、プッシュペイロードに存在する暗号化データの復号化が含まれます。 詳細については、[ リモート通知のペイロードの変更](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)を参照してください。 <br> （iOS 10以降にのみ適用） |
| 利用可能なコンテンツ | content-available | NA | このオプションを選択すると、iOS アプリがバックグラウンドまたはサスペンド状態のときに起動できるようになります。 ウェイクアップとは、アプリがバックグラウンドで実行され、プッシュ通知データペイロードの受信を担当する適切なイベントハンドラーが制御を取得し、データを使用してカスタムプッシュ通知の作成や表示など、あらゆる計算を行うことができることを意味します。 詳細については、[通知配信を使用したアプリの起動](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)を参照してください。 |
| リッチメディアコンテンツ URL （画像ファイル） <br> （Androidにのみ適用） | NA | media-attachment-url | 通知にリッチコンテンツを追加する画像ファイルのURL。 |
| NA | _mId<br>_dId | _mId <br>_dId | broadlogIdおよびdeliveryIdの値。<br> プッシュ通知がクリック/開かれたときにトラッキング ポストバックをトラッキングに呼び出してトラッキングを実行する場合は、これらの属性が必要です。 この情報は、ユーザーの介入なしにアプリサーバーによって内部的に計算および送信されます。<br> ポストバックに関する情報は、この[ ページ ](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)にあります。 |

### モバイルアプリコードでペイロード情報を取得する方法 {#payload-information}

アプリサーバーが送信したペイロード情報は、プッシュ通知を受信したことを示すイベントハンドラー内のモバイルアプリコードによって受信されます。 このイベントは、作業中のモバイルプラットフォームと、アプリが前景または背景で実行されているかどうかに応じて異なります。 次のドキュメントは、ユースケースに基づいて、処理するイベントハンドラーを特定するのに役立ちます。

* iOS アプリケーション：[ リモート通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)の&#x200B;**リモート通知の処理** セクション。
* Android アプリケーション：[Android クライアントアプリでメッセージを受信](https://firebase.google.com/docs/cloud-messaging/android/receive)

iOS モバイルアプリの&#x200B;**サンプル**

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

Android Mobile FCM アプリの&#x200B;**サンプル**

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
