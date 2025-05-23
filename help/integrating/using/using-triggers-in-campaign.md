---
title: Campaign での Triggers の使用
description: 既存のAdobe Experience Cloudトリガーに基づいて、Adobe Campaignにトリガーイベントを作成します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6b8d5118-89ed-49c2-b601-0aff472fcadd
source-git-commit: cf2ded703e53d6db27e62712734f7ea846da9a21
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 74%

---

# Campaign での Triggers の使用{#using-triggers-in-campaign}

## Campaign でのマッピングされたトリガーの作成 {#creating-a-mapped-trigger-in-campaign}

>[!NOTE]
>
>トリガーを作成するには、**[!UICONTROL Administration]** の役割または **[!UICONTROL Administrators]** セキュリティ グループに属している必要があります。 詳しくは、この [ ページ ](../../administration/using/list-of-roles.md) を参照してください。

Adobe Experience Cloud（**[!UICONTROL Triggers]** コアサービス）で事前にモニタリングするビヘイビアーを定義しておく必要があります。 詳しくは、[Adobe Experience Cloud のドキュメント](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=ja)を参照してください。トリガーを定義する場合は、エイリアスを有効にする必要があります。各ビヘイビアー（ブラウジング／フォームの放棄、製品の追加／削除、セッションの有効期限切れなど）について、Adobe Experience Cloud に新規トリガーを追加する必要があります。

次に、既存の Adobe Experience Cloud のトリガーを基にして、Adobe Campaign でトリガーイベントを作成する必要があります。

これをおこなうには、次の手順に従います。

1. 左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、**&#x200B;[!UICONTROL Marketing plans]&#x200B;**/**&#x200B;[!UICONTROL Transactional messages]&#x200B;**/**&#x200B;[!UICONTROL Experience Cloud Triggers]&#x200B;**を選択します。**

   ![](assets/remarketing_1.png)

1. 「**[!UICONTROL Create]**」ボタンをクリックします。作成ウィザードが開き、Adobe Experience Cloud で定義されたすべてのトリガーのリストが表示されます。この「**[!UICONTROL Fired by Analytics]**」列には、Adobe Experience Cloud のトリガーによって Campaign に送信されたイベントの数が表示されます。これは、Experience Cloud インターフェイスで作成されたトリガーのマッピングです。

   ![](assets/remarketing_2.png)

1. 使用する Adobe Experience Cloud のトリガーを選択し、「**[!UICONTROL Next]**」をクリックします。
1. トリガーの一般的なプロパティを設定しますウィザードのこの手順で、トリガーに使用するチャネルとターゲティングディメンションも指定します（[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)を参照）。次に、トリガーの作成を確認します。
1. 「**[!UICONTROL Event content and enrichment]**」フィールドの右側のボタンをクリックして、ペイロードの内容を表示します。また、この画面では、イベントデータを Adobe Campaign データベースに保存されているプロファイルデータに拡張することもできます。エンリッチメントは、標準トランザクションメッセージと同じ方法で実行されます。

   ![](assets/remarketing_3.png)

1. この「**[!UICONTROL Transactional message validity duration]**」フィールドで、Analytics からイベントが送信された後、メッセージが有効である期間を定義します。期間を 2 日と定義した場合、その期間が過ぎると、メッセージは送信されなくなります。複数のメッセージを保留にすると、一定期間後に再開した場合でも、これらのメッセージは送信されません。

   ![](assets/remarketing_4.png)

1. これで、トリガーを公開できます。 詳しくは、[Campaign でのトリガーの公開 ](../../integrating/using/using-triggers-in-campaign.md#publishing-trigger-in-campaign) を参照してください。

## Campaign でのトリガーの公開 {#publishing-trigger-in-campaign}

既存のAdobe Experience Cloud トリガーに基づいてAdobe Campaignでトリガーイベントを作成したら、それを公開する必要があります。

1. 以前に作成したトリガーから、「**[!UICONTROL Publish]**」ボタンをクリックしてトリガーイベントの公開を開始します。

   ![](assets/trigger_publish_1.png)

1. トリガーの公開の進行状況は、**[!UICONTROL Publication]** で確認できます。

   ![](assets/trigger_publish_2.png)

1. 公開が完了すると、「**[!UICONTROL Publication]**」の下に次のメッセージが表示されます。

   ![](assets/trigger_publish_3.png)

1. トリガーイベントを公開した後でもトリガースキーマに変更を加える必要がある場合は、「**[!UICONTROL Update schema]**」ボタンをクリックして最新の変更を取得します。

   この操作により、トリガーとトランザクションメッセージが非公開になり、後で再公開する必要があります。

   ![](assets/trigger_publish_4.png)

1. 「」ボタン **[!UICONTROL Show Trigger in Experience Cloud]** クリックすると、Adobe Experience Cloudでトリガー定義を表示できます。

イベントが公開されると、新規イベントにリンクされたトランザクションテンプレートが自動的に作成されます。その後、作成したテンプレートを変更して公開する必要があります。詳しくは、[テンプレートの編集](../../start/using/marketing-activity-templates.md)の節を参照してください。

## トランザクションメッセージテンプレートの編集 {#editing-the-transactional-message-template}

トリガーイベントを作成して公開すると、対応するトランザクションテンプレートが自動的に作成されます。詳しくは、[Campaign でのマッピングされたトリガーの作成](#creating-a-mapped-trigger-in-campaign)の節を参照してください。

イベントがトランザクションメッセージの送信をトリガーするには、テンプレートをパーソナライズしてテストし、公開する必要があります。これらの手順は、標準トランザクションメッセージの場合と同じです。詳しくは、[ トランザクションメッセージの編集 ](../../channels/using/editing-transactional-message.md) の節を参照してください。

>[!NOTE]
>
>テンプレートの公開を取り消すと、トリガーイベントの公開が自動的に取り消されます。

コンテンツを編集する際、Analytics トリガーから送信される情報に基づいてパーソナライゼーションフィールドを追加できます。イベントデータを Adobe Campaign プロファイルデータと共に拡張する場合、この情報に基づいてメッセージをパーソナライズできます。メッセージをパーソナライズするには、**[!UICONTROL Transactional event]**／**[!UICONTROL Event context]** と選択し、フィールドを選択します。

![](assets/remarketing_8.png)

## レポートへのアクセス {#accessing-the-reports}

専用のトリガーレポートを Adobe Campaign で表示するには、以前に作成したトリガーイベントを開き、「**[!UICONTROL Show trigger report]**」をクリックします。

![](assets/remarketing_9.png)

このレポートには、処理されたイベントの数と Analytics から送信されたイベントの数が表示されます。また、最近実行したすべてのトリガーのリストも表示されます。

![](assets/trigger_uc_browse_14.png)
