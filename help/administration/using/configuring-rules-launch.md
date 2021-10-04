---
title: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
description: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 1%

---

# Adobe Campaign Standard のユースケースをサポートするための Launch ルールの設定 {#configuring-rules-launch}

[!DNL Adobe Experience Platform Launch] で、PII やその他のデータをモバイルアプリケーションから [!DNL Adobe Campaign Standard] に送信するためのデータ要素とルールを作成します。

[!DNL Adobe Experience Platform Launch] 内のすべての設定変更を有効にするには、これらの変更を公開する必要があります。 詳しくは、[ 公開 ](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration) を参照してください。

[!DNL Experience Platform Launch] でルールを作成するには、次の手順に従います。

1. [データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [サポート](../../administration/using/configuring-rules-launch.md#create-data-elements) するユースケースのルールの作成：
   * [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [アプリ内トラッキングポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [プッシュ通知トラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [場所ポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

## データ要素の作成 {#create-data-elements}

[!DNL Experience Platform Launch] で作成することをお勧めするデータ要素を次に示します。
必要に応じて、追加のデータ要素を作成できます。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

次のデータ要素を作成するには：

1. [!DNL Experience Platform Launch] のモバイルアプリケーションダッシュボードで、「**[!UICONTROL Data Elements]**」タブをクリックします。

1. **[!UICONTROL Experience Cloud ID]** データ要素を作成するには、**[!UICONTROL Create New Data Element]** をクリックします。

1. **[!UICONTROL Name]** フィールドに、例えば **mcid** と入力します。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Data element]** タイプのドロップダウンで **[!UICONTROL Experience Cloud ID]** を入力します。

   ![](assets/do-not-localize/rules_1.png)

1. Pkey データ要素を作成するには、**[!UICONTROL Add data element]** をクリックします。

1. **[!UICONTROL Name]** フィールドに、例えば **pkey** と入力します。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、**[!UICONTROL Data element]** タイプのドロップダウンで **[!UICONTROL pkey]** を入力します。

1. Campaign サーバーのデータ要素を作成するには、**[!UICONTROL Add data element]** をクリックします。

1. **[!UICONTROL Name]** フィールドに名前を入力します（例：**camp-server**）。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、**[!UICONTROL Data element]** タイプのドロップダウンで **[!UICONTROL Campaign Server]** を指定します。

## ルールの作成 {#creating-rules}

次のルールを作成する必要があります。

* [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
* [アプリ内トラッキングポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [プッシュ通知トラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [場所ポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

### PII ポストバック {#pii-postback}

>[!NOTE]
>
>モバイルアプリからAdobe Campaignに PII 情報を送信するには、SDK API を実装する必要があります。 詳しくは、[CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii) を参照してください。

PII データを [!DNL Adobe Campaign Standard] に送信するには、[!DNL Experience Platform Launch] にルールを作成します。

1. [!DNL Experience Platform Launch] で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Create New Rule]**」をクリックします。

1. 名前を入力します（例：**Mobile Core - Collect PII**）。

1. **[!UICONTROL Events]** セクションで、**[!UICONTROL Add]** をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Event type]** ドロップダウンで **[!UICONTROL Collect PII]** を選択します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. **[!UICONTROL Actions]** セクションで、**[!UICONTROL Add]** をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Action type]** ドロップダウンで **[!UICONTROL Send PII]** を選択します。

1. **[!UICONTROL URL]** に、次の URL を入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. **[!UICONTROL Add Post Body]** チェックボックスをオンにします。

1. **[!UICONTROL Post Body]** に、次のように入力します。

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   marketingCloudId を使用すると、アプリの購読者とデータベース内の受信者を紐付けでき、その結果、が必要になります。 ビジネスのニーズに応じて、他のキーと値のペアを指定できます。 上記の例では、アプリから電子メール、名、姓が渡されています。

   キー（例えば、cusEmail、cusFirstName、cusLastName）は、Adobe Campaign Standardインスタンスのカスタムリソースで定義されたフィールド ID と一致する必要があります。 値の変数（email、firstName、LastName など）は、アプリコードから AMS collectPII API を呼び出す際にモバイルアプリから送信される JSON データのキーと一致する必要があります。

   また、ライフサイクルデータを、イベントデータに応じて PII ポストバックを収集または別のポストバックに渡すこともできます。トリガー ライフサイクルデータ JSON の例を次に示します。

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   [!DNL Experience Platform Launch] で定義するデータ要素は、%%mcid%%のように 2 倍の割合で囲み、アプリのコンテキスト変数は%contextdata.email%のように 1 つの割合で囲む必要があります。

1. **[!UICONTROL Content Type]** で、**application/json** と入力します。

1. **[!UICONTROL Timeout]** で、「0」を選択します。

   ![](assets/do-not-localize/rules_2.png)

これで、ユーザーデータが Campaign に送信されるように設定されました。

### アプリ内トラッキングポストバック {#inapp-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0 以降または iOS ACPCore v2.3.0 以降を使用している場合、トラッキングポストバックを設定する必要はありません。

モバイルアプリケーションでユーザーがアプリ内メッセージとどのようにやり取りするかを報告するために、[!DNL Adobe Campaign Standard] にトラッキングデータを送信するには、[!DNL Experience Platform Launch] で次のルールを作成します。

1. [!DNL Experience Platform Launch] で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブを選択し、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します ( 例：**Adobe Campaign — アプリ内クリック追跡**)。

1. **[!UICONTROL Events]** セクションで、**[!UICONTROL Add]** をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、**[!UICONTROL Event type]** ドロップダウンで **[!UICONTROL In-App click tracking]** を選択します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. **[!UICONTROL Actions]** セクションで、**[!UICONTROL Add]** をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Event type]** ドロップダウンで **[!UICONTROL Send postback]** を選択します。

1. **[!UICONTROL URL]** に、次の URL を入力します。

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. **[!UICONTROL Add post body]** チェックボックスをオンにします。

1. **[!UICONTROL Post Body]** に、**{}** と入力します。

1. **[!UICONTROL Content Type]** で、**application/json** と入力します。

1. **[!UICONTROL Timeout]** で、「0」を選択します。

   ![](assets/do-not-localize/rules_3.png)

### プッシュ通知トラッキングポストバック {#push-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0 以降または iOS ACPCore v2.3.0 以降を使用している場合、トラッキングポストバックを設定する必要はありません。

プッシュ通知配信とユーザーのモバイルアプリケーションとのやり取りを追跡するのに役立つトラッキングデータを [!DNL Adobe Campaign Standard] に送信するには、[!DNL Experience Platform Launch] にルールを作成する必要があります。

プッシュトラッキングについて詳しくは、[ プッシュトラッキング ](../../administration/using/push-tracking.md) を参照してください。

アプリのアクションを追跡するには、 trackAction API を使用します。 詳しくは、[ アプリのアクションの追跡 ](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions) を参照してください。

1. [!DNL Experience Platform Launch] のモバイルアプリケーションダッシュボードで、「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します ( 例：**Adobe Campaign — プッシュクリック追跡**)。

1. **[!UICONTROL Events]** セクションで、**[!UICONTROL Add]** をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Event type]** ドロップダウンで **[!UICONTROL Track Action]** を選択します。

1. 「**[!UICONTROL Action]**」ドロップダウンから「**[!UICONTROL Action]**」を選択し、「**[!UICONTROL equals]**」を選択して、「**tracking**」と入力します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。次に、「**[!UICONTROL Actions]**」セクションで「**[!UICONTROL Add]**」をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Action type]** ドロップダウンで **[!UICONTROL Send postback]** を選択します。

1. **[!UICONTROL URL]** に、次の URL を入力します。

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. **[!UICONTROL Add post body]** チェックボックスをオンにします。

1. 投稿の本文を追加します（例： { } ）。

1. **[!UICONTROL Content Type]** で、**application/json** と入力します。

1. **[!UICONTROL Timeout]** で、「0」を選択します。

### 場所ポストバック {#location-postback}

1. [!DNL Experience Platform Launch] のモバイルアプリケーションダッシュボードで、「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前を入力します（例：**Location postback**）。

1. **[!UICONTROL Events]** セクションで、**[!UICONTROL Add]** をクリックします。

1. イベント（「POI を入力」や「POI を終了」など）を作成します。 「**[!UICONTROL Extension]**」ドロップダウンから「**Places - Beta**」を選択します。 次に、****[!UICONTROL Event type]**ドロップダウンに POI** または **出口 POI** と入力します。

1. 名前を入力します（例： **Places - Beta - POI** または **Exit POI**）。

1. **[!UICONTROL Actions]** セクションで、**[!UICONTROL Add]** をクリックします。

1. 「**[!UICONTROL Extension]**」ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Action type]** ドロップダウンから **[!UICONTROL Send postback]** を選択します。

1. 名前を入力します（例：**Mobile Core - Send Location Postback**）。

1. **[!UICONTROL URL]** に、次の URL を入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 「**[!UICONTROL Add post body]**」チェックボックスを選択して、次のように投稿本文を追加します。

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
   >上記の例では、[ データ要素の作成 ](../../administration/using/configuring-rules-launch.md#create-data-elements) の手順を利用して、右側のデータ要素を [!DNL Experience Platform Launch] で設定する必要があります。 左側のデータ要素は [!DNL Adobe Campaign Standard] でサポートされており、設定は不要です。 追加のデータが必要な場合は、[!DNL Adobe Campaign Standard] でカスタムリソース拡張を実行する必要があります。

1. **[!UICONTROL Content Type]** で、**application/json** と入力します。

1. **[!UICONTROL Timeout]** で、「5」を選択します。

   ![](assets/do-not-localize/rules_4.png)
