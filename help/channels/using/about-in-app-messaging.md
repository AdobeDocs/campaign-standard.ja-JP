---
title: アプリ内メッセージについて
seo-title: アプリ内メッセージについて
description: アプリ内メッセージについて
seo-description: アプリ内メッセージを使用して、モバイルアプリケーション内でメッセージまたはアラートを表示します。
page-status-flag: 常にアクティブ化されていない
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: アプリ内メッセージ
discoiquuid: a4168cfb-22bf-4ab3- b9d8-6e76e1bdc055
context-tags: 配信、トリガー、戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 90b478d1d58b67e763b8b6685c12530a5b5ee9c3

---


# About In-App messaging{#about-in-app-messaging}

アプリ内メッセージは、ユーザーがモバイルアプリケーション内でアクティブになったときにメッセージを表示するためのメッセージチャネルです。このメッセージタイプは、ユーザーの電話の通知センターに配信されるプッシュ通知です。For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

このチャネルには、Adobe Experience Platform SDKと統合するためのモバイルアプリケーションが必要です。これらのアプリは、Adobe Campaignプラットフォームの起動でアクティブ化する必要があります。これは、アプリ内配信のためにAdobe Campaignで利用できます。

![](assets/launch_campaign.png)

Experience Platform SDKを使用するモバイルアプリケーションにアプリ内メッセージを送信するには、次の前提条件を満たす必要があります。

1. In Adobe Campaign, make sure you can access the **[!UICONTROL In-App]** channel. これらのチャネルにアクセスできない場合は、アカウントチームにお問い合わせください。
1. Experience Platform Launchでモバイルアプリケーションを作成し、モバイルプロパティを作成し、Experience Platform SDKを使用してモバイルアプリを計測します。

   For more information, refer to the [Set up a mobile property](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) section in Adobe Launch documentation.

1. In Experience Platform Launch, install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more on extensions, refer to the [Configure Campaign Standard Extension in Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) in Experience Platform Launch documentation.

1. In Experience Platform Launch, configure rules and data elements for your application, see [Configuring your application in Experience Platform Launch](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ConfiguringyourapplicationinLaunch)
1. Configure your Experience Platform Launch application in Adobe Campaign Standard, see [Setting up your Experience Platform Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign) .

To learn how to configure Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

**関連コンテンツ:**

* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)
* [ローカル通知メッセージタイプのカスタマイズ](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)
* [ワークフロー内でのアプリ内メッセージの送信](../../automating/using/in-app-delivery.md)
* [プッシュおよびアプリ内FAQ](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)