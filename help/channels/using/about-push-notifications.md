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
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 39%

---

# プッシュ通知について{#about-push-notifications}

>[!CAUTION]
>
>プッシュ通知は、エキスパートユーザーによって実装される必要があります。支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。プッシュ通知はオプションの機能です。この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。

Adobe Campaign では、iOS および Android モバイルデバイスにパーソナライズおよびセグメント化されたプッシュ通知を送信できます。

これらのメッセージは、Experience Platform SDK を利用して、Adobe Campaign で設定したモバイルアプリケーションで受信されます。詳しくは、[Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)を参照してください。

Adobe Campaign では、モバイルデバイスから送信されたモバイルプロファイル属性データは、アプリケーション購読者から収集するデータを定義できる「**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**」リソースに保存されます。

モバイルデバイスから Adobe Campaign に送信するデータを収集するには、このリソースを拡張する必要があります。その詳しい手順については、この[ページ](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)を参照してください。

Adobe Campaign では、2 つのプッシュ通知を使用できます。

* **[!UICONTROL Alert/Message/Badge]** タイプの通知を使用すると、標準のテキストベースのメッセージに追加のコンテンツ（音声、バッジ、ディープリンクなど）を添付して送信できます。これらは「**[!UICONTROL Advanced options]**」セクションで定義できます。

  この通知タイプでは、パーソナライゼーションフィールドを使用できるタイトルとメッセージを追加できます。メッセージをパーソナライズするには、必ず **[!UICONTROL Send push on profiles]** テンプレートを選択してください。

* **[!UICONTROL Silent push]** タイプの通知は、エンドユーザーに対してメッセージやコンテンツを表示せずに、アプリケーションに通知するために使用します。このタイプのメッセージの一般的な使用例は、ダウンロードするサーバー上のコンテンツがあることをアプリケーションに知らせることです。

一部の設定は、通知動作を定義できます。詳しくは、[この節](../../channels/using/customizing-a-push-notification.md)を参照してください。

>[!NOTE]
>
>プライバシーに関する法律は国によって異なります。一部の国では、モバイルアプリケーションで収集されるデータの種類をユーザーに通知する必要があります。お住まいの国のモバイルアプリケーションに関する法律をご確認ください。モバイルアプリケーションに送信されるプッシュ通知が、Apple（Apple Push Notification Service）および Google（Google Cloud Messaging または Firebase Cloud Messaging）で指定されている前提条件と条件に従っていることを確認します。

**関連するコンテンツ：**

* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md)
* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [Campaign Standardモバイルガイド](../../channels/using/get-started-communication-channels.md)

## 前提条件 {#prerequisites}

>[!NOTE]
>Campaign のプッシュ通知機能を利用するには、パスワードを指定せずに、.pem 形式の有効なプッシュ証明書を指定する必要があります。
>
>有効な p12 証明書がある場合は、オンラインリソースを使用して .pem ファイルに容易に変換できます。

プッシュ通知を送信する前に、次の操作を実行する必要があります。

1. Adobe Campaign で、**[!UICONTROL Push notification]** チャネルにアクセスできることを確認します。これらのチャネルにアクセスできない場合は、アカウントチームにお問い合わせください。

1. ユーザーがAdobe Campaign Standardで必要な権限を持っていて、Adobe Experience Platformでタグを付けていることを確認します。

1. データ収集 UI で、モバイルプロパティを作成します。 詳しくは、[モバイルプロパティの設定](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)を参照してください。

1. データ収集 UI で、 **[!UICONTROL Adobe Campaign Standard]** 拡張子。

