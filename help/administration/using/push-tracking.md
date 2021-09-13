---
title: プッシュトラッキングの実装
description: このドキュメントを使用すると、プッシュ通知トラッキングがiOSおよびAndroidで正しく実装されていることを確認できます。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# プッシュトラッキングの実装 {#push-tracking}

## プッシュトラッキングについて {#about-push-tracking}

プッシュ通知が完全に開発されていることを確認するには、すべてのプッシュ通知でトラッキングが有効になっているわけではないので、トラッキング部分が正しく実装されていることを確認する必要があります。 これを有効にするには、開発者がトラッキングが有効になっている配信を特定する必要があります。Adobe Campaign Standardは、**on**&#x200B;または&#x200B;**off**&#x200B;の2つの値で`_acsDeliveryTracking`というフラグを送信します。 アプリ開発者は、**に**&#x200B;と設定された変数を持つ配信でのみ、トラッキングリクエストを送信する必要があります。

>[!IMPORTANT]
>
>この変数は、21.1リリースより前に設定された配信や、カスタムテンプレートを使用した配信には使用できません。

プッシュトラッキングは、次の3つのタイプに分かれています。

* **プッシュインプレッション**  — デバイスにプッシュ通知が配信され、通知センターに座っているが、まったくタッチされていない場合。これは印象と見なされます。  ほとんどの場合、インプレッション数は、配信された数と異なる場合は、類似した数にする必要があります。 これにより、デバイスはメッセージを取得し、その情報をサーバーに中継しました。

* **プッシュクリック**  — デバイスにプッシュ通知が配信され、ユーザーがデバイスをクリックした場合。ユーザーは、通知を表示する（次にプッシュ開封トラッキングに移行する）か、通知を閉じた。

* **プッシュオープン**  — デバイスにプッシュ通知が配信され、ユーザーが通知をクリックしてアプリが開いたとき。これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。

Campaign Standardのトラッキングを実装するには、モバイルアプリにMobile SDKを含める必要があります。 これらのSDKは、Mobile ServicesのAdobeで使用できます。 詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md)を参照してください。

トラッキング情報を送信するには、3つの変数を送信する必要があります。 Campaign Standardから受信したデータの一部である2つと、**インプレッション**、**クリック**&#x200B;または&#x200B;**開く**&#x200B;のいずれかを示すアクション変数の1つです。

| 変数 | 値 |
|:-:|:-:|
| broadlogId | データからの_mId |
| deliveryId | データからの_dId |
| action | 1は開封、2はクリック、7はインプレッション |

## Androidの実装 {#implementation-android}

### プッシュインプレッショントラッキングの実装方法 {#push-impression-tracking-android}

インプレッショントラッキングの場合、**[!UICONTROL trackAction()]**&#x200B;関数を呼び出す際に、アクションの値「7」を送信する必要があります。

21.1リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、この[節](../../administration/using/push-tracking.md#about-push-tracking)を参照してください。

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

クリックの追跡の場合、**[!UICONTROL trackAction()]**&#x200B;関数を呼び出す際に、アクションの値「2」を送信する必要があります。

クリックを追跡するには、次の2つのシナリオを処理する必要があります。

* ユーザーは通知を表示しますが、クリアします。
* ユーザーは通知を表示し、クリックすると、通知がオープントラッキングに変わります。

これを処理するには、次の2つの目的を使用する必要があります。1つは通知をクリックするためのもの、もう1つは通知を閉じるためのものです。

21.1リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、この[節](../../administration/using/push-tracking.md#about-push-tracking)を参照してください。

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

**[!UICONTROL BroadcastReceiver]**&#x200B;を動作させるには、**[!UICONTROL AndroidManifest.xml]**&#x200B;に登録する必要があります。

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

ユーザーがアプリを開くには通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 プッシュ通知を通じてアプリが起動または開封されない場合、トラッキングイベントは発生しません。

開封を追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、特定のアクションが実行されたときにAndroid OSがメソッドを呼び出すことができます。 この場合、通知をクリックしてアプリを開きます。

このコードは、クリックインプレッショントラッキングの実装に基づいています。 **[!UICONTROL Intent]**&#x200B;を設定したら、トラッキング情報をAdobe Campaign Standardに送り返す必要があります。 この場合、**[!UICONTROL Open Intent]**&#x200B;をアプリ内の特定のビューで開くように設定する必要があります。これにより、**[!UICONTROL Intent Object]**&#x200B;の通知データと共にonResumeメソッドが呼び出されます。

21.1リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、この[節](../../administration/using/push-tracking.md#about-push-tracking)を参照してください。

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

## iOS向けの実装 {#implementation-iOS}

### プッシュインプレッショントラッキングの実装方法 {#push-impression-tracking-iOS}

インプレッショントラッキングの場合、**[!UICONTROL trackAction()]**&#x200B;関数を呼び出す際に、アクションの値「7」を送信する必要があります。

iOS通知の仕組みを理解するには、アプリの次の3つの状態を詳細に記述する必要があります。

* **フォアグラウンド**:アプリが現在アクティブで、現在（フォアグラウンドで）画面にある場合。
* **背景**:isアプリが画面に表示されていないが、プロセスが閉じられていない場合。ホームボタンをダブルクリックすると、通常はバックグラウンドにあるすべてのアプリが表示されます。
* **オフ/クローズ**:プロセスが終了したアプリ

アプリが閉じられると、Appleはアプリが再起動されるまでアプリを呼び出しません。 つまり、iOSで通知がいつ受信されたかを知ることはできません。

アプリがバックグラウンドになっている間も&#x200B;**[!UICONTROL Impression]**&#x200B;トラッキングを機能させるには、**[!UICONTROL Content-Available]**&#x200B;を送信して、トラッキングが必要であることをアプリに知らせる必要があります。

>[!CAUTION]
>
>iOSインプレッショントラッキングは正確ではなく、信頼性が高いとは見なされません。

21.1リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、この[節](../../administration/using/push-tracking.md#about-push-tracking)を参照してください。

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

クリックの追跡の場合、**[!UICONTROL trackAction()]**関数を呼び出す際に、アクションの値「2」を送信する必要があります。
21.1リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、この[節](../../administration/using/push-tracking.md#about-push-tracking)を参照してください。

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

次に、プッシュ通知を送信する際に、カテゴリを追加する必要があります。 この場合、「DEFAULT」と呼びます。

![](assets/tracking_push.png)

次に、**[!UICONTROL Dismiss]**&#x200B;を処理してトラッキング情報を送信するには、以下を追加する必要があります。

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

ユーザーがアプリを開くには通知をクリックする必要があるので、「1」と「2」を送信する必要があります。 プッシュ通知を通じてアプリが起動または開封されない場合、トラッキングイベントは発生しません。

21.1リリースより前に作成された配信またはカスタムテンプレートを使用した配信については、この[節](../../administration/using/push-tracking.md#about-push-tracking)を参照してください。

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
