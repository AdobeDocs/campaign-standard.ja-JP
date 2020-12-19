---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
description: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# Adobe Campaign Standard の使用例をサポートするための Launch ルールの設定 {#configuring-rules-launch}

[!DNL Adobe Experience Platform Launch]では、PIIや他のデータをモバイルアプリケーションから[!DNL Adobe Campaign Standard]に送信するためのデータ要素とルールを作成する必要があります。

[!DNL Adobe Experience Platform Launch]内のすべての設定変更を有効にするには、これらの変更を発行する必要があります。 詳しくは、[発行](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)を参照してください。

[!DNL Experience Platform Launch]にルールを作成するには、次の手順に従います。

1. [データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [サポートする使用](../../administration/using/configuring-rules-launch.md#create-data-elements) 例のルールの作成：
   * [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [アプリ内追跡ポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [プッシュ通知追跡ポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [場所のポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

## データ要素{#create-data-elements}を作成しています

[!DNL Experience Platform Launch]に作成することをお勧めするデータ要素を以下に示します。
必要に応じて、追加のデータ要素を作成できます。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

これらのデータ要素を作成するには：

1. [!DNL Experience Platform Launch]のモバイルアプリケーションダッシュボードで、「**[!UICONTROL Data Elements]**」タブをクリックします。

1. **[!UICONTROL Experience Cloud ID]**&#x200B;データ要素を作成するには、**[!UICONTROL Create New Data Element]**&#x200B;をクリックします。

1. **[!UICONTROL Name]**&#x200B;フィールドに、例えば&#x200B;**mcid**&#x200B;と入力します。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。 次に&#x200B;**[!UICONTROL Data element]**&#x200B;タイプのドロップダウンで&#x200B;**[!UICONTROL Experience Cloud ID]**&#x200B;を入力します。

   ![](assets/do-not-localize/rules_1.png)

1. Pkeyデータ要素を作成するには、**[!UICONTROL Add data element]**&#x200B;をクリックします。

1. **[!UICONTROL Name]**&#x200B;フィールドに、例えば&#x200B;**pkey**&#x200B;と入力します。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;を選択します。 次に&#x200B;**[!UICONTROL Data element]**&#x200B;タイプのドロップダウンで&#x200B;**[!UICONTROL pkey]**&#x200B;を入力します。

1. キャンペーンサーバーのデータ要素を作成するには、**[!UICONTROL Add data element]**&#x200B;をクリックします。

1. **[!UICONTROL Name]**&#x200B;フィールドに名前を入力します（例：**camp-server**）。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;を選択します。 次に、**[!UICONTROL Data element]**&#x200B;タイプのドロップダウンで&#x200B;**[!UICONTROL Campaign Server]**&#x200B;を指定します。

## ルールの作成{#creating-rules}

次のルールを作成する必要があります。

* [PIIポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
* [アプリ内追跡ポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [プッシュ通知追跡ポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [場所のポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

### PIIポストバック{#pii-postback}

>[!NOTE]
>
>モバイルアプリからAdobe CampaignにPII情報を送信するには、SDK APIを実装する必要があります。 詳細については、[CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)を参照してください。

PIIデータを[!DNL Adobe Campaign Standard]に送信するには、[!DNL Experience Platform Launch]にルールを作成します。

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから&#x200B;**[!UICONTROL Rules]**&#x200B;タブをクリックし、**[!UICONTROL Create New Rule]**&#x200B;をクリックします。

1. 名前を入力します（例：**Mobile Core - Collect PII**）。

1. **[!UICONTROL Events]**&#x200B;セクションで、**[!UICONTROL Add]**&#x200B;をクリックします。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンの&#x200B;**[!UICONTROL Collect PII]**。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. **[!UICONTROL Actions]**&#x200B;セクションで、**[!UICONTROL Add]**&#x200B;をクリックします。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。 次に、**[!UICONTROL Action type]**&#x200B;ドロップダウンの&#x200B;**[!UICONTROL Send PII]**。

1. **[!UICONTROL URL]**&#x200B;に次のURLを入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. **[!UICONTROL Add Post Body]**&#x200B;チェックボックスを選択します。

1. **[!UICONTROL Post Body]**&#x200B;に次のように入力します。

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

   [!DNL Experience Platform Launch]で定義するデータ要素は、重複の割合（%%mcid%%など）で囲む必要があります。また、アプリのコンテキスト変数は、%contextdata.email%など、1つの割合で囲む必要があります。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「0」を選択します。

   ![](assets/do-not-localize/rules_2.png)

これで、ユーザーデータがキャンペーンに送信されるように設定されました。

### アプリ内トラッキングポストバック{#inapp-tracking-postback}

モバイルアプリケーションでユーザーがアプリ内メッセージをどのように操作するかに関するレポートを得るために、トラッキングデータを[!DNL Adobe Campaign Standard]に送信するには、[!DNL Experience Platform Launch]に次のルールを作成します。

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブを選択し、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します(例：**Adobe Campaign — アプリ内クリック追跡**)。

1. **[!UICONTROL Events]**&#x200B;セクションで、**[!UICONTROL Add]**&#x200B;をクリックします。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンの&#x200B;**[!UICONTROL In-App click tracking]**。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. **[!UICONTROL Actions]**&#x200B;セクションで、**[!UICONTROL Add]**&#x200B;をクリックします。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンの&#x200B;**[!UICONTROL Send postback]**。

1. **[!UICONTROL URL]**&#x200B;に次のURLを入力します。

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. **[!UICONTROL Add post body]**&#x200B;チェックボックスを選択します。

1. **[!UICONTROL Post Body]**&#x200B;に&#x200B;**{}**&#x200B;と入力します。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「0」を選択します。

   ![](assets/do-not-localize/rules_3.png)

### プッシュ通知トラッキングポストバック{#push-tracking-postback}

プッシュ通知配信およびユーザーによるモバイルアプリケーションとのインタラクションを追跡するのに役立つ追跡データを[!DNL Adobe Campaign Standard]に送信するには、[!DNL Experience Platform Launch]にルールを作成する必要があります。

プッシュ追跡について詳しくは、[プッシュ追跡](../../administration/using/push-tracking.md)を参照してください。

アプリのアクションを追跡するには、trackAction APIを使用します。 詳しくは、[アプリのアクションを追跡](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)を参照してください。

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します(例：**Adobe Campaign — プッシュクリック追跡**)。

1. **[!UICONTROL Events]**&#x200B;セクションで、**[!UICONTROL Add]**&#x200B;をクリックします。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。 次に、**[!UICONTROL Event type]**&#x200B;ドロップダウンの&#x200B;**[!UICONTROL Track Action]**。

1. 「**[!UICONTROL Action]**」ドロップダウンから「**[!UICONTROL Action]**」を選択し、「**[!UICONTROL equals]**」を選択して、「**追跡**」と入力します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。次に、**[!UICONTROL Actions]**&#x200B;セクションで&#x200B;**[!UICONTROL Add]**&#x200B;をクリックします。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。 次に、**[!UICONTROL Action type]**&#x200B;ドロップダウンの&#x200B;**[!UICONTROL Send postback]**。

1. **[!UICONTROL URL]**&#x200B;に次のURLを入力します。

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. **[!UICONTROL Add post body]**&#x200B;チェックボックスを選択します。

1. 追加投稿本文（例： { }）。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「0」を選択します。

### ポストバック{#location-postback}

1. [!DNL Experience Platform Launch]で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します（例：**ポストバック**）。

1. **[!UICONTROL Events]**&#x200B;セクションで、**[!UICONTROL Add]**&#x200B;をクリックします。

1. 例えば、POIと入力する、POIと入力する、POIと入力するなどのイベントを作成します。 「**[!UICONTROL Extension]**」ドロップダウンから「**場所 — ベータ版**」を選択します。 次に、****[!UICONTROL Event type]**ドロップダウンにPOI**&#x200B;または&#x200B;**出口POI**&#x200B;と入力します。

1. 名前を入力します（例：**場所 — ベータ — POI**&#x200B;または&#x200B;**出口POI**）。

1. **[!UICONTROL Actions]**&#x200B;セクションで、**[!UICONTROL Add]**&#x200B;をクリックします。

1. **[!UICONTROL Extension]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。 次に、**[!UICONTROL Action type]**&#x200B;ドロップダウンから&#x200B;**[!UICONTROL Send postback]**&#x200B;を選択します。

1. 名前を入力します（例：**Mobile Core - Send Location Postback**）。

1. **[!UICONTROL URL]**&#x200B;に次のURLを入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. **[!UICONTROL Add post body]**&#x200B;チェックボックスを選択し、投稿本文を追加します。例：

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
   >上の例では、[データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements)の手順を活用して、右側のデータ要素を[!DNL Experience Platform Launch]に設定する必要があります。 左側のデータ要素は[!DNL Adobe Campaign Standard]でサポートされており、設定は不要です。 追加のデータが必要な場合は、[!DNL Adobe Campaign Standard]でカスタムリソース拡張を行う必要があります。

1. **[!UICONTROL Content Type]**&#x200B;に、**application/json**&#x200B;と入力します。

1. **[!UICONTROL Timeout]**&#x200B;で、「5」を選択します。

   ![](assets/do-not-localize/rules_4.png)
