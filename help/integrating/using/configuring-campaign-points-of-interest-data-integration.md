---
solution: Campaign Standard
product: campaign
title: Campaign と POI データの統合の設定
description: Adobe Campaignで目標地点データ機能を設定して、購読者の場所に基づいてパーソナライズされたメッセージを送信する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: 68be77ba6ae38734688cf3f5c8667bffb90844b4
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 3%

---

# Campaign と POI データの統合の設定{#configuring-campaign-points-of-interest-data-integration}

## Adobe Experience Platform SDKを使用したCampaignとPOIデータの統合の設定 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Adobe Experience Platform SDKを使用して、Adobe Campaign Standardでモバイルアプリケーションを既に設定しておく必要があります。 詳細な手順については、[ページ](https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html)を参照してください。

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの&#x200B;**管理者**&#x200B;が設定する必要があります。

Adobe Experience Platform SDKを使用して設定されたモバイルアプリケーションでAdobe Experience Platform Location Servicesを使用するには、次の操作が必要です。

1. Adobe Experience Platform Launchのモバイルアプリ設定に&#x200B;**[!UICONTROL Places]**&#x200B;と&#x200B;**[!UICONTROL Places Monitor]**&#x200B;拡張機能を追加します。 Adobe Campaignでモバイルアプリケーションを設定します。 「[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch)にPlaces拡張機能をインストールする」および「[Experience Platform Launch](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)にPlaces監視拡張機能をインストールする」を参照してください。

1. 拡張機能を設定したら、**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;内にデータ要素を作成して、これらの拡張機能からデータを取得します。 データ要素を作成するには、この[ページ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)を参照してください。

1. 次に、**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;で、目標地点とAdobe Campaignの間のモバイル使用例をサポートするルールを作成する必要があります。\
   このルールは、ユーザーが地域に入るとトリガーされます&#x200B;**[!UICONTROL Point of Interest]**。 ルールを作成するには、この[ページ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback)を参照してください。

1. Placesで&#x200B;**[!UICONTROL Points of Interest]**&#x200B;を定義します。 [目標地点の作成](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html)を参照してください。

