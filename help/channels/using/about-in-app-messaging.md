---
title: アプリ内メッセージについて
seo-title: アプリ内メッセージについて
description: アプリ内メッセージについて
seo-description: アプリ内メッセージを使用して、モバイルアプリ内でメッセージまたは警告を表示します。
page-status-flag: 非活性化の
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: アプリ内メッセージ
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: 配信，トリガー，戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 96001355220a9dd0cd3851d3f7de9f4dc8ea2782

---


# アプリ内メッセージについて{#about-in-app-messaging}

アプリ内メッセージは、モバイルアプリ内でユーザーがアクティブな場合にメッセージを表示できるメッセージングチャネルです。 このメッセージタイプは、ユーザーの電話の通知センターに配信されるプッシュ通知を優先します。 For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

このチャネルを使用するには、モバイルアプリケーションがAdobe Experience Platform SDKと統合されている必要があります。 これらのアプリは、Adobe Campaignでアプリ内配信用に使用する前に、Adobe Experience Platform Launchでアクティベートする必要があります。

![](assets/launch_campaign.png)

Experience Platform SDKを利用したモバイルアプリケーションでアプリ内メッセージの送信を開始するには、次の前提条件を満たす必要があります。

1. Adobe Campaignで、チャネルにアクセスできることを確認し **[!UICONTROL In-App]** ます。 これらのチャネルにアクセスできない場合は、アカウントチームにお問い合わせください。

1. Experience Cloud SDKアプリケーションでAdobe Campaign Standardのモバイル使用例を活用するには、モバイルアプリをAdobe Experience Platform Launchで作成し、Adobe Campaign Standardで設定する必要があります。 詳細手順については、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

1. 設定が完了すると、アプリ内メッセージを準備できるようになります。 詳しくは、この[ページ](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message)を参照してください。

1. その後、アプリ内メッセージを送信するか、 [ローカル通知メッセージの](../../channels/using/customizing-an-in-app-message.md) 種類 [をカスタマイズするかを決定できます](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. これで、配信を送信する準備が整いました。 詳しくは、このページを参照してく [ださい](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**関連コンテンツ：**

* [アプリ内レポート](../../reporting/using/in-app-report.md)
* [プッシュおよびアプリ内FAQ](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Adobe Campaign Standardでサポートされるモバイルの使用例](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
