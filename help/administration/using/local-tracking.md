---
title: ローカルトラッキングの実装
description: iOSとAndroidにプッシュ通知トラッキングが正しく実装されていることを確認する方法を説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 1%

---

# ローカルトラッキングの実装 {#local-tracking}

## ローカルトラッキングについて {#about-local-tracking}

このページでは、ローカル通知トラッキングが正しく実装されていることを確認する方法を説明します。 これは、ローカル通知が既に設定されていることを意味します。

ローカル通知のトラッキングは、次の 3 つのタイプに分類できます。

* **ローカルインプレッション** - ローカル通知がデバイスに配信され、通知センターに配置されているが、まったくタッチされていない場合。 ほとんどの場合、インプレッション数は、配信された数と同じでない限り、類似している必要があります。 これにより、デバイスがメッセージを確実に取得し、その情報をサーバーに中継します。

* **ローカルクリック** - ローカル通知がデバイスに配信され、ユーザーが通知をクリックした場合。 ユーザーは、通知を表示するか（これにより、ローカルオープントラッキングに移動します）、通知を閉じるか、します。

* **ローカルオープン** - ローカル通知がデバイスに配信され、ユーザーが通知をクリックしてアプリケーションを開いたとき。 これは、ローカルクリックと似ていますが、通知が閉じられた場合にローカルオープンがトリガーされない点が異なります。

Adobe Campaign Standardのトラッキングを実装するには、モバイルアプリケーションで Mobile SDKをアプリケーションに含める必要があります。 これらの SDK は [!DNL Adobe Mobile Services] で入手できます。

トラッキング情報を送信するには、3 つの変数を送信する必要があります。2 つはAdobe Campaignから受信したデータの一部で、もう 1 つはインプレッション、クリック、開くかどうかを指示するアクション変数です。

| 変数 | 値 |
| :-: | :-: |
| deliveryId | 受信データから `deliveryId` 信（`_dld` が使用されるプッシュトラッキングと同様） |
| broadlogId | 受信データから `broadlogId` 信（`_mld` が使用されるプッシュトラッキングと同様） |
| アクション | 「1」（オープン）、「2」（クリック）および「7」（インプレッション） |

## ローカルインプレッショントラッキングの実装 {#implement-local-impression-tracking}

Adobe Experience Platform モバイル SDKは、追加の設定を行わずに、AndroidとiOSの両方に対してインプレッションイベントを自動的に送信します。

## クリックの追跡の実装 {#implementing-click-tracking}

クリックの追跡の場合、`collectMessageInfo()` 関数または `trackAction()` 関数を呼び出す際に、アクションの値「2」を送信する必要があります。

### Android の場合 {#implement-click-tracking-android}

クリックを追跡するには、次の 2 つのシナリオを実装する必要があります。

* ユーザーには通知が表示されますが、クリアされます。

  解雇シナリオが発生した場合にクリックを追跡するには、ブロードキャスト受信者 `NotificationDismissalHandler` をアプリケーションモジュールの AndroidManifest ファイルに追加します。

  ```
  <receiver
  android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
  </receiver>
  ```

* ユーザーが通知を表示してクリックすると、開いたトラッキングに変わります。

  このシナリオでは、クリックとオープンが発生します。 このクリックの追跡は、開始を追跡するために必要な実装の一部になります。 [ オープントラッキングの実装 ](#implement-open-tracking) を参照してください。

### iOS用 {#implement-click-tracking-ios}

クリックの追跡情報を送信するには、次の情報を追加する必要があります。

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

アプリケーションを開くには通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 アプリケーションがローカル通知で起動/開かれていない場合、トラッキングイベントは発生しません。

### Android の場合 {#implement-open-tracking-android}

開封を追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、Android OS は特定のアクション（この場合は、通知をクリックしてアプリを開く）が完了したときにメソッドを呼び出すことができます。

このコードは、クリックインプレッションのトラッキングの実装に基づいています。 インテントが設定された状態で、トラッキング情報をAdobe Campaignに送り返す必要があります。 この場合、ユーザー [!DNL Activity] のクリックの結果、通知をトリガーしたAndroid ビューが開かれるか、フォアグラウンドに移動します。 [!DNL Activity] のインテントオブジェクトには、開封を追跡するために使用できる通知データが含まれています。

MainActivity.java （[!DNL Activity] を拡張）

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

### iOS用 {#implement-open-tracking-ios}

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
