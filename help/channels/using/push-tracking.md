---
title: プッシュ追跡の実装
description: このドキュメントを使用すると、プッシュ通知追跡がiOSおよびAndroidに正しく実装されていることを確認できます。
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# プッシュ追跡の実装 {#push-tracking}

## プッシュ追跡について {#about-push-tracking}

プッシュ通知が完全に開発されていることを確認するには、トラッキング部分が正しく実装されていることを確認する必要があります。

次の手順では、プッシュ追跡が正しく実装されていることを確認できます。 ここでは、プッシュ通知の最初の部分が既に実装済みであることを前提としています。アプリユーザーの登録とプッシュ通知メッセージの処理を行います。

プッシュ追跡は、次の3つのタイプに分かれています。

* **プッシュインプレッション** — プッシュ通知がデバイスに配信され、通知センターに配信されているが、まったく操作されていない場合。  これは印象と見なされます。  ほとんどの場合、インプレッション数は、配信された数と同じでない場合は類似した数値にする必要があります。 これにより、デバイスはメッセージを取得し、その情報を確実にサーバーに転送しました。

* **プッシュクリック** — プッシュ通知がデバイスに配信され、ユーザーがデバイスをクリックしたとき。  ユーザーが通知を表示する（その後、プッシュオープン追跡に移動する）か、通知を閉じるかを選択した。

* **プッシュ開く** — プッシュ通知がデバイスに配信され、ユーザーが通知をクリックしてアプリが開いたとき。  これはプッシュクリックに似ていますが、通知が閉じられた場合に「プッシュで開く」がトリガーされない点が異なります。

モバイルアプリにCampaign Standardの追跡を実装するには、モバイルSDKを含める必要があります。 これらのSDKは、Adobe Mobile Servicesで使用できます。

トラッキング情報を送信するには、3つの変数を送信する必要があります。 Campaign Standardから受け取ったデータの一部である2つの変数と、それが **Impression**、 **Click** 、または **Openのいずれであるかを示すアクション変数**。

| 変数 | 値 |
|:-:|:-:|
| broadlogId | データのID(_M) |
| deliveryId | データからの_dId |
| action | [開く]に1、[クリック]に2、[インプレッション]に7 |

## Androidの実装 {#implementation-android}

### プッシュインプレッショントラッキングの実装方法 {#push-impression-tracking-android}

インプレッション追跡の場合、trackAction()関数を呼び出す際に、アクションの値&quot;7&quot;を送信する必要があります。

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### クリック追跡の実装方法 {#push-click-tracking-android}

クリック追跡の場合、trackAction()関数を呼び出す際に、アクションの値&quot;2&quot;を送信する必要があります。

クリックを追跡するには、次の2つのシナリオを処理する必要があります。

* ユーザーは通知を表示しますが、クリアします。
* ユーザーは通知を表示し、クリックして開いた追跡に変換します。

これを処理するには、次の2つのインテントを使用する必要があります。1つは通知をクリックするためのもので、もう1つは通知を閉じるためのものです。

MyFirebaseMessagingService.java

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

BroadcastReceiverを動作させるには、AndroidManifest.xmlに登録する必要があります

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### オープントラッキングの導入方法 {#push-open-tracking-android}

アプリを開くにはユーザーが通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 プッシュ通知を通じてアプリが起動または開かれない場合、追跡イベントは発生しません。

開いている状態を追跡するには、「インテント」を作成する必要があります。 インテントオブジェクトを使用すると、特定の操作が行われたときにAndroid OSがメソッドを呼び出すことができます。 この場合、通知をクリックしてアプリを開きます。

このコードは、クリックインプレッショントラッキングの実装に基づいています。 インテントを設定した場合、追跡情報をキャンペーンに戻す必要があります。 この場合、アプリ内の特定の表示を開くように「開く」インテントを設定する必要があります。これにより、インテントオブジェクトの通知データを使用してonResumeメソッドが呼び出されます。

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
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## iOSの実装 {#implementation-iOS}

### プッシュインプレッショントラッキングの実装方法 {#push-impression-tracking-iOS}

インプレッション追跡の場合、trackAction()関数を呼び出す際に、アクションの値&quot;7&quot;を送信する必要があります。

iOS通知の動作を理解するには、アプリの3つの状態を詳しく説明する必要があります。

* **前景**:アプリが現在アクティブで、現在画面（前景）にある場合。
* **背景**:isアプリが画面に表示されず、プロセスが閉じられない場合。 ホームボタンを重複でクリックすると、通常、バックグラウンドにあるすべてのアプリが表示されます。
* **オフ/クローズ**:プロセスが停止されたアプリ。

アプリが閉じられた場合、アプリが再起動されるまで、Appleはアプリを呼び出しません。 つまり、iOSで通知がいつ受信されたかを知ることはできません。

アプリがバックグラウンドにある間もImpressionの追跡を引き続き機能させるには、 **Content-Available** （利用可能なコンテンツ）を送信して、追跡が必要なことをアプリに通知する必要があります。

>[!CAUTION]
>
>iOSインプレッションの追跡は正確ではなく、信頼性が高いとは見なされません。

次のコードターゲット背景アプリ：

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

次のコードターゲット前景アプリ：

```
// This will get called when the app is in the foreground
  
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
  
  
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### クリック追跡の実装方法 {#push-click-tracking-iOS}

クリック追跡の場合、trackAction()関数を呼び出す際に、アクションの値&quot;2&quot;を送信する必要があります。

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

プッシュ通知を送信する際に、通知を追加する必要があります。カテゴリ この場合、「DEFAULT」と呼びます。

![](assets/tracking_push.png)

次に、「却下」を処理し、追跡情報を送信するには、以下を追加する必要があります。

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### オープントラッキングの導入方法 {#push-open-tracking-iOS}

アプリを開くにはユーザーが通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 プッシュ通知を通じてアプリが起動または開かれない場合、追跡イベントは発生しません。

```
import Foundation
import UserNotifications
import UserNotificationsUI
  
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
  
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
