---
title: キャンペーンでのTriggersの使用
seo-title: キャンペーンでのTriggersの使用
description: キャンペーンでのTriggersの使用
seo-description: null
page-status-flag: 常にアクティブ化されていない
uuid: d844d013- b38a-4e69-9df5-0edc01fa9c6e
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- trigger
discoiquuid: a524c700- bad6-4fcf-857a- c31bfae4d30c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Using Triggers in Campaign{#using-triggers-in-campaign}

## Creating a mapped trigger in Campaign {#creating-a-mapped-trigger-in-campaign}

You should make sure to define the behaviors that you want to monitor beforehand in Adobe Experience Cloud ( **[!UICONTROL Triggers]** core service). For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). トリガーを定義するときは、エイリアスを有効にする必要があります。各動作（参照/フォームの破棄、製品の追加/削除、セッションの有効期限など）については、Adobe Experience Cloudに新しいトリガーを追加する必要があります。

既存のAdobe Experience Cloudトリガーに基づいて、Adobe Campaignでトリガーイベントを作成する必要があります。

You can watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) to help you understand how triggers are set up in Adobe Campaign.

これを配置する手順は次のとおりです。

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. 作成ウィザードによって、Adobe Experience Cloudで定義されているすべてのトリガーのリストが表示されます。**[!UICONTROL Fired by Analytics]** この列には、Adobe Experience Cloudトリガーからキャンペーンに送信されたイベントの数が表示されます。これは、Experience Cloudインターフェイスで作成されたトリガーのマッピングです。

   ![](assets/remarketing_2.png)

1. Select the Adobe Experience Cloud trigger that you want to use and click **[!UICONTROL Next]**.
1. トリガーの一般プロパティを設定します。At this step of the wizard, also specify the channel and the targeting dimension to use for the trigger (see [targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). 次に、トリガーの作成を確認します。
1. **[!UICONTROL Event content and enrichment]** フィールドの右側のボタンをクリックして、ペイロードの内容を表示します。この画面では、Adobe Campaignデータベースに保存されているプロファイルデータを使用してイベントデータを拡張することもできます。エンリッチメントは、標準的なトランザクションメッセージと同じ方法で実行します。

   ![](assets/remarketing_3.png)

1. **[!UICONTROL Transactional message validity duration]** フィールド内で、Analyticsによってイベントが送信された後に、メッセージが有効になる期間を定義します。2日の期間が定義されている場合、その期間が過ぎるとメッセージは送信されなくなります。いくつかのメッセージを保留すると、一定期間の経過後にそれらのメッセージが送信されないようになります。

   ![](assets/remarketing_4.png)

1. If a propensity scoring is defined in Analytics (see the [Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html)), you can choose not to send the message if the customer has a high probability of coming back to the website in the near future. スコアとしきい値のコンテンツはペイロードのコンテンツで利用でき、これらの値を使用してメッセージをパーソナライズすることができます。このオプションを使用するには、画面の下部にあるチェックボックスをオンにします。近い将来にサイトに戻ってくる確度が強いクライアントは、メッセージを受け取りません。
1. Click the **[!UICONTROL Publish]** button to start publishing the trigger event.
1. If you need to make a change in your trigger schema even after publishing your trigger event, click the **[!UICONTROL Update schema]** button to retrieve the latest changes.

   このアクションによってトリガーおよびトランザクションメッセージの公開が取り消しられます。後で再公開する必要があります。

   ![](assets/remarketing_11.png)

**[!UICONTROL Show Trigger in Experience Cloud]** このボタンを使用すると、Adobe Experience Cloudでトリガー定義を表示できます。

イベントが発行されると、新しいイベントにリンクされたトランザクションテンプレートが自動的に作成されます。その後、作成したテンプレートを変更して発行する必要があります。For more on this, refer to the [Editing the template](../../start/using/about-templates.md) section.

## Editing the transactional message template {#editing-the-transactional-message-template}

トリガーイベントを作成して公開すると、対応するトランザクションテンプレートが自動的に作成されます。For more on this, refer to the [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) section.

イベントがトランザクションメッセージの送信をトリガーするには、テンプレートをカスタマイズし、テストして公開する必要があります。これらの手順は、標準的なトランザクションメッセージと同じです。For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>テンプレートの公開を取り消すと、自動的にトリガーイベントが非公開になります。

コンテンツを編集する際に、Analyticsトリガーによって送信された情報に基づいてパーソナライゼーションフィールドを追加できます。Adobe Campaignプロファイルデータを使用してイベントデータを充実させる場合、この情報に基づいてメッセージをパーソナライズできます。To personalize your message, select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]** and select a field.

![](assets/remarketing_8.png)

## Accessing the reports {#accessing-the-reports}

To view the dedicated trigger report in Adobe Campaign, open the trigger event that you previously created, and click **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

このレポートには、処理されたイベント数が、Analyticsから送信されたイベント数と比較されます。また、最近のすべてのトリガーのリストも表示されます。

![](assets/trigger_uc_browse_14.png)

