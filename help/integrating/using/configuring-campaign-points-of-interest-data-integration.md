---
solution: Campaign Standard
product: campaign
title: Campaign と POI データの統合の設定
description: Adobe Campaignで目標地点データ機能を設定し、購読者の場所に基づいてパーソナライズされたメッセージを送信する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---


# Campaign と POI データの統合の設定{#configuring-campaign-points-of-interest-data-integration}

## Adobe Experience PlatformSDKとの目標地点データ統合の設定 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Adobe Experience PlatformSDKを使用して、モバイルアプリケーションがAdobe Campaign Standardで設定済みである必要があります。 For the detailed steps, refer to this [page](https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html).

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの **管理者** が設定する必要があります。

Adobe Experience PlatformSDKで設定されたモバイルアプリケーションでAdobe Experience Platformロケーションサービスを使用するには、次の操作が必要です。

1. Adobe Experience Platform Launchのモバイルアプリ設定追加の拡張子 **[!UICONTROL Places]****[!UICONTROL Places Monitor]** と拡張子。 Adobe Campaignでモバイルアプリを設定します。 詳しくは、「Adobe Experience Platform LaunchにPlaces拡張機能を [インストールする](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) 」および「Experience Platform LaunchにPlaces Monitor拡張機能を [インストールする」を参照してください](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)。

1. 拡張機能を設定したら、内にデータ要素を作成して、これらの拡張機能 **[!UICONTROL Adobe Experience Platform Launch]** からデータを取得します。 データ要素を作成するには、この [ページを参照し](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) ます。

1. 次に、 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;で目標地点とAdobe Campaignの間のモバイルユースケースをサポートするルールを作成する必要があります。\
   このルールは、ユーザーが地域フェンスに入ったときにトリガーされ **[!UICONTROL Point of Interest]**&#x200B;ます。 ルールを作成するには、この [ページを参照](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) 。

1. 「場所」 **[!UICONTROL Points of Interest]** でユーザーを定義します。 目標地点 [の作成を参照してください](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html)。

