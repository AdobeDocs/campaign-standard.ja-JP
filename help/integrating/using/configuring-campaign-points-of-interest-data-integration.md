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
source-git-commit: d857bee3e7cb54ec179a73d9c256a14771cbd474

---


# キャンペーン目標地点データ統合の設定{#configuring-campaign-points-of-interest-data-integration}

## Adobe Experience Platform SDKとの目標地点データ統合の設定 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>モバイルアプリケーションは、Adobe Experience Platform SDKを使用してAdobe Campaign Standardで既に設定されている必要があります。詳細手順については、 [このページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)を参照してください。

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの **管理者** が設定する必要があります。

Adobe Experience Platform SDKを使用して設定されたモバイルアプリケーションでAdobe Experience Platformロケーションサービスを使用できるようにするには、以下を行う必要があります。

1. Adobe **[!UICONTROL Places]** Experience Platform Launchのモバイルアプリ設定に **[!UICONTROL Places Monitor]** 、および拡張機能を追加します。Adobe Campaignでモバイルアプリケーションをセットアップします。詳しくは、Adobe Experience Platform Launchに場所拡張を [インストール](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) し [、Experience Platform Launchで場所モニター拡張機能をインストールするを](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension)参照してください。

1. 拡張子が設定されたら、これらの拡張子からデータを取得 **[!UICONTROL Adobe Experience Platform Launch]** するためにデータ要素を作成します。データ要素を作成するには [、このページ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) を参照してください。

1. 次に、 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;目標地点とAdobe Campaignの間のモバイルユースケースをサポートするルールを作成する必要があります。\
   このルールは、ユーザーが地域フィードに入るとトリガー **[!UICONTROL Point of Interest]**&#x200B;されます。ルールを作成するには [、このページ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) を参照してください。

1. 場所 **[!UICONTROL Points of Interest]** を定義します。目標地点 [の作成を参照](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi)してください。

1. Adobe Campaignでモバイルアプリケーションおよび収集された場所データにアクセスすることを確認してください。場所データの収集に使用するモバイルアプリ [および収集された場所](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) データ [へのアクセスを参照](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data)してください。

## SDK V4を使用した、キャンペーン目標地点データ統合の設定 {#configuring-campaign-poi-sdkv4}

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの **管理者** が設定する必要があります。

SDK V4で設定されたモバイルアプリケーションで目標地点データ機能を使用するには、以下を行う必要があります。

1. モバイル用Adobe Analyticsにアクセスできます。使用許諾契約書を確認するか、アドビのアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリケーションをセットアップします。詳しくは、キャンペーンでのモバイルアプリ [の設定を](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)参照してください。
1. Adobe Mobile Servicesインターフェイスでモバイルアプリケーションをセットアップします。これにより、Adobe Mobile Servicesによって収集されたデータがAdobe Campaignに送信されるようになります。Adobe Mobile Servicesでのモバイルアプリ [の設定](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services)を参照してください。
1. モバイルアプリケーションの具体的な設定を実行します。

   * Adobe Mobile Servicesインターフェイスからダウンロードした設定ファイルをモバイルアプリケーションにパッケージ化します。
   * Experience Cloud Mobile SDKをモバイルアプリケーションに統合します。"SDKと [モバイルアプリケーション](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application)の統合」を参照してください。

1. Adobe Mobile Servicesインターフェイスで目標地点を定義します。Adobe Mobile Servicesでの目標地点 [の定義](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services)を参照してください。
1. モバイルアプリケーションのサブスクライバーから収集するデータを定義します。購読者の目標地点データ [の収集を参照](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data)してください。
1. Adobe Campaignでモバイルアプリケーションおよび収集された場所データにアクセスすることを確認してください。場所データの収集に使用するモバイルアプリ [および収集された場所](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) データ [へのアクセスを参照](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data)してください。

### SDK V4を使用したAdobe Campaignでのモバイルアプリの設定 {#setting-up-a-mobile-app-in-campaign}

Adobe Campaignで目標地点データを収集できるようにするには、Adobe Campaignがデータを受信するモバイルアプリケーションを設定する必要があります。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、 **[!UICONTROL Administration]** / **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**&#x200B;を選択します。
1. をクリック **[!UICONTROL Create]** してアプリケーションを設定します。
1. **[!UICONTROL Application name]** フィールドに名前を入力し、をクリック **[!UICONTROL Create]**&#x200B;します。

   **[!UICONTROL Device-specific settings]** セクションに入力しないでください。これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

**[!UICONTROL Mobile application properties]** このセクションでは、2つのURLが表示されます。 **[!UICONTROL Collect PII endpoint]** および&#x200B;**[!UICONTROL Location Services endpoint]**&#x200B;これらはAdobe Mobile Servicesインターフェイスで使用されます。Adobe Mobile Servicesでのモバイルアプリ [の設定](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services)を参照してください。

* URLは **[!UICONTROL Collect PII endpoint]** 、起動時にモバイルアプリケーションからユーザーのExperience Cloud IDおよび登録トークンを収集するために使用されます。電子メール、姓名、姓などの資格情報を使用してユーザーログにログインすると、このデータも収集され、ユーザーの登録トークンとAdobe Campaignプロファイルの調整に使用されます。
* **[!UICONTROL Location Services endpoint]** URLは、目標地点からのユーザーの緯度、経度、半径などの位置データを収集するために使用されます。

