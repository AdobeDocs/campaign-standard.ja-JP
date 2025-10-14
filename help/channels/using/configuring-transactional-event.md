---
title: トランザクションイベントの設定
description: Adobe Campaignでトランザクションイベントを設定する方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 1b91fb97-fe97-4564-936c-438be7ea7bc0
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '1709'
ht-degree: 3%

---

# トランザクションイベントの設定 {#configuring-transactional-event}

Adobe Campaignでトランザクションメッセージを送信するには、まずイベントを作成して設定し、イベントデータの構造を記述する必要があります。

>[!IMPORTANT]
>
>イベント設定を作成および編集する適切な権限を持つのは [&#x200B; 機能管理者 &#x200B;](../../administration/using/users-management.md#functional-administrators)<!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) --> のみです。

設定は、送信する [&#x200B; トランザクションメッセージのタイプ &#x200B;](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) と、使用するチャネルによって異なります。 詳しくは、[&#x200B; 特定の設定 &#x200B;](#transactional-event-specific-configurations) を参照してください。

設定が完了したら、イベントを公開する必要があります。 [&#x200B; トランザクションイベントの公開 &#x200B;](../../channels/using/publishing-transactional-event.md) を参照してください。

## イベントの作成 {#creating-an-event}

開始するには、必要に応じてイベントを作成します。

1. 左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、**&#x200B;[!UICONTROL Marketing plans]&#x200B;**/**&#x200B;[!UICONTROL Transactional messages]&#x200B;**/**&#x200B;[!UICONTROL Event configuration]&#x200B;**を選択します。**
1. 「**[!UICONTROL Create]**」ボタンをクリックします。
1. イベントの **[!UICONTROL Label]** と **[!UICONTROL ID]** を入力します。 **[!UICONTROL ID]** フィールドは必須で、プレフィックス「EVT」で始める必要があります。 このプレフィックスを使用しない場合は、[**[!UICONTROL Create]**] をクリックすると自動的に追加されます。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID は、EVT プレフィックスを含めて 64 文字以内にする必要があります。

1. トランザクションメッセージを **[!UICONTROL Mobile (SMS)]**、**[!UICONTROL Push notification]** のいずれか **[!UICONTROL Email]** 送信するために使用するチャネルを選択します。 各イベントで使用できるチャネルは 1 つだけです。後で変更することはできません。

1. 目的のイベント設定に対応するターゲティングディメンションを選択し、「**[!UICONTROL Create]**」をクリックします。

   イベントベースのトランザクションメッセージはイベント自体に含まれるデータをターゲットにし、プロファイルベースのトランザクションメッセージはAdobe Campaign データベースに含まれるデータをターゲットにします。 詳しくは、[&#x200B; 特定の設定 &#x200B;](#transactional-event-specific-configurations) を参照してください。

>[!NOTE]
>
>トランザクションイベントの数は、プラットフォームに影響を与える可能性があります。 最適なパフォーマンスを確保するには、未使用のイベントを必ず削除してください。 [&#x200B; イベントの削除 &#x200B;](../../channels/using/publishing-transactional-event.md#deleting-an-event) を参照してください。

## イベント属性の定義 {#defining-the-event-attributes}

**[!UICONTROL Fields]** セクションでは、イベントコンテンツに統合され、トランザクションメッセージのパーソナライズに使用できる属性を定義します。

フィールドの追加と変更の手順は、[&#x200B; カスタムリソース &#x200B;](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource) の場合と同じです。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は、**[!UICONTROL AC_language]** ID を持つ追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ適用されます。 イベントの公開後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語標準メールの場合と同じです。 [&#x200B; 多言語メールの作成 &#x200B;](../../channels/using/creating-a-multilingual-email.md) を参照してください。

## データコレクションの定義 {#defining-data-collections}

イベントコンテンツに要素のコレクションを追加できます。各要素自体には、複数の属性が含まれます。

このコレクションをトランザクションメールで使用すると、価格、参照番号、数量などの [&#x200B; 製品リスト &#x200B;](../../designing/using/using-product-listings.md) をメッセージのコンテンツに追加できます。 リストの各製品。

1. **[!UICONTROL Collections]** セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_collection_create.png)

1. コレクションのラベルと ID を追加します。
1. リストの各製品のトランザクションメッセージに表示するすべてのフィールドを追加します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

1. 「**[!UICONTROL Enrichment]**」タブを使用すると、コレクションの各項目をエンリッチメントできます。 これにより、Adobe Campaign データベースまたは自分で作成したその他のリソースの情報を使用して、対応する商品リストの要素をパーソナライズできます。

>[!NOTE]
>
>コレクションの要素をエンリッチメントする手順は、「[&#x200B; イベントのエンリッチメント &#x200B;](#enriching-the-transactional-message-content)」節で説明する手順と同じです。 イベントをエンリッチメントしても、コレクションをエンリッチメントすることはできません。コレクション自体にエンリッチメントを追加する必要が **[!UICONTROL Collections]** ります。

イベントとメッセージが公開されると、このコレクションをトランザクションメッセージで使用できるようになります。

この例での API プレビューは次のとおりです。

![](assets/message-center_collection_api-preview.png)

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](../../designing/using/using-product-listings.md)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## イベントの機能強化 {#enriching-the-transactional-message-content}

メッセージをパーソナライズするために、Adobe Campaign データベースの情報を使用してトランザクションメッセージのコンテンツを強化できます。 例えば、各受信者の姓または CRM ID から、住所や生年月日などのデータや、プロファイルテーブルに追加されたその他のカスタムフィールドを復元して、受信者に送信される情報をパーソナライズできます。

拡張 **[!UICONTROL Profile and services Ext API]** ータからの情報を使用して、トランザクションメッセージのコンテンツを強化できます。 詳しくは、[API の拡張：拡張機能の公開 &#x200B;](../../developing/using/step-2-publish-the-extension.md) を参照してください。

この情報は、新しいリソースに保存することもできます。 その場合、リソースは、直接または別のテーブルを介して **[!UICONTROL Profile]** または **[!UICONTROL Service]** リソースにリンクされている必要があります。 例えば、以下の設定では、**[!UICONTROL Product]** リソースが **[!UICONTROL Profile]** リソースにリンクされている場合、製品カテゴリや ID など、**[!UICONTROL Product]** リソースからの情報でトランザクションメッセージのコンテンツをエンリッチメントすることができます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、[&#x200B; この節 &#x200B;](../../developing/using/key-steps-to-add-a-resource.md) を参照してください。

1. **[!UICONTROL Enrichment]** セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 この場合は、**[!UICONTROL Profile]** リソースを選択します。

   ![](assets/message-center_new-enrichment.png)

1. 「**[!UICONTROL Create element]**」ボタンを使用して、選択したリソースのフィールドを、イベントに以前に追加したフィールドの 1 つにリンクします（[&#x200B; イベント属性の定義 &#x200B;](#defining-the-event-attributes) を参照）。

   ![](assets/message-center_enrichment-join.png)

   >[!NOTE]
   >
   >複数の受信者を選択できる条件（複数のプロファイルに対して同じ値を持つフィールドなど）を定義した場合、複数のプロファイルはターゲットになりません。

1. この例では、「**[!UICONTROL Last name]**」フィールドと「**[!UICONTROL First name]**」フィールドを、**[!UICONTROL Profile]** リソース内の対応するフィールドと紐付けます。

   ![](assets/message-center_enrichment-join-fields.png)

   また、**[!UICONTROL Service]** リソースを使用して、トランザクションメッセージのコンテンツをエンリッチメントすることもできます。 サービスについて詳しくは、[&#x200B; この節 &#x200B;](../../audiences/using/creating-a-service.md) を参照してください。

1. [&#x200B; プロファイルベースのイベント &#x200B;](#profile-based-transactional-messages) を作成または編集する場合は、「**[!UICONTROL Targeting enrichment]**」セクションで、配信の実行中にメッセージターゲットとして使用されるエンリッチメントを選択します。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >プロファイルベースのイベントの場合は、エンリッチメントの作成と、**[!UICONTROL Profile]** リソースに基づくターゲティングエンリッチメントの選択が必須です。

イベントとメッセージが公開されると、このリンクを使用してトランザクションメッセージのコンテンツをエンリッチメントできます。

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージのパーソナライズ](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## トランザクションイベントの検索 {#searching-transactional-events}

作成済みのトランザクションイベントにアクセスして検索するには、次の手順に従います。

1. 左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、**&#x200B;[!UICONTROL Marketing plans]&#x200B;**/**&#x200B;[!UICONTROL Transactional messages]&#x200B;**/**&#x200B;[!UICONTROL Event configuration]&#x200B;**を選択します。**
1. 「**[!UICONTROL Show search]**」ボタンをクリックします。

   ![](assets/message-center_search-events.png)

1. **[!UICONTROL Publication status]** ージに対してフィルタリングできます。 これにより、例えば、公開済みのイベントのみを表示できます。
1. **[!UICONTROL Last event received]** を使用してイベントをフィルタリングすることもできます。 例えば、10 と入力した場合、最後に受信したイベントが 10 日以上前のイベント設定のみが表示されます。 これにより、特定の期間に非アクティブであったイベントを表示できます。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >デフォルト値は 0 です。 すべてのイベントが表示されます。

## 特定の設定 {#transactional-event-specific-configurations}

トランザクションイベントの設定は、[&#x200B; トランザクションメッセージのタイプ &#x200B;](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) 送信する（イベントまたはプロファイル）、および使用するチャネルによって異なります。

以下の節では、目的のトランザクションメッセージに応じて設定すべき特定の設定について詳しく説明します。 イベントを設定するための一般的な手順について詳しくは、[&#x200B; イベントの作成 &#x200B;](#creating-an-event) を参照してください。

### イベントベースのトランザクションメッセージ {#event-based-transactional-messages}

イベントをターゲットにしたイベントトランザクションメッセージを送信できます。この種類のトランザクションメッセージには、プロファイル情報が含まれません。配信ターゲットは、イベント自体に含まれるデータによって定義されます。

イベントベースのトランザクションメッセージを送信するには、まず、**イベント自体に含まれるデータ** をターゲットにするイベントを作成して設定する必要があります。

1. イベント設定を作成する場合は、**[!UICONTROL Real-time event]** のターゲティングディメンションを選択します（[&#x200B; イベントの作成 &#x200B;](#creating-an-event) を参照）。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します（[&#x200B; イベント属性の定義 &#x200B;](#defining-the-event-attributes) を参照）。
1. イベントベースのトランザクションメッセージでは、送信されたイベントにあるデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義します。

   ただし、Adobe Campaign データベースから追加情報を使用する場合は、トランザクションメッセージコンテンツをエンリッチメントできます（[&#x200B; トランザクションメッセージコンテンツのエンリッチメント &#x200B;](#enriching-the-transactional-message-content) を参照）。

1. イベントをプレビューして公開します（[&#x200B; イベントのプレビューと公開 &#x200B;](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event) を参照）。

   イベントをプレビューする際、REST API には、選択したチャネルに応じて、メールアドレス、携帯電話、プッシュ通知固有の属性を指定する属性が含まれます。

   イベントが公開されると、新規イベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーにするには、作成したメッセージを [&#x200B; 変更 &#x200B;](../../channels/using/editing-transactional-message.md) および [&#x200B; 公開 &#x200B;](../../channels/using/publishing-transactional-message.md) する必要があります。

1. イベントを Web サイトに統合します（[&#x200B; イベントトリガーの統合 &#x200B;](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照）。

### プロファイルベースのトランザクションメッセージ {#profile-based-transactional-messages}

顧客プロファイルに基づいてトランザクションメッセージを送信できます。これにより、マーケティングタイポロジルールの適用、登録解除リンクの組み込み、グローバル配信レポートへのメッセージの追加およびカスタマージャーニーでの活用を行うことができます。

プロファイルベースのトランザクションメッセージを送信するには、まず、**Adobe Campaign データベースからのデータ** をターゲットにするイベントを作成して設定する必要があります。

1. イベント設定を作成する場合は、**[!UICONTROL Profile event]** のターゲティングディメンションを選択します（[&#x200B; イベントの作成 &#x200B;](#creating-an-event) を参照）。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します（[&#x200B; イベント属性の定義 &#x200B;](#defining-the-event-attributes) を参照）。 エンリッチメントを作成するには、少なくとも 1 つのフィールドを追加する必要があります。 Adobe Campaign データベースからパーソナライゼーションフィールドを使用できるので、**名** や **姓** など、他のフィールドを作成する必要はありません。
1. エンリッチメントを作成して、イベントを **[!UICONTROL Profile]** リソースにリンクし（[&#x200B; イベントのエンリッチメント &#x200B;](#enriching-the-transactional-message-content) を参照）、このエンリッチメントを **[!UICONTROL Targeting enrichment]** として選択します。

   >[!IMPORTANT]
   >
   >この手順は、プロファイルベースのイベントに必須です。

1. イベントをプレビューして公開します（[&#x200B; イベントのプレビューと公開 &#x200B;](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event) を参照）。

   イベントのプレビュー時に、REST API にはメールアドレス、携帯電話、プッシュ通知固有の属性を指定する属性は含まれていません。この属性は **[!UICONTROL Profile]** リソースから取得されるからです。

   イベントが公開されると、新規イベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーにするには、作成したメッセージを [&#x200B; 変更 &#x200B;](../../channels/using/editing-transactional-message.md) および [&#x200B; 公開 &#x200B;](../../channels/using/publishing-transactional-message.md) する必要があります。

1. イベントを Web サイトに統合します（[&#x200B; イベントトリガーの統合 &#x200B;](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照）。

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### トランザクションプッシュ通知 {#transactional-push-notifications}

2 種類のトランザクションプッシュ通知を送信できます。
* モバイルアプリケーションから通知を受信することをオプトインしたすべてのユーザーに対する匿名のトランザクションプッシュ通知。 [&#x200B; イベントベースのトランザクションプッシュ通知の設定 &#x200B;](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications) を参照してください。
* モバイルアプリケーションを購読しているAdobe Campaign プロファイルへのトランザクションプッシュ通知。 [&#x200B; プロファイルベースのトランザクションプッシュ通知の設定 &#x200B;](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications) を参照してください。

>[!IMPORTANT]
>
>トランザクションプッシュ通知を送信するには、それに応じてAdobe Campaignを設定する必要があります。 [&#x200B; モバイルアプリケーションの設定 &#x200B;](../../administration/using/configuring-a-mobile-application.md) を参照してください。

### フォローアップメッセージ {#follow-up-messages}

特定のトランザクションメッセージを受信した顧客にフォローアップメッセージを送信できます。

フォローアップメッセージを送信できるイベントを設定する手順については、[&#x200B; この節 &#x200B;](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message) を参照してください。
