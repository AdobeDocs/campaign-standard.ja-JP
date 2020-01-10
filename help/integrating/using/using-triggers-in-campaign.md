---
title: キャンペーンでのトリガーの使用
description: null
page-status-flag: 非活性化の
uuid: d844d013-b38a-4e69-9df5-0edc01fa9c6e
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとトリガーの連携
discoiquuid: a524c700-bad6-4fcf-857a-c31bfae4d30c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# キャンペーンでのトリガーの使用{#using-triggers-in-campaign}

## Campaignでのマッピング済みトリガーの作成 {#creating-a-mapped-trigger-in-campaign}

Adobe Experience Cloud（コアサービス）で事前に監視する動作を定義しておく必 **[!UICONTROL Triggers]** 要があります。 For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). トリガーを定義する場合は、エイリアスを有効にする必要があります。 各動作（閲覧/フォームの中断、製品の追加/削除、セッションの有効期限切れなど）に対して、Adobe Experience cloudに新しいトリガーを追加する必要があります。

既存のAdobe Experience cloudトリガーに基づいて、Adobe Campaignでトリガーイベントを作成する必要があります。

このビデオを見ると [](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) 、Adobe Campaignでトリガーが設定される方法を理解できます。

これを配置する手順は次のとおりです。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を選 **[!UICONTROL Marketing plans]** 択し **[!UICONTROL Transactional messages]** ます **[!UICONTROL Experience Cloud Triggers]**。

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. 作成ウィザードが開き、Adobe Experience cloudで定義されているすべてのトリガーのリストが表示されます。 この列 **[!UICONTROL Fired by Analytics]** には、Adobe Experience cloudトリガーによってCampaignに送信されたイベントの数が表示されます。 これは、Experience cloudインターフェイスで作成されたトリガーのマッピングです。

   ![](assets/remarketing_2.png)

1. 使用するAdobe Experience cloudのトリガーを選択し、をクリックします **[!UICONTROL Next]**。
1. トリガーの一般的なプロパティを設定します。 ウィザードのこの手順で、トリガーに使用するチャネルとターゲットディメンションも指定します(ディメンションとリソ [ースのターゲット設定を参照](../../automating/using/query.md#targeting-dimensions-and-resources))。 次に、トリガーの作成を確認します。
1. フィールドの右側のボタンをクリックし **[!UICONTROL Event content and enrichment]** て、ペイロードのコンテンツを表示します。 また、この画面では、イベントデータをAdobe Campaignデータベースに保存されたプロファイルデータで拡張することもできます。 エンリッチメントは、標準のトランザクションメッセージと同じ方法で実行されます。

   ![](assets/remarketing_3.png)

1. このフィー **[!UICONTROL Transactional message validity duration]** ルドで、Analyticsからイベントが送信された後にメッセージが有効なままである期間を定義します。 期間を2日と定義した場合、その期間が過ぎると、メッセージは送信されなくなります。 複数のメッセージを保留にすると、一定期間後に再開した場合に、これらのメッセージは送信されなくなります。

   ![](assets/remarketing_4.png)

1. 傾向スコアリングがAnalyticsで定義されている場合( [Experience cloudのドキュメントを参照](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html))、顧客が近い将来にWebサイトに再訪する可能性が高い場合は、メッセージを送信しないように選択できます。 スコアとしきい値の内容はペイロードの内容で利用でき、これらの値を使用してメッセージをパーソナライズできます。 このオプションを使用するには、画面の下部にあるチェックボックスをオンにします。 近い将来にサイトに戻る確率が高いクライアントは、メッセージを受信しません。
1. トリガーイベント **[!UICONTROL Publish]** の発行を開始するには、このボタンをクリックします。
1. トリガーイベントを発行した後でもトリガースキーマに変更を加える必要がある場合は、ボタンをクリックし **[!UICONTROL Update schema]** て最新の変更を取得します。

   この操作を行うと、トリガーおよびトランザクションメッセージの公開が取り消され、後で再公開する必要があります。

   ![](assets/remarketing_11.png)

このボ **[!UICONTROL Show Trigger in Experience Cloud]** タンを使用すると、Adobe Experience cloudでトリガーの定義を表示できます。

イベントが公開されると、新しいイベントにリンクされたトランザクションテンプレートが自動的に作成されます。 その後、作成したテンプレートを変更して公開する必要があります。 詳しくは、「テンプレートの編集」の節 [を参照してください](../../start/using/marketing-activity-templates.md) 。

## トランザクションメッセージテンプレートの編集 {#editing-the-transactional-message-template}

トリガーイベントを作成して発行すると、対応するトランザクションテンプレートが自動的に作成されます。 詳しくは、「キャンペーンでのマッピン [グされたトリガーの作成](#creating-a-mapped-trigger-in-campaign) 」を参照してください。

イベントがトランザクションメッセージの送信をトリガーするには、テンプレートをパーソナライズし、テストして公開する必要があります。 これらの手順は、標準のトランザクションメッセージの場合と同じです。 For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>テンプレートの公開を取り消すと、トリガーイベントの公開が自動的に取り消されます。

コンテンツを編集する際に、Analyticsトリガーから送信された情報に基づいてパーソナライゼーションフィールドを追加できます。 イベントデータをAdobe Campaignプロファイルデータに含めると、この情報に基づいてメッセージをパーソナライズできます。 メッセージをパーソナライズするには、/ **[!UICONTROL Transactional event]** を選択 **[!UICONTROL Event context]** し、フィールドを選択します。

![](assets/remarketing_8.png)

## レポートへのアクセス {#accessing-the-reports}

Adobe Campaignで専用のトリガーレポートを表示するには、以前に作成したトリガーイベントを開き、をクリックしま **[!UICONTROL Show trigger report]**&#x200B;す。

![](assets/remarketing_9.png)

このレポートには、Analyticsが送信したイベント数と比較して、処理されたイベントの数が表示されます。 また、最近のすべてのトリガーのリストも表示されます。

![](assets/trigger_uc_browse_14.png)

