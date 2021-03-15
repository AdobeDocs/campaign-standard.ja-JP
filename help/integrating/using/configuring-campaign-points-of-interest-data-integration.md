---
solution: Campaign Standard
product: campaign
title: Campaign と POI データの統合の設定
description: Adobe Campaignで目標地点データ機能を設定し、購読者の場所に基づいてパーソナライズされたメッセージを送信する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: オーディエンス
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 3%

---


# Campaign と POI データの統合の設定{#configuring-campaign-points-of-interest-data-integration}

## Adobe Experience PlatformSDKとのキャンペーン目標地点データ統合の設定{#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Adobe Experience PlatformSDKを使用して、モバイルアプリケーションがAdobe Campaign Standardで設定済みである必要があります。 詳細な手順については、[ページ](https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html)を参照してください。

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの&#x200B;**管理者**&#x200B;が設定する必要があります。

Adobe Experience PlatformSDKで設定されたモバイルアプリケーションでAdobe Experience Platformロケーションサービスを使用するには、次の操作が必要です。

1. Adobe Experience Platform Launch追加のモバイルアプリ設定の&#x200B;**[!UICONTROL Places]**&#x200B;拡張子と&#x200B;**[!UICONTROL Places Monitor]**&#x200B;拡張子です。 Adobe Campaignでモバイルアプリを設定します。 「[Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch)にPlaces拡張機能をインストールする」および「[Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)にPlaces Monitor拡張機能をインストールする」を参照してください。

1. 拡張機能を設定したら、**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;内にデータ要素を作成し、これらの拡張機能からデータを取得します。 データ要素を作成するには、この[ページ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)を参照してください。

1. 次に、**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;で、目標地点とAdobe Campaignの間のモバイルユースケースをサポートするルールを作成する必要があります。\
   このルールは、ユーザーが地域フェンス&#x200B;**[!UICONTROL Point of Interest]**&#x200B;に入るとトリガーされます。 ルールを作成するには、この[ページ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback)を参照してください。

1. **[!UICONTROL Points of Interest]**&#x200B;をPlacesに定義します。 「[目標地点を作成](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html)」を参照してください。

