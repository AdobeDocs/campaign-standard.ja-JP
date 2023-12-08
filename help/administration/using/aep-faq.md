---
title: Adobe Experience Platform SDK とAdobe Campaignの統合に関する FAQ
description: Adobe Experience Platform SDK とAdobe Campaignの統合に関する FAQ
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 3%

---

# Experience PlatformSDK 統合 FAQ {#aep-faq}

Experience PlatformSDK アプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリケーションをAdobe Experience Platform SDK で設定し、Adobe Campaignで設定する必要があります。

以下の節では、この同期に関するよくある質問を示します。

プッシュまたはアプリ内について詳しくは、次の FAQ を参照してください。

* [プッシュ通知の FAQ](../../channels/using/about-push-notifications.md#push-faq)
* [アプリ内 FAQ](../../channels/using/in-app-faq.md)
* [Adobe Experience Platform 同期のタグに関する FAQ](../../administration/using/syncwithlaunch-faq.md)

## 開始前に役立つリソース {#resource-mobile-property}

Adobe Experience Platform SDK とCampaign Standardの統合について詳しくは、以下のリソースを参照してください。

* Launch/Mobile [概要ビデオ](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [ヒントとテクニックガイド](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK の統合は、Adobe Campaign StandardとAdobe Campaign Classicの両方で利用できますか？ {#aep-validity}

はい、 [!DNL Adobe Experience Platform SDK] 統合は、Adobe Campaign StandardとAdobe Campaign Classicの両方で使用できます。 対応する **[!UICONTROL Extension]** 経由 [!DNL Data Collection UI] をクリックして、統合を有効にします。

詳しくは、この[ページ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard)を参照してください。

## Adobe CampaignでAdobe Experience Platform SDK を統合すると、どのような機能が容易になりますか？ {#aep-capabilities}

これらの機能の詳細については、次の表を参照してください。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 統合には、places イベントがアプリ内メッセージのトリガーとして含まれます（プッシュ通知の場合はなし）。 [!DNL Places] データとローカル通知のサポート。 これを参照してください。 [ページ](../../channels/using/preparing-and-sending-an-in-app-message.md) を参照してください。 <br>[!DNL Places] 制限付き統合には、 [!DNL Places] データ。

## Adobe Campaign StandardでAdobe Experience Platform SDK を統合すると、どのようなユースケースが容易になりますか？ {#aep-use-cases}

次の使用例がサポートされます。

* の獲得 **[!UICONTROL Mobile Profile]** Campaign 内 ( **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** タブ )
* エンリッチメント： **[!UICONTROL Mobile Profile]** Adobe Campaign内 ( **[!UICONTROL Custom resource Extension]** （appSubscriberRcp テーブル）
* プッシュメッセージ送信用のプッシュトークンの取得（プッシュメッセージを受け取るにはユーザーのオプトインが必要）
* プッシュメッセージとアプリ内メッセージの送信
* プッシュメッセージおよびアプリ内メッセージを使用したユーザーのインタラクションを追跡し、それに関するレポートを提供します

## Campaign でモバイルプロファイルを取得するには、何をする必要がありますか？ {#mobile-profile-campaign}

これをおこなうには、以下の手順に従います。

1. の設定 **[!UICONTROL Mobile property]** in [!DNL Launch].
1. Adobe Campaign Standard拡張機能をインストールします。 Adobe Campaign Standard拡張機能には、 **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** および **[!UICONTROL Lifecycle]** デフォルトでインストールされる拡張機能 [!DNL Launch].
   * ユーザーは、でセッションタイムアウトを設定する必要があります。 **[!UICONTROL Mobile Core]** ライフサイクルイベントの頻度に影響する拡張機能。
   * 拡張機能が設定されたら、ユーザーは、iOS用 Cocoapods と Android 用 Gradle を使用して、モバイルアプリに適切な依存関係を追加する必要があります。 指示に従う [ここ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).
   * 常に最新バージョンのライブラリを使用してください。
   * モバイルアプリで、を登録します。 **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** および **[!UICONTROL Signal]** 拡張機能。 指示に従う [ここ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#register-the-campaign-standard-extension-with-mobile-core).
   * 拡張機能が登録されたら、ACPCore を起動します。 Android の場合は、必ず setApplication onCreate() を使用してください。 Launch のモバイルプロパティに関するモバイルインストール手順に記載されている手順に従います。
   * 以下の SDK API も必要です。 ライフサイクル開始 API と一時停止 API の実装（説明を参照） [ここ](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android) Android の場合は、ここはiOSの場合。
1. の設定 **[!UICONTROL Mobile Property]** Adobe Campaign Standardで 手順に従います。 [ここ](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Campaign でモバイルプロファイルをエンリッチメントするには、何をおこなう必要がありますか？ {#enrich-mobile-profile}

CollectPII ポストバックを設定する必要があります ( [ページ](../../administration/using/configuring-rules-launch.md#pii-postback)) を実装し、SDK から CollectPII API を実装します（これを参照）。 [ページ](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference)) をクリックします。

## CollectPII 呼び出しは、どのくらいの頻度で実行する必要がありますか？ {#collect-pii}

CollectPII 呼び出しの目的は、Campaign でモバイルプロファイルをエンリッチメントすることです。 使用例やビジネスニーズに応じて、顧客がプロファイルに追加したい新しい意味のある情報がある場合は常に実行する必要があります。

## 複数のイベントに応じて CollectPII 呼び出しを実行することはできますか。トリガー {#collect-pii-calls}

はい。ビジネスニーズに応じて、アプリ内のユーザーログに応じて、または購入、ライフサイクルイベント、またはジオフェンスに入るユーザーなどに応じて、 CollectPII 呼び出しを実行できます。 要約すると、プロファイルエンリッチメントに使用する情報を生成する、アプリとのユーザーのやり取りです。

## すべてのモバイルイベントに応じて CollectPII 呼び出しを実行できますか？ {#collect-pii-events}

CollectPII 呼び出しの頻度と設計は、ビジネスニーズに基づいて決定される必要があり、DB に余分な負荷がかかるので、盲目的に実行されるべきではありません。

### Campaign または Launch でAdobe Experience Platformアプリにアクセスしようとすると、プロパティが利用できないエラーが表示されることがあります。 {#aep-error}

これは既知の問題で、トークンの有効期限が原因で発生します。 ログインしてから、で試す必要があります。

## Adobe Experience Platform SDK（旧称 SDK V5）の詳細について学ぶための、役に立つリソース推奨事項を教えてください。{#resource-aep}

以下のリソースを確認します。

* Experience PlatformSDK [ドキュメント](https://developer.adobe.com/client-sdks/documentation/)
* Launch &amp;Experience PlatformSDK の概要 [ドキュメント](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)
* Experience PlatformSDK へのアップグレード [ドキュメント](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/)
* GithubExperience PlatformSDK [ドキュメント](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## プッシュ通知配信の作成中に、「配信に対する書き込みアクセス権がありません」というエラーが表示されます。 {#write-access-error}

次の点を確認する必要があります。

* モバイルアプリは、プッシュ配信を作成して送信する必要があるユーザーの組織単位にマッピングされる必要があります。 子の組織単位のユーザーは、親の組織単位にマッピングされたアプリを使用してプッシュ配信を作成できません。

* プッシュ配信を作成して送信する必要があるユーザーの組織単位に、プッシュ配信を作成するキャンペーンまたはプログラムをマッピングする必要があります。 子組織単位のユーザーは、親組織単位にマッピングされたキャンペーンまたはプログラムにプッシュ配信を作成できません。
