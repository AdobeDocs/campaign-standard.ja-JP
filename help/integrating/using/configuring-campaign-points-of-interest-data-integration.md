---
title: Campaign と POI データの統合の設定
description: Adobe Campaignの目標点データ機能を設定して、購読者の場所に基づいてパーソナライズされたメッセージを送信する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 1%

---

# Campaign と POI データの統合の設定{#configuring-campaign-points-of-interest-data-integration}

## Adobe Experience Platform SDK を使用した Campaign と POI データの統合の設定 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>モバイルアプリケーションは、Adobe Experience Platform SDKを使用してAdobe Campaign Standardで既に設定されている必要があります。 詳細な手順については、こちらの [ ページ ](https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html) を参照してください。

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaign インターフェイスで **管理者** が設定する必要があります。

Adobe Experience Platform SDKで設定されたモバイルアプリケーションでAdobe Experience Platform ロケーションサービスを使用するには、次が必要です。

1. データ収集 UI のモバイルアプリ設定に **[!UICONTROL Places]** 拡張機能を追加します。 Adobe Campaignでモバイルアプリケーションを設定します。 [Places 拡張機能のインストール ](https://developer.adobe.com/client-sdks/solution/places) を参照してください。

1. 拡張機能を設定したら、データ収集 UI 内でデータ要素を作成して、これらの拡張機能からデータを取得します。 データ要素を作成するには、この [ ページ ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) を参照してください。

1. 次に、データ収集 UI で、目標点とAdobe Campaignの間のモバイルユースケースをサポートするルールを作成する必要があります。\
   このルールは、ユーザーが地域 **[!UICONTROL Point of Interest]** 囲に入るとトリガーされます。 ルールを作成するには、この [ ページ ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) を参照してください。

1. **[!UICONTROL Points of Interest]** を場所で定義します。 [ 目標点の作成 ](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html) を参照してください。

1. モバイルアプリケーションと、収集したAdobe Campaignの場所データに必ずアクセスしてください。 [ 場所データの収集に使用するモバイルアプリへのアクセス ](#accessing-mobile-apps-used-to-collect-location-data) および [ 収集された場所データへのアクセス ](#accessing-collected-location-data) を参照してください。

## SDK V4 を使用した Campaign と POI データの統合の設定 {#configuring-campaign-poi-sdkv4}

場所データの収集に使用するモバイルアプリケーションは、Adobe Campaign インターフェイスで **管理者** が設定する必要があります。

SDK V4 で設定されたモバイルアプリケーションで目標点データ機能を使用するには、次の操作が必要です。

1. モバイル用Adobe Analyticsにアクセスできる。 詳細については、使用許諾契約書を確認するか、Adobeアカウント担当者にお問い合わせください。
1. Adobe Campaignでモバイルアプリケーションを設定します。 [Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照してください。
1. Adobe Mobile Services インターフェイスでモバイルアプリケーションを設定します。 これにより、Adobeモバイルサービスで収集されたデータをAdobe Campaignに確実に送信できます。 [Adobe Mobile Services でのモバイルアプリの設定 ](#configuring-a-mobile-app-in-adobe-mobile-services) を参照してください。
1. モバイルアプリケーション固有の設定を実行します。

   * Adobe Mobile Services インターフェイスからダウンロードした設定ファイルをモバイルアプリケーションとパッケージ化します。
   * Experience CloudのモバイルSDKをモバイルアプリケーションに統合します。 [ モバイルアプリケーションへのSDKの統合 ](#integrating-the-sdk-into-a-mobile-application) を参照してください。

1. Adobe Mobile Services インターフェイスで目標地点を定義します。 [Adobeモバイルサービスにおける目標点の定義 ](#defining-points-of-interest-in-adobe-mobile-services) を参照してください。
1. モバイルアプリケーションの購読者から収集するデータを定義します。 [ 購読者の興味ポイントに関するデータの収集 ](#collecting-subscribers--points-of-interest-data) を参照してください。
1. モバイルアプリケーションと、収集したAdobe Campaignの場所データに必ずアクセスしてください。 [ 場所データの収集に使用するモバイルアプリへのアクセス ](#accessing-mobile-apps-used-to-collect-location-data) および [ 収集された場所データへのアクセス ](#accessing-collected-location-data) を参照してください。

### SDK V4 を使用したAdobe Campaignでのモバイルアプリの設定 {#setting-up-a-mobile-app-in-campaign}

Adobe Campaignで目標地点データを収集できるようにするには、Adobe Campaignがデータを受信するモバイルアプリケーションを設定する必要があります。

1. 左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、**&#x200B;[!UICONTROL Administration]&#x200B;**/**&#x200B;[!UICONTROL Channels]&#x200B;**/**&#x200B;[!UICONTROL Mobile app]&#x200B;**を選択します。**
1. 「**[!UICONTROL Create]**」をクリックしてアプリケーションを設定します。
1. **[!UICONTROL Application name]** フィールドに名前を入力し、「**[!UICONTROL Create]**」をクリックします。

   **[!UICONTROL Device-specific settings]** のセクションには入力しないでください。 これは、プッシュ通知を受信するアプリケーションの設定にのみ適用されます。

**[!UICONTROL Mobile application properties]** セクションには、**[!UICONTROL Collect PII endpoint]** と **[!UICONTROL Location Services endpoint]** の 2 つの URL が一覧表示されます。 これらは、Adobeの Mobile Services インターフェイスで使用されます。 [Adobe Mobile Services でのモバイルアプリの設定 ](#configuring-a-mobile-app-in-adobe-mobile-services) を参照してください。

* **[!UICONTROL Collect PII endpoint]** URL は、モバイルアプリケーションの起動時に、ユーザーのExperience CloudID と登録トークンを収集するために使用されます。 ユーザーがメール、名、姓などの資格情報を使用してアプリケーションにログインすると、このデータも収集され、ユーザーの登録トークンをAdobe Campaign プロファイルと照合するために使用されます。
* **[!UICONTROL Location Services endpoint]** URL は、ユーザーの緯度、経度、半径などの位置データを目標点から収集するために使用されます。

[Adobe Mobile Services でのモバイルアプリの設定 ](#configuring-a-mobile-app-in-adobe-mobile-services) の節で説明しているように、Adobe Mobile Services でこれらの値を使用して設定を完了できるようになりました。

![](assets/poi_mobile_app_properties.png)

### Adobe Mobile Services での V4 モバイルアプリの設定 {#configuring-a-mobile-app-in-adobe-mobile-services}

Adobe Mobile Services によって収集されたデータをAdobe Campaignに送信するには、Mobile Services インターフェイスでポストバックを設定する必要があります。

Adobe Campaignで設定されたモバイルアプリケーションのパラメーターで見つけることができる具体的な情報が必要です（[Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照）。

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

次の設定を行うには、Adobe Analyticsにアクセスできる必要があります。 Adobe Analytics ユーザーでない場合は、Adobe Campaign管理者にお問い合わせください。

1. [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/) にログインします。
1. アプリケーションを作成するか、既存のアプリケーションを選択します。
1. **[!UICONTROL Manage App Settings]** のページに移動します。
1. 「**訪問者 ID サービス**」セクションで、「**有効にする** をオンにし、ドロップダウンリストから組織を選択します。 「**保存**」をクリックします。

   >[!CAUTION]
   >
   >この組織は、Adobe Campaign インスタンスで使用する組織と同じである必要があります。

1. 「**[!UICONTROL Manage Postbacks]**」をクリックします。
1. ポストバックを作成します。

   * **[!UICONTROL Postback Type]** として **[!UICONTROL PII]** を選択します。
   * 「**[!UICONTROL URL]**」フィールドで、Adobe Campaign インターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Collect PII Endpoint]** URL をコピーし、先頭にサーバー名を付けます。 [Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照してください。
   * **[!UICONTROL Post Body]** フィールドに次のように入力します。

     iOS用：

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

     Android用：

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

   * **コンテンツタイプ** を **[!UICONTROL application/json]** のように設定します。
   * **どのデータタグがポストバックをトリガーにするか？任意** イベント（通常は **[!UICONTROL Launched]** と **[!UICONTROL exists]**）を選択します。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

1. 2 番目のポストバックを作成します。

   * **[!UICONTROL Postback Type]** として **[!UICONTROL Postback]** を選択します。
   * 「**[!UICONTROL URL]**」フィールドで、Adobe Campaign インターフェイスで設定したモバイルアプリケーションから **[!UICONTROL Location Services Endpoint]** URL をコピーし、先頭にサーバー名を付けます。 [Campaign でのモバイルアプリの設定 ](#setting-up-a-mobile-app-in-campaign) を参照してください。
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

   * **コンテンツタイプ** を **[!UICONTROL application/json]** のように設定します。
   * **どのデータタグがポストバックをトリガーにするか？**、**[!UICONTROL campaign.test]** と **[!UICONTROL exists]** を選択します。
   * 「**[!UICONTROL Save & Activate]**」をクリックします。

>[!NOTE]
>
>ポストバックの構成の詳細については、[Adobe Mobile Services ドキュメント ](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html) を参照してください。

### モバイルアプリケーションへのSDKの統合 {#integrating-the-sdk-into-a-mobile-application}

Mobile コアサービスのソフトウェア開発キット（SDK）は、モバイルアプリケーションのAdobe Campaignへの統合を容易にします。

この手順については、この [ ページ ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) を参照してください。

### Adobeモバイルサービスの目標点の定義 {#defining-points-of-interest-in-adobe-mobile-services}

位置データの収集に使用する目標点を定義する手順は、次のとおりです。

1. Adobe Mobile Services インターフェイスに移動します。
1. アプリケーションを追加します。

   Mobile Services でのアプリケーションの管理について詳しくは、[Mobile Services のAdobeドキュメント ](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html) を参照してください。

1. 目標点を定義します。

   POI の管理について詳しくは、[Adobe Mobile Services ドキュメント ](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html) を参照してください。

### 購読者の POI データの収集 {#collecting-subscribers--points-of-interest-data}

特定のカスタムリソースを使用すると、アプリケーションの購読者から収集するデータを定義できます。

この手順については、[SDK V4 を使用したモバイルアプリケーションの設定 ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) ページで説明します。

## 場所データの収集に使用するモバイルアプリへのアクセス {#accessing-mobile-apps-used-to-collect-location-data}

Adobe Campaignで正常に作成されたアプリケーションにアクセスするには：

1. 左上隅の **Adobe** ロゴをクリックします。
1. SDKに応じて、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (SDK v4)]** または **[!UICONTROL Mobile app (AEP SDK)]** を選択します。
1. リストからモバイルアプリケーションを選択して、そのプロパティを表示します。

   ![](assets/poi_mobile_app_subscribers.png)

アプリケーションの購読者のリストは、「**[!UICONTROL Mobile application subscribers]**」タブにも表示されます。 購読者は、モバイルデバイスにアプリケーションをインストールしたすべてのユーザーです。 Adobe Campaign データベースプロファイルは、登録トークンで識別されます。

## 収集された場所データへのアクセス {#accessing-collected-location-data}

設定が完了すると、収集された POI データが各プロファイルの「**[!UICONTROL Places]**」タブに表示されます。 リストにアクセスするには：

1. プロファイルを選択します。
1. 右側の「**[!UICONTROL Edit profile properties]**」ボタンをクリックします。
1. 「**[!UICONTROL Places]**」タブを選択します。

   ![](assets/poi_profile_places.png)

現在のプロファイルについて収集された POI データが一覧表示されます。 場所のデータは、6 か月間Adobe Campaign データベースに保存されます。

プロファイルへのアクセスと編集について詳しくは、[ プロファイル ](../../audiences/using/about-profiles.md) を参照してください。
