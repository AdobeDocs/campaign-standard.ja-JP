---
title: Adobe Campaign Standard のユースケースをサポートするタグルールの設定
description: Adobe Campaign Standardのユースケースをサポートするタグルールの設定方法を説明します
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 2%

---

# Adobe Campaign Standard のユースケースをサポートするタグルールの設定 {#configuring-rules-launch}

データ収集 UI で、データ要素とルールを作成して、モバイルアプリケーションから [!DNL Adobe Campaign Standard] に PII やその他のデータを送信します。

データ収集 UI のすべての設定変更を有効にするには、これらの変更を公開する必要があります。 詳しくは、「[&#x200B; 公開 &#x200B;](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)」を参照してください。

データ収集 UI でルールを作成するには、次の手順に従います。

1. [データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [&#x200B; ルールの作成 &#x200B;](../../administration/using/configuring-rules-launch.md#create-data-elements)：サポートを必要とするユースケースに対応
   * [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [アプリ内トラッキングのポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [ポストバックを追跡するプッシュ通知](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [場所のポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

## データ要素の作成 {#create-data-elements}

データ収集 UI で作成することをお勧めするデータ要素は次のとおりです。
必要に応じて、追加のデータ要素を作成できます。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

これらのデータ要素を作成するには：

1. データ収集 UI で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Data Elements]**」タブをクリックします。

1. **[!UICONTROL Experience Cloud ID]** データ要素を作成するには、「**[!UICONTROL Create New Data Element]**」をクリックします。

1. 例えば、「**[!UICONTROL Name]**」フィールドに **mcid** と入力します。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、**[!UICONTROL Data element]** のタイプ ドロップダウンで **[!UICONTROL Experience Cloud ID]** をクリックします。

   ![](assets/do-not-localize/rules_1.png)

1. Pkey データ要素を作成するには、[**[!UICONTROL Add data element]**] をクリックします。

1. 例えば、「**[!UICONTROL Name]**」フィールドに「**pkey**」と入力します。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、**[!UICONTROL Data element]** のタイプ ドロップダウンで **[!UICONTROL pkey]** をクリックします。

1. Campaign サーバーデータ要素を作成するには、「**[!UICONTROL Add data element]**」をクリックします。

1. **[!UICONTROL Name]** フィールドに名前（例：**camp-server**）を入力します。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、「**[!UICONTROL Data element]** type」ドロップダウンに **[!UICONTROL Campaign Server]** 力します。

## ルールの作成 {#creating-rules}

次のルールを作成する必要があります。

* [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
* [アプリ内トラッキングのポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [ポストバックを追跡するプッシュ通知](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [場所のポストバック](../../administration/using/configuring-rules-launch.md#location-postback)

### PII ポストバック {#pii-postback}

>[!NOTE]
>
>モバイルアプリからAdobe Campaignに PII 情報を送信するには、SDK API を実装する必要があります。 詳細については、[CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii) を参照してください。

PII データを [!DNL Adobe Campaign Standard] に送信するには、データ収集 UI でルールを作成します。

1. データ収集 UI のモバイルアプリケーションダッシュボードで、「**[!UICONTROL Rules]**」タブをクリックし、**[!UICONTROL Create New Rule]** をクリックします。

1. 名前（例：**Mobile Core - PII を収集** を入力します。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、「**[!UICONTROL Event type]**」ドロップダウンに **[!UICONTROL Collect PII]** 力します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. 「**[!UICONTROL Actions]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、「**[!UICONTROL Action type]**」ドロップダウンに **[!UICONTROL Send PII]** 力します。

1. **[!UICONTROL URL]** で、次の URL を入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 「**[!UICONTROL Add Post Body]**」チェックボックスをオンにします。

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

   marketingCloudId を使用すると、アプリ購読者とデータベース内の受信者を紐付けることができ、その結果、が必要になります。 ビジネスニーズに応じて、他のキーと値のペアを指定できます。 上記の例では、メール、名および姓がアプリから渡されています。

   キー（例：cusEmail、cusFirstName、cusLastName）は、Adobe Campaign Standard インスタンスのカスタムリソースで定義されているフィールド ID と一致する必要があります。 値変数（email、firstName、LastName など）は、アプリコードから AMS collectPII API を呼び出す際に、モバイルアプリから送信される JSON データのキーと一致する必要があります。

   ライフサイクルデータは、イベントトリガーに応じて、PII の収集ポストバックまたは別のポストバックに渡すこともできます。 ライフサイクルデータ JSON の例を次に示します。

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   データ収集 UI で定義するデータ要素は `%%mcid%%` のように二重の割合で囲む必要があり、アプリのコンテキスト変数は %contextdata.email% のように単一の割合で囲む必要があります。

1. **[!UICONTROL Content Type]** に **application/json** と入力します。

1. **[!UICONTROL Timeout]** で、0 を選択します。

   ![](assets/do-not-localize/rules_2.png)

これで、Campaign に送信するようにユーザーデータが設定されました。

### アプリ内トラッキングのポストバック {#inapp-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0 以降またはiOS ACPCore v2.3.0 以降を使用している場合、トラッキングポストバックの設定は必要ありません。

トラッキングデータを [!DNL Adobe Campaign Standard] に送信して、ユーザーがモバイルアプリケーションのアプリ内メッセージとやり取りする方法をレポートするには、データ収集 UI で次のルールを作成します。

1. データ収集 UI で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブを選択し、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前（例：**Adobe Campaign - アプリ内クリックの追跡**）を入力します。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Adobe Campaign Standard]**」を選択します。 次に、「**[!UICONTROL Event type]**」ドロップダウンに **[!UICONTROL In-App click tracking]** 力します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. 「**[!UICONTROL Actions]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、「**[!UICONTROL Event type]**」ドロップダウンに **[!UICONTROL Send postback]** 力します。

1. **[!UICONTROL URL]** に、次の URL を入力します。

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 「**[!UICONTROL Add post body]**」チェックボックスをオンにします。

1. **[!UICONTROL Post Body]** に **{}** と入力します。

1. **[!UICONTROL Content Type]** に **application/json** と入力します。

1. **[!UICONTROL Timeout]** で、0 を選択します。

   ![](assets/do-not-localize/rules_3.png)

### ポストバックを追跡するプッシュ通知 {#push-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0 以降またはiOS ACPCore v2.3.0 以降を使用している場合、トラッキングポストバックの設定は必要ありません。

プッシュ通知配信とモバイルアプリケーションとのユーザーのインタラクションを追跡するのに役立つトラッキングデータを [!DNL Adobe Campaign Standard] に送信するには、データ収集 UI でルールを作成する必要があります。

プッシュトラッキングについて詳しくは、[&#x200B; プッシュトラッキング &#x200B;](../../administration/using/push-tracking.md) を参照してください。

アプリのアクションを追跡するには、trackAction API を使用します。 詳しくは、「[&#x200B; アプリのアクションのトラッキング &#x200B;](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」を参照してください。

1. データ収集 UI で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前（例：**Adobe Campaign - プッシュクリックの追跡**）を入力します。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、「**[!UICONTROL Event type]**」ドロップダウンに **[!UICONTROL Track Action]** 力します。

1. **[!UICONTROL Action]** ドロップダウンから「**[!UICONTROL Action]**」を選択し、「**[!UICONTROL equals]**」を選択して **トラッキング** と入力します。

1. 「**[!UICONTROL Keep changes]**」をクリックします。次に、[**[!UICONTROL Actions]**] セクションの [**[!UICONTROL Add]**] をクリックします。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、「**[!UICONTROL Action type]**」ドロップダウンに **[!UICONTROL Send postback]** 力します。

1. **[!UICONTROL URL]** で、次の URL を入力します。

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 「**[!UICONTROL Add post body]**」チェックボックスをオンにします。

1. 投稿の本文を追加します（例：{ }）。

1. **[!UICONTROL Content Type]** に **application/json** と入力します。

1. **[!UICONTROL Timeout]** で、0 を選択します。

### 場所のポストバック {#location-postback}

1. データ収集 UI で、モバイルアプリケーションダッシュボードから「**[!UICONTROL Rules]**」タブをクリックし、「**[!UICONTROL Add Rule]**」をクリックします。

1. 名前（例：**Location postback**）を入力します。

1. 「**[!UICONTROL Events]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. イベント（Enter POI や Exit POI など）を作成します。 **[!UICONTROL Extension]** ドロップダウンから、「**場所 – Beta**」を選択します。 次に、**POI を入力** または **POI を終了** して **[!UICONTROL Event type]** ださい。

1. 名前を入力します（例：**場所 – Beta - POI を入力** または **POI を終了**。

1. 「**[!UICONTROL Actions]**」セクションで、「**[!UICONTROL Add]**」をクリックします。

1. **[!UICONTROL Extension]** ドロップダウンから「**[!UICONTROL Mobile Core]**」を選択します。 次に、「**[!UICONTROL Action type]**」ドロップダウンから **[!UICONTROL Send postback]** 力します。

1. 名前（例：**Mobile Core – 場所のポストバックを送信** を入力します。

1. **[!UICONTROL URL]** で、次の URL を入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 「**[!UICONTROL Add post body]**」チェックボックスをオンにして、投稿本文を追加します。次に例を示します。

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
   >上記の例では、[&#x200B; データ要素の作成 &#x200B;](../../administration/using/configuring-rules-launch.md#create-data-elements) の手順を利用して、右側のデータ要素をデータ収集 UI で設定する必要があります。 左側のデータ要素は [!DNL Adobe Campaign Standard] でサポートされており、設定は必要ありません。 追加のデータが必要な場合は、[!DNL Adobe Campaign Standard] でカスタムリソース拡張を実行する必要があります。

1. **[!UICONTROL Content Type]** に **application/json** と入力します。

1. **[!UICONTROL Timeout]** で、「5」を選択します。

   ![](assets/do-not-localize/rules_4.png)