1. モバイルアプリケーションと、Adobe Campaignで収集した場所データにアクセスしてください。 [場所データの収集に使用するモバイルアプリへのアクセス](#accessing-mobile-apps-used-to-collect-location-data)および[収集した場所データへのアクセス](#accessing-collected-location-data)を参照してください。

## SDK V4を使用したCampaignとPOIデータの統合の設定 {#configuring-campaign-poi-sdkv4}

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの&#x200B;**管理者**&#x200B;が設定する必要があります。

SDK V4を使用して設定されたモバイルアプリケーションで目標地点データ機能を使用するには、次の操作が必要です。

1. Mobile用のAdobe Analyticsにアクセスできます。 詳しくは、ライセンス契約を確認するか、Adobeアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリケーションを設定します。 [Campaignでのモバイルアプリの設定](#setting-up-a-mobile-app-in-campaign)を参照してください。
1. Mobile ServicesインターフェイスでモバイルAdobeを設定します。 これにより、Mobile Servicesによって収集されたAdobeをAdobe Campaignに送信できます。 [Mobile ServicesでのモバイルアプリのAdobe](#configuring-a-mobile-app-in-adobe-mobile-services)を参照してください。
1. モバイルアプリケーション固有の設定を実行します。

   * Mobile Servicesインターフェイスからダウンロードした設定ファイルを、Adobeアプリケーションにパッケージ化します。
   * Experience CloudMobile SDKをモバイルアプリケーションに統合します。 [SDKをモバイルアプリケーションに統合する](#integrating-the-sdk-into-a-mobile-application)を参照してください。

1. Mobile Servicesインターフェイスで目標地点をAdobeします。 [Mobile ServicesでのAdobe目標地点の定義](#defining-points-of-interest-in-adobe-mobile-services)を参照してください。
1. モバイルアプリケーションの購読者から収集するデータを定義します。 [購読者の目標地点データの収集](#collecting-subscribers--points-of-interest-data)を参照してください。
1. モバイルアプリケーションと、Adobe Campaignで収集した場所データにアクセスしてください。 [場所データの収集に使用するモバイルアプリへのアクセス](#accessing-mobile-apps-used-to-collect-location-data)および[収集した場所データへのアクセス](#accessing-collected-location-data)を参照してください。

### SDK V4を使用したAdobe Campaignでのモバイルアプリの設定 {#setting-up-a-mobile-app-in-campaign}

Adobe Campaignで目標地点データを収集できるようにするには、Adobe Campaignがデータを受信するモバイルアプリを設定する必要があります。

1. 左上隅の&#x200B;**Adobe**&#x200B;ロゴをクリックし、**[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Mobile app]**&#x200B;を選択します。
1. **[!UICONTROL Create]**&#x200B;をクリックして、アプリケーションを設定します。
1. 「**[!UICONTROL Application name]**」フィールドに名前を入力し、「**[!UICONTROL Create]**」をクリックします。

   **[!UICONTROL Device-specific settings]**&#x200B;セクションには入力しないでください。 これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

**[!UICONTROL Mobile application properties]**&#x200B;セクションには、次の2つのURLが表示されます。**[!UICONTROL Collect PII endpoint]**&#x200B;と&#x200B;**[!UICONTROL Location Services endpoint]**。 これらは、Mobile ServicesインターフェイスでAdobeされます。 [Mobile ServicesでのモバイルアプリのAdobe](#configuring-a-mobile-app-in-adobe-mobile-services)を参照してください。

* **[!UICONTROL Collect PII endpoint]** URLは、起動時にモバイルアプリケーションからユーザーのExperience CloudIDと登録トークンを収集するために使用されます。 ユーザーがEメール、名、姓などの資格情報を使用してアプリケーションにログインすると、このデータも収集され、ユーザーの登録トークンをAdobe Campaignプロファイルと紐付けするために使用されます。
* **[!UICONTROL Location Services endpoint]** URLは、目標地点からユーザーの緯度、経度、半径などの位置データを収集するために使用されます。

これらの値をAdobeMobile Servicesで使用して設定を完了できます。詳しくは、AdobeMobile Servicesでのモバイルアプリの設定](#configuring-a-mobile-app-in-adobe-mobile-services)の節を参照してください。[

![](assets/poi_mobile_app_properties.png)

### Mobile ServicesでのV4モバイルアプリのAdobe {#configuring-a-mobile-app-in-adobe-mobile-services}

Mobile Servicesで収集されたデータをAdobe Campaignに送信するには、Mobile ServicesインターフェイスでAdobeポストバックを設定する必要があります。

Adobe Campaignで設定されたモバイルアプリケーションパラメーターで確認できる特定の情報が必要です（[Campaignでのモバイルアプリの設定](#setting-up-a-mobile-app-in-campaign)を参照）。

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定をおこなうには、Adobe Analyticsへのアクセス権が必要です。 Adobe Analyticsユーザーでない場合は、Adobe Campaign管理者に問い合わせてください。

1. [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/)にログインします。
1. アプリケーションを作成するか、既存のアプリケーションを選択します。
1. **[!UICONTROL Manage App Settings]**&#x200B;ページに移動します。
1. 「**訪問者IDサービス**」セクションで、「**有効**」をオンにして、ドロップダウンリストから組織を選択します。 「**保存**」をクリックします。

   >[!CAUTION]
   >
   >この組織は、Adobe Campaignインスタンスで使用する組織と同じである必要があります。

1. 「**[!UICONTROL Manage Postbacks]**」をクリックします。
1. ポストバックを作成します。

   * **[!UICONTROL Postback Type]**&#x200B;として&#x200B;**[!UICONTROL PII]**&#x200B;を選択します。
   * 「**[!UICONTROL URL]**」フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから&#x200B;**[!UICONTROL Collect PII Endpoint]** URLをコピーし、サーバー名の前にを付けます。 [Campaignでのモバイルアプリの設定](#setting-up-a-mobile-app-in-campaign)を参照してください。
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

   * 「**コンテンツタイプ**」を&#x200B;**[!UICONTROL application/json]**&#x200B;に設定します。
   * **で、ポストバックをトリガーするデータタグは？**、任意のイベント（通常は、および）を **[!UICONTROL Launched]** 選択しま **[!UICONTROL exists]**&#x200B;す。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

1. 2つ目のポストバックを作成します。

   * **[!UICONTROL Postback Type]**&#x200B;として&#x200B;**[!UICONTROL Postback]**&#x200B;を選択します。
   * 「**[!UICONTROL URL]**」フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから&#x200B;**[!UICONTROL Location Services Endpoint]** URLをコピーし、サーバー名の前にを付けます。 [Campaignでのモバイルアプリの設定](#setting-up-a-mobile-app-in-campaign)を参照してください。
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

   * 「**コンテンツタイプ**」を&#x200B;**[!UICONTROL application/json]**&#x200B;に設定します。
   * **で、ポストバックをトリガーするデータタグは？**、およびを選 **[!UICONTROL campaign.test]** 択しま **[!UICONTROL exists]**&#x200B;す。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

>[!NOTE]
>
>ポストバックの設定について詳しくは、[Mobile ServicesのAdobe](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)を参照してください。

### SDKをモバイルアプリケーションに統合する {#integrating-the-sdk-into-a-mobile-application}

Mobileコアサービスのソフトウェア開発キット(SDK)は、モバイルアプリケーションをAdobe Campaignに統合するのを容易にします。

この手順は、この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html)で説明します。

### Mobile ServicesでのAdobe目標地点の定義 {#defining-points-of-interest-in-adobe-mobile-services}

場所データの収集に使用する目標地点を定義するには：

1. Mobile ServicesのAdobeインターフェイスに移動します。
1. アプリを追加します。

   Mobile Servicesでのアプリケーション管理の詳細については、[Mobile ServicesのAdobeのドキュメント](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html)を参照してください。

1. 目標地点を定義します。

   目標地点の管理の詳細については、[AdobeMobile Servicesのドキュメント](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html)を参照してください。

### 購読者の目標地点データの収集 {#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーション購読者から収集するデータを定義できます。

この手順は、 SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)を使用したモバイルアプリケーションの設定で説明します。[


## 場所データの収集に使用するモバイルアプリへのアクセス {#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaignで正常に作成されたアプリケーションにアクセスするには：

1. 左上隅の&#x200B;**Adobe**&#x200B;ロゴをクリックします。
1. SDKに応じて、 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]**&#x200B;または&#x200B;**[!UICONTROL Mobile app (AEP SDK)]**&#x200B;を選択します。
1. リストからモバイルアプリを選択して、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリケーションの購読者のリストも「**[!UICONTROL Mobile application subscribers]**」タブに表示されます。 購読者は、モバイルデバイスにアプリケーションをインストールしたすべてのユーザーです。 Adobe Campaignデータベースプロファイルは、登録トークンで識別されます。

## 収集された場所データへのアクセス {#accessing-collected-location-data}

設定が完了すると、収集した目標地点データが各プロファイルの「**[!UICONTROL Places]**」タブに表示されます。 リストにアクセスするには：

1. プロファイルを選択します。
1. 右側の&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;ボタンをクリックします。
1. 「**[!UICONTROL Places]**」タブを選択します。

   ![](assets/poi_profile_places.png)

現在のプロファイルで収集された目標地点データが表示されます。 場所のデータはAdobe Campaignデータベースに6ヶ月間保存されます。

プロファイルへのアクセスと編集について詳しくは、[プロファイル](../../audiences/using/about-profiles.md)を参照してください。
