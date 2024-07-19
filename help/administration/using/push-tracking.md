---
title: プッシュトラッキングの実装
description: iOSとAndroidにプッシュ通知トラッキングが正しく実装されていることを確認する方法を説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: 1346f7d833515fb2e6feabb39d199ffd5610c88e
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 0%

---

# プッシュトラッキングの実装 {#push-tracking}

## プッシュトラッキングについて {#about-push-tracking}

プッシュ通知が完全に開発されたことを確認するには、すべてのプッシュ通知でトラッキングが有効になっているわけではないので、トラッキング部分が正しく実装されていることを確認する必要があります。 これを有効にするには、デベロッパーはどの配信でトラッキングが有効になっているかを特定する必要があります。Adobe Campaign Standardは `_acsDeliveryTracking` というフラグを 2 つの値 **オン** または **オフ** で送信します。 アプリ開発者は、変数が **on** に設定されている配信に対してのみトラッキングリクエストを送信する必要があります。

>[!IMPORTANT]
>
>この変数は、21.1 リリースより前のリリースで設定された配信や、カスタムテンプレートを使用した配信には使用できません。

プッシュトラッキングは次の 3 つのタイプに分かれています。

* **プッシュインプレッション** - プッシュ通知がデバイスに正常に配信され、ユーザーの操作なしに通知センターに存在する場合。

* **プッシュクリック** - プッシュ通知がデバイスに配信され、ユーザーがデバイスをクリックしたとき。  ユーザーは、通知を表示するか（プッシュオープントラッキングに移動します）、通知を閉じようとしました。

* **プッシュオープン** - プッシュ通知がデバイスに配信され、ユーザーが通知をクリックしてアプリを開いたとき。 これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。

