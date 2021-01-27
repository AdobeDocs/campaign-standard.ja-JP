---
solution: Campaign Standard
product: campaign
title: Adobe Experience PlatformSDKを使用してAdobe Campaign Standardでサポートされるモバイル用途
description: このドキュメントでは、モバイルの使用例をサポートする方法について説明します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 1%

---


# Adobe Campaign Standard でサポートされるモバイルの使用例 {#mobile-use-cases}

このページでは、[!DNL Adobe Campaign Standard]で[!DNL Adobe Experience Platform SDKs]を使用してサポートされるすべてのモバイル用途のリストを見つけ出します。 これらの使用例をサポートするには、[!DNL Adobe Experience Platform SDKs]、[!DNL Adobe Experience Platform Launch]、[!DNL Adobe Campaign Standard]のインストールと設定が必要です。 これについて詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md)を参照してください。

Adobe Campaign Standardは、次の使用例をサポートしています。

* [モバイルプロファイルのCampaign Standardへの登録](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Campaign Standardへのプッシュトークンの送信](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [アプリケーションのカスタムデータを使用したモバイルプロファイルの拡張](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [アプリケーションのライフサイクルデータを使用したモバイルプロファイルの拡張](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [プッシュ通知を使用したユーザーの操作を追跡する](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [トリガーのアプリ内メッセージに対するモバイルアプリへのカスタムイベントの実装](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [アプリ内メッセージに基づくプロファイルテンプレートの追加認証用のリンケージフィールドを設定します](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

これらの使用例を設定するには、[!DNL Experience Platform Launch]の次の拡張が必要です。

* **[!DNL Adobe Campaign Standard]** <br>Campaign Standard拡張機能をインストールして設定するには、「Experience Platform LaunchでのCampaign Standard拡張の [設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch)」を参照してください。
* **[!DNL Mobile Core]**&#x200B;に設定され、自動的にインストールされます。<br>Mobile Core拡張機能について詳しくは、「 [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)」を参照してください。
* **[!DNL Profile]**&#x200B;に設定され、自動的にインストールされます。<br>プロファイル拡張機能について詳しくは、「 [プロファイル](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile)」を参照してください。

## Campaign Standard{#register-mobile-profile}にモバイルプロファイルを登録する

### iOSの場合{#register-mobile-profile-ios}

iOSでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL Lifecycle Start]**（アプリの起動時とアプリがフォアグラウンドの場合）。
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドにある場合）。

詳しくは、「[iOSのライフサイクル拡張機能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)」を参照してください。

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

### Androidの場合{#register-mobile-profile-android}

Androidでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、[Androidのライフサイクル拡張機能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)を参照してください。

Androidのこの使用例の実装例を以下に示します。

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

## プッシュトークンをAdobe Campaign Standardに送信{#send-push-token}

### iOSの場合{#send-push-token-ios}

iOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、setPushIdentifierを参照して [ください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

iOSでのこの使用例の実装例を次に示します。

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Androidの場合{#send-push-token-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、setPushIdentifierを参照して [ください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

Androidのこの使用例の実装例を次に示します。

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## アプリケーション{#enrich-mobile-profile-custom}のカスタムデータを使用したモバイルプロファイルの拡張

この使用例を機能させるには、PIIポストバックのルールを作成する必要があります。 詳しくは、[PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)を参照してください。

### iOSの場合{#enrich-mobile-profile-custom-ios}

iOSでは、次の[!DNL Experience Platform API]が必要です。

* collectPII <br>詳しくは、collectPIIを参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Androidの場合{#enrich-mobile-profile-custom-android}

Androidでは、次の[!DNL Experience Platform API]が必要です。

* collectPII <br>詳しくは、collectPIIを参照してください。

Androidのこの使用例の実装例を以下に示します。

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## アプリケーション{#enrich-mobile-profile-lifecycle}のライフサイクルデータを使用したモバイルプロファイルの拡張

この使用例を機能させるには、PIIポストバックのルールを作成する必要があります。 詳しくは、[PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)を参照してください。

>[!NOTE]
>
>Adobe Campaignでは、カスタムデータまたはライフサイクルデータをモバイルアプリと区別しません。 モバイルアプリのイベントに応じて、collectPiiポストバックルールを使用して、両方のタイプのデータをサーバーに送信できます。

### iOSの場合{#enrich-mobile-profile-lifecycle-ios}

iOSでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL Lifecycle Start]**（アプリの起動時とアプリがフォアグラウンドの場合）。
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドにある場合）。

詳しくは、「[iOSのライフサイクル拡張機能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)」を参照してください。

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

### Androidの場合{#enrich-mobile-profile-lifecycle-android}

Androidでは、次の[!DNL Experience Platform APIs]が必要です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、[Androidのライフサイクル拡張機能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)を参照してください。

Androidのこの使用例の実装例を以下に示します。

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

## プッシュ通知を使用したユーザーの操作を追跡{#track-user-push}

ポストバックを追跡するプッシュ通知のルールを作成する必要があります。 詳しくは、[ポストバックを追跡するプッシュ通知](../../administration/using/configuring-rules-launch.md#push-tracking-postback)を参照してください。

### iOSの場合{#track-user-push-ios}

iOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**.」詳しくは、[アプリのアクションを追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)を参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Androidの場合{#track-user-push-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**
詳しくは、「アプリのアクションを [追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

Androidのこの使用例の実装例を以下に示します。

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## アプリ内メッセージをトリガーするためのカスタムイベント{#custom-event-inapp}

### iOSの場合{#custom-event-inapp-ios}

iOSでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**.」詳しくは、[アプリのアクションを追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)を参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Androidの場合{#custom-event-inapp-android}

Androidでは、次の[!DNL Experience Platform SDK]が必要です。

* **[!UICONTROL trackAction]**
詳しくは、「アプリのアクションを [追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

Androidのこの使用例の実装例を以下に示します。

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 追加の認証用のリンケージフィールドの設定{#linkage-fields-inapp}

### iOSの場合{#linkage-fields-inapp-ios}

iOSのアプリ内メッセージに基づくプロファイルテンプレートに追加認証用のリンケージフィールドを設定するには、次の[!DNL Experience Platform SDK]が必要です。

* リンケージフィールドの設定<br>詳しくは、[リンケージフィールドの設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)を参照してください。
* リンケージフィールドのリセット<br>詳しくは、[リンケージフィールドのリセット](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)を参照してください。

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

### Androidの場合{#linkage-fields-inapp-android}

Androidのアプリ内メッセージに基づくプロファイルテンプレートに、追加の認証用のリンケージフィールドを設定するには、次のExperience PlatformSDKが必要です。

* リンケージフィールドの設定<br>詳しくは、[リンケージフィールドの設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)を参照してください。
* リンケージフィールドのリセット<br>詳しくは、[リンケージフィールドのリセット](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)を参照してください。

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
