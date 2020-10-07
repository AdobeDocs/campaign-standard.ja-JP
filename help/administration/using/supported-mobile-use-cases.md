---
title: Adobe Experience PlatformSDKを使用してAdobe Campaign Standardでサポートされるモバイル用途
description: このドキュメントでは、モバイルの使用例をサポートする方法について説明します。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 1%

---


# Adobe Campaign Standard でサポートされるモバイルの使用例 {#mobile-use-cases}

このページでは、の使用でサポートされるすべてのモバイル使用例のリストを見 [!DNL Adobe Campaign Standard] ることができ [!DNL Adobe Experience Platform SDKs]ます。 これらの使用例をサポートするには、、、およびのインストールと設定 [!DNL Adobe Experience Platform SDKs]を行う必要があり [!DNL Adobe Experience Platform Launch]ま [!DNL Adobe Campaign Standard]す。 これについて詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md)を参照してください。

Adobe Campaign Standardは、次の使用例をサポートしています。

* [モバイルプロファイルのCampaign Standardへの登録](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Campaign Standardへのプッシュトークンの送信](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [アプリケーションのカスタムデータを使用したモバイルプロファイルの拡張](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [アプリケーションのライフサイクルデータを使用したモバイルプロファイルの拡張](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [プッシュ通知を使用したユーザーの操作を追跡する](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [アプリ内メッセージをトリガーするためのカスタムイベントのモバイルアプリへの実装](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [アプリ内メッセージに基づくプロファイルテンプレートの追加認証用のリンケージフィールドを設定します](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

これらの使用例を設定するには、次の拡張機能が必要で [!DNL Experience Platform Launch]す。

* **[!DNL Adobe Campaign Standard]** <br>Campaign Standard拡張機能をインストールして設定するには、「Experience Platform LaunchでのCampaign Standard拡張の [設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch)」を参照してください。
* **[!DNL Mobile Core]**&#x200B;に設定され、自動的にインストールされます。 <br>Mobile Core拡張機能について詳しくは、「 [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)」を参照してください。
* **[!DNL Profile]**&#x200B;に設定され、自動的にインストールされます。 <br>プロファイル拡張機能について詳しくは、「 [プロファイル](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile)」を参照してください。

## モバイルプロファイルのCampaign Standardへの登録 {#register-mobile-profile}

### iOSの場合 {#register-mobile-profile-ios}

iOSでは、次の情報が必要 [!DNL Experience Platform APIs] です。

* **[!UICONTROL Lifecycle Start]**（アプリの起動時とアプリがフォアグラウンドの場合）。
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドにある場合）。

詳しくは、iOSの [ライフサイクル拡張機能を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)。

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

### Androidの場合 {#register-mobile-profile-android}

Androidでは、以下が必要 [!DNL Experience Platform APIs] です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、Androidでの [ライフサイクル拡張機能を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)。

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

## プッシュトークンのAdobe Campaign Standardへの送信 {#send-push-token}

### iOSの場合 {#send-push-token-ios}

iOSでは、次の情報が必要 [!DNL Experience Platform SDK] です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、setPushIdentifierを参照して [ください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

iOSでのこの使用例の実装例を次に示します。

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Androidの場合 {#send-push-token-android}

Androidでは、以下が必要 [!DNL Experience Platform SDK] です。

* **[!UICONTROL setPushIdentifier]** <br>詳しくは、setPushIdentifierを参照して [ください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

Androidのこの使用例の実装例を次に示します。

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## アプリケーションのカスタムデータを使用したモバイルプロファイルの拡張 {#enrich-mobile-profile-custom}

この使用例を機能させるには、PIIポストバックのルールを作成する必要があります。 詳しくは、「 [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)」を参照してください。

### iOSの場合 {#enrich-mobile-profile-custom-ios}

iOSでは、次の情報が必要 [!DNL Experience Platform API] です。

* collectPII詳 <br> しくは、collectPIIを参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Androidの場合 {#enrich-mobile-profile-custom-android}

Androidでは、以下が必要 [!DNL Experience Platform API] です。

* collectPII詳 <br> しくは、collectPIIを参照してください。

Androidのこの使用例の実装例を以下に示します。

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## アプリケーションのライフサイクルデータを使用したモバイルプロファイルの拡張 {#enrich-mobile-profile-lifecycle}

この使用例を機能させるには、PIIポストバックのルールを作成する必要があります。 詳しくは、「 [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)」を参照してください。

>[!NOTE]
>
>Adobe Campaignでは、カスタムデータまたはライフサイクルデータをモバイルアプリと区別しません。 モバイルアプリのイベントに応じて、collectPiiポストバックルールを使用して、両方のタイプのデータをサーバーに送信できます。

### iOSの場合 {#enrich-mobile-profile-lifecycle-ios}

iOSでは、次の情報が必要 [!DNL Experience Platform APIs] です。

* **[!UICONTROL Lifecycle Start]**（アプリの起動時とアプリがフォアグラウンドの場合）。
* **[!UICONTROL Lifecycle Pause]**（アプリがバックグラウンドにある場合）。

詳しくは、iOSの [ライフサイクル拡張機能を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)。

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

### Androidの場合 {#enrich-mobile-profile-lifecycle-android}

Androidでは、以下が必要 [!DNL Experience Platform APIs] です。

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

詳しくは、Androidでの [ライフサイクル拡張機能を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)。

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

## プッシュ通知を使用したユーザーの操作を追跡する {#track-user-push}

ポストバックを追跡するプッシュ通知のルールを作成する必要があります。 詳しくは、 [プッシュ通知トラッキングポストバックを参照してください](../../administration/using/configuring-rules-launch.md#push-tracking-postback)。

### iOSの場合 {#track-user-push-ios}

iOSでは、次の情報が必要 [!DNL Experience Platform SDK] です。

* **[!UICONTROL trackAction]**.」詳しくは、「アプリのアクションを [追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Androidの場合 {#track-user-push-android}

Androidでは、以下が必要 [!DNL Experience Platform SDK] です。

* **[!UICONTROL trackAction]**
詳しくは、「アプリのアクションを [追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

Androidのこの使用例の実装例を以下に示します。

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## アプリ内イベントをトリガーするためのカスタムメッセージのアプリへの実装 {#custom-event-inapp}

### iOSの場合 {#custom-event-inapp-ios}

iOSでは、次の情報が必要 [!DNL Experience Platform SDK] です。

* **[!UICONTROL trackAction]**.」詳しくは、「アプリのアクションを [追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

iOSでのこの使用例の実装例を以下に示します。

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Androidの場合 {#custom-event-inapp-android}

Androidでは、以下が必要 [!DNL Experience Platform SDK] です。

* **[!UICONTROL trackAction]**
詳しくは、「アプリのアクションを [追跡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

Androidのこの使用例の実装例を以下に示します。

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 追加の認証用のリンケージフィールドの設定 {#linkage-fields-inapp}

### iOSの場合 {#linkage-fields-inapp-ios}

iOSのアプリ内メッセージに基づくプロファイルテンプレートに、追加の認証用のリンケージフィールドを設定するには、以下が必要 [!DNL Experience Platform SDK] です。

* リンケージフィールド <br>の設定詳しくは、リン [ケージフィールドの設定を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)。
* リンケージフィールド <br>のリセット詳しくは、リンケージフィールドの [リセットを参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)。

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

### Androidの場合 {#linkage-fields-inapp-android}

Androidのアプリ内メッセージに基づくプロファイルテンプレートに、追加の認証用のリンケージフィールドを設定するには、次のExperience PlatformSDKが必要です。

* リンケージフィールド <br>の設定詳しくは、リン [ケージフィールドの設定を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)。
* リンケージフィールド <br>のリセット詳しくは、リンケージフィールドの [リセットを参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)。

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
