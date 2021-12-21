---
title: プッシュトラッキングの実装
description: このドキュメントでは、iOSおよび Android で、プッシュ通知トラッキングが正しく実装されていることを確認できます。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: 95d4b9fbb41f5204f387971be3710817a281a8c4
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 1%

---

# プッシュトラッキングの実装 {#push-tracking}

## プッシュトラッキングについて {#about-push-tracking}

プッシュ通知の開発が完全に完了していることを確認するには、すべてのプッシュ通知でトラッキングが有効になっていないので、トラッキング部分が正しく実装されていることを確認する必要があります。 これを有効にするには、開発者がトラッキングが有効になっている配信を特定する必要があります。Adobe Campaign Standardは、 `_acsDeliveryTracking` 2 つの値 **オン** または **オフ**. アプリ開発者は、変数が **オン**.

>[!IMPORTANT]
>
>この変数は、21.1 リリースより前に設定された配信や、カスタムテンプレートを使用した配信では使用できません。

プッシュトラッキングは、次の 3 つのタイプに分かれています。

* **プッシュインプレッション**  — プッシュ通知がデバイスに配信され、通知センターに座っているが、まったくタッチされていない場合。  これは印象と見なされます。  ほとんどの場合、インプレッション数は、配信された数と異なる場合は、類似した数になります。 これにより、デバイスがメッセージを取得し、その情報がサーバーにリレーされたことが確認されます。

* **プッシュクリック**  — デバイスにプッシュ通知が配信され、ユーザーがデバイスをクリックした場合。  ユーザーは、通知を表示したか（通知がプッシュ開封トラッキングに移行します）、通知を閉じたかのどちらかです。

* **プッシュして開く**  — デバイスにプッシュ通知が配信され、ユーザーが通知をクリックしたときに、アプリが開いたとき。  これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。

Campaign Standardのトラッキングを実装するには、モバイルアプリに Mobile SDK を含める必要があります。 これらの SDK は、Mobile ServicesAdobeで使用できます。 詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md)を参照してください。

トラッキング情報を送信するには、3 つの変数を送信する必要があります。 Campaign Standardから受け取ったデータの一部である 2 つと、それが **インプレッション**, **クリック** または **開く**.

| 変数 | 値 |
|:-:|:-:|
| broadlogId | データからの_mId |
| deliveryId | データからの_dId |
| アクション | 1 は「開く」、2 は「クリック」、7 は「インプレッション」です。 |

## Android の実装 {#implementation-android}

### プッシュインプレッショントラッキングの実装方法 {#push-impression-tracking-android}

インプレッショントラッキングの場合、 **[!UICONTROL trackAction()]** 関数に置き換えます。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、 [セクション](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### クリック追跡の実装方法 {#push-click-tracking-android}

クリックの追跡の場合、 **[!UICONTROL trackAction()]** 関数に置き換えます。

クリックを追跡するには、次の 2 つのシナリオを処理する必要があります。

* ユーザーは通知を表示しますが、通知をクリアします。
* ユーザーが通知を表示し、クリックすると、通知がオープントラッキングに変わります。

これを処理するには、次の 2 つの目的を使用する必要があります。1 つは通知をクリックするためのもので、もう 1 つは通知を閉じるためのものです。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、 [セクション](../../administration/using/push-tracking.md#about-push-tracking).

**[!UICONTROL MyFirebaseMessagingService.java]**

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

を **[!UICONTROL BroadcastReceiver]** 働くには、それをに登録する必要があります **[!UICONTROL AndroidManifest.xml]**

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
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### オープントラッキングの実装方法 {#push-open-tracking-android}

ユーザーがアプリを開くには通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 プッシュ通知を通じてアプリが起動または開かれていない場合、トラッキングイベントは発生しません。

開いた状態を追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、特定のアクションが実行されたときに Android OS がメソッドを呼び出すことができます。 この場合、通知をクリックしてアプリを開きます。

このコードは、クリックインプレッショントラッキングの実装に基づいています。 を使用 **[!UICONTROL Intent]** 設定したら、トラッキング情報をAdobe Campaign Standardに送り返す必要があります。 この場合、 **[!UICONTROL Open Intent]** アプリケーションの特定のビューに開くには、通知データを **[!UICONTROL Intent Object]**.

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、 [セクション](../../administration/using/push-tracking.md#about-push-tracking).

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
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
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

インプレッショントラッキングの場合、 **[!UICONTROL trackAction()]** 関数に置き換えます。

iOS通知の仕組みを理解するには、アプリの次の 3 つの状態について詳しく説明する必要があります。

* **前景**:：アプリが現在アクティブで、現在（フォアグラウンドで）画面に表示されているとき。
* **背景**:is アプリが画面に表示されていないが、プロセスが閉じられていない場合。 ホームボタンをダブルクリックすると、通常はバックグラウンドにあるすべてのアプリを表示します。
* **オフ/クローズ**:プロセスが強制終了されたアプリ。

まだ **[!UICONTROL Impression]** アプリがバックグラウンドになっている間のトラッキングで、 **[!UICONTROL Content-Available]** 追跡を実行する必要があることをアプリに知らせるために。

>[!CAUTION]
>
> アプリが閉じられた場合、Appleは、アプリが再起動されるまでアプリを呼び出しません。 つまり、iOSでいつ通知を受け取ったかを知ることはできません。 </br> この理由により、iOSのインプレッショントラッキングは、正確ではない可能性があり、信頼できるものとは見なされません。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、 [セクション](../../administration/using/push-tracking.md#about-push-tracking).

次のコードは、バックグラウンドアプリを対象としています。

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

次のコードは、フォアグラウンドアプリをターゲットにします。

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### クリック追跡の実装方法 {#push-click-tracking-iOS}

クリックの追跡の場合、 **[!UICONTROL trackAction()]** 関数に置き換えます。
21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、 [セクション](../../administration/using/push-tracking.md#about-push-tracking).

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

プッシュ通知を送信する際に、カテゴリを追加する必要があります。 この場合、「DEFAULT」と呼びます。

![](assets/tracking_push.png)

次に、 **[!UICONTROL Dismiss]** 次の情報を追加して、トラッキング情報を送信します。

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### オープントラッキングの実装方法 {#push-open-tracking-iOS}

ユーザーがアプリを開くには通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 プッシュ通知を通じてアプリが起動または開かれていない場合、トラッキングイベントは発生しません。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、 [セクション](../../administration/using/push-tracking.md#about-push-tracking).

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
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