Adobe Mobile [Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) の"Adobe Mobile Servicesでのモバイルアプリの設定」の説明に従って、これらの値をAdobe Mobile Servicesで使用できるようになりました。

![](assets/poi_mobile_app_properties.png)

### Adobe Mobile ServicesでのV4モバイルアプリの設定 {#configuring-a-mobile-app-in-adobe-mobile-services}

Adobe Mobile Servicesによって収集されたデータをAdobe Campaignに送信するには、Mobile Servicesインターフェイスでポストバックを設定する必要があります。

Adobe Campaignで設定されたモバイルアプリケーションパラメーターで特定できる情報が必要です（キャンペーンでのモバイルアプリ [の設定を参照](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)）。

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定を行うには、Adobe Analyticsにアクセスできる必要があります。Adobe Analyticsユーザーではない場合は、Adobe Campaign管理者に問い合わせてください。

1. [mobilemarketing.adobe.comにログイン](http://mobilemarketing.adobe.com/)します。
1. アプリケーションを作成するか、既存のアプリケーションを選択します。
1. **[!UICONTROL Manage App Settings]** ページに移動します。
1. **「訪問者IDサービス** »セクションで、?«有効&#x200B;****「 **保存**」をクリックします。

   >[!CAUTION]
   >
   >この組織は、Adobe Campaignインスタンスで使用しているものと同じである必要があります。

1. **[!UICONTROL Manage Postbacks]**&#x200B;をクリックします。
1. ポストバックを作成します。

   * として選択 **[!UICONTROL PII]****[!UICONTROL Postback Type]**&#x200B;します。
   * **[!UICONTROL URL]** フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Collect PII Endpoint]** URLをコピーし、それ前にサーバー名を付けます。詳しくは、キャンペーンでのモバイルアプリ [の設定を](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)参照してください。
   * 次のように **[!UICONTROL Post Body]** フィールドに入力します。

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

   * として選択 **[!UICONTROL Postback]****[!UICONTROL Postback Type]**&#x200B;します。
   * **[!UICONTROL URL]** フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Location Services Endpoint]** URLをコピーし、それ前にサーバー名を付けます。詳しくは、キャンペーンでのモバイルアプリ [の設定を](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)参照してください。
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

   * **コンテンツタイプを** 設定 **[!UICONTROL application/json]**&#x200B;します。
   * **どのデータタグがポストバックをトリガーしているか**、 **[!UICONTROL campaign.test]****[!UICONTROL exists]**&#x200B;および
   * **[!UICONTROL Save & Activate]**&#x200B;をクリックします。

>[!NOTE]
>
>ポストバックの設定について詳しくは、 [Adobe Mobile Servicesのドキュメント](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html)を参照してください。

### SDKとモバイルアプリケーションの統合 {#integrating-the-sdk-into-a-mobile-application}

Mobileコアサービスのソフトウェア開発キット（SDK）を使用すると、モバイルアプリケーションをAdobe Campaignに統合できます。

この手順については、 [このページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)で説明します。

### Adobe Mobile Servicesでの目標地点の定義 {#defining-points-of-interest-in-adobe-mobile-services}

場所データの収集に使用する目標地点を定義するには:

1. Adobe Mobile Servicesインターフェイスに移動します。
1. アプリケーションを追加します。

   Mobile Servicesでのアプリケーションの管理について詳しくは、 [Adobe Mobile Servicesのドキュメント](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html)を参照してください。

1. 目標地点を定義します。

   目標地点の管理について詳しくは、 [Adobe Mobile Servicesのドキュメント](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html)を参照してください。

### 購読者の目標地点データの収集 {#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーションの購読者から収集するデータを定義できます。

この手順については、"SDK [V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) ページを使用したモバイルアプリケーションの設定」を参照してください。


## 場所データの収集に使用するモバイルアプリへのアクセス {#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaignで正常に作成されたアプリケーションにアクセスするには:

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックします。
1. 選択 **[!UICONTROL Administration]** / **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** またはSDK **[!UICONTROL Mobile app (AEP SDK)]** によって異なります。
1. リストからモバイルアプリケーションを選択して、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリの購読者のリストもタブに **[!UICONTROL Mobile application subscribers]** 表示されます。購読者とは、モバイルデバイスにアプリケーションをインストールしたユーザーのことです。Adobe Campaignデータベースプロファイルは、登録トークンで識別されます。

## 収集された場所データへのアクセス {#accessing-collected-location-data}

セットアップが完了すると、収集された目標地点データが各プロファイルの **[!UICONTROL Places]** タブに表示されます。リストにアクセスするには:

1. プロファイルを選択します。
1. 右側の **[!UICONTROL Edit profile properties]** ボタンをクリックします。
1. **[!UICONTROL Places]** タブを選択します。

   ![](assets/poi_profile_places.png)

現在のプロファイルの目標地点データが収集されます。場所データは、6か月間Adobe Campaignデータベースに保存されます。

プロファイルへのアクセスと編集について詳しくは [、プロファイル](../../audiences/using/about-profiles.md)を参照してください。
