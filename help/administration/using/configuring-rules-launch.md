---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
description: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: インスタンス設定
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 1%

---

# Adobe Campaign Standard のユースケースをサポートするための Launch ルールの設定 {#configuring-rules-launch}

[!DNL Adobe Experience Platform Launch]では、PIIやその他のデータをモバイルアプリケーションから[!DNL Adobe Campaign Standard]に送信するためのデータ要素とルールを作成する必要があります。

[!DNL Adobe Experience Platform Launch]内のすべての設定変更を有効にするには、これらの変更を公開する必要があります。 詳しくは、[公開](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)を参照してください。

[!DNL Experience Platform Launch]にルールを作成するには、次の手順に従います。

1. [データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [サポ](../../administration/using/configuring-rules-launch.md#create-data-elements) ートするユースケースのルールの作成：
   * [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [アプリ内トラッキングポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [プッシュ通知のトラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [場所ポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

## データ要素の作成 {#create-data-elements}

以下に、[!DNL Experience Platform Launch]で作成することをお勧めするデータ要素を示します。
必要に応じて、追加のデータ要素を作成できます。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

次のデータ要素を作成するには：

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Data Elements]**」タブをクリックします。

1. **[!UICONTROL Experience Cloud ID]**&#x200B;データ要素を作成するには、**[!UICONTROL Create New Data Element]**&#x200B;をクリックします。

1. **[!UICONTROL Name]**&#x200B;フィールドに、例えば&#x200B;**mcid**&#x200B;と入力します。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Data element]**&#x200B;タイプのドロップダウンで&#x200B;**[!UICONTROL Experience Cloud ID]**&#x200B;を選択します。

   ![](assets/do-not-localize/rules_1.png)

1. Pkeyデータ要素を作成するには、**[!UICONTROL Add data element]**&#x200B;をクリックします。

1. **[!UICONTROL Name]**&#x200B;フィールドに、例えば&#x200B;**pkey**&#x200B;と入力します。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、**[!UICONTROL Data element]**&#x200B;タイプのドロップダウンで&#x200B;**[!UICONTROL pkey]**&#x200B;を選択します。

1. Campaignサーバーのデータ要素を作成するには、**[!UICONTROL Add data element]**&#x200B;をクリックします。

1. **[!UICONTROL Name]**&#x200B;フィールドに名前を入力します（例：**camp-server**）。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、**[!UICONTROL Data element]**&#x200B;タイプのドロップダウンで&#x200B;**[!UICONTROL Campaign Server]**&#x200B;を指定します。

## ルールの作成 {#creating-rules}

次のルールを作成する必要があります。

* [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
* [アプリ内トラッキングポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [プッシュ通知のトラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [場所ポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

### PIIポストバック {#pii-postback}

>[!NOTE]
>
>モバイルアプリからAdobe CampaignにPII情報を送信するには、SDK APIを実装する必要があります。 詳しくは、[CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)を参照してください。

PIIデータを[!DNL Adobe Campaign Standard]に送信するには、[!DNL Experience Platform Launch]にルールを作成します。

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、次に「**[!UICONTROL Create New Rule]**」をクリックします。

1. 名前を入力します（例：**Mobile Core - Collect PII**）。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL Collect PII]**&#x200B;を選択します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. 「**[!UICONTROL Actions]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Action type]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL Send PII]**&#x200B;を選択します。

1. **[!UICONTROL URL]**&#x200B;に、次のURLを入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 「**[!UICONTROL Add Post Body]**」チェックボックスをオンにします。

1. **[!UICONTROL Post Body]**&#x200B;に、次のように入力します。

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

   marketingCloudIdを使用すると、アプリの購読者とデータベース内の受信者を紐付けでき、その結果、が必要になります。 ビジネスのニーズに応じて、他のキーと値のペアを指定できます。 上記の例では、アプリからEメール、名、姓が渡されています。

   キー（例えば、cusEmail、cusFirstName、cusLastName）は、Adobe Campaign Standardインスタンスのカスタムリソースで定義されたフィールドIDと一致する必要があります。 値の変数（email、firstName、LastNameなど）は、アプリコードからAMS collectPII APIを呼び出す際にモバイルアプリから送信されるJSONデータのキーと一致する必要があります。

   また、イベントデータに応じて、PII収集ポストバックまたは別のポストバックにライフサイクルデータを渡すこともできますトリガー。 ライフサイクルデータJSONの例を次に示します。

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   [!DNL Experience Platform Launch]で定義するデータ要素は、%%mcid%%のように2倍の割合で囲み、アプリのコンテキスト変数は、%contextdata.email%のように1つの割合で囲む必要があります。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「0」を選択します。

   ![](assets/do-not-localize/rules_2.png)

これで、ユーザーデータがCampaignに送信されるように設定されました。

### アプリ内トラッキングポストバック {#inapp-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0以降またはiOS ACPCore v2.3.0以降を使用している場合、トラッキングポストバックを設定する必要はありません。

モバイルアプリケーションでユーザーがアプリ内メッセージとどのようにやり取りするかに関するレポート用に[!DNL Adobe Campaign Standard]にトラッキングデータを送信するには、[!DNL Experience Platform Launch]で次のルールを作成します。

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブを選択し、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します(例：**Adobe Campaign — アプリ内クリック追跡**)。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL In-App click tracking]**&#x200B;を選択します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. 「**[!UICONTROL Actions]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL Send postback]**&#x200B;を選択します。

1. **[!UICONTROL URL]**&#x200B;に、次のURLを入力します。

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 「**[!UICONTROL Add post body]**」チェックボックスをオンにします。

1. **[!UICONTROL Post Body]**&#x200B;に&#x200B;**{}**&#x200B;と入力します。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「0」を選択します。

   ![](assets/do-not-localize/rules_3.png)

### プッシュ通知のトラッキングポストバック {#push-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0以降またはiOS ACPCore v2.3.0以降を使用している場合、トラッキングポストバックを設定する必要はありません。

プッシュ通知配信とユーザーのモバイルアプリケーションとのやり取りを追跡するのに役立つトラッキングデータを[!DNL Adobe Campaign Standard]に送信するには、[!DNL Experience Platform Launch]にルールを作成する必要があります。

プッシュトラッキングについて詳しくは、[プッシュトラッキング](../../administration/using/push-tracking.md)を参照してください。

アプリのアクションを追跡するには、 trackAction APIを使用します。 詳しくは、[アプリのアクションの追跡](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)を参照してください。

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します(例：**Adobe Campaign — プッシュクリック追跡**)。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL Track Action]**&#x200B;を選択します。

1. 「**[!UICONTROL Action]**」ドロップダウンから「**[!UICONTROL Action]**」を選択し、「**[!UICONTROL equals]**」を選択して、「**トラッキング**」と入力します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。次に、「**[!UICONTROL Actions]**」セクションで「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Action type]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL Send postback]**&#x200B;を選択します。

1. **[!UICONTROL URL]**&#x200B;に、次のURLを入力します。

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 「**[!UICONTROL Add post body]**」チェックボックスをオンにします。

1. 投稿本文（例： { }）を追加します。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「0」を選択します。

### 場所ポストバック {#location-postback}

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します（例： **Location postback** ）。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. イベントを作成します（例： POIを入力またはPOIを終了）。 「**[!UICONTROL Extension]**」ドロップダウンから「**Places - Beta**」を選択します。 次に、****[!UICONTROL Event type]**ドロップダウンにPOI**&#x200B;または&#x200B;**出口POI**&#x200B;を入力します。

1. 名前を入力します（例： **Places - Beta - POI**&#x200B;または&#x200B;**Exit POI**）。

1. 「**[!UICONTROL Actions]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Action type]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Send postback]**&#x200B;を選択します。

1. 名前を入力します（例：**Mobile Core - Send Location Postback**）。

1. **[!UICONTROL URL]**&#x200B;に、次のURLを入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 「**[!UICONTROL Add post body]**」チェックボックスを選択して、投稿本文を追加します。次に例を示します。

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
   >上記の例では、[データ要素](../../administration/using/configuring-rules-launch.md#create-data-elements)の作成の手順を利用して、右側のデータ要素を[!DNL Experience Platform Launch]で設定する必要があります。 左側のデータ要素は[!DNL Adobe Campaign Standard]でサポートされており、設定は不要です。 追加のデータが必要な場合は、[!DNL Adobe Campaign Standard]でカスタムリソース拡張を実行する必要があります。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「5」を選択します。

   ![](assets/do-not-localize/rules_4.png)
