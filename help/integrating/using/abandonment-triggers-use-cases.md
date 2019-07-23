---
title: 破棄トリガーの使用例
seo-title: 破棄トリガーの使用例
description: 破棄トリガーの使用例
seo-description: Experience Cloud Triggersの使用方法を、様々な用途について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 9e236165- afd5-4155-9151- c1941dc0af99
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- trigger
discoiquuid: 1b9eec5-70bb-4d72- a3e9-12342abf08f7
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eed2e3597548c97345f51fe62dd2b56af5042e87

---


# Abandonment Triggers use cases{#abandonment-triggers-use-cases}

この節では、Adobe CampaignとExperience Cloud Triggersの統合を使用して実装できる様々な使用例を紹介します。使用例の2つの例を示します。

* [参照放棄トリガー](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger):貴社のウェブサイトでの訪問を破棄した顧客にコミュニケーションを送信します。
* [検索放棄トリガー](../../integrating/using/abandonment-triggers-use-cases.md#search-abandonment-trigger):Webサイトで検索を行ったが、購入しなかった訪問者との関連付けを行います。

>[!NOTE]
>
>この節で説明する使用例は、Experience Cloud訪問者IDに依存しています。また、Experience Cloud宣言IDを使用して実装することもできます。ハッシュ化された宣言済みIDも、暗号化されたIDもサポートされます。暗号化された電子メールアドレス/モバイル番号を直接復号化することで、キャンペーンに存在しないプロファイルに電子メール/SMSを送信できます。ただし、この場合、プロファイルデータを使用するパーソナライゼーションは使用できません。

## Pre-requisites {#pre-requisites}

これらの使用例を導入するには、次のソリューション/コアサービスにアクセスする必要があります。

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、モバイルApps、Select、Standard。
* Experience Cloud Triggersコアサービス
* Experience Cloud DTMコアサービス
* Experience Cloud訪問者IDおよびExperience Cloud Peopleコアサービス

また、作業中のWebサイトも必要です。

For more information, refer to [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Browse abandonment Trigger {#browse-abandonment-trigger}

この使用事例では、クライアントがWebサイトへの訪問を中止するたびに実行されるシンプルなトリガーを作成します。この例では、既にDTMを収集してAdobe Analyticsにプッシュし、すべてのイベントを作成していることを前提としています。

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger}

1. Select **[!UICONTROL Manage Triggers]** from the Experience Cloud Activation Core Service menu.

   ![](assets/trigger_uc_browse_1.png)

1. Choose a trigger type ( **[!UICONTROL Abandonment]** in our use case).

   ![](assets/trigger_uc_browse_2.png)

1. この使用事例では、単純な中断トリガーが必要です。ビジネスの目的は、旅行予約Webサイトを閲覧した訪問者を特定することであり、「掘り出し物」ページを見て、旅行を予約しないということです。このオーディエンスを特定すると、短期間でそのオーディエンスに戻ります。この例では、10分後にトリガーを送信します。

   ![](assets/trigger_uc_browse_3.png)

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign}

ここでは、Experience Cloudトリガーを作成して、Adobe Campaignで使用します。

Adobe Campaignで、Experience Cloudで作成したトリガーを作成する必要があります。

1. To create the Trigger in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. **[!UICONTROL Create]**&#x200B;をクリックします。
1. Select the Trigger you created earlier and click **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. **[!UICONTROL Email]** チャネルと **[!UICONTROL Real-time event]** ターゲットディメンションを選択し、をクリック **[!UICONTROL Create]**&#x200B;します。

   ![](assets/trigger_uc_browse_6bis.png)

1. Adobe Campaignでトリガーを公開します。このプロセスでは、トランザクションメッセージテンプレートが自動的に作成されます。

   ![](assets/trigger_uc_browse_6.png)

1. To display the message template, click the **[!UICONTROL More]** button, on the top right, then click **[!UICONTROL Trigger Transactional Template]** .

1. コンテンツおよび送信者の詳細をパーソナライズします。

   ![](assets/trigger_uc_browse_8.png)

1. メッセージテンプレートを公開します。トリガーがライブおよび機能になりました。

   ![](assets/trigger_uc_browse_0.png)

### Running the scenario {#running-the-scenario}

1. この使用例は、Adobe Campaignでオーディエンスに送信される最初の電子メールで開始します。

   ![](assets/trigger_uc_browse_9.png)

1. 受信者が電子メールを開きます。

   ![](assets/trigger_uc_browse_10.png)

1. 彼は、Webサイトに移動するリンクをクリックします。この例では、バナーは受信者を旅行予約Webサイトのホームページに導いています。

   ![](assets/trigger_uc_browse_11.png)

1. 受信者は「掘り出し物」ページに移動しますが、突然訪問が停止します。10分間の経過後、Adobe Campaignはトランザクションメッセージの送信をトリガーします。

   ![](assets/trigger_uc_browse_12.png)

1. いつでも、Experience Cloudログをチェックしてトリガーが何回起動されたかを確認できます。

   ![](assets/trigger_uc_browse_13.png)

1. Adobe Campaignトリガーレポートを表示することもできます。

   ![](assets/trigger_uc_browse_14.png)

## Search abandonment Trigger {#search-abandonment-trigger}

この使用事例では、旅行予約Webサイトに来訪し、行き先を検索し、成功しなかった訪問者を惹きつけ、その後に予約していない訪問者に対して、トリガーを作成します。The general process is the same as in the previous use case (see [Browse abandonment Trigger](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger)). ここでは、リマーケティングの電子メールメッセージをパーソナライズする方法について説明します。

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger-1}

