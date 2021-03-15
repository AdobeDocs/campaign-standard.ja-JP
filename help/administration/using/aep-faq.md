---
solution: Campaign Standard
product: campaign
title: Adobe Experience PlatformSDKとAdobe Campaign統合FAQ
description: Adobe Experience PlatformSDKとAdobe Campaign統合FAQ
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: インスタンス設定
role: 管理者
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 4%

---


# Experience Platform SDK 統合 FAQ {#aep-faq}

Experience PlatformSDKアプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリをAdobe Experience PlatformSDKで設定し、Adobe Campaignで設定する必要があります。

以下の節では、この同期に関してよくある質問をリストします。

プッシュまたはアプリ内について詳しくは、次のFAQを参照してください。

* [プッシュ通知FAQ](../../channels/using/about-push-notifications.md#push-faq)
* [アプリ内FAQ](../../channels/using/about-in-app-messaging.md#in-app-faq)
* [起動の技術的なワークフローと同期FAQ](../../administration/using/syncwithlaunch-faq.md)

## {#resource-mobile-property}を起動する前に役立つリソース

Adobe Experience PlatformSDKとCampaign Standardの統合について詳しくは、以下のリソースを参照してください。

* 起動/モバイル[概要ビデオ](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [ヒントとテクニックガイド](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience PlatformSDKの統合は、Adobe Campaign StandardとAdobe Campaign Classicの両方で利用できますか？{#aep-validity}

はい、[!DNL Adobe Experience Platform SDK]統合はAdobe Campaign StandardとAdobe Campaign Classicの両方で利用できます。 統合を有効にするには、対応する&#x200B;**[!UICONTROL Extension]**&#x200B;を[!DNL Adobe Launch]経由でインストールする必要があります。

詳しくは、この[ページ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)を参照してください。

## Adobe Experience PlatformSDKを統合すると、どのような機能がAdobe Campaignを容易にしますか？{#aep-capabilities}

これらの機能の詳細については、次の表を参照してください。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 統合には、アプリ内メッセージのトリガーとして場所イベントが含まれます（プッシュ通知の場合は該当なし）。 [!DNL Places] データとローカル通知のサポートによってプロファイルが強化されます。詳細は、この[ページ](../../channels/using/preparing-and-sending-an-in-app-message.md)を参照してください。 <br>[!DNL Places] 制限付き統合には、 [!DNL Places] データをプロファイルに富化する機能が含まれます。

## Adobe Campaign StandardでのAdobe Experience PlatformSDKの統合が容易になる使用例を教えてください。{#aep-use-cases}

次の使用例がサポートされています。

* キャンペーン内の&#x200B;**[!UICONTROL Mobile Profile]**&#x200B;を取得（**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]**&#x200B;タブのECIDで識別）
* Adobe Campaignに&#x200B;**[!UICONTROL Mobile Profile]**&#x200B;をエンリッチ（appSubscriberRcpテーブルの&#x200B;**[!UICONTROL Custom resource Extension]**&#x200B;が必要）
* プッシュメッセージを送信するためのプッシュトークンの取得（プッシュメッセージを受信するには、ユーザーのオプトインが必要）
* プッシュメッセージとアプリ内メッセージの送信
* プッシュメッセージおよびアプリ内メッセージに対するユーザーのインタラクションを追跡し、それに関するレポートを提供します

## キャンペーンでモバイルプロファイルを取得するには、何をする必要がありますか？{#mobile-profile-campaign}

これをおこなうには、以下の手順に従います。

1. [!DNL Launch]で&#x200B;**[!UICONTROL Mobile property]**&#x200B;を設定します。
1. Adobe Campaign Standard拡張機能をインストールします。 Adobe Campaign Standardの拡張機能には、**[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]**、**[!UICONTROL Lifecycle]**&#x200B;拡張機能も必要です。拡張機能は、デフォルトで[!DNL Launch]にインストールされます。
   * ライフサイクルイベントの頻度に影響する&#x200B;**[!UICONTROL Mobile Core]**&#x200B;拡張で、セッションタイムアウトを設定する必要があります。
   * 拡張機能を設定したら、iOS用のCocopodsとAndroid用のGradleを使用して、モバイルアプリに適切な依存関係を追加する必要があります。 [ここ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)の指示に従ってください。
   * 常に最新バージョンのライブラリを使用してください。
   * モバイルアプリで、**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]**、**[!UICONTROL Signal]**&#x200B;拡張子を登録します。 [ここ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)の指示に従ってください。
   * 拡張機能が登録されると、開始ACPCoreが起動します。 Androidの場合は、setApplication onCreate()を必ず指定します。 「起動」の「モバイルプロパティのモバイルインストール手順」に記載されている手順に従います。
   * 以下のSDK APIも必要です。 ライフサイクル開始および一時停止APIを実装します。説明に従って、[ここ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)（Androidの場合）および（iOSの場合）を参照してください。
1. Adobe Campaign Standardで&#x200B;**[!UICONTROL Mobile Property]**&#x200B;を設定します。 [ここ](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)の手順に従います。

## モバイルプロファイルをキャンペーンに拡張するには、何をする必要がありますか？{#enrich-mobile-profile}

CollectPIIポストバックを設定し（[page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)を参照）、SDKからCollectPII APIを実装する必要があります（この[page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)を参照）。

## CollectPII呼び出しを呼び出す頻度はどのくらいですか。{#collect-pii}

CollectPII呼び出しの目的は、モバイルプロファイルをキャンペーンに拡張することです。 使用事例やビジネスニーズに応じて、お客様がプロファイルに追加したいと思う新しい意味のある情報がある場合は必ず発行してください。

## 複数のトリガーイベントに応答してCollectPII呼び出しを実行できますか。{#collect-pii-calls}

はい。ビジネスのニーズに応じて、アプリ内のユーザーログに応じて、または何か、ライフサイクルイベントを購入したり、ジオフェンスに入るユーザーに応じて、CollectPII呼び出しを実行できます。 要約すると、プロファイルのエンリッチメントに使用したい情報を生成するアプリとのユーザーの対話です。

## すべてのモバイルイベントに対してCollectPII呼び出しを実行できますか。{#collect-pii-events}

CollectPII呼び出しの頻度と設計は、ビジネスニーズに応じて決定される必要があり、DBに余分な負荷が発生するので、計画的に実行する必要はありません。

### キャンペーンまたは起動でAdobe Experience Platformアプリにアクセスしようとすると、プロパティが利用できないというエラーが表示されることがあります。{#aep-error}

これは既知の問題で、トークンの有効期限が切れたために発生します。 ログアウトしてから、ログインしてみてください。

## Adobe Experience PlatformSDK（旧称SDK V5）の詳細を知るために役立つリソースの推奨事項は何ですか？{#resource-aep}

以下のリソースを確認します。

* Experience PlatformSDK [ドキュメント](https://aep-sdks.gitbook.io/docs/)
* 起動とExperience PlatformSDKの使用の手引き[ドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Experience PlatformSDK [ドキュメント](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)へのアップグレード
* GithubExperience PlatformSDK [ドキュメント](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## プッシュ通知配信の作成中に、「配信への書き込みアクセス権がありません」というエラーが表示されます。{#write-access-error}

次の項目を確認する必要があります。

* プッシュ配信を作成して送信する必要があるユーザーの組織単位にモバイルアプリをマッピングする必要があります。 子の組織単位のユーザーは、親の組織単位にマッピングされたアプリを使用してプッシュ配信を作成できません。

* プッシュ配信が作成されるキャンペーンまたはプログラムは、プッシュ配信を作成して送信する必要があるユーザーの組織単位にマップする必要があります。 子組織単位のユーザーは、親組織単位にマップされたキャンペーンまたはプログラムにプッシュ配信を作成できません。