1. モバイルアプリと収集した場所のデータには、Adobe Campaignからアクセスしてください。 場所データの収集に使用するモバイルアプリへの [アクセスおよび収集した場所データへの](#accessing-mobile-apps-used-to-collect-location-data) アクセスを参照してください [](#accessing-collected-location-data)。

## SDK V4を使用した目標地点データ統合の設定 {#configuring-campaign-poi-sdkv4}

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの **管理者** が設定する必要があります。

SDK V4で設定されたモバイルアプリケーションで目標地点データ機能を使用するには、次の操作を行う必要があります。

1. モバイル用にAdobe Analyticsにアクセスできます。 詳しくは、使用許諾契約を確認するか、Adobeのアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリを設定します。 詳しくは、キャンペーンでのモバイルアプリの [設定を参照してください](#setting-up-a-mobile-app-in-campaign)。
1. AdobeのMobile Servicesインターフェイスでモバイルアプリを設定します。 これにより、AdobeのMobile Servicesによって収集されたデータを確実にAdobe Campaignに送信できます。 「AdobeMobile Services [のモバイルアプリの設定](#configuring-a-mobile-app-in-adobe-mobile-services)」を参照してください。
1. モバイルアプリケーション固有の設定を実行します。

   * AdobeのMobile Servicesインターフェイスからダウンロードした設定ファイルを、モバイルアプリケーションにパッケージ化します。
   * Experience CloudMobile SDKをモバイルアプリケーションに統合します。 詳しくは、SDKのモバイルアプリケーションへの [統合を参照してください](#integrating-the-sdk-into-a-mobile-application)。

1. AdobeのMobile Servicesインターフェイスで目標地点を定義します。 AdobeMobile Servicesでの目標地点の [定義を参照してください](#defining-points-of-interest-in-adobe-mobile-services)。
1. モバイルアプリケーションのサブスクリプションから収集するデータを定義します。 購読者の目標地点データの [収集を参照してください](#collecting-subscribers--points-of-interest-data)。
1. モバイルアプリと収集した場所のデータには、Adobe Campaignからアクセスしてください。 場所データの収集に使用するモバイルアプリへの [アクセスおよび収集した場所データへの](#accessing-mobile-apps-used-to-collect-location-data) アクセスを参照してください [](#accessing-collected-location-data)。

### SDK V4を使用したAdobe Campaignでのモバイルアプリの設定 {#setting-up-a-mobile-app-in-campaign}

Adobe Campaignを使用して目標地点データを収集できるようにするには、Adobe Campaignがデータを受信するモバイルアプリを設定する必要があります。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Administration]**／**[!UICONTROL Channels]**／**[!UICONTROL Mobile app]** を選択します。
1. をクリック **[!UICONTROL Create]** して、アプリを設定します。
1. フィールドに名前を入力し、 **[!UICONTROL Application name]** をクリックし **[!UICONTROL Create]**&#x200B;ます。

   セクションに入力しな **[!UICONTROL Device-specific settings]** い。 これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

この節には、2つのURLが表示され **[!UICONTROL Mobile application properties]** ます。 **[!UICONTROL Collect PII endpoint]** と **[!UICONTROL Location Services endpoint]**。 これらは、AdobeのMobile Servicesインターフェイスで使用されます。 「AdobeMobile Services [のモバイルアプリの設定](#configuring-a-mobile-app-in-adobe-mobile-services)」を参照してください。

* この **[!UICONTROL Collect PII endpoint]** URLは、モバイルアプリケーションの起動時に、ユーザーのExperience CloudIDと登録トークンを収集するために使用されます。 ユーザーが電子メール、名、姓などの資格情報を使用してアプリにログインすると、このデータも収集され、Adobe Campaignの登録トークンとユーザーのプロファイルとの調整に使用されます。
* この **[!UICONTROL Location Services endpoint]** URLは、目標地点からユーザーの緯度、経度、半径などの位置データを収集するために使用されます。

「AdobeMobile Services [」の「モバイルアプリの](#configuring-a-mobile-app-in-adobe-mobile-services) 設定」の説明に従って、これらの値をAdobeMobile Servicesで使用して設定を完了できるようになりました。

![](assets/poi_mobile_app_properties.png)

### AdobeMobile ServicesでのV4モバイルアプリの設定 {#configuring-a-mobile-app-in-adobe-mobile-services}

AdobeのMobile Servicesによって収集されたデータをAdobe Campaignに送信するには、Mobile Servicesインターフェイスでポストバックを設定する必要があります。

Adobe Campaignで設定したモバイルアプリのパラメーターに記載されている具体的な情報が必要になります(キャンペーンでのモバイルアプリの [設定を参照](#setting-up-a-mobile-app-in-campaign))。

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定を行うには、Adobe Analyticsにアクセスできる必要があります。 Adobe Analyticsユーザでない場合は、Adobe Campaign管理者に問い合わせてください。

1. mobilemarketing.adobe.com [にログインします](https://mobilemarketing.adobe.com/)。
1. アプリを作成するか、既存のアプリを選択します。
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. 「 **訪問者IDサービス** 」セクションで、「 **有効にする** 」をチェックし、ドロップダウンリストから組織を選択します。 「**保存**」をクリックします。

   >[!CAUTION]
   >
   >この組織は、Adobe Campaignインスタンスで使用する組織と同じである必要があります。

1. 「**[!UICONTROL Manage Postbacks]**」をクリックします。
1. ポストバックを作成します。

   * を **[!UICONTROL PII]** に選択し **[!UICONTROL Postback Type]**&#x200B;ます。
   * このフィールドで、サーバーインターフェイスで設定したモバイルAdobe Campaignから **[!UICONTROL URL]****[!UICONTROL Collect PII Endpoint]** URLをコピーし、サーバー名の前にURLを付けます。 詳しくは、キャンペーンでのモバイルアプリの [設定を参照してください](#setting-up-a-mobile-app-in-campaign)。
   * 次のように **[!UICONTROL Post Body]** フィールドに入力します。

      iOS の場合:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      Android の場合:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * 「 **コンテンツタイプ** 」を「次 **[!UICONTROL application/json]**&#x200B;の値」に設定します。
   * 「ど **のデータタグでポストバックがトリガーされるか」**&#x200B;で、任意のイベント(通常は **[!UICONTROL Launched]** および)を選択し **[!UICONTROL exists]**&#x200B;ます。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

1. 2つ目のポストバックを作成します。

   * を **[!UICONTROL Postback]** に選択し **[!UICONTROL Postback Type]**&#x200B;ます。
   * このフィールドで、サーバーインターフェイスで設定したモバイルAdobe Campaignから **[!UICONTROL URL]****[!UICONTROL Location Services Endpoint]** URLをコピーし、サーバー名の前にURLを付けます。 詳しくは、キャンペーンでのモバイルアプリの [設定を参照してください](#setting-up-a-mobile-app-in-campaign)。
   * 次のように **[!UICONTROL Post Body]** フィールドに入力します。

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * 「 **コンテンツタイプ** 」を「次 **[!UICONTROL application/json]**&#x200B;の値」に設定します。
   * 「ど **のデータタグでポストバックがトリガーされるか」**&#x200B;を選択し **[!UICONTROL campaign.test]** 、を選択し **[!UICONTROL exists]**&#x200B;ます。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

>[!NOTE]
>
>ポストバックの設定について詳しくは、 [Adobe版Mobile Servicesのドキュメントを参照してください](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)。

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

Mobileコアサービスのソフトウェア開発キット(SDK)は、モバイルアプリケーションをAdobe Campaignに統合するのに役立ちます。

この手順については、この [ページで説明します](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.translate.html)。

### AdobeのMobile Servicesでの目標地点の定義 {#defining-points-of-interest-in-adobe-mobile-services}

場所データの収集に使用する目標地点を定義するには：

1. AdobeのMobile Servicesインターフェイスに移動します。
1. 申し込み追加を行います。

   Mobile Servicesでのアプリケーション管理の詳細については、 [Adobe版Mobile Servicesのドキュメントを参照してください](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)。

1. 目標地点を定義します。

   目標地点の管理について詳しくは、 [AdobeMobile Servicesのドキュメントを参照してください](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)。

### 購読者の目標地点データの収集 {#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーションのサブスクライバーから収集するデータを定義できます。

この手順は、V4を使用したモバイルアプリケーションの [設定](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.translate.html) ページで説明します。


## 場所データの収集に使用するモバイルアプリへのアクセス {#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaign内に正常に作成されたアプリケーションにアクセスするには：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. SDKに応じて、/ **[!UICONTROL Administration]** / **[!UICONTROL Channels]** またはを選択 **[!UICONTROL Mobile app (SDK v4)]****[!UICONTROL Mobile app (AEP SDK)]** します。
1. リストからモバイルアプリを選択し、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリケーションのサブスクライバのリストも **[!UICONTROL Mobile application subscribers]** タブに表示されます。 購読者は、モバイルデバイスにアプリケーションをインストールしたすべてのユーザーです。 Adobe Campaignデータベースプロファイルは、登録トークンで識別されます。

## 収集した場所のデータへのアクセス {#accessing-collected-location-data}

設定が完了すると、収集した目標地点データが各プロファイルの **[!UICONTROL Places]** タブに表示されます。 リストにアクセスするには：

1. プロファイルを選択します。
1. 右側の **[!UICONTROL Edit profile properties]** ボタンをクリックします。
1. 「**[!UICONTROL Places]**」タブを選択します。

   ![](assets/poi_profile_places.png)

現在のプロファイルで収集された目標地点データが表示されます。 位置データは、Adobe Campaignデータベースに6か月間保存されます。

プロファイルへのアクセスと編集について詳しくは、 [プロファイルを参照してください](../../audiences/using/about-profiles.md)。