前の使用例で説明した手順に従って、Experience Cloudトリガーを作成します。See [Creating an Experience Cloud Trigger](../../integrating/using/abandonment-triggers-use-cases.md#creating-an-experience-cloud-trigger). 主な違いはトリガーの定義です。

![](assets/trigger_uc_search_1.png)

**[!UICONTROL Include Meta Data]** このセクションでは、Analyticsから収集されたデータをトリガーペイロードに渡すことができます。この例では、訪問者が入力した検索キーワードを収集するためにカスタムeVar（例えば、eVar3）を作成します。このキーワードは、同じ訪問者に送信されるトランザクション電子メールメッセージで使用されます。

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. 前の使用例で説明した手順に従って、Adobe Campaignでトリガーを作成します。See [Using the trigger in Adobe Campaign](../../integrating/using/abandonment-triggers-use-cases.md#using-the-trigger-in-adobe-campaign). 主な違いは、Adobe Campaignでは、Adobe Campaignで、トリガーペイロードでプッシュされるメタデータです。
1. In the Search Abandonment trigger you created in Adobe Campaign, click on the **[!UICONTROL Event content and enrichment]** icon to view the payload pushed to Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. As you can see, the custom eVar is passed in the Trigger payload and mapped to the **Event Context** table (ctx). これにアクセスして、トランザクションメッセージをパーソナライズできるようになりました。

   ![](assets/trigger_uc_search_3.png)

1. この例では、件名行と電子メール本文に宛先検索用語を含めるように選択しています。

   ![](assets/trigger_uc_search_4.png)

1. When selecting a personalized field, look for your payload meta data in the **Transactional event** (rtEvent) table then in the **Event context** (ctx) sub table.

   ![](assets/trigger_uc_search_5.png)

### Running the scenario {#running-the-scenario-1}

1. 訪問者は旅行予約Webサイトにアクセスし、宛先を検索します。この例では、訪問者は日本への旅行を探していますが、結果は見つかりません。これは、この訪問者に戻って別の旅行計画を推奨するチャンスです。

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >この使用事例では、訪問者/受信者が既に同じWebサイトからの電子メールを開いてクリックしていると想定しています。これにより、visitorIDを使用して収集し、受信者にマッピングすることができます。1回だけ実行する必要があります。

1. しばらくすると、同じ訪問者/受信者が再マーケティングメッセージを受け取ります。メッセージには、最近検索された宛先が含まれています。

   ![](assets/trigger_uc_search_7.png)

