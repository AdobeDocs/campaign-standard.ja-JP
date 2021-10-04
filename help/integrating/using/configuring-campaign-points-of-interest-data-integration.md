---
title: Campaign と POI データの統合の設定
description: Adobe Campaignで目標地点データ機能を設定し、購読者の場所に基づいてパーソナライズされたメッセージを送信する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1328'
ht-degree: 3%

---

# Campaign と POI データの統合の設定{#configuring-campaign-points-of-interest-data-integration}

## Adobe Experience Platform SDK との Campaign と POI データの統合の設定 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Adobe Experience Platform SDK を使用して、モバイルアプリケーションが既にAdobe Campaign Standardで設定されているはずです。 詳細な手順については、[ ページ ](https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html) を参照してください。

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの **管理者** が設定する必要があります。

Adobe Experience Platform SDK で設定されたモバイルアプリケーションでAdobe Experience Platform Location Services を使用するには、次の操作が必要です。

1. **[!UICONTROL Places]** と **[!UICONTROL Places Monitor]** の拡張機能をAdobe Experience Platform Launchのモバイルアプリ設定に追加します。 Adobe Campaignでモバイルアプリケーションを設定します。 「[Adobe Experience Platform Launchの Places 拡張機能のインストール ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch)」および「[Experience Platform Launchの Places 監視拡張機能のインストール ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)」を参照してください。

1. 拡張機能を設定したら、**[!UICONTROL Adobe Experience Platform Launch]** 内にデータ要素を作成して、これらの拡張機能からデータを取得します。 データ要素を作成するには、この [ ページ ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) を参照してください。

1. 次に、**[!UICONTROL Adobe Experience Platform Launch]** で、目標地点とAdobe Campaignの間のモバイル使用例をサポートするルールを作成する必要があります。\
   このルールは、ユーザーが地域に入るとトリガーされます **[!UICONTROL Point of Interest]**。 ルールを作成するには、この [ ページ ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) を参照してください。

1. Places で **[!UICONTROL Points of Interest]** を定義します。 [ 目標地点の作成 ](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html) を参照してください。

