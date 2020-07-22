---
title: Adobe Experience Platform SDK and Adobe Campaign integration FAQ
description: Adobe Experience Platform SDK and Adobe Campaign integration FAQ
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6c5cf90211451587537b9a6121430fc4f352384c
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---


# Get Started with Adobe Experience Platform SDK and Campaign Standard {#aep-faq}

Experience PlatformSDKアプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリをAdobe Experience PlatformSDKで設定し、Adobe Campaignで設定する必要があります。

以下の節では、この同期に関してよくある質問をリストします。

For more information on Push or In-app, refer to the following FAQs:

* [Push notification FAQ](../../channels/using/about-push-notifications.md#push-faq)
* [In-App FAQ](../../channels/using/about-push-notifications.md#in-app-faq)
* [起動の技術的なワークフローと同期FAQ](../../administration/using/syncwithlaunch-faq.md)

## Useful resources before starting {#resource-mobile-property}

Adobe Experience PlatformSDKとCampaign Standardの統合について詳しくは、以下のリソースを参照してください。

* Launch/Mobile [Overview Video](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [Tips &amp; Tricks Guide](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Is Adobe Experience Platform SDK integration available for both Adobe Campaign Standard and Adobe Campaign Classic? {#aep-validity}

はい、 [!DNL Adobe Experience Platform SDK] Adobe Campaign StandardとAdobe Campaignの両方で統合を利用できます。 You need to install the corresponding **[!UICONTROL Extension]** via [!DNL Adobe Launch] to enable the integration.

For more on this, refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic) for Campaign Classic and this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) for Campaign Standard.

## Adobe Experience PlatformSDKを統合すると、どのような機能をAdobe Campaignしやすくなりますか？ {#aep-capabilities}

これらの機能の詳細については、次の表を参照してください。

![](assets/faq.png)

>[!N注意]
>
>[!DNL Places] 統合には、アプリ内メッセージのトリガーとして配置イベントが含まれます（プッシュ通知の場合は除く）。データとローカル通知のサポートによってプロファイルを強化し [!DNL Places] ます。 Refer to this [page](../../channels/using/preparing-and-sending-an-in-app-message.md) for more information. <br>[!DNL Places] 制限付き統合には、 [!DNL Places] データをプロファイルに富化する機能が含まれます。

## Adobe Experience PlatformSDKの統合によってAdobe Campaign Standardが容易になる使用例を教えてください。 {#aep-use-cases}

次の使用例がサポートされています。

* キャンペーン **[!UICONTROL Mobile Profile]** を取得する(「ECID」(「>>> **[!UICONTROL Administration]** > **[!UICONTROL Channels]** 」 **[!UICONTROL Mobile app (AEP SDK)]****[!UICONTROL Mobile Application subscribers]** タブで識別)
* Adobe Campaign **[!UICONTROL Mobile Profile]** を拡張する(appSubscriberRcpテーブル **[!UICONTROL Custom resource Extension]** が必要)
* プッシュメッセージを送信するためのプッシュトークンの取得（プッシュメッセージを受信するには、ユーザーのオプトインが必要）
* プッシュメッセージとアプリ内メッセージの送信
* プッシュメッセージおよびアプリ内メッセージに対するユーザーのインタラクションを追跡し、それに関するレポートを提供します

## キャンペーンでモバイルプロファイルを取得するには、何をする必要がありますか？ {#mobile-profile-campaign}

これを行うには、次の手順に従います。

1. Configure a **[!UICONTROL Mobile property]** in [!DNL Launch].
1. Install Adobe Campaign Standard extension. Note that Adobe Campaign Standard extension also requires **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** and **[!UICONTROL Lifecycle]** extensions which are installed by default in [!DNL Launch].
   * Users should configure Session timeout in **[!UICONTROL Mobile Core]** extension which impacts the frequency of lifecycle events.
   * Once the extension is configured, users should add appropriate dependencies in the Mobile App using Cocoapods for iOS and Gradle for Android. Follow the directions [here](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Always take the latest versions of the libraries.
   * In Mobile App, register **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** and **[!UICONTROL Signal]** extensions. Follow the directions [here](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Once extensions are registered, start ACPCore. For Android, be sure to setApplication onCreate(). Follow the exact instructions provided in Mobile Install Instructions for your Mobile Property in Launch.
   * Following SDK APIs will also be required. Implement Lifecycle Start and Pause APIs as described [here](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) for Android and here for iOS.
1. Configure a **[!UICONTROL Mobile Property]** in Adobe Campaign Standard. Follow the procedure [here](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## What do I have to do in order to enrich a Mobile Profile in Campaign? {#enrich-mobile-profile}

You need to configure a CollectPII postback (refer to this [page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) and implement CollectPII API from SDK (refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## How frequently should a CollectPII call be fired? {#collect-pii}

The objective of CollectPII call is to enrich the Mobile Profile in Campaign. It should be fired whenever there is new meaningful information that customers would like to add to the profile depending on their use cases and business needs.

## 複数のトリガーイベントに応答してCollectPII呼び出しを実行できますか。 {#collect-pii-calls}

はい。 ビジネスのニーズに応じて、アプリ内のユーザーログに応じて、または何か、ライフサイクルイベントを購入したり、ジオフェンスに入るユーザーに応じて、CollectPII呼び出しを実行できます。 To sum up, an interaction of user with the app that generates information you would want to use for Profile enrichment.

## すべてのモバイルイベントに対してCollectPII呼び出しを実行できますか。 {#collect-pii-events}

Frequency and design of CollectPII calls should be dictated by business needs and shouldn&#39;t be fired blindly as it creates extra load on the DB.

### キャンペーンまたは起動でAdobe Experience Platformアプリにアクセスしようとすると、プロパティが利用できないというエラーが表示されることがあります。 {#aep-error}

This is a known issue and happens due to token expiration. You should try login out and in.

## What would be some useful resource recommendations to learn more about Adobe Experience Platform SDK (formerly known as SDK V5)?{#resource-aep}

Check out the resources below:

* Experience Platform SDK [documentation](https://aep-sdks.gitbook.io/docs/)
* 起動とExperience PlatformSDKに関する [ドキュメントの概要](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Experience PlatformSDK [ドキュメントへのアップグレード](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GithubExperience PlatformSDK [ドキュメント](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)
