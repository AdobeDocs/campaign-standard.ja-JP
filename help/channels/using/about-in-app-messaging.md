---
title: アプリ内メッセージについて
description: アプリ内メッセージを使用して、モバイルアプリ内でメッセージまたは警告を表示します。
page-status-flag: never-activated
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: delivery,triggers,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 501ba6f97a86076116d4d84f43df674536e12f6a

---


# アプリ内メッセージについて{#about-in-app-messaging}

アプリ内メッセージは、モバイルアプリ内でユーザーがアクティブな場合にメッセージを表示できるメッセージングチャネルです。 このメッセージタイプは、ユーザーの電話の通知センターに配信されるプッシュ通知を優先します。 For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

このチャネルを使用するには、モバイルアプリケーションがAdobe Experience Platform SDKと統合されている必要があります。 これらのアプリは、Adobe Campaignでアプリ内配信用に使用する前に、Adobe Experience Platform Launchでアクティベートする必要があります。

![](assets/launch_campaign.png)

Experience Platform SDKを利用したモバイルアプリケーションでアプリ内メッセージの送信を開始するには、次の前提条件を満たす必要があります。

1. Adobe Campaignで、チャネルにアクセスできることを確認し **[!UICONTROL In-App]**ます。 これらのチャネルにアクセスできない場合は、アカウントチームにお問い合わせください。

1. Experience Cloud SDKアプリケーションでAdobe Campaign Standardのモバイル使用例を活用するには、モバイルアプリをAdobe Experience Platform Launchで作成し、Adobe Campaign Standardで設定する必要があります。 詳細手順については、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

1. 設定が完了すると、アプリ内メッセージを準備できるようになります。 詳しくは、この[ページ](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message)を参照してください。

1. その後、アプリ内メッセージを送信するか、 [ローカル通知メッセージの](../../channels/using/customizing-an-in-app-message.md) 種類 [をカスタマイズするかを決定できます](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. これで、配信を送信する準備が整いました。 詳しくは、このページを参照してく [ださい](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**関連コンテンツ：**

* [アプリ内レポート](../../reporting/using/in-app-report.md)
* [プッシュおよびアプリ内FAQ](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Adobe Campaign Standardでサポートされるモバイルの使用例](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
* [キャンペーン標準モバイルガイド](https://helpx.adobe.com/campaign/kb/acs-mobile.html)