1. モバイルアプリと収集した場所のデータには、Adobe Campaignからアクセスしてください。 [場所データの収集に使用するモバイルアプリへのアクセス](#accessing-mobile-apps-used-to-collect-location-data)および[収集した場所データへのアクセス](#accessing-collected-location-data)を参照してください。

## SDK V4 {#configuring-campaign-poi-sdkv4}を使用した目標地点データ統合の設定

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの&#x200B;**管理者**&#x200B;が設定する必要があります。

SDK V4で設定されたモバイルアプリケーションで目標地点データ機能を使用するには、次の操作を行う必要があります。

1. モバイル用にAdobe Analyticsにアクセスできます。 詳しくは、使用許諾契約を確認するか、Adobeのアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリを設定します。 [キャンペーン](#setting-up-a-mobile-app-in-campaign)でのモバイルアプリの設定を参照してください。
1. AdobeのMobile Servicesインターフェイスでモバイルアプリを設定します。 これにより、AdobeのMobile Servicesによって収集されたデータを確実にAdobe Campaignに送信できます。 「AdobeMobile Services](#configuring-a-mobile-app-in-adobe-mobile-services)のモバイルアプリの設定」を参照してください。[
1. モバイルアプリケーション固有の設定を実行します。

   * AdobeのMobile Servicesインターフェイスからダウンロードした設定ファイルを、モバイルアプリケーションにパッケージ化します。
   * Experience CloudMobile SDKをモバイルアプリケーションに統合します。 [モバイルアプリケーションへのSDKの統合](#integrating-the-sdk-into-a-mobile-application)を参照してください。

1. AdobeのMobile Servicesインターフェイスで目標地点を定義します。 「[AdobeのMobile Servicesでの目標地点の定義](#defining-points-of-interest-in-adobe-mobile-services)」を参照してください。
1. モバイルアプリケーションのサブスクリプションから収集するデータを定義します。 [購読者の目標地点データの収集](#collecting-subscribers--points-of-interest-data)を参照してください。
1. モバイルアプリと収集した場所のデータには、Adobe Campaignからアクセスしてください。 [場所データの収集に使用するモバイルアプリへのアクセス](#accessing-mobile-apps-used-to-collect-location-data)および[収集した場所データへのアクセス](#accessing-collected-location-data)を参照してください。

### SDK V4 {#setting-up-a-mobile-app-in-campaign}を使用したAdobe Campaignでのモバイルアプリの設定

Adobe Campaignを使用して目標地点データを収集できるようにするには、Adobe Campaignがデータを受信するモバイルアプリを設定する必要があります。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Administration]**／**[!UICONTROL Channels]**／**[!UICONTROL Mobile app]** を選択します。
1. **[!UICONTROL Create]**&#x200B;をクリックして、アプリケーションを設定します。
1. **[!UICONTROL Application name]**&#x200B;フィールドに名前を入力し、**[!UICONTROL Create]**&#x200B;をクリックします。

   **[!UICONTROL Device-specific settings]**&#x200B;セクションには記入しないでください。 これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

**[!UICONTROL Mobile application properties]**&#x200B;セクションには、次の2つのURLが表示されます。**[!UICONTROL Collect PII endpoint]**&#x200B;と&#x200B;**[!UICONTROL Location Services endpoint]**。 これらは、AdobeのMobile Servicesインターフェイスで使用されます。 「AdobeMobile Services](#configuring-a-mobile-app-in-adobe-mobile-services)のモバイルアプリの設定」を参照してください。[

* **[!UICONTROL Collect PII endpoint]** URLは、モバイルアプリケーションの起動時に、ユーザーのExperience CloudIDと登録トークンを収集するために使用されます。 ユーザーが電子メール、名、姓などの資格情報を使用してアプリにログインすると、このデータも収集され、Adobe Campaignの登録トークンとユーザーのプロファイルとの調整に使用されます。
* **[!UICONTROL Location Services endpoint]** URLは、目標地点からユーザーの緯度、経度、半径などの位置データを収集するために使用されます。

「AdobeMobile Services](#configuring-a-mobile-app-in-adobe-mobile-services)の[モバイルアプリの設定」の節で説明したように、AdobeMobile Servicesでこれらの値を使用して設定を完了できるようになりました。

![](assets/poi_mobile_app_properties.png)

### AdobeMobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}でのV4モバイルアプリの設定

AdobeのMobile Servicesによって収集されたデータをAdobe Campaignに送信するには、Mobile Servicesインターフェイスでポストバックを設定する必要があります。

Adobe Campaignで設定したモバイルアプリのパラメーターに記載されている特定の情報が必要になります([キャンペーンでのモバイルアプリの設定](#setting-up-a-mobile-app-in-campaign)を参照)。

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定を行うには、Adobe Analyticsにアクセスできる必要があります。 Adobe Analyticsユーザでない場合は、Adobe Campaign管理者に問い合わせてください。

1. [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/)にログインします。
1. アプリを作成するか、既存のアプリを選択します。
1. **[!UICONTROL Manage App Settings]**&#x200B;ページに移動します。
1. 「**訪問者IDサービス**」セクションで、「**有効にする**」を選択し、ドロップダウンリストから組織を選択します。 「**保存**」をクリックします。

   >[!CAUTION]
   >
   >この組織は、Adobe Campaignインスタンスで使用する組織と同じである必要があります。

1. 「**[!UICONTROL Manage Postbacks]**」をクリックします。
1. ポストバックを作成します。

   * **[!UICONTROL PII]**&#x200B;を&#x200B;**[!UICONTROL Postback Type]**&#x200B;として選択します。
   * **[!UICONTROL URL]**&#x200B;フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから&#x200B;**[!UICONTROL Collect PII Endpoint]** URLをコピーし、先頭にサーバー名を付けます。 [キャンペーン](#setting-up-a-mobile-app-in-campaign)でのモバイルアプリの設定を参照してください。
   * **[!UICONTROL Post Body]**&#x200B;フィールドに次のように入力します。

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

   * **コンテンツタイプ**&#x200B;を&#x200B;**[!UICONTROL application/json]**&#x200B;に設定します。
   * **ポストバックをトリガーするデータタグはどれか。**&#x200B;で、任意のイベント(通常は **[!UICONTROL Launched]** と)を選択し **[!UICONTROL exists]**&#x200B;ます。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

1. 2つ目のポストバックを作成します。

   * **[!UICONTROL Postback]**&#x200B;を&#x200B;**[!UICONTROL Postback Type]**&#x200B;として選択します。
   * **[!UICONTROL URL]**&#x200B;フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから&#x200B;**[!UICONTROL Location Services Endpoint]** URLをコピーし、先頭にサーバー名を付けます。 [キャンペーン](#setting-up-a-mobile-app-in-campaign)でのモバイルアプリの設定を参照してください。
   * **[!UICONTROL Post Body]**&#x200B;フィールドに次のように入力します。

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

   * **コンテンツタイプ**&#x200B;を&#x200B;**[!UICONTROL application/json]**&#x200B;に設定します。
   * **ポストバックをトリガーするデータタグはどれか。**&#x200B;を選択 **[!UICONTROL campaign.test]** し **[!UICONTROL exists]**&#x200B;ます。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

>[!NOTE]
>
>ポストバックの設定について詳しくは、[Adobe版Mobile Servicesドキュメント](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)を参照してください。

### SDKのモバイルアプリケーションへの統合{#integrating-the-sdk-into-a-mobile-application}

Mobileコアサービスのソフトウェア開発キット(SDK)は、モバイルアプリケーションをAdobe Campaignに統合するのに役立ちます。

この手順は、この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.translate.html)で説明します。

### AdobeMobile Servicesでの目標地点の定義{#defining-points-of-interest-in-adobe-mobile-services}

場所データの収集に使用する目標地点を定義するには：

1. AdobeのMobile Servicesインターフェイスに移動します。
1. 申し込み追加を行います。

   Mobile Servicesでのアプリケーション管理の詳細については、[Adobe版Mobile Servicesドキュメント](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)を参照してください。

1. 目標地点を定義します。

   目標地点の管理の詳細については、[Adobe版Mobile Servicesドキュメント](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)を参照してください。

### 購読者の目標地点データの収集{#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーションのサブスクライバーから収集するデータを定義できます。

この手順については、[SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)ページを使用したモバイルアプリケーションの設定で説明します。


## 場所データの収集に使用するモバイルアプリへのアクセス{#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaign内に正常に作成されたアプリケーションにアクセスするには：

1. 左上隅の&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;ロゴをクリックします。
1. SDKに応じて&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]**&#x200B;または&#x200B;**[!UICONTROL Mobile app (AEP SDK)]**&#x200B;を選択します。
1. リストからモバイルアプリを選択し、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリケーションのサブスクライバのリストも&#x200B;**[!UICONTROL Mobile application subscribers]**&#x200B;タブに表示されます。 購読者は、モバイルデバイスにアプリケーションをインストールしたすべてのユーザーです。 Adobe Campaignデータベースプロファイルは、登録トークンで識別されます。

## 収集した場所のデータへのアクセス{#accessing-collected-location-data}

設定が完了すると、収集した目標地点データが各プロファイルの&#x200B;**[!UICONTROL Places]**&#x200B;タブに表示されます。 リストにアクセスするには：

1. プロファイルを選択します。
1. 右側の&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;ボタンをクリックします。
1. 「**[!UICONTROL Places]**」タブを選択します。

   ![](assets/poi_profile_places.png)

現在のプロファイルで収集された目標地点データが表示されます。 位置データは、Adobe Campaignデータベースに6か月間保存されます。

プロファイルへのアクセスと編集について詳しくは、[プロファイル](../../audiences/using/about-profiles.md)を参照してください。
