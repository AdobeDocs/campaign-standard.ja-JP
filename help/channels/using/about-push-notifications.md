---
title: プッシュ通知について
seo-title: プッシュ通知について
description: プッシュ通知について
seo-description: Adobe Campaignのプッシュ通知チャネルの主な特性を確認します。
page-status-flag: 非活性化の
uuid: 961aeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp，概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 96001355220a9dd0cd3851d3f7de9f4dc8ea2782

---


# プッシュ通知について{#about-push-notifications}

>[!CAUTION]
>
>プッシュ通知の実装は、エキスパートユーザーが実行する必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。プッシュ通知はオプションの機能です。 この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。

Adobe Campaignを使用すると、パーソナライズされたセグメント化されたプッシュ通知をiOSおよびAndroid携帯端末に送信できます。

これらのメッセージは、Experience Cloud Mobile SDK V4またはExperience Platform SDKを利用して、Adobe Campaignで設定したモバイルアプリケーションで受信されます。 詳しくは、SDK V4を使用したモバイルアプリケーションの設定および [Adobe Experience Platform SDKを使用したモバ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) イルアプリケーションの設定を参照してください [](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

モバイルデバイスからAdobe Campaignに送信するデータを収集するには、このリソースを拡張する必要があります。 そのためには、詳細な手順につ [いては](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) 、このページを参照してください。

Adobe Campaignでは、次の2種類のプッシュ通知を使用できます。

* **[!UICONTROL Alert/Message/Badge]** タイプ通知を使用すると、標準のテキストベースのメッセージに追加のコンテンツ（サウンド、バッジ、ディープリンクなど）を送信できます。」セクションで定義でき **[!UICONTROL Advanced options]** ます。

   この通知タイプを使用すると、タイトルとメッセージを追加して、パーソナライゼーションフィールドを使用できます。 メッセージをパーソナライズするには、テンプレートを選択していることを確認し **[!UICONTROL Send push on profiles]** ます。

* **[!UICONTROL Silent push]** タイプ通知は、エンドユーザーに対するメッセージやコンテンツを一切通知せずに、アプリケーションに通知するために使用します。 このタイプのメッセージの一般的な使用例は、ダウンロードするサーバー上で利用可能なコンテンツがあることをアプリケーションに知らせることです。

一部の特定の設定は、通知動作を定義するために設定できます。 詳しくは、[この節](../../channels/using/customizing-a-push-notification.md)を参照してください。

これらの具体的な設定を定義するには、エキスパートユーザーがモバイルアプリのテクノロジーを参照して [くださ](https://helpx.adobe.com/campaign/kb/acs-article-list.html)い。

>[!NOTE]
>
>プライバシーに関する法律は国によって異なる。 一部の国では、モバイルアプリケーションが収集したデータの種類をユーザーに通知する必要があります。 お住まいの国のモバイルアプリケーションに関する法律を確認してください。 モバイルアプリに送信されるプッシュ通知が、Apple(Apple Push Notification Service)およびGoogle（Google Cloud MessagingまたはFirebase Cloud Messaging）で指定された前提条件と条件に準拠していることを確認します。

**関連コンテンツ：**

* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md)
* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [プッシュおよびアプリ内FAQ](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## 前提条件 {#prerequisites}

>[!NOTE]
>Campaignのプッシュ通知機能を利用するには、パスワードなしで.pem形式の有効なプッシュ証明書を指定する必要があります。
有効なp12証明書がある場合は、オンラインリソースを使用して簡単に.pemファイルに変換できます。

まず、プッシュ通知の送信を開始するには、SDK V4を使用してモバイルアプリケーションを設定する必要があります。 また、Experience Platform SDKを使用してモバイルアプリケーションを設定することもできます。 詳しくは、この[ページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)を参照してください。

プッシュ通知を送信する前に、次の操作を行う必要があります。

1. Adobe Campaignでチャネルにアクセスできるこ **[!UICONTROL Mobile app]** とを確認してください。
1. モバイルアプリケーションの設定：

   * Adobe Campaign
   * Adobe Mobile Servicesインターフェイス

1. モバイルアプリケーション固有の設定を実行します。

   * Adobe Mobile Servicesインターフェイスからダウンロードした設定ファイルをモバイルアプリケーションにパッケージ化します。
   * Experience Cloud Mobile SDKをモバイルアプリケーションに統合します。

1. アプリのサブスクリプションから収集するデータを定義します。 Adobe Campaignデータベースにプロファイルを持つモバイルアプリケーションのサブスクリプションは、定義した条件に基づいて調整されます。

モバイルアプリケーションの設定後、アプリ内メッセージの準備と送信を開始できます。 詳しくは、プッシュ通知の準備 [と送信を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。
