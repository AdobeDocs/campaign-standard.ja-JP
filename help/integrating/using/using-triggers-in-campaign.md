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
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 98%

---


# Campaign でのトリガーの使用{#using-triggers-in-campaign}

## Campaign でのマッピングされたトリガーの作成{#creating-a-mapped-trigger-in-campaign}

Adobe Experience Cloud（**[!UICONTROL Triggers]** コアサービス）では、事前に監視するビヘイビアーを定義する必要があります。詳しくは、[Adobe Experience Cloud のドキュメント](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html)を参照してください。トリガーを定義する場合は、エイリアスを有効にする必要があります。各ビヘイビアー（ブラウジング／フォームの放棄、製品の追加／削除、セッションの有効期限切れなど）について、Adobe Experience Cloud に新規トリガーを追加する必要があります。

次に、既存の Adobe Experience Cloud のトリガーを基にして、Adobe Campaign でトリガーイベントを作成する必要があります。

この[ビデオ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)を見ると、Adobe Campaign でのトリガーの設定方法を理解できます。

これをおこなうには、次の手順に従います。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Experience Cloud Triggers]** を選択します。

   ![](assets/remarketing_1.png)

1. 「**[!UICONTROL Create]**」ボタンをクリックします。作成ウィザードが開き、Adobe Experience Cloud で定義されたすべてのトリガーのリストが表示されます。この「**[!UICONTROL Fired by Analytics]**」列には、Adobe Experience Cloud のトリガーによって Campaign に送信されたイベントの数が表示されます。これは、Experience Cloud インターフェイスで作成されたトリガーのマッピングです。

   ![](assets/remarketing_2.png)

1. 使用する Adobe Experience Cloud のトリガーを選択し、「**[!UICONTROL Next]**」をクリックします。
1. トリガーの一般的なプロパティを設定しますウィザードのこの手順で、トリガーに使用するチャネルとターゲティングディメンションも指定します（[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)を参照）。次に、トリガーの作成を確認します。
1. 「**[!UICONTROL Event content and enrichment]**」フィールドの右側のボタンをクリックして、ペイロードの内容を表示します。また、この画面では、イベントデータを Adobe Campaign データベースに保存されているプロファイルデータに拡張することもできます。エンリッチメントは、標準トランザクションメッセージと同じ方法で実行されます。

   ![](assets/remarketing_3.png)

1. この「**[!UICONTROL Transactional message validity duration]**」フィールドで、Analytics からイベントが送信された後、メッセージが有効である期間を定義します。期間を 2 日と定義した場合、その期間が過ぎると、メッセージは送信されなくなります。複数のメッセージを保留にすると、一定期間後に再開した場合でも、これらのメッセージは送信されません。

   ![](assets/remarketing_4.png)

1. トリガーイベントの公開を開始するには、「**[!UICONTROL Publish]**」ボタンをクリックします。
1. トリガーイベントを公開した後でもトリガースキーマに変更を加える必要がある場合は、「**[!UICONTROL Update schema]**」ボタンをクリックして最新の変更を取得します。

   この操作により、トリガーとトランザクションメッセージが非公開になり、後で再公開する必要があります。

   ![](assets/remarketing_11.png)

この「**[!UICONTROL Show Trigger in Experience Cloud]**」ボタンを使用すると、Adobe Experience Cloud でトリガー定義を表示できます。

イベントが公開されると、新規イベントにリンクされたトランザクションテンプレートが自動的に作成されます。その後、作成したテンプレートを変更して公開する必要があります。詳しくは、[テンプレートの編集](../../start/using/marketing-activity-templates.md)の節を参照してください。

## トランザクションメッセージテンプレートの編集{#editing-the-transactional-message-template}

トリガーイベントを作成して公開すると、対応するトランザクションテンプレートが自動的に作成されます。詳しくは、[Campaign でのマッピングされたトリガーの作成](#creating-a-mapped-trigger-in-campaign)の節を参照してください。

イベントがトランザクションメッセージの送信をトリガーするには、テンプレートをパーソナライズしてテストし、公開する必要があります。これらの手順は、標準トランザクションメッセージの場合と同じです。詳しくは、[トランザクションテンプレート](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)の節を参照してください。

>[!NOTE]
>
>テンプレートの公開を取り消すと、トリガーイベントの公開が自動的に取り消されます。

コンテンツを編集する際、Analytics トリガーから送信される情報に基づいてパーソナライゼーションフィールドを追加できます。イベントデータを Adobe Campaign プロファイルデータと共に拡張する場合、この情報に基づいてメッセージをパーソナライズできます。メッセージをパーソナライズするには、**[!UICONTROL Transactional event]**／**[!UICONTROL Event context]** と選択し、フィールドを選択します。

![](assets/remarketing_8.png)

## レポートへのアクセス{#accessing-the-reports}

専用のトリガーレポートを Adobe Campaign で表示するには、以前に作成したトリガーイベントを開き、「**[!UICONTROL Show trigger report]**」をクリックします。

![](assets/remarketing_9.png)

このレポートには、処理されたイベントの数と Analytics から送信されたイベントの数が表示されます。また、最近実行したすべてのトリガーのリストも表示されます。

![](assets/trigger_uc_browse_14.png)

