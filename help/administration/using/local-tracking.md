---
solution: Campaign Standard
product: campaign
title: プッシュトラッキングの実装
description: このドキュメントを使用すると、プッシュ通知追跡がiOSとAndroidで正しく実装されていることを確認できます。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---


# ローカルトラッキングの導入{#local-tracking}

## ローカルトラッキングについて{#about-local-tracking}

このページでは、ローカル通知追跡が正しく実装されていることを確認する方法を説明します。 これは、ローカル通知が既に設定されていることを意味します。

ローカル通知追跡は、次の3つのタイプに分割できます。

* **ローカルインプレッション**  — ローカル通知がデバイスに配信され、通知センターに座っているが、何も操作されていない場合。ほとんどの場合、インプレッション数は、配信された数と異なる場合は同じにする必要があります。 これにより、デバイスはメッセージを受け取り、その情報をサーバーにリレーします。

* **ローカルクリック**  — ローカル通知がデバイスに配信され、ユーザーが通知をクリックしたとき。ユーザーは、通知の表示（ローカルで開いている追跡に移動）または通知の却下を希望していた。

* **Local open**  — ローカル通知がデバイスに配信され、ユーザーが通知をクリックした場合にアプリケーションが開きます。これはローカルクリックと似ていますが、通知が閉じられた場合にローカルで開く操作はトリガーされません。

Adobe Campaign Standardのトラッキングを導入するには、モバイルアプリケーションにMobile SDKを含める必要があります。 これらのSDKは[!DNL Adobe Mobile Services]で入手できます。

トラッキング情報を送信するには、3つの変数を送信する必要があります。2つはAdobe Campaignから受け取ったデータの一部で、もう1つはインプレッション、クリック、または開くかどうかを指示するアクション変数です。

| 変数 | 値 |
| :-: | :-: |
| deliveryId | `deliveryId` 受信データから（が使用されるプッシュ追跡と同様） `_dld`  |
| broadlogId | `broadlogId` 受信データから（が使用されるプッシュ追跡と同様） `_mld`  |
| action | 「開く」は「1」、「クリック」は「2」、「インプレッション」は「7」 |

## ローカルインプレッショントラッキングの実装{#implement-local-impression-tracking}

Adobe Experience PlatformモバイルSDKは、AndroidとiOSの両方に対して、追加の設定なしにインプレッションイベントを自動的に送信します。

## クリック追跡{#implementing-click-tracking}を実装

クリック追跡の場合、`collectMessageInfo()`または`trackAction()`関数を呼び出す際に、アクションの値&quot;2&quot;を送信する必要があります。

### Android の場合 {#implement-click-tracking-android}

クリックを追跡するには、次の2つのシナリオを処理する必要があります。

* ユーザーは通知を表示しますが、クリアします。

   却下シナリオの場合にクリックを追跡するには、ブロードキャスト受信者`NotificationDismissalHandler`をアプリケーションモジュールのAndroidManifestファイルに追加します。

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* ユーザーは通知を表示し、その通知をクリックすると、開いている追跡に変わります。

   このシナリオでは、クリックとオープンが発生します。 このクリックを追跡することは、開いているものを追跡するために必要な実装の一部です。 [オープントラッキングの導入](#implement-open-tracking)を参照してください。

### iOS の場合 {#implement-click-tracking-ios}

クリック追跡情報を送信するには、以下を追加する必要があります。

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

## オープントラッキング{#implement-open-tracking}を実装

ユーザーがアプリケーションを開くには通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 ローカル通知を通じてアプリケーションが起動または開かれない場合、追跡イベントは発生しません。

### Android の場合 {#implement-open-tracking-android}

オープンを追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、特定のアクションが実行された場合に、Android OSがメソッドを呼び出すことができます。この場合、通知をクリックしてアプリを開きます。

このコードは、クリックインプレッショントラッキングの導入に基づいています。 インテントを設定した場合は、トラッキング情報をAdobe Campaignに送り返す必要があります。 この場合、ユーザーがクリックした結果、通知をトリガーしたAndroid表示([!DNL Activity])が開かれるか、フォアグラウンドになります。 [!DNL Activity]のintentオブジェクトには、開いているかどうかを追跡するために使用できる通知データが含まれています。

MainActivity.java（拡張子[!DNL Activity]）

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

        //Opened based on the notification, you need to get the tracking that was passed on.

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

### iOS の場合 {#implement-open-tracking-ios}

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
