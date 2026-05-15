---
title: Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされているモバイルユースケース
description: モバイルのユースケースをサポートする方法を学ぶ
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
TQID: https://experienceleague.adobe.com/sIwJVutJ9iO9GIKSPquL5LOKVqkj34x3LTaI072C8V4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1006
ht-degree: 1%

---

# Adobe Campaign Standard でサポートされるモバイルのユースケース {#mobile-use-cases}

このページでは、[!DNL Adobe Experience Platform SDKs]を使用して[!DNL Adobe Campaign Standard]でサポートされているすべてのモバイルのユースケースのリストを表示します。 これらのユースケースをサポートするには、[!DNL Adobe Experience Platform SDKs]、[!DNL tags in Adobe Experience Platform]および[!DNL Adobe Campaign Standard]のインストールと設定が必要です。 これについて詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md)を参照してください。

Adobe Campaign Standardでは、次のユースケースをサポートしています。

* [Campaign Standardでのモバイルプロファイルの登録](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Campaign Standardへのプッシュトークンの送信](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [アプリケーションのカスタムデータでモバイルプロファイルを充実させましょう](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [アプリケーションのライフサイクルデータでモバイルプロファイルを充実させる](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [プッシュ通知によるユーザーインタラクションの追跡](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [モバイルアプリにカスタムイベントを実装して、アプリ内メッセージをトリガーする](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [アプリ内メッセージに基づくプロファイルテンプレートの追加認証にリンクフィールドを設定します](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

これらのユースケースを設定するには、次の拡張機能が必要です。

* **[!DNL Adobe Campaign Standard]** <br>Campaign Standard拡張機能をインストールして設定するには、[Data Collection UIでのCampaign Standard拡張機能の設定](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension)を参照してください。
* **[!DNL Mobile Core]**&#x200B;が自動的にインストールされます。 <br> モバイルコア拡張機能について詳しくは、[ モバイルコア ](https://developer.adobe.com/client-sdks/documentation/mobile-core/)を参照してください。
* **[!DNL Profile]**&#x200B;が自動的にインストールされます。 <br> プロファイル拡張機能について詳しくは、[ プロファイル ](https://developer.adobe.com/client-sdks/documentation/profile/)を参照してください。

## Campaign Standardでのモバイルプロファイルの登録 {#register-mobile-profile}

### IOSで実現 {#register-mobile-profile-ios}

IOSでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL Lifecycle Start]**、アプリの開始時およびアプリがフォアグラウンドにあるとき。
* アプリがバックグラウンドで実行されている場合は&#x200B;**[!UICONTROL Lifecycle Pause]**。

詳しくは、[iOSのライフサイクル拡張機能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/)を参照してください。

IOSを使用したユースケースのサンプルを以下に示します。

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Androidで実現 {#register-mobile-profile-android}

Androidでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、[Androidのライフサイクル拡張機能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/)を参照してください。

Androidを使用したこのユースケースのサンプル実装を次に示します。

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Adobe Campaign Standardへのプッシュトークンの送信 {#send-push-token}

### IOSで実現 {#send-push-token-ios}

IOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL setPushIdentifier]** <br>詳細については、[setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/)を参照してください。

IOSを使用したこのユースケースのサンプル実装を次に示します。

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Androidで実現 {#send-push-token-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL setPushIdentifier]** <br>詳細については、[setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/)を参照してください。

Androidを使用したこのユースケースのサンプル実装を次に示します。

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## アプリケーションのカスタムデータでモバイルプロファイルを充実させましょう {#enrich-mobile-profile-custom}

このユースケースを機能させるには、PII ポストバックのルールを作成する必要があります。 詳しくは、[PII Postbacks](../../administration/using/configuring-rules-launch.md#pii-postback)を参照してください。

### IOSで実現 {#enrich-mobile-profile-custom-ios}

IOSでは、次の[!DNL Experience Platform API]が必要です。

* collectPII <br>詳しくは、collectPIIを参照してください。

IOSを使用したユースケースのサンプルを以下に示します。

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### Androidで実現 {#enrich-mobile-profile-custom-android}

Androidでは、次の[!DNL Experience Platform API]が必要です。

* collectPII <br>詳しくは、collectPIIを参照してください。

Androidを使用したこのユースケースのサンプル実装を次に示します。

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## アプリケーションのライフサイクルデータでモバイルプロファイルを充実させる {#enrich-mobile-profile-lifecycle}

このユースケースを機能させるには、PII ポストバックのルールを作成する必要があります。 詳しくは、[PII Postbacks](../../administration/using/configuring-rules-launch.md#pii-postback)を参照してください。

>[!NOTE]
>
>Adobe Campaignでは、モバイルアプリからのカスタムデータとライフサイクルデータは区別されません。 どちらのタイプのデータも、モバイルアプリのイベントに応じてcollectPii ポストバックルールを使用してサーバーに送信できます。

### IOSで実現 {#enrich-mobile-profile-lifecycle-ios}

IOSでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL Lifecycle Start]**、アプリの開始時およびアプリがフォアグラウンドにあるとき。
* アプリがバックグラウンドで実行されている場合は&#x200B;**[!UICONTROL Lifecycle Pause]**。

詳しくは、[iOSのライフサイクル拡張機能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/)を参照してください。

IOSを使用したユースケースのサンプルを以下に示します。

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Androidで実現 {#enrich-mobile-profile-lifecycle-android}

Androidでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、[Androidのライフサイクル拡張機能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/)を参照してください。

Androidを使用したこのユースケースのサンプル実装を次に示します。

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## プッシュ通知によるユーザーインタラクションの追跡 {#track-user-push}

ポストバックを追跡するプッシュ通知のルールを作成する必要があります。 詳細については、[ ポストバックを追跡するプッシュ通知](../../administration/using/configuring-rules-launch.md#push-tracking-postback)を参照してください。

### IOSで実現 {#track-user-push-ios}

IOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**. 詳しくは、[ アプリのアクションを追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)を参照してください。

IOSを使用したユースケースのサンプルを以下に示します。

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Androidで実現 {#track-user-push-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**
詳しくは、[ アプリのアクションを追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)を参照してください。

Androidを使用したこのユースケースのサンプル実装を次に示します。

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## アプリケーションにカスタムイベントを実装して、アプリ内メッセージをトリガーする {#custom-event-inapp}

### IOSで実現 {#custom-event-inapp-ios}

IOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**. 詳しくは、[ アプリのアクションを追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)を参照してください。

IOSを使用したユースケースのサンプルを以下に示します。

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Androidで実現 {#custom-event-inapp-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**
詳しくは、[ アプリのアクションを追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)を参照してください。

Androidを使用したこのユースケースのサンプル実装を次に示します。

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 追加認証のためのリンクフィールドを設定します {#linkage-fields-inapp}

### IOSで実現 {#linkage-fields-inapp-ios}

IOSのアプリ内メッセージに基づくプロファイルテンプレートの追加認証にリンクフィールドを設定するには、次の[!DNL Experience Platform SDK]が必要です。

* リンク フィールドの設定<br>詳細については、[ リンク フィールドの設定](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields)を参照してください。
* リンクフィールドのリセット <br>詳細については、[ リンクフィールドのリセット ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields)を参照してください。

IOSのユースケースのサンプルを以下に示します。

リンクフィールドを設定するには：

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

リンクフィールドをリセットするには：

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Androidで実現 {#linkage-fields-inapp-android}

Androidのアプリ内メッセージに基づくプロファイルテンプレートの追加認証にリンクフィールドを設定するには、次のExperience Platform SDKが必要です。

* リンク フィールドの設定<br>詳細については、[ リンク フィールドの設定](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields)を参照してください。
* リンクフィールドのリセット <br>詳細については、[ リンクフィールドのリセット ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields)を参照してください。

Androidのユースケースのサンプルを以下に示します。

リンクフィールドを設定するには：

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

リンクフィールドをリセットするには：

```
Campaign.resetLinkageFields()
```
