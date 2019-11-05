---
title: キャンペーン目標地点データ統合の設定
description: 購読者の場所に基づいてパーソナライズされたメッセージを送信するためのAdobe Campaignの目標地点データ機能の設定方法について説明します。
page-status-flag: 非活性化の
uuid: 0689a06c-cc1a-442f-95b8-a07fcec85d79
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンと分析をモバイル用に活用
discoiquuid: a967c6cc-c53b-41b4-866b-90860d78f463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# キャンペーン目標地点データ統合の設定{#configuring-campaign-points-of-interest-data-integration}

## Adobe Experience Platform SDKとのキャンペーン目標地点データ統合の設定 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Adobe Experience Platform SDKを使用して、モバイルアプリケーションがAdobe Campaign Standardで設定済みである必要があります。 詳細手順については、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェ **イスの管理** 者が設定する必要があります。

Adobe Experience Platform SDKで設定されたモバイルアプリケーションでAdobe Experience Platform Location Servicesを使用するには、次の操作を行う必要があります。

1. Adobe Experience Platform Launchで、モ **[!UICONTROL Places]** バイルア **[!UICONTROL Places Monitor]** プリ設定に拡張機能と拡張機能を追加します。 Adobe Campaignでモバイルアプリを設定します。 詳しくは、 [Adobe Experience Platform LaunchへのPlaces拡張のインストール](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) およびExperience Platform LaunchへのPlaces Monitor拡 [張のインストールを参照してください](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension)。

1. 拡張機能を設定したら、内にデータ要素を作成して、これらの拡 **[!UICONTROL Adobe Experience Platform Launch]** 張機能からデータを取得します。 データ要素を作成す [るには](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) 、このページを参照してください。

1. 次に、で目標地 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;点とAdobe Campaignの間のモバイルの使用例をサポートするルールを作成する必要があります。\
   このルールは、ユーザーが地域フェンスに入ったときにトリガーされま **[!UICONTROL Point of Interest]**&#x200B;す。 ルールを作成するに [は](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) 、このページを参照してください。

1. 「場所」でユーザーを **[!UICONTROL Points of Interest]** 定義します。 目標地 [点の作成を参照してください](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi)。

