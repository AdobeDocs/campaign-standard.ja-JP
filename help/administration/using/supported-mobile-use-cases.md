---
title: Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされるモバイルの使用例
description: モバイルのユースケースをサポートする方法を学ぶ
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

このページでは、[!DNL Adobe Experience Platform SDKs] を使用して [!DNL Adobe Campaign Standard] でサポートされているすべてのモバイルユースケースのリストを示します。 これらのユースケースをサポートするには、[!DNL Adobe Experience Platform SDKs]、[!DNL tags in Adobe Experience Platform]、[!DNL Adobe Campaign Standard] のインストールと設定が必要です。 詳しくは、この [&#x200B; ページ &#x200B;](../../administration/using/configuring-a-mobile-application.md) を参照してください。

Adobe Campaign Standardでは、次のユースケースをサポートしています。

* [Campaign Standardへのモバイルプロファイルの登録](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Campaign Standardへのプッシュトークンの送信](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [アプリケーションのカスタムデータでモバイルプロファイルを強化](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [アプリケーションのライフサイクルデータでモバイルプロファイルを強化](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [プッシュ通知を使用したユーザーインタラクションを追跡](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [モバイルアプリにカスタムイベントを実装して、アプリ内メッセージをトリガーにします](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [アプリ内メッセージに基づくプロファイルテンプレートの追加認証用のリンケージフィールドの設定](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

これらのユースケースを設定するには、次の拡張機能が必要です。

* **[!DNL Adobe Campaign Standard]** <br> 拡張機能をインストールして設定するには、[Data Collection UI のCampaign StandardCampaign Standardの設定 &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension) を参照してください。
* 自動的にインストールされる **[!DNL Mobile Core]**。 <br>Mobile Core 拡張機能について詳しくは、「[Mobile Core](https://developer.adobe.com/client-sdks/documentation/mobile-core/)」を参照してください。
* 自動的にインストールされる **[!DNL Profile]**。 <br> プロファイル拡張機能について詳しくは、[&#x200B; プロファイル &#x200B;](https://developer.adobe.com/client-sdks/documentation/profile/) を参照してください。

## Campaign Standardへのモバイルプロファイルの登録 {#register-mobile-profile}

### （iOSを使用） {#register-mobile-profile-ios}

iOSでは、次の [!DNL Experience Platform APIs] が必要です。

* つまり、アプリの起動時と、フォアグラウンドでの **[!UICONTROL Lifecycle Start]** 動です。
* **[!UICONTROL Lifecycle Pause]**：アプリがバックグラウンドにある場合。

詳しくは、[iOSのライフサイクル拡張 &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/) を参照してください。

以下は、iOSを使用したこのユースケースの実装例です。

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

### （Androidを使用） {#register-mobile-profile-android}

Androidでは、次の [!DNL Experience Platform APIs] が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、[Androidのライフサイクル拡張 &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/) を参照してください。

以下は、Androidを使用したこのユースケースの実装例です。

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

### （iOSを使用） {#send-push-token-ios}

iOSでは、次の [!DNL Experience Platform SDK] が必要です。

* **[!UICONTROL setPushIdentifier]** <br> 詳しくは、[setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) を参照してください。

以下は、iOSを使用したこのユースケースの実装例です。

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### （Androidを使用） {#send-push-token-android}

Androidでは、次の [!DNL Experience Platform SDK] が必要です。

* **[!UICONTROL setPushIdentifier]** <br> 詳しくは、[setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) を参照してください。

以下は、Androidを使用したこのユースケースの実装例です。

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## アプリケーションのカスタムデータでモバイルプロファイルを強化 {#enrich-mobile-profile-custom}

このユースケースが機能するには、PII ポストバックのルールを作成する必要があります。 詳しくは、[PII ポストバック &#x200B;](../../administration/using/configuring-rules-launch.md#pii-postback) を参照してください。

### （iOSを使用） {#enrich-mobile-profile-custom-ios}

iOSでは、次の [!DNL Experience Platform API] が必要です。

* collectPII <br> 詳しくは、collectPII を参照してください。

以下は、iOSを使用したこのユースケースの実装例です。

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### （Androidを使用） {#enrich-mobile-profile-custom-android}

Androidでは、次の [!DNL Experience Platform API] が必要です。

* collectPII <br> 詳しくは、collectPII を参照してください。

以下は、Androidを使用したこのユースケースの実装例です。

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## アプリケーションのライフサイクルデータでモバイルプロファイルを強化 {#enrich-mobile-profile-lifecycle}

このユースケースが機能するには、PII ポストバックのルールを作成する必要があります。 詳しくは、[PII ポストバック &#x200B;](../../administration/using/configuring-rules-launch.md#pii-postback) を参照してください。

>[!NOTE]
>
>Adobe Campaignでは、モバイルアプリからのカスタムデータまたはライフサイクルデータを区別しません。 モバイルアプリ内のイベントに応答して、collectPii ポストバックルールを使用して両方のタイプのデータをサーバーに送信できます。

### （iOSを使用） {#enrich-mobile-profile-lifecycle-ios}

iOSでは、次の [!DNL Experience Platform APIs] が必要です。

* つまり、アプリの起動時と、フォアグラウンドでの **[!UICONTROL Lifecycle Start]** 動です。
* **[!UICONTROL Lifecycle Pause]**：アプリがバックグラウンドにある場合。

詳しくは、[iOSのライフサイクル拡張 &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/) を参照してください。

以下は、iOSを使用したこのユースケースの実装例です。

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

### （Androidを使用） {#enrich-mobile-profile-lifecycle-android}

Androidでは、次の [!DNL Experience Platform APIs] が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、[Androidのライフサイクル拡張 &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/) を参照してください。

以下は、Androidを使用したこのユースケースの実装例です。

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

## プッシュ通知を使用したユーザーインタラクションを追跡 {#track-user-push}

ポストバックを追跡するプッシュ通知のルールを作成する必要があります。 詳しくは、[&#x200B; プッシュ通知のトラッキングポストバック &#x200B;](../../administration/using/configuring-rules-launch.md#push-tracking-postback) を参照してください。

### （iOSを使用） {#track-user-push-ios}

iOSでは、次の [!DNL Experience Platform SDK] が必要です。

* **[!UICONTROL trackAction]**.詳しくは、「[&#x200B; アプリのアクションのトラッキング &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)」を参照してください。

以下は、iOSを使用したこのユースケースの実装例です。

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### （Androidを使用） {#track-user-push-android}

Androidでは、次の [!DNL Experience Platform SDK] が必要です。

* **[!UICONTROL trackAction]**
詳しくは、「[&#x200B; アプリのアクションのトラッキング &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)」を参照してください。

以下は、Androidを使用したこのユースケースの実装例です。

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## アプリケーションにカスタムイベントを実装して、アプリ内メッセージをトリガーにします {#custom-event-inapp}

### （iOSを使用） {#custom-event-inapp-ios}

iOSでは、次の [!DNL Experience Platform SDK] が必要です。

* **[!UICONTROL trackAction]**.詳しくは、「[&#x200B; アプリのアクションのトラッキング &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)」を参照してください。

以下は、iOSを使用したこのユースケースの実装例です。

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### （Androidを使用） {#custom-event-inapp-android}

Androidでは、次の [!DNL Experience Platform SDK] が必要です。

* **[!UICONTROL trackAction]**
詳しくは、「[&#x200B; アプリのアクションのトラッキング &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)」を参照してください。

以下は、Androidを使用したこのユースケースの実装例です。

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 追加認証用のリンケージフィールドの設定 {#linkage-fields-inapp}

### （iOSを使用） {#linkage-fields-inapp-ios}

iOSのアプリ内メッセージに基づくプロファイルテンプレートに対して追加の認証用のリンケージフィールドを設定するには、次の [!DNL Experience Platform SDK] が必要です。

* リンクフィールドを設定します <br> 詳しくは、[&#x200B; リンクフィールドを設定 &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields) を参照してください。
* リンケージフィールドのリセット <br> 詳しくは、[&#x200B; リンケージフィールドのリセット &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields) を参照してください。

iOSを使用したこのユースケースの実装例を次に示します。

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

### （Androidを使用） {#linkage-fields-inapp-android}

Androidのアプリ内メッセージに基づくプロファイルテンプレートに対して追加の認証用のリンケージフィールドを設定するには、次のSDKExperience Platformが必要です。

* リンクフィールドを設定します <br> 詳しくは、[&#x200B; リンクフィールドを設定 &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields) を参照してください。
* リンケージフィールドのリセット <br> 詳しくは、[&#x200B; リンケージフィールドのリセット &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields) を参照してください。

Androidを使用したこのユースケースの実装例を次に示します。

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
