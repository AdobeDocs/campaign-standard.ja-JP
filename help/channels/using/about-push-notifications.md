---
title: プッシュ通知について
description: Adobe Campaign内のプッシュ通知チャネルの主な特性を見つけます。
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
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 6%

---


# プッシュ通知について{#about-push-notifications}

>[!CAUTION]
>
>プッシュ通知の実装は、エキスパートユーザーが実行する必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。プッシュ通知はオプションの機能です。 この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。

Adobe Campaignを使用すると、パーソナライズされたセグメント化されたプッシュ通知をiOSおよびAndroidモバイルデバイスに送信できます。

これらのメッセージは、Experience PlatformSDKを利用してAdobe Campaignで設定したモバイルアプリケーションで受信されます。 詳しくは、Adobe Experience PlatformSDKを使用したモバイルアプリケーションの [設定を参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

モバイルデバイスからAdobe Campaignに送信するデータを収集するには、このリソースを拡張する必要があります。 これを行うには、この [ページで詳細な手順を参照してください](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) 。

Adobe Campaignでは、2種類のプッシュ通知を使用できます。

* **[!UICONTROL Alert/Message/Badge]** タイプ通知を使用すると、標準のテキストベースのメッセージに追加のコンテンツ（サウンド、バッジ、ディープリンクなど）を送信できます。 」を **[!UICONTROL Advanced options]** 選択します。

   この通知タイプでは、パーソナライゼーションフィールドを使用できるタイトルとメッセージを追加できます。 メッセージをパーソナライズするには、テンプレートを選択していることを確認し **[!UICONTROL Send push on profiles]** ます。

* **[!UICONTROL Silent push]** タイプ通知は、エンドユーザーに対して何もメッセージやコンテンツを表示せずに、アプリケーションに通知するために使用します。 このタイプのメッセージの一般的な使用例は、ダウンロードするサーバー上のコンテンツがあることをアプリケーションに知らせることです。

一部の設定は、通知動作を定義するために設定できます。 詳しくは、[この節](../../channels/using/customizing-a-push-notification.md)を参照してください。

これらの具体的な設定を定義するには、エキスパートがモバイルアプリの [テクノロジー](https://helpx.adobe.com/jp/campaign/kb/acs-article-list.html)（英語）を参照してください。

>[!NOTE]
>
>プライバシーに関する法律は国によって異なる。 一部の国では、モバイルアプリで収集されるデータの種類をユーザーに通知する必要があります。 お住まいの国のモバイルアプリケーションに関する法律を確認してください。 モバイルアプリに送信されるプッシュ通知が、Apple(Apple Push Notification Service)およびGoogle（Google Cloud MessagingまたはFirebase Cloud Messaging）で指定されている前提条件と条件に従っていることを確認します。

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

1. Adobe Campaignで、 **[!UICONTROL Push notification]** チャネルにアクセスできることを確認します。 これらのチャネルにアクセスできない場合は、アカウントチームにお問い合わせください。

1. ユーザーがAdobe Campaign StandardとExperience Platform Launchに必要な権限を持っていることを確認します。

1. Experience Platform Launchで、モバイルプロパティを作成します。 詳しくは、「モバイルプロパティの [設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)」を参照してください。

1. Experience Platform Launchで、 **[!UICONTROL Adobe Campaign Standard]** 拡張機能をインストールします。

1. Adobe Campaign Standardで、Experience Platform Launchで作成したモバイルプロパティを設定します。 詳しくは、「Adobe CampaignでのExperience Platform Launchアプリケーションの [設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)」を参照してください。

1. モバ追加イルアプリケーションの設定に対するチャネル固有の設定。 詳しくは、「Adobe Campaign [」の「](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)チャネル固有のアプリケーション設定」を参照してください。

1. モバイルユースケース実装をサポートするには、Adobe Experience PlatformSDKを使用したAdobe Campaign Standardでサポートされる [Mobileユースケースの拡張機能、Experience Platform Launchルール、SDK実装に関する詳細な手順を参照してください](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

## プッシュ通知FAQ {#push-faq}

### プッシュチャネルの詳細について、役立つリソースの推奨事項は何ですか？ {#resource-push}

以下のリソースを確認します。

* [ビデオチュートリアル](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [製品ドキュメント](../../channels/using/about-push-notifications.md)
* AEP SDKドキュメントを使用した [設定](../../administration/using/configuring-a-mobile-application.md)
* [コミュニティページ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### キャンペーンでプッシュトークンを取得するには、何をする必要がありますか。 {#push-token-acquisition}

プロビジョニングチームがAdobe Campaign Standardのプッシュチャネルのプロビジョニングを完了したことを確認します。 SDKからsetPushIdentifier APIを実装します。 詳しくは、この[ページ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging)を参照してください。

### キャンペーンでプッシュトークンとECIDを取得したら、プッシュ通知を送信する他に必要なことは何ですか。 {#sending-push}

プッシュ通知を送信するには、.pem形式の有効なプッシュ証明書を提供する必要があります。 この証明書のパスワードは必要ありません。

### .pem証明書ではなく.p12証明書を持っている場合はどうなりますか。 {#certificates}

ターミナルで次のコマンドを実行して、.p12証明書を.pem証明書に変換できます。 変換手順に関するオンラインリソースもいくつか用意されています。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 証明書のアップロードが成功したかどうかを確認する方法を教えてください。 {#certificate-upload}

次のメッセージが表示されます。

![](assets/faq_2.png)

### iOSアプリ用に実稼働版証明書とSandbox証明書の両方を同時にアップロードできますか（Android用は該当なし）? {#prod-sandbox-certificate}

いいえ。アプリはサンドボックスまたは実稼働モードで動作し、一度セットアップすると他のモード（サンドボックスから実稼動アプリへ）に変更することはできません。 最初にサンドボックスモードでアプリをテストし、次に実稼働モードにトランジションすることをお勧めします。

実稼働モードに変更するには、別のアプリを作成する必要があります。 また、「サンドボックス」チェックボックスをオフにし、実稼動用証明書をアップロードしないようにしてください。

### iOSとAndroidの両方の資格情報を同時にアップロードできますか？ {#ios-android-credentials}

はい。キャンペーンは両方のプラットフォームを同時にサポートし、両方のプラットフォームの資格情報をアップロードできます。

### プッシュ証明書は正常にアップロードされましたが、プッシュメッセージは送信されません。 {#push-certificates-upload}

プッシュ証明書が有効であることを確認するには、 [ここでテストします](https://pushtry.com/)。

### pushtry.comからプッシュ通知を正常に送信できますが、キャンペーンを通じては送信できません。 {#push-not-sending}

ここに示すプッシュペイロードの手順に従っていることを確認し [てください](../../administration/using/push-payload.md)。

Androidの場合、キャンペーンーは、通知ペイロードではなく、Dataペイロードのみをサポートします

### Adobe Campaign Standardの「管理」セクションでアプリを設定したが、配信のプロパティでモバイルアプリを使用できない。 {#mobile-app-unavailable}

配信のプロパティでアプリを有効にするには、有効なプッシュ証明書もアップロードする必要があります。

### このページのすべての手順を試したが、キャンペーンからプッシュを送信できません。 {#push-troubleshoot}

カスタマーケアチケットを開けてください。

### キャンペーンからプッシュ通知が配信されるが、メディアファイルが表示されない。{#media-file-unavailable}

モバイルアプリの開発者は、アプリ内のメディアファイルのサポートを処理する必要があります。 ネットワーク帯域幅によっては、メディアファイルのレンダリングが妨げられる場合もあります。 その他のポインタについては、この [ページ](../../administration/using/image-push-notification.md) を参照してください。

### キャンペーンでプッシュレポートを有効にするには、何をする必要がありますか？ {#push-reporting-enable}

次の手順に従います。

* プッシュ追跡ポストバックの設定を参照してください。 Instructions can be found [here](../../administration/using/configuring-a-mobile-application.md).
* Mobile CoreからtrackAction APIを実装します。 Refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) for more information.

詳細な手順については、この [ページを参照してください](../../administration/using/push-tracking.md)。

### プッシュチャネルに使用できるレポートはどれですか。 {#push-report-available}

プッシュチャネルのAdobe Campaignから、すぐに使用できるレポートを利用できます。 Refer to this [documentation](../../reporting/using/push-notification-report.md).

各プッシュ指標の計算方法について詳しくは [](../../reporting/using/indicator-calculation.md#push-notification-delivery) 、このページを参照してください。

### ディープリンクはプッシュメッセージとアプリ内メッセージでサポートされていますか？ {#deeplink-push}

はい、プッシュメッセージではディープリンクがサポートされます。 ディープリンクには次のものを含める必要があります。

* ディープリンクを機能させるために配信追跡を無効にする必要があることを示す言語。
* ディープリンクの追跡を行うパートナーとしてBranchを持つAppsflier。 ブランチとAdobe Campaign Standardの統合の詳細については、この [ページを参照してください](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。