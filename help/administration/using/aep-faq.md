---
title: Adobe Experience Platform SDKとAdobe Campaignの統合に関する FAQ
description: Adobe Experience Platform SDKとAdobe Campaignの統合に関する FAQ
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 2f3a0f4233df2915c5b7d293452246c688d69228
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 3%

---

# Experience PlatformのSDK統合に関するよくある質問 {#aep-faq}

Experience Platform SDK アプリケーションでプッシュ通知およびアプリ内メッセージを送信するには、Adobe Experience Platform SDKでモバイルアプリケーションを設定し、Adobe Campaignで設定する必要があります。

以下のセクションでは、この同期に関するよくある質問を示しています。

プッシュまたはアプリ内について詳しくは、次の FAQ を参照してください。

* [プッシュ通知の FAQ](../../channels/using/about-push-notifications.md#push-faq)
* [アプリ内 FAQ](../../channels/using/in-app-faq.md)
* [Adobe Experience Platform 同期のタグに関する FAQ](../../administration/using/syncwithlaunch-faq.md)

## 開始する前に役立つリソース {#resource-mobile-property}

Adobe Experience Platform SDKとCampaign Standardの統合について詳しくは、次のリソースを参照してください。

* Launch/Mobile[ 概要ビデオ ](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video){target="_blank"}
* Launch/Mobile[ ヒントとコツのガイド ](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK統合は、Adobe Campaign StandardとAdobe Campaign Classicの両方で利用できますか？ {#aep-validity}

はい、[!DNL Adobe Experience Platform SDK] 統合はAdobe Campaign StandardとAdobe Campaign Classicの両方で利用できます。 統合を有効にするには、[!DNL Data Collection UI] を介して対応する **[!UICONTROL Extension]** をインストールする必要があります。

詳しくは、こちらの[ページ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard){target="_blank"}を参照してください。

## Adobe Experience Platform SDK統合は、Adobe Campaignでどのような機能を促進しますか？ {#aep-capabilities}

これらの機能について詳しくは、次の表を参照してください。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] の統合には、アプリ内メッセージのトリガーとしての places イベント（プッシュ通知の場合は該当なし）、[!DNL Places] データとローカル通知のサポートによるプロファイルの強化が含まれます。 詳しくは、この [ ページ ](../../channels/using/preparing-and-sending-an-in-app-message.md) を参照してください。 限定的な統合 <br>[!DNL Places] は、[!DNL Places] データを使用したプロファイルのエンリッチメントが含まれます。

## Adobe Experience Platform SDK統合によりAdobe Campaign Standardで容易になるユースケースは何ですか？ {#aep-use-cases}

次のユースケースがサポートされています。

* Campaign での **[!UICONTROL Mobile Profile]** の取得（**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (AEP SDK)]**/**[!UICONTROL Mobile Application subscribers]** タブの ECID で識別）
* Adobe Campaignでの **[!UICONTROL Mobile Profile]** のエンリッチメント （appSubscriberRcp テーブルの **[!UICONTROL Custom resource Extension]** が必要）
* プッシュメッセージを送信するためのプッシュトークンを取得します（プッシュメッセージを受信するにはユーザーのオプトインが必要です）。
* プッシュおよびアプリ内メッセージの送信
* ユーザーのプッシュメッセージおよびアプリ内メッセージのインタラクションを追跡し、それに関するレポートを提供します

## Campaign でモバイルプロファイルを取得するにはどうすればよいですか？ {#mobile-profile-campaign}

これをおこなうには、以下の手順に従います。

1. [!DNL Launch] で **[!UICONTROL Mobile property]** を設定します。
1. Adobe Campaign Standard拡張機能をインストールします。 なお、Adobe Campaign Standard拡張機能には、[!DNL Launch] にデフォルトでインストールされる **[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]** および **[!UICONTROL Lifecycle]** 拡張機能も必要です。
   * ライフサイクルイベントの頻度に影響 **[!UICONTROL Mobile Core]** 与えるセッションタイムアウトを拡張機能で設定する必要があります。
   * 拡張機能を設定したら、Cocoapods for iOSと Gradle for Androidを使用して、モバイルアプリに適切な依存関係を追加する必要があります。 [ こちら ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard) の指示に従ってください。
   * 常に最新バージョンのライブラリを使用します。
   * モバイルアプリで、**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]** および **[!UICONTROL Signal]** 拡張機能を登録します。 [ こちら ](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#register-the-campaign-standard-extension-with-mobile-core) の指示に従ってください。
   * 拡張機能が登録されたら、ACPCore を起動します。 Androidの場合は、必ず setApplication onCreate （）を使用します。 Launch のモバイルプロパティのモバイルインストール手順に記載されている正確な手順に従います。
   * 次のSDK API も必要になります。 Androidの場合は [ こちら ](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android)、iOSの場合はこちらを参照して、ライフサイクルの開始 API と一時停止 API を実装します。
1. Adobe Campaign Standardで **[!UICONTROL Mobile Property]** を設定します。 [ こちら ](../../administration/using/configuring-a-mobile-application.md#channel-specific-config) の手順に従います。

## Campaign でモバイルプロファイルをエンリッチメントするには、どうすればよいですか？ {#enrich-mobile-profile}

CollectPII ポストバックを設定（この [ ページ ](../../administration/using/configuring-rules-launch.md#pii-postback) を参照）し、SDKから CollectPII API を実装する必要があります（この [ ページ ](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference) を参照）。

## CollectPII 呼び出しは、どのくらいの頻度で実行する必要がありますか？ {#collect-pii}

CollectPII 呼び出しの目的は、Campaign でモバイルプロファイルを強化することです。 ユースケースやビジネスニーズに応じて、顧客がプロファイルに追加したい意味のある新しい情報がある場合は常に実行する必要があります。

## CollectPII 呼び出しは、複数のトリガーイベントに応答して実行できますか。 {#collect-pii-calls}

はい。ビジネスニーズに応じて、アプリにログインしたユーザーに応じて、または何か、ライフサイクルイベント、またはジオフェンスなどを入力するユーザーを購入するために、CollectPII 呼び出しを実行できます。 要約すると、ユーザーとアプリのインタラクションは、プロファイルのエンリッチメントに使用する情報を生成します。

## すべてのモバイルイベントに応答して CollectPII 呼び出しを実行することはできますか？ {#collect-pii-events}

CollectPII 呼び出しの頻度とデザインは、ビジネスニーズに応じて決定する必要があり、DB に追加の負荷がかかるので、やみくもに実行しないでください。

### Campaign または Launch でAdobe Experience Platform アプリにアクセスしようとすると、「プロパティを使用できません」というエラーが表示されることがあります。 {#aep-error}

これは既知の問題で、トークンの有効期限が原因で発生します。 ログアウトしてからログインしてください。

## Adobe Experience Platform SDK（旧称SDK V5）の詳細を学ぶのに役立つリソースレコメンデーションは何でしょうか？{#resource-aep}

以下のリソースを確認してください。

* SDKのExperience Platform[ ドキュメント ](https://developer.adobe.com/client-sdks/documentation/)
* Launch とExperience PlatformSDKの概要 [ ドキュメント ](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)
* Experience Platform SDKへのアップグレード [ ドキュメント ](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/)
* GithubExperience PlatformSDK[ ドキュメント ](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## プッシュ通知配信の作成中に、「配信に対する書き込みアクセス権がありません」というエラーが発生します。 {#write-access-error}

次の点を確認してください。

* モバイルアプリは、プッシュ配信を作成して送信する必要があるユーザーの組織単位にマッピングする必要があります。 子組織単位のユーザーは、親組織単位にマッピングされたアプリを使用してプッシュ配信を作成できません。

* プッシュ配信を作成するキャンペーンまたはプログラムは、プッシュ配信の作成と送信を必要とするユーザーの組織単位にマッピングする必要があります。 子組織単位のユーザーは、親組織単位にマッピングされたキャンペーンまたはプログラムでプッシュ配信を作成できません。
