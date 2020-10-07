---
title: プッシュトラッキングの実装
description: このドキュメントを使用すると、プッシュ通知追跡がiOSとAndroidで正しく実装されていることを確認できます。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 2%

---


# ローカルトラッキングの導入 {#local-tracking}

## ローカルトラッキングについて {#about-local-tracking}

このページでは、ローカル通知追跡が正しく実装されていることを確認する方法を説明します。 これは、ローカル通知が既に設定されていることを意味します。

ローカル通知追跡は、次の3つのタイプに分割できます。

* **ローカルインプレッション** — ローカル通知がデバイスに配信され、通知センターに設置されているが、何も操作されていない場合。 ほとんどの場合、インプレッション数は、配信された数と異なる場合は同じにする必要があります。 これにより、デバイスはメッセージを受け取り、その情報をサーバーにリレーします。

* **ローカルクリック** — ローカル通知がデバイスに配信され、ユーザーがデバイスをクリックしたとき。 ユーザーは、通知の表示（ローカルで開いている追跡に移動）または通知の却下を希望していた。

* **Local open** — ローカル通知がデバイスに配信され、ユーザーが通知をクリックした場合にアプリケーションが開きます。 これはローカルクリックと似ていますが、通知が閉じられた場合にローカルで開く操作はトリガーされません。

Adobe Campaign Standardのトラッキングを導入するには、モバイルアプリケーションにMobile SDKを含める必要があります。 これらのSDKは、で使用でき [!DNL Adobe Mobile Services]ます。

トラッキング情報を送信するには、3つの変数を送信する必要があります。2つはAdobe Campaignから受け取ったデータの一部で、もう1つはインプレッション、クリック、または開くかどうかを指示するアクション変数です。

| 変数 | 値 |
| :-: | :-: |
| deliveryId | 受信データからの&quot;deliveryId&quot;（&quot;_dld&quot;を使用するプッシュ追跡と同様） |
| broadlogId | 受信データからの&quot;broadlogId&quot;（&quot;_mld&quot;を使用するプッシュ追跡と同様） |
| action | 「開く」は「1」、「クリック」は「2」、「インプレッション」は「7」 |

## ローカルインプレッション追跡の実装 {#implement-local-impression-tracking}

インプレッション追跡の場合、collectMessageInfo()関数またはtrackAction()関数を呼び出す際に、アクションに値&quot;7&quot;を送信する必要があります。

### Android の場合 {#implement-local-impression-tracking-android}

Adobe Experience PlatformモバイルSDKは、ローカル通知をトリガーする際に、ローカル通知のインプレッショントラッキングを開始します。

### iOS の場合 {#implement-local-impression-tracking-ios}

インプレッション追跡の導入方法を説明するには、アプリケーションの3つの状態を理解する必要があります。

* **前景**:アプリが現在アクティブで、前景の画面に表示されたとき。

* **背景**:アプリが画面に表示されず、プロセスも閉じられない場合。 重複がホームボタンをクリックすると、通常はバックグラウンドのすべてのアプリケーションが表示されます。

* **オフ/閉じる**:アプリケーションのプロセスが終了したとき。 アプリケーションが閉じられた場合、Appleはアプリケーションが再起動されるまでアプリケーションを呼び出しません。 つまり、iOSで通知が受信されたタイミングを実際には把握できないということです。

アプリがバックグラウンドにある間もインプレッションの追跡を引き続き機能させるには、「Content-Available」を送信して、追跡を行う必要があることをアプリに知らせる必要があります。

Adobe Experience PlatformモバイルSDKは、ローカル通知をトリガーする際に、ローカル通知のインプレッショントラッキングを開始します。

>[!CAUTION]
>
>iOSのインプレッショントラッキングは正確ではなく、正確に調べる必要はありません。

## クリック追跡の導入 {#implementing-click-tracking}

クリック追跡の場合、collectMessageInfo()関数またはtrackAction()関数を呼び出す際に、アクションに値&quot;2&quot;を送信する必要があります。

### Android の場合 {#implement-click-tracking-android}

クリックを追跡するには、次の2つのシナリオを処理する必要があります。

* ユーザーは通知を表示しますが、クリアします。

* ユーザーは通知を表示し、その通知をクリックすると、開いている追跡に変わります。

クリックの最初のシナリオは、Adobe Experience PlatformモバイルSDKで追跡されます。

### iOS の場合 {#implement-click-tracking-ios}

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

次に、dismissを処理し、トラッキング情報を送信するには、以下を追加する必要があります。

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

## オープントラッキングの導入 {#implement-open-tracking}

ユーザーがアプリケーションを開くには通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 ローカル通知を通じてアプリケーションが起動または開かれない場合、追跡イベントは発生しません。

### Android の場合 {#implement-open-tracking-android}

オープンを追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、特定のアクションが実行された場合に、Android OSがメソッドを呼び出すことができます。この場合、通知をクリックしてアプリを開きます。

このコードは、クリックインプレッショントラッキングの導入に基づいています。 インテントを設定した場合は、トラッキング情報をAdobe Campaignに送り返す必要があります。 この場合、ユーザーがクリックした結果、通知をトリガーしたAndroid表示([!DNL Activity])が開くか、フォアグラウンドになります。 のintentオブジェクトには、開いているかどうかを追跡するために使用できる通知データが [!DNL Activity] 含まれます。

MainActivity.java(拡張 [!DNL Activity])

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
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
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
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
