---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされるモバイルの使用例
description: このドキュメントでは、モバイルの使用例をサポートする方法について説明します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: インスタンス設定
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 1%

---

# Adobe Campaign Standard でサポートされるモバイルのユースケース {#mobile-use-cases}

このページでは、[!DNL Adobe Experience Platform SDKs]を使用して[!DNL Adobe Campaign Standard]でサポートされるすべてのモバイル使用例のリストを示します。 これらの使用例をサポートするには、 [!DNL Adobe Experience Platform SDKs]、 [!DNL Adobe Experience Platform Launch]および[!DNL Adobe Campaign Standard]のインストールと設定が必要です。 これについて詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md)を参照してください。

Adobe Campaign Standardは、次の使用例をサポートしています。

* [モバイルプロファイルのCampaign Standardへの登録](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Campaign Standardへのプッシュトークンの送信](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [アプリケーションのカスタムデータを使用したモバイルプロファイルの強化](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [アプリケーションのライフサイクルデータを使用したモバイルプロファイルの強化](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [プッシュ通知を使用したユーザーインタラクションの追跡](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [モバイルアプリにカスタムイベントを実装してアプリ内メッセージをトリガーする](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [アプリ内メッセージに基づくプロファイルテンプレートの追加認証用のリンケージフィールドの設定](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

これらの使用例を設定するには、[!DNL Experience Platform Launch]の次の拡張機能が必要です。

* **[!DNL Adobe Campaign Standard]** <br>Campaign Standard拡張機能のインストールと設定については、「 [Experience Platform LaunchでのCampaign Standard拡張機能の設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch)」を参照してください。
* **[!DNL Mobile Core]**：自動的にインストールされます。<br>Mobile Core拡張機能について詳しくは、「Mobile Core」を参照 [してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)。
* **[!DNL Profile]**：自動的にインストールされます。<br>Profile拡張機能について詳しくは、「プロファイル」を参照 [してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile)。

## モバイルプロファイルのCampaign Standardへの登録 {#register-mobile-profile}

### iOSの場合 {#register-mobile-profile-ios}

iOSでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL Lifecycle Start]**（アプリの起動時とアプリがフォアグラウンドになっている場合）
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドになっている場合）

詳しくは、「iOSのライフサイクル拡張](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)」を参照してください。[

iOSでのこの使用例の実装例を以下に示します。

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

### Androidを使用 {#register-mobile-profile-android}

Androidでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、「Androidのライフサイクル拡張[」を参照してください。](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)

Androidでのこの使用例の実装例を次に示します。

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

### iOSの場合 {#send-push-token-ios}

iOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、「 setPushIdentifier 」を参照し [てください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

iOSでのこの使用例の実装例を次に示します。

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Androidを使用 {#send-push-token-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、「 setPushIdentifier 」を参照し [てください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

Androidでのこの使用例の実装例を次に示します。

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## アプリケーションのカスタムデータを使用したモバイルプロファイルの強化 {#enrich-mobile-profile-custom}

この使用例を機能させるには、PIIポストバックのルールを作成する必要があります。 詳しくは、[PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)を参照してください。

### iOSの場合 {#enrich-mobile-profile-custom-ios}

iOSでは、次の[!DNL Experience Platform API]が必要です。

* collectPII <br>詳しくは、 collectPIIを参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Androidを使用 {#enrich-mobile-profile-custom-android}

Androidでは、次の[!DNL Experience Platform API]が必要です。

* collectPII <br>詳しくは、 collectPIIを参照してください。

Androidでのこの使用例の実装例を次に示します。

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## アプリケーションのライフサイクルデータを使用したモバイルプロファイルの強化 {#enrich-mobile-profile-lifecycle}

この使用例を機能させるには、PIIポストバックのルールを作成する必要があります。 詳しくは、[PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)を参照してください。

>[!NOTE]
>
>Adobe Campaignは、カスタムデータまたはライフサイクルデータをモバイルアプリと区別しません。 モバイルアプリのイベントに応じて、collectPiiポストバックルールを使用して、両方のタイプのデータをサーバーに送信できます。

### iOSの場合 {#enrich-mobile-profile-lifecycle-ios}

iOSでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL Lifecycle Start]**（アプリの起動時とアプリがフォアグラウンドになっている場合）
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドになっている場合）

詳しくは、「iOSのライフサイクル拡張](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)」を参照してください。[

iOSでのこの使用例の実装例を以下に示します。

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

### Androidを使用 {#enrich-mobile-profile-lifecycle-android}

Androidでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、「Androidのライフサイクル拡張[」を参照してください。](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)

Androidでのこの使用例の実装例を次に示します。

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

プッシュ通知トラッキングポストバック用のルールを作成する必要があります。 詳しくは、[プッシュ通知のトラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)を参照してください。

### iOSの場合 {#track-user-push-ios}

iOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**.詳しくは、[アプリのアクションの追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)を参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Androidを使用 {#track-user-push-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**
詳しくは、「アプリのアクションの追 [跡」を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

Androidでのこの使用例の実装例を次に示します。

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## アプリ内メッセージのトリガーへのカスタムイベントの実装 {#custom-event-inapp}

### iOSの場合 {#custom-event-inapp-ios}

iOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**.詳しくは、[アプリのアクションの追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)を参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Androidを使用 {#custom-event-inapp-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**
詳しくは、「アプリのアクションの追 [跡」を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

Androidでのこの使用例の実装例を次に示します。

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 追加の認証用のリンケージフィールドの設定 {#linkage-fields-inapp}

### iOSの場合 {#linkage-fields-inapp-ios}

iOSのアプリ内メッセージに基づくプロファイルテンプレートに対して追加の認証用のリンケージフィールドを設定するには、次の[!DNL Experience Platform SDK]が必要です。

* リンケージフィールド<br>を設定します。詳しくは、[リンケージフィールドの設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)を参照してください。
* リンケージフィールドをリセット<br>詳しくは、[リンケージフィールドのリセット](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)を参照してください。

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

### Androidを使用 {#linkage-fields-inapp-android}

Androidのアプリ内メッセージに基づくプロファイルテンプレートに対して追加の認証用のリンケージフィールドを設定するには、次のExperience PlatformSDKが必要です。

* リンケージフィールド<br>を設定します。詳しくは、[リンケージフィールドの設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)を参照してください。
* リンケージフィールドをリセット<br>詳しくは、[リンケージフィールドのリセット](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)を参照してください。

Androidでのこの使用例の実装例を以下に示します。

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
