---
title: Campaign でのトリガーの使用
description: null
page-status-flag: never-activated
uuid: d844d013-b38a-4e69-9df5-0edc01fa9c6e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: a524c700-bad6-4fcf-857a-c31bfae4d30c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3aa987c423181180a5c20bcca04cde04a2bf6086
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 2%

---


# Campaign でのトリガーの使用{#using-triggers-in-campaign}

## キャンペーンでのマッピングされたトリガーの作成 {#creating-a-mapped-trigger-in-campaign}

Adobe Experience Cloud( **[!UICONTROL Triggers]** コアサービス)では、事前に監視する動作を定義する必要があります。 詳しくは、 [Adobe Experience Cloudのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)。 トリガーを定義する場合は、エイリアスを有効にする必要があります。 各動作（閲覧/フォームの中断、製品の追加/削除、セッションの有効期限切れなど）について、Adobe Experience Cloudに新しいトリガーを追加する必要があります。

既存のAdobe Experience Cloudのトリガーを基にして、Adobe Campaignでトリガーイベントを作成する必要があります。

この [ビデオを見て](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) 、Adobe Campaignでのトリガーの設定方法を理解していただけます。

この設定を行う手順は次のとおりです。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、 **[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** /を選択し **[!UICONTROL Experience Cloud Triggers]**&#x200B;ます。

   ![](assets/remarketing_1.png)

1. ボタンをクリックし **[!UICONTROL Create]** ます。 作成ウィザードが開き、Adobe Experience Cloudで定義されたすべてのトリガーのリストが表示されます。 この **[!UICONTROL Fired by Analytics]** 列には、Adobe Experience Cloudのトリガーによってキャンペーンに送信されたイベントの数が表示されます。 これは、Experience Cloudインターフェイスで作成されたトリガーのマッピングです。

   ![](assets/remarketing_2.png)

1. 使用するAdobe Experience Cloudのトリガーを選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. トリガーの一般的なプロパティを設定します ウィザードのこの手順で、トリガーに使用するチャネルとターゲティングディメンションも指定します( [ターゲティングディメンションとリソースを参照](../../automating/using/query.md#targeting-dimensions-and-resources))。 次に、トリガーの作成を確認します。
1. フィールドの右側のボタンをクリックして、ペイロードの内容を表示し **[!UICONTROL Event content and enrichment]** ます。 また、この画面では、イベントデータをAdobe Campaignデータベースに保存されているプロファイルデータに拡張することもできます。 エンリッチメントは、標準トランザクションメッセージと同じ方法で実行されます。

   ![](assets/remarketing_3.png)

1. この **[!UICONTROL Transactional message validity duration]** フィールドで、Analyticsからイベントが送信された後、メッセージが有効である期間を定義します。 期間を2日と定義した場合、その期間が過ぎると、メッセージは送信されなくなります。 複数のメッセージを保留にすると、一定期間後に再開した場合に、これらのメッセージは送信されません。

   ![](assets/remarketing_4.png)

1. トリガーイベントの公開を開始するには、 **[!UICONTROL Publish]** ボタンをクリックします。
1. トリガーイベントを公開した後でもトリガースキーマに変更を加える必要がある場合は、 **[!UICONTROL Update schema]** ボタンをクリックして最新の変更を取得します。

   この操作により、トリガーとトランザクションメッセージが非公開になり、後で再公開する必要があります。

   ![](assets/remarketing_11.png)

この **[!UICONTROL Show Trigger in Experience Cloud]** ボタンを使用すると、Adobe Experience Cloudでトリガー定義を表示できます。

イベントが公開されると、新しいイベントにリンクされたトランザクションテンプレートが自動的に作成されます。 その後、作成したテンプレートを変更して公開する必要があります。 For more on this, refer to the [Editing the template](../../start/using/marketing-activity-templates.md) section.

## トランザクションメッセージテンプレートの編集 {#editing-the-transactional-message-template}

トリガーイベントを作成して公開すると、対応するトランザクションテンプレートが自動的に作成されます。 この詳細については、「キャンペーンでのマッピングされたトリガーの [作成](#creating-a-mapped-trigger-in-campaign) 」を参照してください。

イベントがトランザクションメッセージの送信をトリガーするには、テンプレートをパーソナライズしてテストし、公開する必要があります。 これらの手順は、標準トランザクションメッセージの場合と同じです。 For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>テンプレートの公開を取り消すと、トリガーイベントの公開が自動的に取り消されます。

コンテンツを編集する際、Analyticsトリガーから送信される情報に基づいてパーソナライゼーションフィールドを追加できます。 イベントデータをAdobe Campaignプロファイルデータと共に拡張する場合、この情報に基づいてメッセージをパーソナライズできます。 メッセージをパーソナライズするには、 **[!UICONTROL Transactional event]** /を選択 **[!UICONTROL Event context]** し、フィールドを選択します。

![](assets/remarketing_8.png)

## レポートへのアクセス {#accessing-the-reports}

専用のトリガーレポートをAdobe Campaignで表示するには、以前に作成したトリガーイベントを開き、をクリックし **[!UICONTROL Show trigger report]**&#x200B;ます。

![](assets/remarketing_9.png)

このレポートには、処理されたイベントの数とAnalyticsから送信されたイベントの数が表示されます。 また、最近実行したすべてのトリガーのリストも表示されます。

![](assets/trigger_uc_browse_14.png)