1. Adobe Campaign Standardで、データ収集 UI で作成したモバイルプロパティを設定します。 詳しくは、 [Adobe Campaignでのタグアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. モバイルアプリケーションの設定にチャネル固有の設定を追加します。詳しくは、[Adobe Campaign のチャネル固有のアプリケーション設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

1. モバイルユースケース実装をサポートするには、拡張機能、タグルールおよび SDK 実装に関する詳細な手順 ( [Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされるモバイルの使用例](../../administration/using/configuring-rules-launch.md).

## プッシュ通知の FAQ {#push-faq}

### プッシュチャネルの詳細を確認するのに役立つリソース推奨事項は何ですか？ {#resource-push}

以下のリソースを確認します。

* [ビデオTutorials](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [製品ドキュメント](../../channels/using/about-push-notifications.md)
* AEP SDK を使用した設定 [ドキュメント](../../administration/using/configuring-a-mobile-application.md)
* [コミュニティページ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Campaign でプッシュトークンを取得するには、何をする必要がありますか？ {#push-token-acquisition}

プロビジョニングチームがAdobe Campaign Standardでプッシュチャネルのプロビジョニングを完了していることを確認します。 SDK から setPushIdentifier API を実装します。 詳しくは、この[ページ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#set-up-push-messaging)を参照してください。

### Campaign でプッシュトークンと ECID を取得したら、プッシュ通知を送信する他に必要なことは何ですか？ {#sending-push}

プッシュ通知を送信するには、.pem 形式の有効なプッシュ証明書を指定する必要があります。 この証明書のパスワードは必要ありません。

### .pem 証明書ではなく.p12 証明書がある場合はどうなりますか？ {#certificates}

ターミナルで次のコマンドを実行すると、.p12 証明書を.pem 証明書に変換できます。 変換手順には、複数のオンラインリソースも使用できます。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 証明書のアップロードが成功したかどうかを確認するには、どうすればよいですか？ {#certificate-upload}

次のメッセージが表示されます。

![](assets/faq_2.png)

### iOSアプリ（Android の場合はなし）用に、実稼動版とサンドボックスの両方の証明書を同時にアップロードできますか？ {#prod-sandbox-certificate}

いいえ。アプリは、サンドボックスモードまたは実稼動モードで動作し、設定後に他の（サンドボックスから実稼動アプリへの）変更をおこなうことはできません。 最初にサンドボックスモードでアプリをテストし、次に実稼動モードに移行することをお勧めします。

実稼動モードに変更するには、別のアプリを作成する必要があります。 また、サンドボックスのチェックボックスをオフにし、実稼動用証明書をアップロードするようにしてください。

### iOSと Android の両方の資格情報を同時にアップロードできますか？ {#ios-android-credentials}

はい、Campaign は両方のプラットフォームを同時にサポートし、両方のプラットフォームの資格情報をアップロードできます。

### プッシュ証明書は正常にアップロードされましたが、プッシュメッセージは送信されません。 {#push-certificates-upload}

プッシュ証明書をテストして、有効であることを確認してください [ここ](https://pushtry.com/).

### pushtry.comからはプッシュ通知を正常に送信できますが、Campaign 経由では送信できません。 {#push-not-sending}

指定されたプッシュペイロードの手順に従っていることを確認してください [ここ](../../administration/using/push-payload.md).

Android の場合、Campaign はデータペイロードのみをサポートし、通知ペイロードはサポートしません

### Adobe Campaign Standardの「管理」セクションでアプリを設定したのに、配信プロパティでモバイルアプリを使用できません。 {#mobile-app-unavailable}

配信プロパティで使用できるようにするには、アプリに有効なプッシュ証明書もアップロードする必要があります。

### このページのすべての手順を試行しましたが、Campaign からプッシュを送信できません。 {#push-troubleshoot}

カスタマーケアチケットを開いてください。

### プッシュ通知が Campaign から配信されますが、メディアファイルが表示されません。{#media-file-unavailable}

モバイルアプリ開発者は、アプリ内でのメディアファイルのサポートを処理する必要があります。 ネットワーク帯域幅によって、メディアファイルのレンダリングが妨げられる場合もあります。 これを参照してください。 [ページ](../../administration/using/image-push-notification.md) を参照してください。

### Campaign でプッシュレポートを有効にするには、どうすればよいですか？ {#push-reporting-enable}

以下の手順に従います。

* プッシュトラッキングポストバックを設定します。 説明が見つかります [ここ](../../administration/using/configuring-a-mobile-application.md).
* Mobile Core から trackAction API を実装します。 これを参照してください。 [ページ](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/) を参照してください。

詳しい手順については、こちらを参照してください。 [ページ](../../administration/using/push-tracking.md).

### プッシュチャネルで使用できるレポートはどれですか？ {#push-report-available}

Adobe Campaignでは、プッシュチャネル用に標準のレポートが利用できます。 これを参照してください。 [ドキュメント](../../reporting/using/push-notification-report.md).

詳しくは、 [ページ](../../reporting/using/indicator-calculation.md#push-notification-delivery) を参照して、各プッシュ指標の計算方法を理解してください。

### ディープリンクはプッシュメッセージとアプリ内メッセージでサポートされていますか？ {#deeplink-push}

はい、ディープリンクはプッシュメッセージでサポートされます。 ディープリンクには次が含まれる必要があります。

* ディープリンクを機能させるには、配信トラッキングを無効にする必要があることを示す言語。
* ディープリンクトラッキングを実行できるパートナーとして、Branch を持つ Appsflyer。 Branch とAdobe Campaign Standardの統合について詳しくは、 [ページ](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