1. モバイルアプリケーションと、Adobe Campaignで収集した場所データにアクセスしていることを確認します。 [ 場所データの収集に使用するモバイルアプリへのアクセス ](#accessing-mobile-apps-used-to-collect-location-data) および [ 収集した場所データへのアクセス ](#accessing-collected-location-data) を参照してください。

## SDK V4 を使用した Campaign と POI データの統合の設定 {#configuring-campaign-poi-sdkv4}

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaignインターフェイスの **管理者** が設定する必要があります。

SDK V4 で設定したモバイルアプリケーションで目標地点データ機能を使用するには、次の操作が必要です。

1. Adobe Analytics for Mobile にアクセスできます。 詳しくは、ライセンス契約を確認するか、Adobeアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリケーションを設定します。 [Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照してください。
1. Mobile Services インターフェイスでモバイルAdobeを設定します。 これにより、Mobile Services によって収集されたAdobeをAdobe Campaignに送信できます。 [Mobile Services でのモバイルアプリのAdobe](#configuring-a-mobile-app-in-adobe-mobile-services) を参照してください。
1. モバイルアプリケーション固有の設定を実行します。

   * Mobile Services インターフェイスからダウンロードした設定ファイルを、Adobeアプリケーションにパッケージ化します。
   * Experience CloudMobile SDK をモバイルアプリケーションに統合します。 [SDK をモバイルアプリケーションに統合する ](#integrating-the-sdk-into-a-mobile-application) を参照してください。

1. Mobile Services インターフェイスで目標地点をAdobeします。 [Mobile Services でのAdobe目標地点の定義 ](#defining-points-of-interest-in-adobe-mobile-services) を参照してください。
1. モバイルアプリケーションの購読者から収集するデータを定義します。 [ 購読者の目標地点データの収集 ](#collecting-subscribers--points-of-interest-data) を参照してください。
1. モバイルアプリケーションと、Adobe Campaignで収集した場所データにアクセスしていることを確認します。 [ 場所データの収集に使用するモバイルアプリへのアクセス ](#accessing-mobile-apps-used-to-collect-location-data) および [ 収集した場所データへのアクセス ](#accessing-collected-location-data) を参照してください。

### SDK V4 を使用したAdobe Campaignでのモバイルアプリの設定 {#setting-up-a-mobile-app-in-campaign}

Adobe Campaignで目標地点データを収集できるようにするには、Adobe Campaignがデータを受け取るモバイルアプリケーションを設定する必要があります。

1. 左上隅の **Adobe** ロゴをクリックし、**[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Mobile app]** を選択します。
1. **[!UICONTROL Create]** をクリックして、アプリケーションを設定します。
1. **[!UICONTROL Application name]** フィールドに名前を入力し、**[!UICONTROL Create]** をクリックします。

   **[!UICONTROL Device-specific settings]** セクションには入力しないでください。 これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

**[!UICONTROL Mobile application properties]** セクションには、次の 2 つの URL が表示されます。**[!UICONTROL Collect PII endpoint]** と **[!UICONTROL Location Services endpoint]**。 Mobile Services インターフェイスでAdobeされます。 [Mobile Services でのモバイルアプリのAdobe](#configuring-a-mobile-app-in-adobe-mobile-services) を参照してください。

* **[!UICONTROL Collect PII endpoint]** URL は、起動時にモバイルアプリケーションからユーザーのExperience CloudID と登録トークンを収集するために使用されます。 ユーザーが電子メール、名、姓などの資格情報を使用してアプリケーションにログインすると、このデータも収集され、ユーザーの登録トークンとAdobe Campaignプロファイルとの紐付けに使用されます。
* **[!UICONTROL Location Services endpoint]** URL は、目標地点からユーザーの緯度、経度、半径などの位置データを収集するために使用されます。

これらの値をAdobeの Mobile Services で使用して設定を完了できます。詳しくは、 Mobile Services でのAdobeのモバイルアプリの設定 ](#configuring-a-mobile-app-in-adobe-mobile-services) の節を参照してください。[

![](assets/poi_mobile_app_properties.png)

### Mobile Services での V4 モバイルアプリのAdobe {#configuring-a-mobile-app-in-adobe-mobile-services}

Mobile Services で収集されたデータをAdobe Campaignに送信するには、Mobile Services インターフェイスでAdobeポストバックを設定する必要があります。

Adobe Campaignのモバイルアプリケーションパラメーターセットにある特定の情報が必要です（[Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照）。

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定をおこなうには、Adobe Analyticsにアクセスできる必要があります。 Adobe Analyticsユーザーでない場合は、Adobe Campaign管理者に問い合わせてください。

1. [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/) にログインします。
1. アプリケーションを作成するか、既存のアプリケーションを選択します。
1. **[!UICONTROL Manage App Settings]** ページに移動します。
1. 「**訪問者 ID サービス**」セクションで、「**有効**」をオンにして、ドロップダウンリストから組織を選択します。 「**保存**」をクリックします。

   >[!CAUTION]
   >
   >この組織は、Adobe Campaignインスタンスで使用する組織と同じである必要があります。

1. 「**[!UICONTROL Manage Postbacks]**」をクリックします。
1. ポストバックを作成します。

   * **[!UICONTROL Postback Type]** として **[!UICONTROL PII]** を選択します。
   * 「**[!UICONTROL URL]**」フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Collect PII Endpoint]** URL をコピーし、先頭にサーバー名を付けます。 [Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照してください。
   * **[!UICONTROL Post Body]** フィールドに次のように入力します。

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

   * 「**コンテンツタイプ**」を **[!UICONTROL application/json]** に設定します。
   * **で、ポストバックのトリガーデータタグは？**、任意のイベント（通常は、および）を **[!UICONTROL Launched]** 選択しま **[!UICONTROL exists]**&#x200B;す。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

1. 2 番目のポストバックを作成します。

   * **[!UICONTROL Postback Type]** として **[!UICONTROL Postback]** を選択します。
   * 「**[!UICONTROL URL]**」フィールドで、Adobe Campaignインターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Location Services Endpoint]** URL をコピーし、先頭にサーバー名を付けます。 [Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照してください。
   * **[!UICONTROL Post Body]** フィールドに次のように入力します。

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

   * 「**コンテンツタイプ**」を **[!UICONTROL application/json]** に設定します。
   * **で、ポストバックのトリガーデータタグは？**、およびを選 **[!UICONTROL campaign.test]** 択しま **[!UICONTROL exists]**&#x200B;す。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

>[!NOTE]
>
>ポストバックの設定について詳しくは、[Mobile Services のAdobe](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html) のドキュメントを参照してください。

### SDK をモバイルアプリケーションに統合する {#integrating-the-sdk-into-a-mobile-application}

Mobile コアサービスのソフトウェア開発キット (SDK) は、モバイルアプリケーションをAdobe Campaignに統合するのを容易にします。

この手順は、この [ ページ ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) で説明します。

### Mobile Services でのAdobe目標地点の定義 {#defining-points-of-interest-in-adobe-mobile-services}

場所データの収集に使用する目標地点を定義するには：

1. Mobile Services インターフェイスをAdobeします。
1. アプリを追加します。

   Mobile Services でのアプリケーション管理の詳細については、[Mobile Services のドキュメント ](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html) のAdobeを参照してください。

1. 目標地点を定義します。

   目標地点の管理の詳細については、[AdobeMobile Services のドキュメント ](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html) を参照してください。

### 購読者の目標地点データの収集 {#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーション購読者から収集するデータを定義できます。

この手順については、 SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) を使用したモバイルアプリケーションの設定ページで説明します。[


## 場所データの収集に使用するモバイルアプリへのアクセス {#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaignで正常に作成されたアプリケーションにアクセスするには：

1. 左上隅の **Adobe** ロゴをクリックします。
1. SDK に応じて、 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** または **[!UICONTROL Mobile app (AEP SDK)]** を選択します。
1. リストからモバイルアプリを選択して、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリケーションの購読者のリストも「**[!UICONTROL Mobile application subscribers]**」タブに表示されます。 購読者とは、モバイルデバイスにアプリケーションをインストールしたすべてのユーザーを指します。 Adobe Campaignデータベースプロファイルは、登録トークンで識別されます。

## 収集された場所データへのアクセス {#accessing-collected-location-data}

設定が完了すると、収集した目標地点データが各プロファイルの「**[!UICONTROL Places]**」タブに表示されます。 リストにアクセスするには：

1. プロファイルを選択します。
1. 右側の **[!UICONTROL Edit profile properties]** ボタンをクリックします。
1. 「**[!UICONTROL Places]**」タブを選択します。

   ![](assets/poi_profile_places.png)

現在のプロファイルで収集された目標地点データが表示されます。 場所データは、Adobe Campaignデータベースに 6 ヶ月間保存されます。

プロファイルへのアクセスと編集について詳しくは、[ プロファイル ](../../audiences/using/about-profiles.md) を参照してください。
