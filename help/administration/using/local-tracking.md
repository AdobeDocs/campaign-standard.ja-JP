---
title: ローカルトラッキングの実装
description: IOSとAndroidでプッシュ通知トラッキングが正しく実装されていることを確認する方法を説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
TQID: https://experienceleague.adobe.com/t8aqY1Bp8McHJjthjuLMZo2zA3-bG6GTC6ZeeVWZD0A
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 574
ht-degree: 1%

---

# ローカルトラッキングの実装 {#local-tracking}

## ローカルトラッキングについて {#about-local-tracking}

このページでは、ローカル通知トラッキングが正しく実装されていることを確認する方法について説明します。 これは、ローカル通知が既に設定されていることを意味します。

ローカル通知トラッキングは、次の3つのタイプに分割できます。

* **ローカルインプレッション** - ローカル通知がデバイスに配信され、通知センターに座っているが、まったくタッチされていない場合。 ほとんどの場合、インプレッション数は、配信数と同じでない場合は同じである必要があります。 これにより、デバイスはメッセージを確実に受信し、その情報をサーバーにリレーします。

* **ローカルクリック** - ローカル通知がデバイスに配信され、ユーザーが通知をクリックした場合。 ユーザーは、通知を表示するか（次にローカルの開いたトラッキングに移動します）、通知を閉じるかを選択しました。

* **ローカルオープン** - ローカル通知がデバイスに配信され、ユーザーが通知をクリックすると、アプリケーションが開きます。 これはローカルクリックに似ていますが、通知が却下された場合、ローカルオープンはトリガーされません。

Adobe Campaign Standardのトラッキングを実装するには、モバイルアプリケーションにMobile SDKを含める必要があります。 これらのSDKは[!DNL Adobe Mobile Services]で利用できます。

トラッキング情報を送信するには、3つの変数を送信する必要があります。2つはAdobe Campaignから受信したデータの一部であり、もう1つはインプレッション、クリック、オープンのどちらであるかを示すアクション変数です。

| 変数 | 値 |
| :-: | :-: |
| deliveryId | 受信データからの`deliveryId` （`_dld`が使用されるプッシュトラッキングと同様） |
| broadlogId | 受信データからの`broadlogId` （`_mld`が使用されるプッシュトラッキングと同様） |
| アクション | 開く場合は「1」、クリックの場合は「2」、インプレッションの場合は「7」 |

## ローカルインプレッション追跡の実装 {#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDKでは、AndroidとiOSの両方にインプレッションイベントが自動的に送信されます。

## クリックトラッキングの実装 {#implementing-click-tracking}

クリック トラッキングの場合、`collectMessageInfo()`または`trackAction()`関数を呼び出す際に、アクションの値「2」を送信する必要があります。

### Android の場合 {#implement-click-tracking-android}

クリック数を追跡するには、次の2つのシナリオを実装する必要があります。

* ユーザーは通知を見たがクリアします。

  却下シナリオの場合にクリックを追跡するには、アプリケーションモジュールのAndroidManifest ファイルにブロードキャスト受信機`NotificationDismissalHandler`を追加します。

  ```
  <receiver
  android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
  </receiver>
  ```

* ユーザーは通知を見てクリックすると、開いたトラッキングに変わります。

  このシナリオでは、クリックとオープンが生成されます。 このクリックのトラッキングは、オープンをトラッキングするために必要な実装の一部になります。 「[&#x200B; オープントラッキングの実装](#implement-open-tracking)」を参照してください。

### IOSの場合 {#implement-click-tracking-ios}

クリック追跡情報を送信するには、次を追加する必要があります。

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## オープントラッキングの実装 {#implement-open-tracking}

ユーザーが通知をクリックしてアプリケーションを開く必要があるため、「1」と「2」を送信する必要があります。 アプリケーションがローカル通知を通じて起動または開かれていない場合、トラッキングイベントは発生しません。

### Android の場合 {#implement-open-tracking-android}

「オープン」を追跡するには、「インテント」を作成する必要があります。 インテントオブジェクトを使用すると、特定のアクションが実行されたときにAndroid OSがメソッドを呼び出すことができます。この場合は、通知をクリックしてアプリを開きます。

このコードは、クリックインプレッション追跡の実装に基づいています。 インテントを設定したら、トラッキング情報をAdobe Campaignに送り返す必要があります。 この場合、通知をトリガーしたAndroid ビュー（[!DNL Activity]）は、ユーザーによるクリックの結果として開かれるか、前景に表示されます。 [!DNL Activity]のインテント オブジェクトには、開いている状態を追跡するために使用できる通知データが含まれています。

MainActivity.java （拡張[!DNL Activity]）

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
 
 
private void handleTracking() {

    //Check to see if this view was opened based on a notification

    Intent intent = getIntent();
    Bundle data = intent.getExtras();
 
    if (data != null) {

        //Opened based on the notification, you must get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### IOSの場合 {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
