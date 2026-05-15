---
title: プッシュ通知について
description: Adobe Campaign 内のプッシュ通知チャネルの主な特徴について説明します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: User
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
TQID: https://experienceleague.adobe.com/xwmywhEboE06iVgZJo2DTSqg2f1F1XHEAHGKjkKoqC4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
  - id: e739ee2b-6228-412e-878f-45de0791417d
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1276
ht-degree: 37%

---

# プッシュ通知について{#about-push-notifications}

>[!CAUTION]
>
>プッシュ通知は、エキスパートユーザーによって実装される必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 プッシュ通知はオプションの機能です。 この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。

Adobe Campaign では、iOS および Android モバイルデバイスにパーソナライズおよびセグメント化されたプッシュ通知を送信できます。

これらのメッセージは、Experience Platform SDK を利用して、Adobe Campaign で設定したモバイルアプリケーションで受信されます。 詳しくは、[Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)を参照してください。

Adobe Campaign では、モバイルデバイスから送信されたモバイルプロファイル属性データは、アプリケーション購読者から収集するデータを定義できる「**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**」リソースに保存されます。

モバイルデバイスから Adobe Campaign に送信するデータを収集するには、このリソースを拡張する必要があります。 その詳しい手順については、この[ページ](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)を参照してください。

Adobe Campaign では、2 つのプッシュ通知を使用できます。

* **[!UICONTROL Alert/Message/Badge]**&#x200B;種類の通知を使用すると、追加コンテンツ（サウンド、バッジ、ディープリンクなど）を含む標準のテキストベースのメッセージを送信できます **[!UICONTROL Advanced options]** セクションで定義できます。

  この通知タイプでは、パーソナライゼーションフィールドを使用できるタイトルとメッセージを追加できます。 メッセージをパーソナライズするには、必ず **[!UICONTROL Send push on profiles]** テンプレートを選択してください。

* **[!UICONTROL Silent push]** タイプの通知は、エンドユーザーに対してメッセージやコンテンツを表示せずに、アプリケーションに通知するために使用します。 このタイプのメッセージの一般的な使用例は、ダウンロードするサーバー上のコンテンツがあることをアプリケーションに知らせることです。

一部の設定は、通知動作を定義できます。 詳しくは、[この節](../../channels/using/customizing-a-push-notification.md)を参照してください。

>[!NOTE]
>
>プライバシーに関する法律は国によって異なります。 一部の国では、モバイルアプリケーションで収集されるデータの種類をユーザーに通知する必要があります。 お住まいの国のモバイルアプリケーションに関する法律をご確認ください。 モバイルアプリケーションに送信されるプッシュ通知が、Apple（Apple Push Notification Service）および Google（Google Cloud Messaging または Firebase Cloud Messaging）で指定されている前提条件と条件に従っていることを確認します。

**関連するコンテンツ：**

* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md)
* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [Campaign Standard モバイルガイド](../../channels/using/get-started-communication-channels.md)

## 前提条件 {#prerequisites}

>[!NOTE]
>Campaignのプッシュ通知機能を活用するには、パスワードを使用せずに.pem形式で有効なプッシュ証明書を指定する必要があります。
>
>有効な p12 証明書がある場合は、オンラインリソースを使用して .pem ファイルに容易に変換できます。

プッシュ通知を送信する前に、次の操作を実行する必要があります。

1. Adobe Campaign で、**[!UICONTROL Push notification]** チャネルにアクセスできることを確認します。 これらのチャネルにアクセスできない場合は、アカウントチームにお問い合わせください。

1. Adobe Campaign Standardで必要な権限を持ち、Adobe Experience Platformでタグを付けていることを確認します。

1. データ収集UIで、モバイルプロパティを作成します。 詳しくは、[モバイルプロパティの設定](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)を参照してください。

1. データ収集UIで、**[!UICONTROL Adobe Campaign Standard]**&#x200B;拡張機能をインストールします。

1. Adobe Campaign Standardで、データ収集UIで作成したモバイルプロパティを設定します。 詳しくは、[Adobe Campaignでのタグアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)を参照してください。

