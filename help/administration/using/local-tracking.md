---
title: ローカルトラッキングの実装
description: iOSおよび Android でプッシュ通知トラッキングが正しく実装されていることを確認する方法について説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 2%

---

# ローカルトラッキングの実装 {#local-tracking}

## ローカルトラッキングについて {#about-local-tracking}

このページでは、ローカル通知トラッキングが正しく実装されていることを確認する方法について説明します。 これは、ローカル通知が既に設定されていることを意味します。

ローカル通知トラッキングは、次の 3 つのタイプに分割できます。

* **ローカルインプレッション**  — ローカル通知がデバイスに配信され、通知センターに座っているが、まったくタッチされていない場合。 ほとんどの場合、インプレッション数は、配信された数と異なる場合は、類似した数になる必要があります。 これにより、デバイスがメッセージを受け取り、その情報をサーバーに返します。

* **ローカルクリック**  — デバイスにローカル通知が配信され、ユーザーが通知をクリックした場合。 ユーザーは、通知を表示したか（通知がローカルのオープントラッキングに移動します）、または通知を閉じたかのどちらかです。

* **ローカルで開く**  — デバイスにローカル通知が配信され、ユーザーが通知をクリックしてアプリケーションが開いたとき。 これは、ローカルクリックと似ていますが、通知が閉じられた場合にローカル開封がトリガーされない点が異なります。

Adobe Campaign Standardのトラッキングを実装するには、モバイルアプリケーションに Mobile SDK をアプリケーションに含める必要があります。 これらの SDK は、 [!DNL Adobe Mobile Services].

トラッキング情報を送信するには、次の 3 つの変数を送信する必要があります。2 つはAdobe Campaignから受け取ったデータの一部で、もう 1 つはインプレッション、クリックまたは開封のどちらであるかを示すアクション変数です。

| 変数 | 値 |
| :-: | :-: |
| deliveryId | `deliveryId` 受信データから（プッシュ追跡と同様） `_dld` が使用されている場合 ) |
| broadlogId | `broadlogId` 受信データから（プッシュ追跡と同様） `_mld` が使用されている場合 ) |
| アクション | 「1」が開封、「2」がクリック、「7」がインプレッション |

## ローカルインプレッショントラッキングの実装 {#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDK は、追加の設定なしで、Android とiOSの両方のインプレッションイベントを自動的に送信します。

## クリック追跡の実装 {#implementing-click-tracking}

クリックの追跡の場合、を呼び出す際にアクションの値「2」を送信する必要があります `collectMessageInfo()` または `trackAction()` 関数

### Android の場合 {#implement-click-tracking-android}

クリックを追跡するには、次の 2 つのシナリオを実装する必要があります。

* ユーザーは通知を表示しますが、通知をクリアします。

   却下シナリオの場合にクリックを追跡するには、ブロードキャストレシーバーを追加します `NotificationDismissalHandler` を設定します。

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* ユーザーが通知を表示し、それをクリックすると、オープントラッキングになります。

   このシナリオでは、クリックとオープンが発生します。 このクリックを追跡することは、開封を追跡するために必要な実装の一部です。 詳しくは、 [オープントラッキングの実装](#implement-open-tracking).

### iOS の場合 {#implement-click-tracking-ios}

クリックの追跡情報を送信するには、以下を追加する必要があります。

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

## 開封トラッキングの実装 {#implement-open-tracking}

ユーザーは通知をクリックしてアプリケーションを開く必要があるので、「1」と「2」を送信する必要があります。 アプリケーションがローカル通知で起動または開かれていない場合、トラッキングイベントは発生しません。

### Android の場合 {#implement-open-tracking-android}

開封を追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、特定のアクションが実行された場合（この場合は通知をクリックしてアプリを開く）に、Android OS がメソッドを呼び出すことができます。

このコードは、クリックインプレッショントラッキングの実装に基づいています。 インテントセットが設定されたら、トラッキング情報をAdobe Campaignに送信する必要があります。 この場合、Android View([!DNL Activity]) をクリックした結果、通知が開くか、フォアグラウンドに移動します。 の intent オブジェクト [!DNL Activity] には、開封を追跡するために使用できる通知データが含まれます。

MainActivity.java (extends [!DNL Activity])

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
