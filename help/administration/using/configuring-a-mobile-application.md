---
title: モバイルアプリケーションの構成
seo-title: モバイルアプリケーションの構成
description: モバイルアプリケーションの構成
seo-description: Adobe Campaignを設定して、SDK V4またはエクスペリエンスプラットフォームSDKを使用してプッシュ通知またはインアプリメッセージを送信する方法を確認します。
page-status-flag: 決して活性化されていない
uuid: 63e1476a-7875-4f48- ba9e-97f1a0007e42
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 管理
content-type: 参照
topic-tags: 構成チャネル
discoiquuid: 2a14500f-5ede-4131-8b1a- b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b7da7df5092476be4c6acc21b2ad2472a80da83

---


# モバイルアプリケーションの構成{#configuring-a-mobile-application}

プッシュ通知またはインアプリメッセージは、使用するチャネルに応じてAdobe Mobile Servicesで最初に構成する必要があるモバイルアプリケーションで受信されます。

* インアプリメッセージとプッシュ通知を送信するには、Adobe Experience Platform SDKを活用して、モバイルアプリケーションをAdobe Campaignでセットアップする必要があります。Adobe Experience Platform SDK [の使用を参照](#using-adobe-experience-platform-sdk)してください。

* Push通知のみを送信するには、SDK V4を使用してAdobe CampaignとAdobe Mobile Service間の統合を設定します。Using SDK [V4](#using-sdk-v4)を参照してください。

モバイルアプリケーションをAdobe Campaignでセットアップした後、エクスペリエンスクラウドモバイルSDK V4またはエクスペリエンスプラットフォームSDKを活用すると、&gt; [!UICONTROL Administration][!UICONTROL Channels] &gt; [!UICONTROL Mobile app] メニューの下に管理者が設定する必要があります。

>[!CAUTION]
>
>プッシュ通知とインアプリの実装は、エキスパートユーザーが実行する必要があります。支援する必要がある場合は、Adobeアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

モバイルアプリケーションをセットアップすると、データベースからプロファイルを作成または更新するために収集したPIIデータを取得できます。詳細については、このセクションを参照してください。 [モバイルアプリケーションデータに基づいてプロファイル情報を作成および更新](../../channels/using/updating-profile-with-mobile-app-data.md)します。

## Adobe Experience Platform SDKの使用 {#using-adobe-experience-platform-sdk}

>[!Nホーテ]
>
>Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされているさまざまなモバイルユースケースの詳細については、この [ページを](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)参照してください。

エクスペリエンスプラットフォームSDKアプリケーションを使用してプッシュ通知とインアプリメッセージを送信するには、Adobe Experience Platform Experience Platform Experience Platform Launchでモバイルアプリケーションをセットアップし、Adobe Campaignで構成する必要があります。Experience Platform SDKを使用してモバイルアプリケーションを構成する詳細な手順については、この [ページを](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)参照してください。

次の手順に従って構成を開始します。

1. **[!UICONTROL Mobile]** チャネルにアクセスできることを確認します。Adobe Campaignでのプッシュ通知およびインアプリメッセージ。そうでない場合は、アカウントチームにお問い合わせください。

   ![](assets/launch_1.png)

1. モバイル型のプロパティを作成して、Experience Platform Launchでモバイルアプリケーションを作成します。詳細については、 [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) のドキュメントを参照してください。
1. モバイルアプリケーションの **[!UICONTROL Adobe Campaign Standard]** 拡張機能を"Experience Platform Launch"にインストールします。

   拡張機能の詳細については、 [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) のドキュメントを参照してください。

1. Adobe Launchでアプリケーションのルールを構成します。「起動時のアプリケーション [の構成」を参照してください](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Adobe Launch ApplicationをAdobe Campaign Standardで構成します。Adobe [CampaignでのAdobe Launchアプリケーションの設定を参照](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign)してください。
1. チャネル固有の構成をモバイルアプリケーションのセットアップに追加します。Adobe Campaignで [のチャネル固有のアプリケーション構成を参照](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)してください。

   ![](assets/launch_2.png)

## SDK V4の使用 {#using-sdk-v4}

Push通知は、App V4とAdobe Experience Platform SDKでは、In- Appと異なりサポートされています。モバイルアプリでプッシュ通知を使用するための詳細な手順については、この [ページを](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)参照してください。

プッシュ通知を受信するモバイルアプリケーションは、Adobe Campaignインターフェイスの管理者によって構成されている必要があります。Adobe CampaignとAdobe Mobile Servicesの両方を設定すると、モバイルアプリケーションのデータをキャンペーンに使用できます。

プッシュ通知を送信できるようにするには、次のことが必要です。

1. Adobe Campaignでチャネル **[!UICONTROL Mobile app]** にアクセスできることを確認します。
1. 次の場所にモバイルアプリケーションを設定します。

   * [Adobeキャンペーン](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign)。
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices)。

1. モバイルアプリケーションの特定のセットアップを実行します。

   * Adobe Mobile Servicesインターフェイスからダウンロードした構成ファイルをモバイルアプリケーションでパッケージ化します。
   * エクスペリエンスクラウドモバイルSDKをモバイルアプリケーションに統合します。

1. アプリケーションのサブスクライバから収集するデータを定義します。Adobe Campaignデータベースにプロファイルを持つモバイルアプリケーションの購読者は、定義した条件に基づいて調整されます。

   詳細については、この [ページを](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication)参照してください。

1. デバイスでモバイルアプリケーションを起動し、サインインすることによって、セットアップが正常に完了したことを確認します。通知を受信することを確認してください。
1. その後、Adobe Campaignの詳細メニューで **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**&#x200B;を選択します。
1. リストからモバイルアプリケーションを選択して、そのプロパティを表示します。購読情報は購読者リストの下に表示されます。

   ![](assets/push_notif_mobile_app.png)

1. プロファイルが購読しているモバイルアプリケーションを確認するには、メニュー **[!UICONTROL Profiles & Audiences > Profiles]** でプロファイルを選択し、右側のボタン **[!UICONTROL Edit profile properties]** をクリックします。モバイルアプリケーションが **[!UICONTROL Mobile App Subscriptions]** タブに表示されます。

   ![](assets/push_notif_subscriptions.png)