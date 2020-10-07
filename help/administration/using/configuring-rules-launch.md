---
title: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
description: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# Adobe Campaign Standard の使用例をサポートするための Launch ルールの設定 {#configuring-rules-launch}

で [!DNL Adobe Experience Platform Launch]は、PIIやその他のデータをモバイルアプリケーションからに送信するデータ要素とルールを作成する必要があり [!DNL Adobe Campaign Standard]ます。

のすべての設定の変更を有効にするに [!DNL Adobe Experience Platform Launch] は、これらの変更を発行する必要があります。 詳しくは、 [発行を参照してください](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)。

でルールを作成するに [!DNL Experience Platform Launch]は、次の手順に従います。

1. [データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [サポートする使用例のルール](../../administration/using/configuring-rules-launch.md#create-data-elements) :
   * [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [アプリ内追跡ポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [プッシュ通知追跡ポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [場所のポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

## データ要素の作成 {#create-data-elements}

で作成することをお勧めするデータ要素を次に示し [!DNL Experience Platform Launch]ます。
必要に応じて、追加のデータ要素を作成できます。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

これらのデータ要素を作成するには：

1. で、モバイルアプリケ [!DNL Experience Platform Launch]ーションダッシュボードの **[!UICONTROL Data Elements]** タブをクリックします。

1. データ要素を作成するには、 **[!UICONTROL Experience Cloud ID]** をクリックし **[!UICONTROL Create New Data Element]**&#x200B;ます。

1. 例えば、 **[!UICONTROL Name]** フィールドに「 **mcid**」と入力します。

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. 次 **[!UICONTROL Experience Cloud ID]** に、「 **[!UICONTROL Data element]** タイプ」ドロップダウンで、

   ![](assets/do-not-localize/rules_1.png)

1. Pkeyデータ要素を作成するには、をクリックし **[!UICONTROL Add data element]**&#x200B;ます。

1. 例えば、 **[!UICONTROL Name]** フィールドに「 **pkey**」と入力します。

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. 次 **[!UICONTROL pkey]** に、「 **[!UICONTROL Data element]** タイプ」ドロップダウンで、

1. キャンペーンサーバーのデータ要素を作成するには、をクリックし **[!UICONTROL Add data element]**&#x200B;ます。

1. フィールドに名前を入力します(例： **[!UICONTROL Name]** camp-server ****)。

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. 次 **[!UICONTROL Campaign Server]** に、「 **[!UICONTROL Data element]** タイプ」ドロップダウンリストで、

## ルールの作成 {#creating-rules}

次のルールを作成する必要があります。

* [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
* [アプリ内追跡ポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [プッシュ通知追跡ポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [場所のポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

### PIIポストバック {#pii-postback}

>[!NOTE]
>
>モバイルアプリからAdobe CampaignにPII情報を送信するには、SDK APIを実装する必要があります。 詳しくは、CollectPIIを参照して [ください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)。

PIIデータをに送信するに [!DNL Adobe Campaign Standard]は、次の場所でルールを作成し [!DNL Experience Platform Launch]ます。

1. で、モバイルアプリケ [!DNL Experience Platform Launch]ーションダッシュボードの **[!UICONTROL Rules]** タブをクリックし、次に **[!UICONTROL Create New Rule]**。

1. 名前を入力します(例：「 **Mobile Core - Collect PII**」)。

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. 次 **[!UICONTROL Collect PII]** に、ドロッ **[!UICONTROL Event type]** プダウン内です。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. 次 **[!UICONTROL Send PII]** に、ドロッ **[!UICONTROL Action type]** プダウン内です。

1. に、次 **[!UICONTROL URL]**&#x200B;のURLを入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. チェックボックスをオンに **[!UICONTROL Add Post Body]** します。

1. に、次 **[!UICONTROL Post Body]**&#x200B;のように入力します。

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   marketingCloudIdを使用すると、アプリの購読者をデータベース内の受信者と紐付けることができます。その結果、アプリの購読者をデータベース内のデータと紐付けることが必要になります。 ビジネスニーズに応じて、他のキーと値のペアを指定できます。 上記の例では、Email、First Name、Last Nameがアプリから渡されています。

   キー（cusEmail、cusFirstName、cusLastNameなど）は、Adobe Campaign Standardインスタンスのカスタムリソースで定義されているフィールドIDと一致する必要があります。 値の変数（email、firstName、LastNameなど）は、アプリコードからAMS collectPII APIを呼び出すときにモバイルアプリから送信されるJSONデータ内のキーと一致する必要があります。

   また、イベントトリガーに応じて、ライフサイクルデータをCollect PIIポストバックに渡したり、別のポストバックに渡したりすることもできます。 ライフサイクルデータJSONの例を次に示します。

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   で定義するデータ要素は、%%mcid%%のように重複の割合で囲み、アプリのコンテキスト変数は、%contextdata.email%のように1つの割合で囲む必要があります。 [!DNL Experience Platform Launch]

1. 「 **[!UICONTROL Content Type]** application/json **」と入力します**。

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_2.png)

これで、ユーザーデータがキャンペーンに送信されるように設定されました。

### アプリ内追跡ポストバック {#inapp-tracking-postback}

モバイルアプリケーションでユーザーがアプリ内メッセージ [!DNL Adobe Campaign Standard] とどのようにやり取りするかに関するレポートを得るために、にトラッキングデータを送信するには、次のルールを作成し [!DNL Experience Platform Launch]ます。

1. で、モバイルアプリケ [!DNL Experience Platform Launch]ーションダッシュボードから **[!UICONTROL Rules]** タブを選択し、をクリックし **[!UICONTROL Add Rule]**&#x200B;ます。

1. 名前を入力します(例： **Adobe Campaign — アプリ内クリック追跡**)。

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. 次 **[!UICONTROL In-App click tracking]** に、ドロッ **[!UICONTROL Event type]** プダウン内です。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. 次 **[!UICONTROL Send postback]** に、ドロッ **[!UICONTROL Event type]** プダウン内です。

1. に、次 **[!UICONTROL URL]**&#x200B;のURLを入力します。

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. チェックボックスをオンに **[!UICONTROL Add post body]** します。

1. に、 **[!UICONTROL Post Body]**{} **と入力します**。

1. 「 **[!UICONTROL Content Type]** application/json **」と入力します**。

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_3.png)

### プッシュ通知追跡ポストバック {#push-tracking-postback}

プッシュ通知配信 [!DNL Adobe Campaign Standard]やユーザーによるモバイルアプリケーションとのインタラクションを追跡できるように、にトラッキングデータを送信するには、でルールを作成する必要があり [!DNL Experience Platform Launch]ます。

プッシュ追跡について詳しくは、 [プッシュ追跡を参照してください](../../administration/using/push-tracking.md)。

アプリのアクションを追跡するには、trackAction APIを使用します。 詳しくは、「アプリのアクションを [追跡](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

1. で、モバイルアプリケ [!DNL Experience Platform Launch]ーションダッシュボードの **[!UICONTROL Rules]** タブをクリックし、をクリックし **[!UICONTROL Add Rule]**&#x200B;ます。

1. 名前を入力します(例： **Adobe Campaign — プッシュクリック追跡**)。

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. 次 **[!UICONTROL Track Action]** に、ドロッ **[!UICONTROL Event type]** プダウン内です。

1. ドロップダウンから、 **[!UICONTROL Action]** を選択し **[!UICONTROL Action]**、を選択し **[!UICONTROL equals]**&#x200B;て、 **追跡を入力します**。

1. 「**[!UICONTROL Keep changes]**」をクリックします。次に、 **[!UICONTROL Actions]** セクションでをクリックし **[!UICONTROL Add]**&#x200B;ます。

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. 次 **[!UICONTROL Send postback]** に、ドロッ **[!UICONTROL Action type]** プダウン内です。

1. に、次 **[!UICONTROL URL]**&#x200B;のURLを入力します。

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. チェックボックスをオンに **[!UICONTROL Add post body]** します。

1. 追加投稿本文（例： { }）。

1. 「 **[!UICONTROL Content Type]** application/json **」と入力します**。

1. In **[!UICONTROL Timeout]**, select 0.

### 場所のポストバック {#location-postback}

1. で、モバイルアプリケ [!DNL Experience Platform Launch]ーションダッシュボードの **[!UICONTROL Rules]** タブをクリックし、をクリックし **[!UICONTROL Add Rule]**&#x200B;ます。

1. 名前を入力します(例：「 **Location postback**」)。

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. 例えば、POIと入力する、POIと入力する、POIと入力するなどのイベントを作成します。 ドロップダウンから **[!UICONTROL Extension]** 、 **[Places - Beta**]を選択します。 次に、ドロップダウンにPOI **** または **Exit POI****[!UICONTROL Event type]** と入力します。

1. 名前を入力します(例： **Places - Beta - Enter POI** 、 **Exit POI**)。

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. 次 **[!UICONTROL Send postback]** に、ドロップダウン **[!UICONTROL Action type]** から。

1. 名前を入力します(例： **Mobile Core - Send Location Postback**)。

1. に、次 **[!UICONTROL URL]**&#x200B;のURLを入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. この **[!UICONTROL Add post body]** チェックボックスを選択し、投稿本文を追加します。次に例を示します。

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >上の例では、データ要素の [!DNL Experience Platform Launch] 作成の手順を利用して、右側のデータ要素をで設定する必要があり [ます](../../administration/using/configuring-rules-launch.md#create-data-elements)。 左側のデータ要素はでサポートされてい [!DNL Adobe Campaign Standard] るので、設定は不要です。 追加のデータが必要な場合は、でカスタムリソース拡張を実行する必要があり [!DNL Adobe Campaign Standard]ます。

1. 「 **[!UICONTROL Content Type]** application/json **」と入力します**。

1. In **[!UICONTROL Timeout]**, select 5.

   ![](assets/do-not-localize/rules_4.png)