Campaign Standard用のトラッキングを実装するには、モバイルアプリにAdobe Experience Platform SDK を含める必要があります。 これらの SDK は、[Adobe Experience Platform SDK ドキュメント ](https://github.com/Adobe-Marketing-Cloud/acp-sdks) で入手できます。

トラッキング情報を送信するには、3 つの変数を送信する必要があります。 Campaign Standardから受信したデータの一部を構成する 2 つのフィールドと、そのフィールドが **インプレッション**、**クリック**、**開く** のいずれであるかを示すアクション変数。

| 変数 | 値 |
|:-:|:-:|
| broadlogId | データからの mId （_m） |
| deliveryId | データから dId を取得（_d） |
| アクション | 「1」（オープン）、「2」（クリック）および「7」（インプレッション） |

## Androidの実装 {#implementation-android}

### プッシュインプレッショントラッキングの実装方法 {#push-impression-tracking-android}

インプレッショントラッキングの場合、`collectMessageInfo()` 関数または `trackAction()` 関数を呼び出す際に、アクションの値「7」を送信する必要があります。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信の場合は、この [ 節 ](../../administration/using/push-tracking.md#about-push-tracking) を参照してください。

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
    if( deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
      contextData.put("deliveryId", deliveryId);
      contextData.put("broadlogId", messageId);
      contextData.put("action", "7");

    //If you are using ACPCore v1.4.0 or later, use the next line.
      
      MobileCore.collectMessageInfo(contextData);
      
    //Else comment out the above line and uncomment the line below
        
    //MobileCore.trackAction("tracking", contextData) ;
    }
  }
}
```

### クリックの追跡の実装方法 {#push-click-tracking-android}

クリックの追跡の場合、`collectMessageInfo()` 関数または `trackAction()` 関数を呼び出す際に、アクションの値「2」を送信する必要があります。
クリックを追跡するには、次の 2 つのシナリオを処理する必要があります。

* ユーザーには通知が表示されますが、クリアされます。
* ユーザーは通知を表示し、クリックすると、開封されたトラッキングに変わります。

これを処理するには、2 つのインテントを使用する必要があります。1 つは通知をクリックするためのインテント、もう 1 つは通知を閉じるためのインテントです。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信の場合は、この [ 節 ](../../administration/using/push-tracking.md#about-push-tracking) を参照してください。

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

**[!UICONTROL BroadcastReceiver]** を機能させるには、**[!UICONTROL AndroidManifest.xml]** に登録する必要があります

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
            
        //If you are using ACPCore v1.4.0 or later, use the next line.
        
            MobileCore.collectMessageInfo(contextData);
            
        //Else comment out the above line and uncomment the line below
        
            //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### オープントラッキングの実装方法 {#push-open-tracking-android}

ユーザーがアプリを開くにはクリック通知が必要なので、「1」と「2」を送信する必要があります。 アプリがプッシュ通知を通じて起動/開封されない場合、トラッキングイベントは発生しません。

オープンを追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、Android OS は特定のアクションが実行されたときにメソッドを呼び出すことができます。 この場合、通知をクリックしてアプリを開きます。

このコードは、クリックインプレッションのトラッキングの実装に基づいています。 **[!UICONTROL Intent]** を設定したら、トラッキング情報をAdobe Campaign Standardに送り返す必要があります。 この場合、アプリの特定のビューを開くように **[!UICONTROL Open Intent]** を設定する必要があります。これにより、**[!UICONTROL Intent Object]** の通知データを使用して onResume メソッドが呼び出されます。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信の場合は、この [ 節 ](../../administration/using/push-tracking.md#about-push-tracking) を参照してください。

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
            contextData.put("action", "2");
            
            //Send Click Tracking since the user did click on the notification
              
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                  
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
 
                //Send Open Tracking since the user opened the app
            
                contextData.put("action", "1");
                
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## iOSの実装 {#implementation-iOS}

### プッシュインプレッショントラッキングの実装方法 {#push-impression-tracking-iOS}

インプレッショントラッキングの場合、`collectMessageInfo()` 関数または `trackAction()` 関数を呼び出す際に、アクションの値「7」を送信する必要があります。

iOSの通知の仕組みを理解するには、アプリの 3 つの状態を詳しく説明する必要があります。

* **フォアグラウンド**：アプリが現在アクティブで、現在スクリーン上にある（フォアグラウンドにある）場合。
* **背景**:is アプリが画面に表示されていないが、プロセスが閉じられていない場合。 ホームボタンをダブルクリックすると、通常、バックグラウンドにあるすべてのアプリが表示されます。
* **オフ/クローズ**：プロセスが強制終了されたアプリ。

アプリがバックグラウンド **[!UICONTROL Impression]** ある間もトラッキングが機能するためには、トラッキングが必要であることをアプリに知らせる **[!UICONTROL Content-Available]** ールを送信する必要があります。

>[!CAUTION]
>
> アプリが閉じられた場合、Appleはアプリが再起動されるまでアプリを呼び出しません。 つまり、iOSで通知を受信した日時を知ることはできません。 </br> この理由から、iOSのインプレッショントラッキングは正確でない可能性があり、信頼性があると見なされるべきではありません。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信の場合は、この [ 節 ](../../administration/using/push-tracking.md#about-push-tracking) を参照してください。

次のコードは、バックグラウンドアプリをターゲットにします。

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

次のコードはフォアグラウンドアプリをターゲットにします。

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])        
            }
        completionHandler([.alert,.sound])
    }
```

### クリックの追跡の実装方法 {#push-click-tracking-iOS}

クリックの追跡の場合、`collectMessageInfo()` 関数または `trackAction()` 関数を呼び出す際に、アクションの値「2」を送信する必要があります。
21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信の場合は、この [ 節 ](../../administration/using/push-tracking.md#about-push-tracking) を参照してください。

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

これで、プッシュ通知を送信する際に、カテゴリを追加する必要があります。 この例では、「DEFAULT」と呼ぶことにします。

![](assets/tracking_push.png)

**[!UICONTROL Dismiss]** を処理してトラッキング情報を送信するには、次の情報が必要です。

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])   
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### オープントラッキングの実装方法 {#push-open-tracking-iOS}

ユーザーがアプリを開くにはクリック通知が必要なので、「1」と「2」を送信する必要があります。 アプリがプッシュ通知を通じて起動/開封されない場合、トラッキングイベントは発生しません。

21.1 リリースより前に作成された配信またはカスタムテンプレートを使用した配信の場合は、この [ 節 ](../../administration/using/push-tracking.md#about-push-tracking) を参照してください。

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

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
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])                
                
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            }
        }
        completionHandler()
    }
}
```
