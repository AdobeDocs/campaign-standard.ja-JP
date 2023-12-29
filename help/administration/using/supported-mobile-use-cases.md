---
title: Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされるモバイルの使用例
description: モバイルの使用例をサポートする方法を説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 0%

---

# Adobe Campaign Standard でサポートされるモバイルのユースケース {#mobile-use-cases}

このページでは、 [!DNL Adobe Campaign Standard] の使用 [!DNL Adobe Experience Platform SDKs]. これらの使用例をサポートするには、 [!DNL Adobe Experience Platform SDKs], [!DNL tags in Adobe Experience Platform]、および [!DNL Adobe Campaign Standard]. 詳しくは、 [ページ](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standardは、次の使用例をサポートしています。

* [モバイルプロファイルをCampaign Standardに登録](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Campaign Standardへのプッシュトークンの送信](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [アプリケーションのカスタムデータを使用したモバイルプロファイルのエンリッチメント](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [アプリケーションのライフサイクルデータを使用したモバイルプロファイルのエンリッチメント](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [プッシュ通知を使用したユーザーインタラクションの追跡](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [モバイルアプリにカスタムイベントを実装してアプリ内メッセージをトリガー](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [アプリ内メッセージに基づくプロファイルテンプレートの追加認証用のリンケージフィールドを設定する](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

これらの使用例を設定するには、次の拡張機能が必要です。

* **[!DNL Adobe Campaign Standard]** <br>拡張機能のインストールとCampaign Standardについては、 [データ収集 UI でのCampaign Standard拡張機能の設定](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**：自動的にインストールされます。 <br>Mobile Core 拡張機能について詳しくは、 [Mobile Core](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**：自動的にインストールされます。 <br>Profile 拡張機能について詳しくは、 [プロファイル](https://developer.adobe.com/client-sdks/documentation/profile/).

## モバイルプロファイルをCampaign Standardに登録 {#register-mobile-profile}

### iOSを使用 {#register-mobile-profile-ios}

iOSでは、次の [!DNL Experience Platform APIs] は必須です。

* **[!UICONTROL Lifecycle Start]**、アプリの起動時とアプリがフォアグラウンドになっているとき。
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドになっている場合）

詳しくは、 [iOSのライフサイクル拡張](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

iOSでのこの使用例の実装例を次に示します。

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

### Android の場合 {#register-mobile-profile-android}

Android では、次のようになります。 [!DNL Experience Platform APIs] は必須です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、 [Android のライフサイクル拡張機能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Android でのこの使用例の実装例を次に示します。

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

### iOSを使用 {#send-push-token-ios}

iOSでは、次の [!DNL Experience Platform SDK] は必須です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、 [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

iOSのこの使用例の実装例を次に示します。

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Android の場合 {#send-push-token-android}

Android では、次のようになります。 [!DNL Experience Platform SDK] は必須です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、 [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Android でのこの使用例の実装例を次に示します。

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## アプリケーションのカスタムデータを使用したモバイルプロファイルのエンリッチメント {#enrich-mobile-profile-custom}

この使用例を機能させるには、PII ポストバックのルールを作成する必要があります。 詳しくは、 [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback).

### iOSを使用 {#enrich-mobile-profile-custom-ios}

iOSでは、次の [!DNL Experience Platform API] は必須です。

* collectPII <br> 詳しくは、「 collectPII 」を参照してください。

iOSでのこの使用例の実装例を次に示します。

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### Android の場合 {#enrich-mobile-profile-custom-android}

Android では、次のようになります。 [!DNL Experience Platform API] は必須です。

* collectPII <br> 詳しくは、「 collectPII 」を参照してください。

Android でのこの使用例の実装例を次に示します。

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## アプリケーションのライフサイクルデータを使用したモバイルプロファイルのエンリッチメント {#enrich-mobile-profile-lifecycle}

この使用例を機能させるには、PII ポストバックのルールを作成する必要があります。 詳しくは、 [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaignは、カスタムデータまたはライフサイクルデータをモバイルアプリと区別しません。 モバイルアプリでのイベントに応じて、collectPii ポストバックルールを使用して、両方のタイプのデータをサーバーに送信できます。

### iOSを使用 {#enrich-mobile-profile-lifecycle-ios}

iOSでは、次の [!DNL Experience Platform APIs] は必須です。

* **[!UICONTROL Lifecycle Start]**、アプリの起動時とアプリがフォアグラウンドになっているとき。
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドになっている場合）

詳しくは、 [iOSのライフサイクル拡張](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

iOSでのこの使用例の実装例を次に示します。

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

### Android の場合 {#enrich-mobile-profile-lifecycle-android}

Android では、次のようになります。 [!DNL Experience Platform APIs] は必須です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、 [Android のライフサイクル拡張機能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Android でのこの使用例の実装例を次に示します。

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

## プッシュ通知を使用したユーザーインタラクションの追跡 {#track-user-push}

プッシュ通知トラッキングポストバック用のルールを作成する必要があります。 詳しくは、 [プッシュ通知トラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### iOSを使用 {#track-user-push-ios}

iOSでは、次の [!DNL Experience Platform SDK] は必須です。

* **[!UICONTROL trackAction]**.詳しくは、 [アプリのアクションの追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

iOSでのこの使用例の実装例を次に示します。

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Android の場合 {#track-user-push-android}

Android では、次のようになります。 [!DNL Experience Platform SDK] は必須です。

* **[!UICONTROL trackAction]**
詳しくは、 [アプリのアクションの追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Android でのこの使用例の実装例を次に示します。

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## アプリ内メッセージのトリガーへのカスタムイベントの実装 {#custom-event-inapp}

### iOSを使用 {#custom-event-inapp-ios}

iOSでは、次の [!DNL Experience Platform SDK] は必須です。

* **[!UICONTROL trackAction]**.詳しくは、 [アプリのアクションの追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

iOSでのこの使用例の実装例を次に示します。

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Android の場合 {#custom-event-inapp-android}

Android では、次のようになります。 [!DNL Experience Platform SDK] は必須です。

* **[!UICONTROL trackAction]**
詳しくは、 [アプリのアクションの追跡](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Android でのこの使用例の実装例を次に示します。

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 追加の認証用にリンケージフィールドを設定 {#linkage-fields-inapp}

### iOSを使用 {#linkage-fields-inapp-ios}

iOSのアプリ内メッセージに基づくプロファイルテンプレートの追加認証用のリンケージフィールドを設定するには、次の手順を実行します。 [!DNL Experience Platform SDK] は必須です。

* リンケージフィールドを設定 <br>詳しくは、 [リンケージフィールドを設定](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* リンケージフィールドをリセット <br>詳しくは、 [リンケージフィールドをリセット](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

iOSでのこの使用例の実装例を以下に示します。

リンケージフィールドを設定するには：

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

リンケージフィールドをリセットするには：

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Android の場合 {#linkage-fields-inapp-android}

Android のアプリ内メッセージに基づくプロファイルテンプレートの追加認証用のリンケージフィールドを設定するには、次のExperience PlatformSDK が必要です。

* リンケージフィールドを設定 <br>詳しくは、 [リンケージフィールドを設定](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* リンケージフィールドをリセット <br>詳しくは、 [リンケージフィールドをリセット](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

Android でのこの使用例の実装例を以下に示します。

リンケージフィールドを設定するには：

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

リンケージフィールドをリセットするには：

```
Campaign.resetLinkageFields()
```
