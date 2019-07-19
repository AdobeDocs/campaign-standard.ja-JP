---
title: プッシュ通知について
seo-title: プッシュ通知について
description: プッシュ通知について
seo-description: Adobe Campaignのプッシュ通知チャネルの重要性を特定します。
page-status-flag: 常にアクティブ化されていない
uuid: 961aaeb5-6948-4fd2- b8d7- de4510c10566
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: 23b4212e- e878-4922- be20-50fb7fa88ae8
context-tags: モバイルアプリ，概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80e65c3fedc5452105c296144a683948daa69150

---


# About push notifications{#about-push-notifications}

>[!CAUTION]
>
>プッシュ通知の実装は、エキスパートユーザーが実行する必要があります。サポートを受ける必要がある場合は、アドビのアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。プッシュ通知はオプションの機能です。使用許諾契約書を確認して、アカウント担当者に連絡してアクティブにしてください。

Adobe Campaignでは、iOSおよびAndroidモバイルデバイスに、パーソナライズされたセグメント化されたプッシュ通知を送信できます。

これらのメッセージは、Experience Cloud Mobile SDK V4またはExperience Platform SDKを利用して、Adobe Campaignで設定したモバイルアプリケーションで受信されます。For more information on this, refer to [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [Configuring a mobile application using Adobe Experience Platform SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

このリソースを拡張して、モバイルデバイスからAdobe Campaignに送信するデータを収集する必要があります。To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

Adobe Campaignでは、2種類のプッシュ通知を使用できます。

* **[!UICONTROL Alert/Message/Badge]** タイプ通知を使用すると、標準的なテキストベースのメッセージを追加のコンテンツ（サウンド、バッジ、ディープリンクなど）と共に送信できます。that you can define in the **[!UICONTROL Advanced options]** section.

   この通知タイプを使用すると、パーソナライゼーションフィールドを使用できるタイトルとメッセージを追加できます。To be able to personalize your message, make sure you select the **[!UICONTROL Send push on profiles]** template.

* **[!UICONTROL Silent push]** タイプ通知を使用して、エンドユーザーのメッセージやコンテンツを一切使用せずにアプリケーションに通知します。このタイプのメッセージの一般的な使用例は、ダウンロードするサーバー上で利用可能なコンテンツがあることをアプリケーションに認識することです。

特定の設定によって、通知の動作を定義することができます。For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

As an expert user, to define these specific configurations, refer to the mobile app [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>プライバシーに関する法律は、国によって異なります。国によっては、モバイルアプリケーションによって収集されたデータのタイプをユーザーに通知する必要があります。国内のモバイルアプリケーションに関する法律を確認してください。モバイルアプリケーションに送信されるプッシュ通知は、Apple（Apple Push Notification Service）およびGoogle（Google Cloud MessagingまたはFirebase Cloud Messaging）によって指定された前提条件と条件に準拠していることを確認してください。

**関連コンテンツ:**

* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
* [プッシュおよびアプリ内FAQ](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Prerequisites {#prerequisites}

>[!NOTE]
>Campaignのプッシュ通知機能を利用するには、パスワードを使用しないで有効なプッシュ証明書を. pem形式で提供する必要があります。
有効なp12証明書がある場合は、オンラインリソースを使用して簡単に. pemファイルに変換できます。

まず、プッシュ通知の送信を開始できるようにするには、SDK V4を使用してモバイルアプリケーションを設定する必要があります。エクスペリエンスプラットフォームSDKを使用してモバイルアプリケーションを設定することもできます。For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

プッシュ通知を送信する前に、以下の事項に注意してください。

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. 次の場所でモバイルアプリケーションを設定します。

   * Adobe Campaign
   * Adobe Mobile Servicesインターフェイス

1. モバイルアプリケーションの具体的な設定を実行します。

   * Adobe Mobile Servicesインターフェイスからダウンロードした設定ファイルをモバイルアプリケーションにパッケージ化します。
   * Experience Cloud Mobile SDKをモバイルアプリケーションに統合します。

1. アプリケーションのサブスクライバーから収集するデータを定義します。Adobe Campaignデータベース内のプロファイルを持つモバイルアプリの購読者は、定義した条件に基づいて調整されます。

モバイルアプリケーションの設定後、アプリ内メッセージの準備と送信を開始できるようになりました。For more on this, refer to [Preparing and sending a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).
