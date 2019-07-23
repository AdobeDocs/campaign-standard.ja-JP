---
title: キャンペーン目標地点データ統合の設定
seo-title: キャンペーン目標地点データ統合の設定
description: キャンペーン目標地点データ統合の設定
seo-description: Adobe Campaignで目標地点データ機能を設定し、加入者の場所に基づいてパーソナライズされたメッセージを送信する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 0689a06c- cc1a-442f-95b8- a07fcec85d79
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- analytics- for- mobile
discoiquuid: a967c6cc- c53b-41b4-866b-90860d78f463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 84fc114152385063ef07927e37d71f0c660225cf

---


# Configuring Campaign-Points of Interest data integration{#configuring-campaign-points-of-interest-data-integration}

## Configuring Campaign-Points of Interest data integration using SDK V4 {#configuring-campaign-poi-sdkv4}

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

SDK V4で設定されたモバイルアプリケーションで目標地点データ機能を使用するには、以下を行う必要があります。

1. モバイル用Adobe Analyticsにアクセスできます。使用許諾契約書を確認するか、アドビのアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリケーションをセットアップします。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. Adobe Mobile Servicesインターフェイスでモバイルアプリケーションをセットアップします。これにより、Adobe Mobile Servicesによって収集されたデータがAdobe Campaignに送信されるようになります。See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. モバイルアプリケーションの具体的な設定を実行します。

   * Adobe Mobile Servicesインターフェイスからダウンロードした設定ファイルをモバイルアプリケーションにパッケージ化します。
   * Experience Cloud Mobile SDKをモバイルアプリケーションに統合します。See [Integrating the SDK into a mobile application](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. Adobe Mobile Servicesインターフェイスで目標地点を定義します。See [Defining Points of Interest in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. モバイルアプリケーションのサブスクライバーから収集するデータを定義します。See [Collecting subscribers' Points of interest data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. Adobe Campaignでモバイルアプリケーションおよび収集された場所データにアクセスすることを確認してください。See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

### Setting up a mobile app in Adobe Campaign using SDK V4 {#setting-up-a-mobile-app-in-campaign}

Adobe Campaignで目標地点データを収集できるようにするには、Adobe Campaignがデータを受信するモバイルアプリケーションを設定する必要があります。

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Click **[!UICONTROL Create]** to set up an application.
1. **[!UICONTROL Application name]** フィールドに名前を入力し、をクリック **[!UICONTROL Create]**&#x200B;します。

   **[!UICONTROL Device-specific settings]** セクションに入力しないでください。これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

**[!UICONTROL Mobile application properties]** このセクションでは、2つのURLが表示されます。 **[!UICONTROL Collect PII endpoint]** および&#x200B;**[!UICONTROL Location Services endpoint]**&#x200B;これらはAdobe Mobile Servicesインターフェイスで使用されます。See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* The **[!UICONTROL Collect PII endpoint]** URL is used to collect the users' Experience Cloud IDs and registration tokens from the mobile application when it is launched. 電子メール、姓名、姓などの資格情報を使用してユーザーログにログインすると、このデータも収集され、ユーザーの登録トークンとAdobe Campaignプロファイルの調整に使用されます。
* **[!UICONTROL Location Services endpoint]** URLは、目標地点からのユーザーの緯度、経度、半径などの位置データを収集するために使用されます。

You can now use these values in Adobe Mobile Services to finish the configuration, as explained in the [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) section.

![](assets/poi_mobile_app_properties.png)

### Configuring a V4 mobile app in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Adobe Mobile Servicesによって収集されたデータをAdobe Campaignに送信するには、Mobile Servicesインターフェイスでポストバックを設定する必要があります。

You will need specific information that you can find in the mobile application parameters set in Adobe Campaign (see [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定を行うには、Adobe Analyticsにアクセスできる必要があります。Adobe Analyticsユーザーではない場合は、Adobe Campaign管理者に問い合わせてください。

1. [mobilemarketing.adobe.comにログイン](http://mobilemarketing.adobe.com/)します。
1. アプリケーションを作成するか、既存のアプリケーションを選択します。
1. **[!UICONTROL Manage App Settings]** ページに移動します。
1. In the **Visitor ID Service ** section, check **Enable** and select your organization from the drop-down list. Click **Save**.

   >[!CAUTION]
   >
   >この組織は、Adobe Campaignインスタンスで使用しているものと同じである必要があります。

1. **[!UICONTROL Manage Postbacks]**&#x200B;をクリックします。
1. ポストバックを作成します。

   * Select **[!UICONTROL PII]** as the **[!UICONTROL Postback Type]**.
   * **[!UICONTROL URL]** フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Collect PII Endpoint]** URLをコピーし、それ前にサーバー名を付けます。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

      iOSの場合:

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

      Androidの場合:

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

   * **コンテンツタイプを** 設定 **[!UICONTROL application/json]**&#x200B;します。
   * **どのデータタグがポストバックをトリガーしているか**&#x200B;では、通常、イベントを選択します **[!UICONTROL Launched]** 。**[!UICONTROL exists]**
   * **[!UICONTROL Save & Activate]**&#x200B;をクリックします。

1. 2番目のポストバックを作成します。

   * Select **[!UICONTROL Postback]** as the **[!UICONTROL Postback Type]**.
   * **[!UICONTROL URL]** フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Location Services Endpoint]** URLをコピーし、それ前にサーバー名を付けます。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

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

   * **コンテンツタイプを** 設定 **[!UICONTROL application/json]**&#x200B;します。
   * **どのデータタグがポストバックをトリガーしているか**、 **[!UICONTROL campaign.test]****[!UICONTROL exists]**&#x200B;および
   * **[!UICONTROL Save & Activate]**&#x200B;をクリックします。

>[!NOTE]
>
>For detailed information on configuring postbacks, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

Mobileコアサービスのソフトウェア開発キット（SDK）を使用すると、モバイルアプリケーションをAdobe Campaignに統合できます。

This step is described in this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Defining Points of Interest in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

場所データの収集に使用する目標地点を定義するには:

1. Adobe Mobile Servicesインターフェイスに移動します。
1. アプリケーションを追加します。

   For more information on managing applications in Mobile Services, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. 目標地点を定義します。

   For more information on managing Points of Interest, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

### Collecting subscribers' Points of interest data {#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーションの購読者から収集するデータを定義できます。

This step is described in the [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) page.

## Configuring Campaign-Points of Interest data integration with Adobe Experience Platform SDKs {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>モバイルアプリケーションは、Adobe Experience Platform SDKを使用してAdobe Campaign Standardで既に設定されている必要があります。For the detailed steps, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

Adobe Experience Platform SDKを使用して設定されたモバイルアプリケーションでAdobe Experience Platformロケーションサービスを使用できるようにするには、以下を行う必要があります。

1. Add the **[!UICONTROL Places]** and **[!UICONTROL Places Monitor]** extensions to your mobile app configuration in Adobe Experience Platform Launch. Adobe Campaignでモバイルアプリケーションをセットアップします。See [Install the Places extension in Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) and [Install the Places Monitor extension in Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Once your extensions are set up, create data elements within **[!UICONTROL Adobe Experience Platform Launch]** to retrieve data from these extensions.

1. Then, in **[!UICONTROL Adobe Experience Platform Launch]**, you need to create rules to support mobile use cases between Point of Interests and Adobe Campaign.\
   This rule will be triggered when a user enters a geo-fenced **[!UICONTROL Point of Interest]**. Refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#Locationpostback) to create your rule.

1. 場所に目標地点を定義する」を参照してください。See [Create a Point of Interest](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. Adobe Campaignでモバイルアプリケーションおよび収集された場所データにアクセスすることを確認してください。See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Accessing mobile apps used to collect location data {#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaignで正常に作成されたアプリケーションにアクセスするには:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** or **[!UICONTROL Mobile app (AEP SDK)]** depending on the SDK.
1. リストからモバイルアプリケーションを選択して、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリケーションの購読者のリストも表示されます。購読者とは、モバイルデバイスにアプリケーションをインストールしたユーザーのことです。Adobe Campaignデータベースプロファイルは、登録トークンで識別されます。

## Accessing collected location data {#accessing-collected-location-data}

Once the setup is done, the collected Points of Interest data is listed in the **[!UICONTROL Places]** tab of each profile. リストにアクセスするには:

1. プロファイルを選択します。
1. Click the **[!UICONTROL Edit profile properties]** button on the right.
1. **[!UICONTROL Places]** タブを選択します。

   ![](assets/poi_profile_places.png)

現在のプロファイルの目標地点データが収集されます。場所データは、6か月間Adobe Campaignデータベースに保存されます。

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/about-profiles.md).
