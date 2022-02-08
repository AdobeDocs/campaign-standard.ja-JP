---
title: Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定
description: Adobe Campaign Standardの使用例をサポートするようにAdobe Experience Platform Launchルールを設定する方法を説明します
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# Adobe Campaign Standard のユースケースをサポートするための Launch ルールの設定 {#configuring-rules-launch}

In [!DNL Adobe Experience Platform Launch]、データ要素とルールを作成して、モバイルアプリケーションからに PII やその他のデータを送信します。 [!DNL Adobe Campaign Standard].

すべての設定を [!DNL Adobe Experience Platform Launch] 有効にするには、これらの変更を公開する必要があります。 詳しくは、 [公開](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

でルールを作成するには、以下を実行します。 [!DNL Experience Platform Launch]を使用する場合は、次の手順に従います。

1. [データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [ルールの作成](../../administration/using/configuring-rules-launch.md#create-data-elements) をサポートする必要があるユースケースの場合：
   * [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [アプリ内トラッキングポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [プッシュ通知トラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [ポストバックの場所](../../administration/using/configuring-rules-launch.md#location-postback)

## データ要素の作成 {#create-data-elements}

次に、 [!DNL Experience Platform Launch].
必要に応じて、追加のデータ要素を作成できます。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

次のデータ要素を作成するには：

1. In [!DNL Experience Platform Launch]モバイルアプリケーションダッシュボードで、 **[!UICONTROL Data Elements]** タブをクリックします。

1. 次の手順で **[!UICONTROL Experience Cloud ID]** データ要素，クリック **[!UICONTROL Create New Data Element]**.

1. 内 **[!UICONTROL Name]** フィールドに、例えば、次のように入力します。 **mcid**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Mobile Core]**. 次に、 **[!UICONTROL Experience Cloud ID]** 内 **[!UICONTROL Data element]** 「 」ドロップダウンリスト。

   ![](assets/do-not-localize/rules_1.png)

1. データ要素を作成するには、 **[!UICONTROL Add data element]**.

1. 内 **[!UICONTROL Name]** フィールドに、例えば、次のように入力します。 **pkey**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Adobe Campaign Standard]**. 次に、 **[!UICONTROL pkey]** 内 **[!UICONTROL Data element]** 「 」ドロップダウンリスト。

1. Campaign サーバーのデータ要素を作成するには、 **[!UICONTROL Add data element]**.

1. 内 **[!UICONTROL Name]** フィールドに、名前を入力します（例： ）。 **キャンプサーバー**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Adobe Campaign Standard]**. すると、 **[!UICONTROL Campaign Server]** 内 **[!UICONTROL Data element]** 「 」ドロップダウンリスト。

## ルールの作成 {#creating-rules}

次のルールを作成する必要があります。

* [PII ポストバック](../../administration/using/configuring-rules-launch.md#pii-postback)
* [アプリ内トラッキングポストバック](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [プッシュ通知トラッキングポストバック](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [ポストバックの場所](../../administration/using/configuring-rules-launch.md#location-postback)

### PII ポストバック {#pii-postback}

>[!NOTE]
>
>モバイルアプリからAdobe Campaignに PII 情報を送信するには、SDK API を実装する必要があります。 詳しくは、を参照してください。 [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

PII データをに送信するには、以下を実行します。 [!DNL Adobe Campaign Standard]、でルールを作成します。 [!DNL Experience Platform Launch]:

1. In [!DNL Experience Platform Launch]モバイルアプリケーションダッシュボードで、 **[!UICONTROL Rules]** タブをタップし、 **[!UICONTROL Create New Rule]**.

1. 名前を入力します（例： ）。 **モバイルコア — PII を収集**.

1. 内 **[!UICONTROL Events]** セクションで、 **[!UICONTROL Add]**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Mobile Core]**. すると、 **[!UICONTROL Collect PII]** 内 **[!UICONTROL Event type]** 」ドロップダウンリストから選択できます。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. 内 **[!UICONTROL Actions]** セクションで、 **[!UICONTROL Add]**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Mobile Core]**. すると、 **[!UICONTROL Send PII]** 内 **[!UICONTROL Action type]** 」ドロップダウンリストから選択できます。

1. In **[!UICONTROL URL]**、次の URL を入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. を選択します。 **[!UICONTROL Add Post Body]** チェックボックスをオンにします。

1. In **[!UICONTROL Post Body]**、次のように入力します。

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

   marketingCloudId を使用すると、アプリの購読者とデータベース内の受信者を紐付けでき、結果としてが必要になります。 ビジネスのニーズに応じて、他のキーと値のペアを指定できます。 上記の例では、E メール、名および姓がアプリから渡されています。

   キー（例えば、cusEmail、cusFirstName、cusLastName）は、Adobe Campaign Standardインスタンスのカスタムリソースで定義されるフィールド ID と一致する必要があります。 値の変数（email、firstName、LastName など）は、アプリコードから AMS collectPII API を呼び出す際にモバイルアプリから送信される JSON データのキーと一致する必要があります。

   また、イベントデータに応じて、PII 収集ポストバックでライフサイクルデータを渡すことも、別のポストバックでライフサイクルトリガーを渡すこともできます。 ライフサイクルデータ JSON の例を次に示します。

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   で定義されているデータ要素 [!DNL Experience Platform Launch] %%mcid%%のように二重の割合で囲み、アプリのコンテキスト変数は 1 つの割合で囲む必要があります（例：%contextdata.email%）。

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]**、「 0 」を選択します。

   ![](assets/do-not-localize/rules_2.png)

これで、ユーザーデータが Campaign に送信されるように設定されました。

### アプリ内トラッキングポストバック {#inapp-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0 以降またはiOS ACPCore v2.3.0 以降を使用している場合、トラッキングポストバックを設定する必要はありません。

にトラッキングデータを送信するには、以下を実行します。 [!DNL Adobe Campaign Standard] モバイルアプリケーションでユーザーがアプリ内メッセージとどのようにやり取りするかをレポートするには、 [!DNL Experience Platform Launch]:

1. In [!DNL Experience Platform Launch]モバイルアプリケーションダッシュボードから、 **[!UICONTROL Rules]** タブをクリックし、 **[!UICONTROL Add Rule]**.

1. 名前を入力します（例： ）。 **Adobe Campaign — アプリ内クリックの追跡**.

1. 内 **[!UICONTROL Events]** セクションで、 **[!UICONTROL Add]**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Adobe Campaign Standard]**. すると、 **[!UICONTROL In-App click tracking]** 内 **[!UICONTROL Event type]** 」ドロップダウンリストから選択できます。

1. 「**[!UICONTROL Keep changes]**」をクリックします。

1. 内 **[!UICONTROL Actions]** セクションで、 **[!UICONTROL Add]**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Mobile Core]**. すると、 **[!UICONTROL Send postback]** 内 **[!UICONTROL Event type]** 」ドロップダウンリストから選択できます。

1. In **[!UICONTROL URL]**、次の URL を入力します。

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. を選択します。 **[!UICONTROL Add post body]** チェックボックスをオンにします。

1. In **[!UICONTROL Post Body]**, type **{}**.

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]**、「 0 」を選択します。

   ![](assets/do-not-localize/rules_3.png)

### プッシュ通知トラッキングポストバック {#push-tracking-postback}

>[!NOTE]
>
>Android ACPCore v1.4.0 以降またはiOS ACPCore v2.3.0 以降を使用している場合、トラッキングポストバックを設定する必要はありません。

にトラッキングデータを送信するには、以下を実行します。 [!DNL Adobe Campaign Standard]（プッシュ通知配信やユーザーのモバイルアプリケーションとのやり取りを追跡するのに役立つ）、 [!DNL Experience Platform Launch].

プッシュトラッキングについて詳しくは、 [プッシュトラッキング](../../administration/using/push-tracking.md).

アプリのアクションを追跡するには、 trackAction API を使用します。 詳しくは、 [アプリのアクションの追跡](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. In [!DNL Experience Platform Launch]モバイルアプリケーションダッシュボードで、 **[!UICONTROL Rules]** タブをクリックし、 **[!UICONTROL Add Rule]**.

1. 名前を入力します（例： ）。 **Adobe Campaign — プッシュクリックの追跡**.

1. 内 **[!UICONTROL Events]** セクションで、 **[!UICONTROL Add]**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Mobile Core]**. すると、 **[!UICONTROL Track Action]** 内 **[!UICONTROL Event type]** 」ドロップダウンリストから選択できます。

1. 次の **[!UICONTROL Action]** ドロップダウンで、「 **[!UICONTROL Action]**&#x200B;を選択します。 **[!UICONTROL equals]**、および **tracking**.

1. 「**[!UICONTROL Keep changes]**」をクリックします。次に、 **[!UICONTROL Actions]** セクションで、 **[!UICONTROL Add]**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Mobile Core]**. すると、 **[!UICONTROL Send postback]** 内 **[!UICONTROL Action type]** 」ドロップダウンリストから選択できます。

1. In **[!UICONTROL URL]**、次の URL を入力します。

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. を選択します。 **[!UICONTROL Add post body]** チェックボックスをオンにします。

1. 投稿の本文を追加します（例： { }）。

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]**、「 0 」を選択します。

### ポストバックの場所 {#location-postback}

1. In [!DNL Experience Platform Launch]モバイルアプリケーションダッシュボードで、 **[!UICONTROL Rules]** タブをクリックし、 **[!UICONTROL Add Rule]**.

1. 名前を入力します（例： ）。 **ポストバックの場所**.

1. 内 **[!UICONTROL Events]** セクションで、 **[!UICONTROL Add]**.

1. イベントを作成します（例： POI を入力、POI を終了）。 次の **[!UICONTROL Extension]** ドロップダウンで、「 **Places — ベータ**. すると、 **POI を入力** または **出口 POI** 内 **[!UICONTROL Event type]** 」ドロップダウンリストから選択できます。

1. 名前を入力します（例： ）。 **Places — ベータ — POI を入力** または **出口 POI**.

1. 内 **[!UICONTROL Actions]** セクションで、 **[!UICONTROL Add]**.

1. 次の **[!UICONTROL Extension]** ドロップダウンで、「 **[!UICONTROL Mobile Core]**. すると、 **[!UICONTROL Send postback]** から **[!UICONTROL Action type]** 」ドロップダウンリストから選択できます。

1. 名前を入力します（例： ）。 **モバイルコア — 場所ポストバックを送信**.

1. In **[!UICONTROL URL]**、次の URL を入力します。

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. を選択します。 **[!UICONTROL Add post body]** チェックボックスをオンにして、次のような post 本文を追加します。

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
   >上記の例では、右側のデータ要素は、 [!DNL Experience Platform Launch] 手順を活用して [データ要素の作成](../../administration/using/configuring-rules-launch.md#create-data-elements). 左側のデータ要素は、 [!DNL Adobe Campaign Standard] 設定は不要です。 追加のデータが必要な場合は、 [!DNL Adobe Campaign Standard].

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]**、「 5 」を選択します。

   ![](assets/do-not-localize/rules_4.png)