1. モバイルアプリケーションの設定にチャネル固有の設定を追加します。 詳しくは、[Adobe Campaign のチャネル固有のアプリケーション設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

1. モバイルユースケースの実装をサポートするには、[Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされているモバイルユースケース &#x200B;](../../administration/using/configuring-rules-launch.md)の拡張機能、タグルール、SDKの実装に関する詳細な手順を参照してください。

## プッシュ通知に関するFAQ {#push-faq}

### プッシュチャネルの詳細を知るための有用なリソースの推奨事項は何ですか？ {#resource-push}

以下のリソースをご覧ください。

* [ビデオチュートリアル](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [製品ドキュメント](../../channels/using/about-push-notifications.md)
* AEP SDK [&#x200B; ドキュメント &#x200B;](../../administration/using/configuring-a-mobile-application.md)を使用して設定
* [コミュニティページ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Campaignでプッシュトークンを取得するにはどうすればよいですか？ {#push-token-acquisition}

プロビジョニングチームがAdobe Campaign Standardのプッシュチャネルのプロビジョニングを完了したことを確認します。 SDKからsetPushIdentifier APIを実装します。 詳しくは、この[ページ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#set-up-push-messaging)を参照してください。

### CampaignでプッシュトークンとECIDを取得したら、プッシュ通知を送信するために他に何が必要ですか？ {#sending-push}

プッシュ通知を送信するには、有効なプッシュ証明書を.pem形式で提供する必要があります。 この証明書にパスワードは必要ありません。

### .pem証明書ではなく.p12証明書を使用している場合はどうなりますか？ {#certificates}

ターミナルで次のコマンドを実行すると、.p12証明書を.pem証明書に変換できます。 コンバージョンの手順に役立つオンラインリソースもいくつかあります。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 証明書のアップロードが成功したかどうかを確認するにはどうすればよいですか？ {#certificate-upload}

次のメッセージが表示されます。

![](assets/faq_2.png)

### IOS アプリ（Androidの場合はN/A）では、実稼動証明書とサンドボックス証明書の両方を同時にアップロードできますか？ {#prod-sandbox-certificate}

いいえ、アプリはサンドボックスまたは実稼動モードで動作し、設定した後に他のサンドボックス（実稼動アプリへのサンドボックス）に変更することはできません。 最初にサンドボックスモードでアプリをテストしてから、実稼動モードに移行することをお勧めします。

実稼動モードに変更するには、別のアプリを作成する必要があります。 また、サンドボックス チェックボックスをオンにせず、実稼動証明書をアップロードしてください。

### IOSとAndroidの両方の資格情報を同時にアップロードできますか？ {#ios-android-credentials}

はい、Campaignは両方のプラットフォームを同時にサポートしており、両方のプラットフォームの資格情報をアップロードできます。

### プッシュ証明書を正常にアップロードしましたが、プッシュメッセージは送信されません。 {#push-certificates-upload}

プッシュ証明書が有効であることを確認するには、テストを行います。[こちら](https://pushtry.com/)。

### pushtry.comからプッシュ通知を正常に送信できますが、Campaignでは送信できません。 {#push-not-sending}

[こちら](../../administration/using/push-payload.md)で提供されているプッシュペイロードの手順に従っていることを確認してください。

Androidの場合、Campaignは通知ペイロードではなくデータペイロードのみをサポートします

### Adobe Campaign Standardの「管理」セクションでアプリを設定しましたが、配信プロパティでモバイルアプリを使用できません。 {#mobile-app-unavailable}

アプリの配信プロパティで有効なプッシュ証明書を使用できるようにするには、事前に有効なプッシュ証明書をアップロードする必要があります。

### このページのすべての手順を試しましたが、Campaignからプッシュを送信できません。 {#push-troubleshoot}

カスタマーケアのチケットを開いてください。

### Campaignからプッシュ通知が配信されますが、メディアファイルが表示されません。{#media-file-unavailable}

モバイルアプリ開発者は、アプリ内のメディアファイルのサポートを処理する必要があります。 ネットワーク帯域幅がメディアファイルのレンダリングを妨げる場合もあります。 追加のポインターについては、この[&#x200B; ページ &#x200B;](../../administration/using/image-push-notification.md)を参照してください。

### Campaignでプッシュレポートを有効にするには、どうすればよいですか？ {#push-reporting-enable}

以下の手順に従います。

* プッシュトラッキングのポストバックを設定します。 手順は[こちら](../../administration/using/configuring-a-mobile-application.md)にあります。
* モバイルコアからtrackAction APIを実装します。 詳しくは、この[&#x200B; ページ &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/)を参照してください。

詳細な手順については、この[&#x200B; ページ &#x200B;](../../administration/using/push-tracking.md)を参照してください。

### プッシュチャネルで使用できるレポートは？ {#push-report-available}

Adobe Campaignのプッシュ通知チャネルでは、すぐに使用できるレポートを利用できます。 この[&#x200B; ドキュメント &#x200B;](../../reporting/using/push-notification-report.md)を参照してください。

各プッシュ指標の計算方法については、この[&#x200B; ページ &#x200B;](../../reporting/using/indicator-calculation.md#push-notification-delivery)を参照してください。

### ディープリンクはプッシュおよびアプリ内メッセージでサポートされていますか？ {#deeplink-push}

はい、ディープリンクはプッシュメッセージでサポートされています。 ディープリンクには次のものが含まれます。

* ディープリンクを機能させるには、配信トラッキングを無効にする必要があることを示す言語。
* AppsflyerとBranchをパートナーとして使用して、ディープリンクの追跡を行うことができます。 分岐とAdobe Campaign Standardの統合について詳しくは、この[&#x200B; ページ &#x200B;](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)を参照してください。