1. Adobe Campaignで、モバイルアプリケーションと収集した場所のデータに必ずアクセスしてください。 場所デー [タの収集に使用するモバイルアプリへのアクセスおよび収集した場所](#accessing-mobile-apps-used-to-collect-location-data)[データへのアクセスを参照してくださ](#accessing-collected-location-data)い。

## SDK V4を使用したキャンペーン目標地点データ統合の設定 {#configuring-campaign-poi-sdkv4}

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェ **イスの管理** 者が設定する必要があります。

SDK V4で設定されたモバイルアプリケーションで目標地点データ機能を使用するには、次の操作を行う必要があります。

1. Adobe Analytics for mobileにアクセスできます。 詳しくは、使用許諾契約を確認するか、アドビのアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリを設定します。 詳しくは、 [Campaignでのモバイルアプリの設定を参照してください](#setting-up-a-mobile-app-in-campaign)。
1. Adobe Mobile Servicesインターフェイスでモバイルアプリケーションを設定します。 これにより、Adobe Mobile Servicesによって収集されたデータを確実にAdobe Campaignに送信できます。 詳しく [は、Adobe Mobile Servicesでのモバイルアプリの設定を参照してください](#configuring-a-mobile-app-in-adobe-mobile-services)。
1. モバイルアプリケーション固有の設定を実行します。

   * Adobe Mobile Servicesインターフェイスからダウンロードした設定ファイルをモバイルアプリケーションにパッケージ化します。
   * Experience Cloud Mobile SDKをモバイルアプリケーションに統合します。 詳しくは、 [SDKのモバイルアプリケーションへの統合を参照してくださ](#integrating-the-sdk-into-a-mobile-application)い。

1. Adobe Mobile Servicesインターフェイスの目標地点を定義します。 Adobe Mobile Services [での目標地点の定義を参照してください](#defining-points-of-interest-in-adobe-mobile-services)。
1. モバイルアプリケーションのサブスクリプションから収集するデータを定義します。 購読者 [の目標地点データの収集を参照してください](#collecting-subscribers--points-of-interest-data)。
1. Adobe Campaignで、モバイルアプリケーションと収集した場所のデータに必ずアクセスしてください。 場所デー [タの収集に使用するモバイルアプリへのアクセスおよび収集した場所](#accessing-mobile-apps-used-to-collect-location-data)[データへのアクセスを参照してくださ](#accessing-collected-location-data)い。

### SDK V4を使用したAdobe Campaignでのモバイルアプリの設定 {#setting-up-a-mobile-app-in-campaign}

Adobe Campaignで目標地点データを収集できるようにするには、Adobe Campaignがデータを受け取るモバイルアプリを設定する必要があります。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を選 **[!UICONTROL Administration]** 択し **[!UICONTROL Channels]** ます **[!UICONTROL Mobile app]**。
1. をクリック **[!UICONTROL Create]** して、アプリを設定します。
1. フィールドに名前を入力し、を **[!UICONTROL Application name]** クリックしま **[!UICONTROL Create]**&#x200B;す。

   セクションに記入しないでく **[!UICONTROL Device-specific settings]** ださい。 これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

この節では、 **[!UICONTROL Mobile application properties]** 2つのURLを示します。 **[!UICONTROL Collect PII endpoint]** と **[!UICONTROL Location Services endpoint]**。 Adobe Mobile Servicesインターフェイスで使用されます。 詳しく [は、Adobe Mobile Servicesでのモバイルアプリの設定を参照してください](#configuring-a-mobile-app-in-adobe-mobile-services)。

* このURL **[!UICONTROL Collect PII endpoint]** は、モバイルアプリケーションの起動時に、ユーザーのExperience Cloud IDと登録トークンを収集するために使用されます。 ユーザーが電子メール、名、姓などの資格情報を使用してアプリケーションにログインすると、このデータも収集され、ユーザーの登録トークンとAdobe Campaignプロファイルとの調整に使用されます。
* この **[!UICONTROL Location Services endpoint]** URLは、目標地点からユーザーの緯度、経度、半径などの位置データを収集するために使用されます。

「Adobe Mobile Services」の「モバイルアプリの設定」で説明されているように、Adobe Mobile Servicesでこれらの値を使用し [て設定を完了できるようになりました](#configuring-a-mobile-app-in-adobe-mobile-services) 。

![](assets/poi_mobile_app_properties.png)

### Adobe Mobile ServicesでのV4モバイルアプリの設定 {#configuring-a-mobile-app-in-adobe-mobile-services}

Adobe Mobile Servicesで収集したデータをAdobe Campaignに送信するには、Mobile Servicesインターフェイスでポストバックを設定する必要があります。

Adobe Campaignで設定したモバイルアプリのパラメーターに記載されている特定の情報が必要になります(「Campaignでのモバイルア [プリの設定](#setting-up-a-mobile-app-in-campaign)」を参照)。

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定を行うには、Adobe Analyticsにアクセスできる必要があります。 Adobe Analyticsユーザーでない場合は、Adobe Campaign管理者に問い合わせてください。

1. mobilemarketing. [adobe.comにログインします](http://mobilemarketing.adobe.com/)。
1. アプリを作成するか、既存のアプリを選択します。
1. ページに移動し **[!UICONTROL Manage App Settings]** ます。
1. 「訪問者IDサ **ービス** 」セクションで「有 **効にする** 」を選択し、ドロップダウンリストから組織を選択します。 「**保存**」をクリックします。

   >[!CAUTION]
   >
   >この組織は、Adobe Campaignインスタンスで使用する組織と同じである必要があります。

1. Click **[!UICONTROL Manage Postbacks]**.
1. ポストバックを作成します。

   * をを **[!UICONTROL PII]** 選択します **[!UICONTROL Postback Type]**。
   * このフィールド **[!UICONTROL URL]** で、Adobe Campaignインターフェイスで **[!UICONTROL Collect PII Endpoint]** 設定したモバイルアプリケーションからURLをコピーし、先頭にサーバー名を付けます。 詳しくは、 [Campaignでのモバイルアプリの設定を参照してください](#setting-up-a-mobile-app-in-campaign)。
   * 次のようにフィールド **[!UICONTROL Post Body]** に入力します。

      iOSの場合：

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

   * 「コンテ **ンツタイプ** 」をに設定し **[!UICONTROL application/json]**&#x200B;ます。
   * ポストバッ **クをトリガーするデータタグ**&#x200B;を選択し、通常は任意のイベントを選択 **[!UICONTROL Launched]** しま **[!UICONTROL exists]**&#x200B;す。
   * Click **[!UICONTROL Save & Activate]**.

1. 2番目のポストバックを作成します。

   * をを **[!UICONTROL Postback]** 選択します **[!UICONTROL Postback Type]**。
   * このフィールド **[!UICONTROL URL]** で、Adobe Campaignインターフェイスで **[!UICONTROL Location Services Endpoint]** 設定したモバイルアプリケーションからURLをコピーし、先頭にサーバー名を付けます。 詳しくは、 [Campaignでのモバイルアプリの設定を参照してください](#setting-up-a-mobile-app-in-campaign)。
   * 次のようにフィールド **[!UICONTROL Post Body]** に入力します。

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

   * 「コンテ **ンツタイプ** 」をに設定し **[!UICONTROL application/json]**&#x200B;ます。
   * ポストバッ **クをトリガーするデータタグ**&#x200B;を選択し、とを選 **[!UICONTROL campaign.test]** 択しま **[!UICONTROL exists]**&#x200B;す。
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>ポストバックの設定について詳しくは、 [Adobe Mobile Servicesのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html)。

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

Mobileコアサービスのソフトウェア開発キット(SDK)は、モバイルアプリケーションをAdobe Campaignに統合するのを容易にします。

この手順については、このページで説 [明します](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

### Adobe Mobile Servicesの目標地点の定義 {#defining-points-of-interest-in-adobe-mobile-services}

場所データの収集に使用する目標地点を定義する手順は、次のとおりです。

1. Adobe Mobile Servicesインターフェイスに移動します。
1. アプリを追加します。

   Mobile Servicesでのアプリケーションの管理について詳しくは、 [Adobe Mobile Servicesのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html)。

1. 目標地点を定義します。

   目標地点の管理について詳しくは、 [Adobe Mobile Servicesのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html)。

### 購読者の目標地点データの収集 {#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーションのサブスクライバーから収集するデータを定義できます。

この手順は、SDK V4を使用したモバ [イルアプリケーションの設定ページで説明します](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) 。


## 場所データの収集に使用するモバイルアプリへのアクセス {#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaignで正常に作成されたアプリにアクセスするには：

1. 左上隅 **[!UICONTROL Adobe Campaign]** にあるロゴをクリックします。
1. SDKに応 **[!UICONTROL Administration]** じて、/ **[!UICONTROL Channels]** または **[!UICONTROL Mobile app (SDK v4)]** を **[!UICONTROL Mobile app (AEP SDK)]** 選択します。
1. リストからモバイルアプリを選択し、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリケーションのサブスクライバーのリストもタブに表示され **[!UICONTROL Mobile application subscribers]** ます。 購読者は、モバイルデバイスにアプリケーションをインストールしたすべてのユーザーです。 Adobe Campaignデータベースプロファイルは、登録トークンで識別されます。

## 収集された場所データへのアクセス {#accessing-collected-location-data}

設定が完了すると、収集した目標地点データが各プロファイルのタブにリ **[!UICONTROL Places]** ストされます。 リストにアクセスするには：

1. プロファイルを選択します。
1. 右側のボタン **[!UICONTROL Edit profile properties]** をクリックします。
1. Select the **[!UICONTROL Places]** tab.

   ![](assets/poi_profile_places.png)

現在のプロファイルで収集された目標地点データが表示されます。 場所のデータは、6か月間Adobe Campaignデータベースに保存されます。

プロファイルへのアクセスと編集について詳しくは、プロファイルを参照し [てくださ](../../audiences/using/about-profiles.md)い。
