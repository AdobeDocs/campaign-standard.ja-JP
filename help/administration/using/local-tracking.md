---
title: プッシュトラッキングの実装
description: このドキュメントを使用すると、プッシュ通知の追跡が iOS および Android で正しく実装されていることを確認できます。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 2%

---

# ローカルトラッキングの実装 {#local-tracking}

## ローカルトラッキングについて {#about-local-tracking}

このページでは、ローカル通知トラッキングが正しく実装されていることを確認する方法について説明します。 これは、ローカル通知が既に設定されていることを意味します。

ローカル通知のトラッキングは、次の 3 つのタイプに分けることができます。

* **ローカルインプレッション**  — デバイスにローカル通知が配信され、通知センターに座っているが、まったく触れられていない場合。ほとんどの場合、インプレッション数は、配信された数と異なる場合は、類似した数にする必要があります。 これにより、デバイスがメッセージを取得し、その情報をサーバーにリレーします。

* **ローカルクリック**  — デバイスにローカル通知が配信され、ユーザーが通知をクリックした場合。ユーザーは、通知を表示する（通知がローカルのオープントラッキングに移動する）か、通知を閉じたいと考えていました。

* **ローカル開封**  — デバイスにローカル通知が配信され、ユーザーが通知をクリックしてアプリケーションが開いたとき。これは、ローカルクリックと似ていますが、通知が閉じられた場合にローカル開封がトリガーされない点が異なります。

Adobe Campaign Standardのトラッキングを実装するには、モバイルアプリケーションに Mobile SDK を含める必要があります。 これらの SDK は [!DNL Adobe Mobile Services] で入手できます。

トラッキング情報を送信するには、次の 3 つの変数を送信する必要があります。2 つはAdobe Campaignから受信したデータの一部で、もう 1 つはインプレッション、クリックまたは開封のどちらであるかを示すアクション変数です。

| 変数 | 値 |
| :-: | :-: |
| deliveryId | `deliveryId` 受信データから ( を使用するプッシュトラッキン `_dld` グと同様 ) |
| broadlogId | `broadlogId` 受信データから ( を使用するプッシュトラッキン `_mld` グと同様 ) |
| action | オープンの場合は「1」、クリックの場合は「2」、インプレッションの場合は「7」 |

## ローカルインプレッション追跡の実装 {#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDK は、追加の設定なしで、Android と iOS の両方にインプレッションイベントを自動的に送信します。

## クリック追跡の実装 {#implementing-click-tracking}

クリック追跡の場合、`collectMessageInfo()` 関数または `trackAction()` 関数を呼び出す際のアクションに対して値「2」を送信する必要があります。

### Android の場合 {#implement-click-tracking-android}

クリックを追跡するには、次の 2 つのシナリオを実装する必要があります。

* ユーザーは通知を表示しますが、通知をクリアします。

   却下シナリオの場合にクリックを追跡するには、ブロードキャストレシーバー `NotificationDismissalHandler` をアプリケーションモジュールの AndroidManifest ファイルに追加します。

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* ユーザーが通知を表示し、その通知をクリックすると、オープントラッキングになります。

   このシナリオでは、クリックと開封が発生します。 このクリックを追跡することは、開封を追跡するために必要な実装の一部です。 [ オープントラッキングの実装 ](#implement-open-tracking) を参照してください。

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

## 開封数の追跡の実装 {#implement-open-tracking}

ユーザーは通知をクリックしてアプリケーションを開く必要があるので、「1」と「2」を送信する必要があります。 アプリケーションがローカル通知で起動または開かれていない場合、トラッキングイベントは発生しません。

### Android の場合 {#implement-open-tracking-android}

開封を追跡するには、インテントを作成する必要があります。 インテントオブジェクトを使用すると、特定のアクションが実行された場合（この場合、通知をクリックしてアプリを開く）に、Android OS がメソッドを呼び出すことができます。

このコードは、クリックインプレッショントラッキングの実装に基づいています。 インテントが設定された状態で、トラッキング情報をAdobe Campaignに送信する必要があります。 この場合、ユーザーがクリックした結果、通知をトリガーした Android View([!DNL Activity]) が開くか、フォアグラウンドに移動します。 [!DNL Activity] の intent オブジェクトには、開封の追跡に使用できる通知データが含まれています。

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
