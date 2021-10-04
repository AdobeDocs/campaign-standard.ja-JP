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
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 6%

---

# トランザクションイベントの設定 {#configuring-transactional-event}

Adobe Campaignでトランザクションメッセージを送信するには、まずイベントを作成して設定し、イベントデータの構造を説明する必要があります。

>[!IMPORTANT]
>
>[ 機能管理者 ](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) --> のみが、イベント設定を作成および編集するための適切な権限を持っています。

設定は、送信するトランザクションメッセージの [ タイプと、使用するチャネルによって異なります。](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) 詳しくは、[ 特定の設定 ](#transactional-event-specific-configurations) を参照してください。

設定が完了したら、イベントを公開する必要があります。 [ トランザクションイベントの公開 ](../../channels/using/publishing-transactional-event.md) を参照してください。

## イベントの作成 {#creating-an-event}

開始するには、必要に応じてイベントを作成します。

1. 左上隅の **Adobe** ロゴをクリックし、**[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** / **[!UICONTROL Event configuration]** を選択します。
1. 「**[!UICONTROL Create]**」ボタンをクリックします。
1. イベントの **[!UICONTROL Label]** と **[!UICONTROL ID]** を入力します。 **[!UICONTROL ID]** フィールドは必須で、プレフィックス「EVT」で始まる必要があります。 このプレフィックスを使用しない場合は、「**[!UICONTROL Create]**」をクリックすると自動的に追加されます。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID は、EVT プレフィックスを含めて 64 文字以下にする必要があります。

1. トランザクションメッセージ **[!UICONTROL Email]**、**[!UICONTROL Mobile (SMS)]** または **[!UICONTROL Push notification]** の送信に使用するチャネルを選択します。 各イベントで使用できるチャネルは 1 つだけです。後で変更することはできません。

1. 目的のイベント設定に対応するターゲティングディメンションを選択し、「**[!UICONTROL Create]**」をクリックします。

   イベントベースのトランザクションメッセージのターゲットデータはイベント自体に含まれるものに対して、プロファイルベースのトランザクションメッセージのターゲットデータはAdobe Campaignデータベースに含まれるものに対して、 詳しくは、[ 特定の設定 ](#transactional-event-specific-configurations) を参照してください。

>[!NOTE]
>
>トランザクションイベントの数は、プラットフォームに影響を与える可能性があります。 最適なパフォーマンスを確保するには、未使用のイベントを必ず削除してください。 [ イベントの削除 ](../../channels/using/publishing-transactional-event.md#deleting-an-event) を参照してください。

## イベント属性の定義 {#defining-the-event-attributes}

**[!UICONTROL Fields]** セクションで、イベントコンテンツに統合され、トランザクションメッセージのパーソナライズに使用できる属性を定義します。

フィールドの追加と変更の手順は、[ カスタムリソース ](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource) の場合と同じです。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は、**[!UICONTROL AC_language]** ID を使用して追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ適用されます。 イベントが公開された後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語の標準 E メールの場合と同じです。 [ 多言語の E メールの作成 ](../../channels/using/creating-a-multilingual-email.md) を参照してください。

## データコレクションの定義 {#defining-data-collections}

イベントコンテンツに要素のコレクションを追加できます。各要素自体には複数の属性が含まれます。

このコレクションは、トランザクション用の E メールで使用して、[ 製品リスト ](../../designing/using/using-product-listings.md) をメッセージのコンテンツに追加できます。例えば、製品のリスト（価格、参照番号、数量など）を追加できます。 リストの各製品の

1. 「**[!UICONTROL Collections]**」セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_collection_create.png)

1. コレクションのラベルと ID を追加します。
1. リストの各製品のトランザクションメッセージに表示するすべてのフィールドを追加します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

1. 「 **[!UICONTROL Enrichment]** 」タブを使用すると、コレクションの各項目をエンリッチメントできます。 これにより、対応する製品リストの要素を、Adobe Campaignデータベースや作成した他のリソースからの情報を使用してパーソナライズできます。

>[!NOTE]
>
>コレクションの要素をエンリッチメントする手順は、[ イベントのエンリッチメント ](#enriching-the-transactional-message-content) の節で説明した手順と同じです。 イベントをエンリッチメントすると、コレクションのエンリッチメントができなくなります。**[!UICONTROL Collections]** セクションのコレクション自体にエンリッチメントを追加する必要があります。

イベントとメッセージが公開されると、トランザクションメッセージでこのコレクションを使用できるようになります。

この例の API プレビューを次に示します。

![](assets/message-center_collection_api-preview.png)

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](../../designing/using/using-product-listings.md)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## イベントのエンリッチメント {#enriching-the-transactional-message-content}

トランザクションメッセージのコンテンツをAdobe Campaignデータベースの情報でエンリッチメントして、メッセージをパーソナライズできます。 例えば、各受信者の姓または CRM ID から、住所や生年月日などのデータや、プロファイルテーブルに追加されたその他のカスタムフィールドなどのデータを取得して、受信者に送信される情報をパーソナライズできます。

拡張 **[!UICONTROL Profile and services Ext API]** の情報を使用して、トランザクションメッセージのコンテンツをエンリッチメントできます。 詳しくは、[API の拡張を参照してください。拡張機能の公開 ](../../developing/using/step-2--publish-the-extension.md)

この情報は、新しいリソースに保存することもできます。 その場合、リソースは **[!UICONTROL Profile]** リソースまたは **[!UICONTROL Service]** リソースに直接リンクするか、別のテーブルを介してリンクする必要があります。 例えば、以下の設定では、**[!UICONTROL Product]** リソースが **[!UICONTROL Profile]** リソースにリンクされている場合、製品カテゴリや ID など、**[!UICONTROL Product]** リソースからの情報でトランザクションメッセージコンテンツをエンリッチメントできます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、[ この節 ](../../developing/using/key-steps-to-add-a-resource.md) を参照してください。

1. 「**[!UICONTROL Enrichment]**」セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 この場合は、**[!UICONTROL Profile]** リソースを選択します。

   ![](assets/message-center_new-enrichment.png)

1. **[!UICONTROL Create element]** ボタンを使用して、選択したリソースのフィールドを、イベントに以前に追加したフィールドの 1 つにリンクします（[ イベント属性の定義 ](#defining-the-event-attributes) を参照）。

   ![](assets/message-center_enrichment-join.png)

1. この例では、**[!UICONTROL Last name]** フィールドと **[!UICONTROL First name]** フィールドを、**[!UICONTROL Profile]** リソース内の対応するフィールドと紐付けします。

   ![](assets/message-center_enrichment-join-fields.png)

   また、**[!UICONTROL Service]** リソースを使用して、トランザクションメッセージのコンテンツをエンリッチメントすることもできます。 サービスについて詳しくは、[ この節 ](../../audiences/using/creating-a-service.md) を参照してください。

1. [ プロファイルベースのイベント ](#profile-based-transactional-messages) を作成または編集する場合は、「**[!UICONTROL Targeting enrichment]**」セクションで、配信の実行中にメッセージターゲットとして使用するエンリッチメントを選択します。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >エンリッチメントを作成し、**[!UICONTROL Profile]** リソースに基づいてターゲティングエンリッチメントを選択することは、プロファイルベースのイベントでは必須です。

イベントとメッセージが公開されると、このリンクを使用してトランザクションメッセージのコンテンツをエンリッチメントできます。

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージのパーソナライズ機能](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## トランザクションイベントの検索 {#searching-transactional-events}

作成済みのトランザクションイベントにアクセスして検索するには、次の手順に従います。

1. 左上隅の **Adobe** ロゴをクリックし、**[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** / **[!UICONTROL Event configuration]** を選択します。
1. 「**[!UICONTROL Show search]**」ボタンをクリックします。

   ![](assets/message-center_search-events.png)

1. **[!UICONTROL Publication status]** でフィルタリングできます。 これにより、例えば、公開済みのイベントのみを表示できます。
1. **[!UICONTROL Last event received]** を使用してイベントをフィルタリングすることもできます。 例えば、10 と入力した場合は、10 日以上前にイベントを受け取ったイベント設定のみが表示されます。 これにより、特定の期間非アクティブになったイベントを表示できます。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >デフォルト値は 0 です。 すべてのイベントが表示されます。

## 特定の設定 {#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージ [ のタイプ（イベントまたはプロファイル）と、使用するチャネルによって異なります。](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)

以下の節では、目的のトランザクションメッセージに応じて具体的な設定を指定します。 イベントを設定する一般的な手順について詳しくは、[ イベント ](#creating-an-event) の作成を参照してください。

### イベントベースのトランザクションメッセージ {#event-based-transactional-messages}

イベントをターゲットにしたイベントトランザクションメッセージを送信できます。この種類のトランザクションメッセージには、プロファイル情報が含まれません。配信ターゲットは、イベント自体に含まれるデータによって定義されます。

イベントベースのトランザクションメッセージを送信するには、まず、イベント自体 **に含まれる** データをターゲットとするイベントを作成して設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Real-time event]** ターゲティングディメンションを選択します（[ イベント ](#creating-an-event) の作成を参照）。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します（[ イベント属性の定義 ](#defining-the-event-attributes) を参照）。
1. イベントベースのトランザクションメッセージでは、受信者とメッセージコンテンツのパーソナライゼーションを定義するために、送信イベント内のデータのみを使用することが想定されています。

   ただし、Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージのコンテンツをエンリッチメントできます（[ トランザクションメッセージのコンテンツのエンリッチメント ](#enriching-the-transactional-message-content) を参照）。

1. イベントをプレビューして公開します（[ イベントのプレビューと公開 ](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event) を参照）。

   イベントをプレビューする場合、REST API には、選択したチャネルに従って、E メールアドレス、携帯電話、またはプッシュ通知固有の属性を指定する属性が含まれます。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージを送信する際にトリガーを設定するには、作成したメッセージを [ 変更 ](../../channels/using/editing-transactional-message.md) および [ 公開 ](../../channels/using/publishing-transactional-message.md) する必要があります。

1. イベントを Web サイトに統合します（[ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照）。

### プロファイルベースのトランザクションメッセージ {#profile-based-transactional-messages}

マーケティングタイポロジルールを適用し、購読解除リンクを含めて、メッセージをグローバル配信レポートに追加し、カスタマージャーニーで活用できる、顧客プロファイルに基づいてトランザクションメッセージを送信できます。

プロファイルベースのトランザクションメッセージを送信するには、まずAdobe Campaignデータベース **の** データをターゲットとするイベントを作成して設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Profile event]** ターゲティングディメンションを選択します（[ イベント ](#creating-an-event) の作成を参照）。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します（[ イベント属性の定義 ](#defining-the-event-attributes) を参照）。 エンリッチメントを作成するには、少なくとも 1 つのフィールドを追加する必要があります。 Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるので、**名** や **姓** など、他のフィールドを作成する必要はありません。
1. イベントを **[!UICONTROL Profile]** リソースにリンクするエンリッチメントを作成し（[ イベントのエンリッチメント ](#enriching-the-transactional-message-content) を参照）、このエンリッチメントを **[!UICONTROL Targeting enrichment]** として選択します。

   >[!IMPORTANT]
   >
   >この手順は、プロファイルベースのイベントでは必須です。

1. イベントをプレビューして公開します（[ イベントのプレビューと公開 ](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event) を参照）。

   イベントをプレビューする場合、REST API には、E メールアドレス、携帯電話、またはプッシュ通知固有の属性を指定する属性が含まれません。これは、 **[!UICONTROL Profile]** リソースから取得されます。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージを送信する際にトリガーを設定するには、作成したメッセージを [ 変更 ](../../channels/using/editing-transactional-message.md) および [ 公開 ](../../channels/using/publishing-transactional-message.md) する必要があります。

1. イベントを Web サイトに統合します（[ イベントトリガーの統合 ](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) を参照）。

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### トランザクションプッシュ通知 {#transactional-push-notifications}

次の 2 種類のトランザクションプッシュ通知を送信できます。
* モバイルアプリケーションからの通知の受信をオプトインしたすべてのユーザーに対する匿名トランザクションプッシュ通知。 [ イベントベースのトランザクションプッシュ通知の設定 ](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications) を参照してください。
* モバイルアプリケーションを購読したAdobe Campaignプロファイルへのトランザクションプッシュ通知。 [ プロファイルベースのトランザクションプッシュ通知の設定 ](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications) を参照してください。

>[!IMPORTANT]
>
>トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。 [ モバイルアプリケーションの設定 ](../../administration/using/configuring-a-mobile-application.md) を参照してください。

### フォローアップメッセージ {#follow-up-messages}

特定のトランザクションメッセージを受け取った顧客にフォローアップメッセージを送信できます。

フォローアップメッセージを送信するイベントを設定する手順については、[ この節 ](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message) を参照してください。
