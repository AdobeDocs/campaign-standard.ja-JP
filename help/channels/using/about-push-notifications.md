---
title: プッシュ通知について
description: プッシュ通知チャネルの主な特性を検出します。Adobe Campaign。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8111dfd2fd3cf254f73d0b01917d606b0a70aa84

---


# プッシュ通知について{#about-push-notifications}

>[!CAUTION]
>
>プッシュ通知の実装は、エキスパートユーザーが実行する必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。プッシュ通知はオプションの機能です。 この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。

Adobe Campaignを使用すると、パーソナライズされたセグメント化されたプッシュ通知をiOSおよびAndroid携帯端末に送信できます。

これらのメッセージは、Experience Platform SDKを利用して、Adobe Campaignで設定したモバイルアプリケーションで受信されます。 詳しくは、「Adobe Experience Platform SDKを使用したモバ [イルアプリケーションの設定」を参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

このリソースは、モバイルデバイスからデバイスに送信するデータを収集するために拡張する必要があります。Adobe Campaign これを行うには、このページで詳 [細な手順](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) を参照してください。

プッシュ通知には、次の2種類がAdobe Campaignで使用できます。

* **[!UICONTROL Alert/Message/Badge]** タイプ通知を使用すると、標準のテキストベースのメッセージに追加のコンテンツ（サウンド、バッジ、ディープリンクなど）を送信できます。を定義でき **[!UICONTROL Advanced options]** ます。

   この通知タイプを使用すると、タイトルとメッセージを追加して、メッセージを使用できます。パーソナライゼーションフィールド メッセージをパーソナライズするには、テンプレートを選択していることを確認し **[!UICONTROL Send push on profiles]** てください。

* **[!UICONTROL Silent push]** タイプ通知は、エンドユーザーに対するメッセージや内容を一切通知せずに、アプリケーションに通知するために使用されます。 このタイプのメッセージの一般的な使用例は、ダウンロードするサーバー上で利用可能なコンテンツがあることをアプリケーションに知らせることです。

通知動作を定義するために、いくつかの特定の設定を設定できます。 詳しくは、[この節](../../channels/using/customizing-a-push-notification.md)を参照してください。

エキスパートユーザーは、これらの設定を定義する際に、モバイルアプリのテクノロジを参照し [てくださ](https://helpx.adobe.com/jp/campaign/kb/acs-article-list.html)い。

>[!NOTE]
>
>プライバシーに関する法律は国によって異なる。 一部の国では、モバイルアプリケーションが収集したデータの種類をユーザーに通知する必要があります。 お住まいの国のモバイルアプリに関する法律を確認してください。 モバイルアプリに送信されるプッシュ通知が、Apple(Apple Push Notification Service)およびGoogle（Google Cloud MessagingまたはFirebase Cloud Messaging）で指定された前提条件と条件に準拠していることを確認します。

**関連コンテンツ：**

* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md)
* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [Campaign Standardモバイルガイド](https://helpx.adobe.com/jp/campaign/kb/acs-mobile.html)

## 前提条件 {#prerequisites}

>[!NOTE]
>キャンペーンのプッシュ通知機能を利用するには、パスワードなしで.pem形式の有効なプッシュ証明書を指定する必要があります。
有効なp12証明書がある場合は、オンラインリソースを使用して簡単に.pemファイルに変換できます。

プッシュ通知を送信する前に、次の操作を行う必要があります。

1. Adobe Campaignで、アクセスできることを確認し **[!UICONTROL Push notification]** ます。 これらのアカウントにアクセスできない場合は、チャネルチームにお問い合わせください。

1. ユーザーがPlatform StandardおよびExperience Platform Launchで必要な権限を持っていることをAdobe Campaignに確認します。

1. エクスペリエンスプラットフォームの起動で、モバイルプロパティを作成します。 詳しくは、モバイルプロパテ [ィの設定を参照してください](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. Experience Platform Launchで、拡張機能をインストール **[!UICONTROL Adobe Campaign Standard]** します。

1. Adobe Campaign標準で、Experience Platform Launchで作成したモバイルプロパティを設定します。 詳しくは、「Experience Platform Launchアプリケ [ーションの設定」を参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)。

1. 追加チャネル固有の設定をモバイルアプリケーションの設定に適用します。 詳しくは、「アプリケーション固有の [チャネル設定」を参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

1. モバイル用途の実装をサポートするには、Adobe Experience Platform SDKを使用してAdobe Campaign標準でサポートされている拡張機能、Experience Platform Launchルール、 [MobileのSDK実装に関する詳細な手順を参照してください](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。