---
title: Adobe Experience Platform SDK とAdobe Campaignの統合に関する FAQ
description: Adobe Experience Platform SDK とAdobe Campaignの統合に関する FAQ
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 4%

---

# Experience Platform SDK 統合に関する FAQ {#aep-faq}

Experience PlatformSDK アプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリケーションをAdobe Experience Platform SDK で設定し、Adobe Campaignで設定する必要があります。

以下の節では、この同期に関するよくある質問を示します。

プッシュまたはアプリ内について詳しくは、次の FAQ を参照してください。

* [プッシュ通知の FAQ](../../channels/using/about-push-notifications.md#push-faq)
* [アプリ内 FAQ](../../channels/using/in-app-faq.md)
* [Launch と同期テクニカルワークフローの FAQ](../../administration/using/syncwithlaunch-faq.md)

## 開始前に役立つリソース {#resource-mobile-property}

Adobe Experience Platform SDK とCampaign Standardの統合について詳しくは、以下のリソースを参照してください。

* Launch/Mobile [ 概要ビデオ ](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [ ヒントとテクニックガイド ](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK の統合は、Adobe Campaign StandardとAdobe Campaign Classicの両方で利用できますか。 {#aep-validity}

はい、[!DNL Adobe Experience Platform SDK] 統合はAdobe Campaign StandardとAdobe Campaign Classicの両方で利用できます。 統合を有効にするには、対応する **[!UICONTROL Extension]** を [!DNL Adobe Launch] 経由でインストールする必要があります。

詳しくは、この[ページ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)を参照してください。

## Adobe Campaignでは、Adobe Experience Platform SDK を統合するとどのような機能が容易になりますか？ {#aep-capabilities}

これらの機能の詳細については、次の表を参照してください。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 統合には、places イベントがアプリ内メッセージのトリガーとして含まれます（プッシュ通知の場合は該当なし）。データとローカル通知のサポートを使用し [!DNL Places] てプロファイルを強化します。詳しくは、この [ ページ ](../../channels/using/preparing-and-sending-an-in-app-message.md) を参照してください。 <br>[!DNL Places] 制限付きの統合には、データを使用したプロファイルのエンリッチメント [!DNL Places] が含まれます。

## Adobe Campaign StandardでAdobe Experience Platform SDK の統合が容易になるユースケースを教えてください。 {#aep-use-cases}

次の使用例がサポートされています。

* Campaign で **[!UICONTROL Mobile Profile]** を取得します（ECID によって **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** タブで識別されます）。
* Adobe Campaignで **[!UICONTROL Mobile Profile]** をエンリッチメントする（appSubscriberRcp テーブルの **[!UICONTROL Custom resource Extension]** が必要）
* プッシュメッセージを送信するためのプッシュトークンの取得（プッシュメッセージを受け取るにはユーザーのオプトインが必要）
* プッシュメッセージとアプリ内メッセージの送信
* プッシュメッセージおよびアプリ内メッセージを使用したユーザーのインタラクションを追跡し、それに関するレポートを提供する

## Campaign でモバイルプロファイルを取得するには、何をする必要がありますか？ {#mobile-profile-campaign}

これをおこなうには、以下の手順に従います。

1. [!DNL Launch] で **[!UICONTROL Mobile property]** を設定します。
1. Adobe Campaign Standard拡張機能をインストールします。 Adobe Campaign Standard拡張機能には **[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]** および **[!UICONTROL Lifecycle]** 拡張機能も必要です。これらの拡張機能は、デフォルトで [!DNL Launch] にインストールされます。
   * ユーザーは、ライフサイクルイベントの頻度に影響する **[!UICONTROL Mobile Core]** 拡張でセッションタイムアウトを設定する必要があります。
   * 拡張機能が設定されたら、ユーザーは、iOS 用 Cocoapods 、Android 用 Gradle を使用してモバイルアプリに適切な依存関係を追加する必要があります。 [ こちら ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) の指示に従います。
   * 常に最新バージョンのライブラリを使用してください。
   * モバイルアプリで、**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]** および **[!UICONTROL Signal]** 拡張機能を登録します。 [ こちら ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core) の指示に従います。
   * 拡張機能が登録されたら、ACPCore を起動します。 Android の場合は、必ず setApplication onCreate() を使用します。 Launch のモバイルプロパティに関する「モバイルインストール手順」に記載されている手順に従います。
   * 以下の SDK API も必要です。 Android の場合は [ ここ ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)、iOS の場合はここで説明するように、ライフサイクル開始および一時停止 API を実装します。
1. Adobe Campaign Standardで **[!UICONTROL Mobile Property]** を設定します。 [ ここ ](../../administration/using/configuring-a-mobile-application.md#channel-specific-config) の手順に従います。

## モバイルプロファイルを Campaign にエンリッチメントするには、どうすればよいですか？ {#enrich-mobile-profile}

CollectPII ポストバックを設定し（この [ ページ ](../../administration/using/configuring-rules-launch.md#pii-postback) を参照）、SDK から CollectPII API を実装する必要があります（この [ ページ ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii) を参照）。

## CollectPII 呼び出しは、どのくらいの頻度で実行する必要がありますか？ {#collect-pii}

CollectPII 呼び出しの目的は、Campaign でモバイルプロファイルを強化することです。 ユースケースやビジネスニーズに応じて、顧客がプロファイルに追加したい新しい意味のある情報がある場合は常に実行します。

## 複数のイベントに応じて CollectPII 呼び出しを実行することはできますか？トリガー {#collect-pii-calls}

はい。ビジネスニーズに応じて、アプリ内でのユーザーログの記録、またはジオフェンスの入力など、何か、ライフサイクルイベント、ユーザーの購入に応じて CollectPII 呼び出しを実行できます。 要約すると、プロファイルのエンリッチメントに使用する情報を生成する、アプリとのユーザーのやり取りです。

## すべてのモバイルイベントに応じて CollectPII 呼び出しを実行できますか？ {#collect-pii-events}

CollectPII 呼び出しの頻度と設計は、ビジネスニーズに左右される必要があり、DB に余分な負荷がかかるので、盲目的に実行すべきではありません。

### Campaign または Launch でAdobe Experience Platformアプリにアクセスしようとすると、プロパティが利用できないエラーが表示されることがあります。 {#aep-error}

これは既知の問題で、トークンの有効期限が原因で発生します。 ログインしてから、で試す必要があります。

## Adobe Experience Platform SDK（旧称 SDK V5）の詳細を確認するために役立つリソース推奨事項を教えてください。{#resource-aep}

以下のリソースを確認します。

* Experience PlatformSDK [ ドキュメント ](https://aep-sdks.gitbook.io/docs/)
* Launch およびExperience PlatformSDK の概要 [ ドキュメント ](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Experience PlatformSDK へのアップグレード [ ドキュメント ](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GitHubExperience PlatformSDK [ ドキュメント ](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## プッシュ通知配信の作成時に「配信時に書き込みアクセス権がありません」というエラーが表示されます。 {#write-access-error}

次の点を確認する必要があります。

* プッシュ配信を作成して送信する必要があるユーザーの組織単位に、モバイルアプリをマッピングする必要があります。 子組織単位のユーザーは、親組織単位にマッピングされたアプリを使用してプッシュ配信を作成できません。

* プッシュ配信を作成するキャンペーンまたはプログラムは、プッシュ配信を作成して送信する必要があるユーザーの組織単位にマッピングする必要があります。 子組織単位のユーザーは、親組織単位にマッピングされたキャンペーンまたはプログラムにプッシュ配信を作成できません。
