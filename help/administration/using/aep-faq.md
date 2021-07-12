---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform SDKとAdobe Campaignの統合に関するFAQ
description: Adobe Experience Platform SDKとAdobe Campaignの統合に関するFAQ
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: インスタンス設定
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 4%

---

# Experience Platform SDK 統合に関する FAQ {#aep-faq}

Experience PlatformSDKアプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリケーションをAdobe Experience Platform SDKで設定し、Adobe Campaignで設定する必要があります。

以下の節では、この同期に関するよくある質問を示します。

プッシュまたはアプリ内について詳しくは、次のFAQを参照してください。

* [プッシュ通知のFAQ](../../channels/using/about-push-notifications.md#push-faq)
* [アプリ内FAQ](../../channels/using/in-app-faq.md)
* [Launchテクニカルワークフローと同期のFAQ](../../administration/using/syncwithlaunch-faq.md)

## 開始前に役立つリソース {#resource-mobile-property}

Adobe Experience Platform SDKとCampaign Standardの統合について詳しくは、以下のリソースを参照してください。

* Launch/Mobile [概要ビデオ](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [ヒントとテクニックガイド](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDKの統合は、Adobe Campaign StandardとAdobe Campaign Classicの両方で利用できますか？ {#aep-validity}

はい、[!DNL Adobe Experience Platform SDK]統合はAdobe Campaign StandardとAdobe Campaign Classicの両方で利用できます。 統合を有効にするには、対応する&#x200B;**[!UICONTROL Extension]**&#x200B;を[!DNL Adobe Launch]経由でインストールする必要があります。

詳しくは、この[ページ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)を参照してください。

## Adobe CampaignでAdobe Experience Platform SDKを統合すると、どのような機能が容易になりますか？ {#aep-capabilities}

これらの機能の詳細については、次の表を参照してください。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 統合には、placesイベントがアプリ内メッセージのトリガーとして含まれます（プッシュ通知の場合は該当なし）。また、データとローカル通知のサポートを使用してプロファ [!DNL Places] イルを強化します。詳しくは、この[ページ](../../channels/using/preparing-and-sending-an-in-app-message.md)を参照してください。 <br>[!DNL Places] 制限付きの統合には、データを使用したプロファイルのエンリッチメントが [!DNL Places] 含まれます。

## Adobe Campaign StandardでAdobe Experience Platform SDKの統合が容易になる使用例を教えてください。 {#aep-use-cases}

次の使用例がサポートされています。

* キャンペーンの&#x200B;**[!UICONTROL Mobile Profile]**&#x200B;を取得する（**[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Mobile app (AEP SDK)]** / **[!UICONTROL Mobile Application subscribers]**&#x200B;タブのECIDで識別）
* Adobe Campaignで&#x200B;**[!UICONTROL Mobile Profile]**&#x200B;をエンリッチメントする（appSubscriberRcpテーブルの&#x200B;**[!UICONTROL Custom resource Extension]**&#x200B;が必要）
* プッシュメッセージを送信するためのプッシュトークンの取得（プッシュメッセージを受け取るにはユーザーのオプトインが必要）
* プッシュメッセージとアプリ内メッセージの送信
* プッシュメッセージおよびアプリ内メッセージを使用したユーザーのインタラクションを追跡し、それに関するレポートを提供する

## Campaignのモバイルプロファイルを取得するには、何をする必要がありますか？ {#mobile-profile-campaign}

これをおこなうには、以下の手順に従います。

1. [!DNL Launch]で&#x200B;**[!UICONTROL Mobile property]**&#x200B;を設定します。
1. Adobe Campaign Standard拡張機能をインストールします。 Adobe Campaign Standard拡張機能には、**[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]**&#x200B;および&#x200B;**[!UICONTROL Lifecycle]**&#x200B;拡張機能も必要です。拡張機能は、デフォルトで[!DNL Launch]にインストールされます。
   * ユーザーは、ライフサイクルイベントの頻度に影響する&#x200B;**[!UICONTROL Mobile Core]**&#x200B;拡張機能でセッションタイムアウトを設定する必要があります。
   * 拡張機能が設定されたら、ユーザーは、iOS用Cocoapods、Android用Gradleを使用してモバイルアプリに適切な依存関係を追加する必要があります。 [ここ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)の指示に従います。
   * 常に最新バージョンのライブラリを使用してください。
   * モバイルアプリで、**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]**&#x200B;および&#x200B;**[!UICONTROL Signal]**&#x200B;拡張機能を登録します。 [ここ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)の指示に従います。
   * 拡張機能が登録されたら、ACPCoreを起動します。 Androidの場合は、必ずsetApplication onCreate()を使用してください。 Launchのモバイルプロパティに関するモバイルインストール手順に記載されている手順に従います。
   * 以下のSDK APIも必要です。 Androidの場合は[ここ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)、iOSの場合はここで説明したように、ライフサイクル開始および一時停止APIを実装します。
1. Adobe Campaign Standardで&#x200B;**[!UICONTROL Mobile Property]**&#x200B;を設定します。 [ここ](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)の手順に従います。

## モバイルプロファイルをCampaignにエンリッチメントするには、どうすればよいですか？ {#enrich-mobile-profile}

CollectPIIポストバックを設定し（この[ページ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)を参照）、SDKからCollectPII APIを実装する必要があります（この[ページ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)を参照）。

## CollectPII呼び出しを実行する頻度はどのくらいですか？ {#collect-pii}

CollectPII呼び出しの目的は、Campaignでモバイルプロファイルをエンリッチメントすることです。 ユースケースやビジネスニーズに応じて、顧客がプロファイルに追加したい新しい意味のある情報がある場合は常に実行する必要があります。

## 複数のイベントに応じてCollectPII呼び出しを実行することはできますか？トリガー {#collect-pii-calls}

はい。ビジネスニーズに応じて、アプリ内でのユーザーログに応じてCollectPII呼び出しを実行したり、ジオフェンスに入る何か、ライフサイクルイベント、ユーザーの購入などをおこなったりできます。 要約すると、プロファイルエンリッチメントに使用する情報を生成する、アプリとのユーザーのやり取りです。

## すべてのモバイルイベントに応じてCollectPII呼び出しを実行できますか？ {#collect-pii-events}

CollectPII呼び出しの頻度とデザインは、ビジネスニーズに基づいて決定される必要があり、DBに余分な負荷がかかるので、盲目的に実行すべきではありません。

### CampaignまたはLaunchのAdobe Experience Platformアプリにアクセスしようとすると、プロパティが利用できないエラーが表示されることがあります。 {#aep-error}

これは既知の問題で、トークンの有効期限が原因で発生します。 ログインしてから、で試す必要があります。

## Adobe Experience Platform SDK（旧称SDK V5）の詳細を確認するために役立つリソース推奨事項を教えてください。{#resource-aep}

以下のリソースを確認します。

* Experience PlatformSDK [ドキュメント](https://aep-sdks.gitbook.io/docs/)
* LaunchおよびExperience PlatformSDKの概要[ドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Experience PlatformSDKへのアップグレード[ドキュメント](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GitHubExperience PlatformSDK [documentation](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## プッシュ通知配信を作成する際に、「配信の書き込みアクセス権がありません」というエラーが表示されます。 {#write-access-error}

次の点を確認する必要があります。

* プッシュ配信を作成して送信する必要があるユーザーの組織単位に、モバイルアプリをマッピングする必要があります。 子組織単位のユーザーは、親組織単位にマッピングされたアプリを使用してプッシュ配信を作成できません。

* プッシュ配信を作成して送信する必要があるユーザーの組織単位に、プッシュ配信が作成されるキャンペーンまたはプログラムをマッピングする必要があります。 子組織単位のユーザーは、親組織単位にマッピングされたキャンペーンまたはプログラムにプッシュ配信を作成できません。
