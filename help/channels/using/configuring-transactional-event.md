---
solution: Campaign Standard
product: campaign
title: トランザクションイベントの設定
description: Adobe Campaignでトランザクションイベントを設定する方法について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: トランザクションメッセージ
role: User
level: Intermediate
exl-id: 1b91fb97-fe97-4564-936c-438be7ea7bc0
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1674'
ht-degree: 7%

---

# トランザクションイベントの設定 {#configuring-transactional-event}

Adobe Campaignでトランザクションメッセージを送信するには、まずイベントを作成して設定し、イベントデータの構造を説明する必要があります。

>[!IMPORTANT]
>
>[機能管理者](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->のみが、イベント設定の作成と編集に関する適切な権限を持っています。

設定は、送信するトランザクションメッセージの[タイプと、使用するチャネルによって異なります。 ](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)詳しくは、[特定の設定](#transactional-event-specific-configurations)を参照してください。

設定が完了したら、イベントを公開する必要があります。 [トランザクションイベントの公開](../../channels/using/publishing-transactional-event.md)を参照してください。

## イベントの作成 {#creating-an-event}

開始するには、必要に応じてイベントを作成します。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** を選択します。
1. 「**[!UICONTROL Create]**」ボタンをクリックします。
1. イベントの&#x200B;**[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL ID]**&#x200B;を入力します。 **[!UICONTROL ID]**&#x200B;フィールドは必須で、プレフィックス「EVT」で始まる必要があります。 このプレフィックスを使用しない場合、「**[!UICONTROL Create]**」をクリックすると自動的に追加されます。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >IDは、EVTプレフィックスを含めて64文字以下にする必要があります。

1. トランザクションメッセージ&#x200B;**[!UICONTROL Email]**、**[!UICONTROL Mobile (SMS)]**&#x200B;または&#x200B;**[!UICONTROL Push notification]**&#x200B;の送信に使用するチャネルを選択します。 各イベントに使用できるチャネルは1つだけで、後で変更することはできません。

1. 目的のイベント設定に対応するターゲティングディメンションを選択し、「**[!UICONTROL Create]**」をクリックします。

   イベントベースのトランザクションメッセージのターゲットデータはイベント自体に含まれるものなのに対して、プロファイルベースのトランザクションメッセージのターゲットデータはAdobe Campaignデータベースに含まれるものです。 詳しくは、[特定の設定](#transactional-event-specific-configurations)を参照してください。

>[!NOTE]
>
>トランザクションイベントの数は、プラットフォームに影響を与える可能性があります。 最適なパフォーマンスを確保するには、未使用のイベントを必ず削除してください。 [イベントの削除](../../channels/using/publishing-transactional-event.md#deleting-an-event)を参照してください。

## イベント属性の定義 {#defining-the-event-attributes}

**[!UICONTROL Fields]**&#x200B;セクションで、イベントコンテンツに統合され、トランザクションメッセージのパーソナライズに使用できる属性を定義します。

フィールドの追加と変更の手順は、[カスタムリソース](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)の場合と同じです。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は、**[!UICONTROL AC_language]** IDを使用して追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ適用されます。 イベントが公開された後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語の標準Eメールの場合と同じです。 [多言語のEメールの作成](../../channels/using/creating-a-multilingual-email.md)を参照してください。

## データコレクションの定義 {#defining-data-collections}

イベントコンテンツに要素のコレクションを追加し、各要素自体に複数の属性を含めることができます。

このコレクションは、トランザクション用のEメールで使用し、価格、参照番号、数量などを含む製品のリストなど、メッセージのコンテンツに[製品リスト](../../designing/using/using-product-listings.md)を追加できます。 リストの各製品に対して。

1. 「**[!UICONTROL Collections]**」セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_collection_create.png)

1. コレクションのラベルとIDを追加します。
1. リストの各製品のトランザクションメッセージに表示するすべてのフィールドを追加します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

1. 「**[!UICONTROL Enrichment]**」タブを使用すると、コレクションの各項目をエンリッチメントできます。 これにより、対応する製品リストの要素を、Adobe Campaignデータベースや作成した他のリソースからの情報を使用してパーソナライズできます。

>[!NOTE]
>
>コレクションの要素をエンリッチメントする手順は、[イベント](#enriching-the-transactional-message-content)のエンリッチメントの節で説明した手順と同じです。 イベントをエンリッチメントすると、コレクションのエンリッチメントができなくなります。**[!UICONTROL Collections]**&#x200B;セクションで、コレクション自体にエンリッチメントを追加する必要があります。

イベントとメッセージが公開されると、このコレクションをトランザクションメッセージで使用できるようになります。

この例のAPIプレビューを次に示します。

![](assets/message-center_collection_api-preview.png)

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](../../designing/using/using-product-listings.md)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## イベントのエンリッチメント {#enriching-the-transactional-message-content}

トランザクションメッセージのコンテンツをAdobe Campaignデータベースの情報でエンリッチメントして、メッセージをパーソナライズできます。 例えば、各受信者の姓またはCRM IDから、住所や生年月日などのデータや、プロファイルテーブルに追加されたその他のカスタムフィールドなどのデータを収集して、受信者に送信される情報をパーソナライズできます。

拡張&#x200B;**[!UICONTROL Profile and services Ext API]**&#x200B;の情報を使用して、トランザクションメッセージのコンテンツをエンリッチメントできます。 詳しくは、[APIの拡張を参照してください。拡張機能のパブリッシュ](../../developing/using/step-2--publish-the-extension.md)

この情報は、新しいリソースに保存することもできます。 その場合、リソースは、直接または別のテーブルを介して、**[!UICONTROL Profile]**&#x200B;リソースまたは&#x200B;**[!UICONTROL Service]**&#x200B;リソースにリンクされている必要があります。 例えば、以下の設定では、**[!UICONTROL Product]**&#x200B;リソースが&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクされている場合、製品カテゴリやIDなどの&#x200B;**[!UICONTROL Product]**&#x200B;リソースの情報を使用してトランザクションメッセージコンテンツをエンリッチメントできます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、[この節](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

1. 「**[!UICONTROL Enrichment]**」セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 この場合、**[!UICONTROL Profile]**&#x200B;リソースを選択します。

   ![](assets/message-center_new-enrichment.png)

1. **[!UICONTROL Create element]**&#x200B;ボタンを使用して、選択したリソースのフィールドを、イベントに以前に追加したフィールドの1つにリンクします（[イベント属性の定義](#defining-the-event-attributes)を参照）。

   ![](assets/message-center_enrichment-join.png)

1. この例では、**[!UICONTROL Last name]**&#x200B;フィールドと&#x200B;**[!UICONTROL First name]**&#x200B;フィールドを、**[!UICONTROL Profile]**&#x200B;リソース内の対応するフィールドに紐付けします。

   ![](assets/message-center_enrichment-join-fields.png)

   **[!UICONTROL Service]**&#x200B;リソースを使用して、トランザクションメッセージコンテンツをエンリッチメントすることもできます。 サービスについて詳しくは、[この節](../../audiences/using/creating-a-service.md)を参照してください。

1. [プロファイルベースのイベント](#profile-based-transactional-messages)を作成または編集する場合は、**[!UICONTROL Targeting enrichment]**&#x200B;セクションで、配信の実行中にメッセージターゲットとして使用するエンリッチメントを選択します。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >エンリッチメントを作成し、**[!UICONTROL Profile]**&#x200B;リソースに基づいてターゲティングエンリッチメントを選択することは、プロファイルベースのイベントに必須です。

イベントとメッセージが公開されると、このリンクを使用してトランザクションメッセージのコンテンツをエンリッチメントできます。

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージのパーソナライズ機能](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## トランザクションイベントの検索 {#searching-transactional-events}

作成済みのトランザクションイベントにアクセスして検索するには、次の手順に従います。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** を選択します。
1. 「**[!UICONTROL Show search]**」ボタンをクリックします。

   ![](assets/message-center_search-events.png)

1. **[!UICONTROL Publication status]**&#x200B;でフィルタリングできます。 これにより、例えば、公開済みのイベントのみを表示できます。
1. **[!UICONTROL Last event received]**&#x200B;を使用してイベントをフィルタリングすることもできます。 例えば、10と入力した場合は、10日以上前に受け取ったイベントを含むイベント設定のみが表示されます。 これにより、特定の期間非アクティブになったイベントを表示できます。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >デフォルト値は0です。 すべてのイベントが表示されます。

## 特定の設定 {#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージ[のタイプ（イベントまたはプロファイル）と、使用するチャネルによって異なります。](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)

以下の節では、目的のトランザクションメッセージに応じて設定する特定の設定について詳しく説明します。 イベントを設定する一般的な手順について詳しくは、[イベント](#creating-an-event)の作成を参照してください。

### イベントベースのトランザクションメッセージ {#event-based-transactional-messages}

イベントをターゲットにしたイベントトランザクションメッセージを送信できます。この種類のトランザクションメッセージには、プロファイル情報が含まれません。配信ターゲットは、イベント自体に含まれるデータによって定義されます。

イベントベースのトランザクションメッセージを送信するには、まず、イベント自体&#x200B;**に含まれる**&#x200B;データをターゲットにしたイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Real-time event]**&#x200B;ターゲティングディメンションを選択します（[イベントの作成](#creating-an-event)を参照）。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します（[イベント属性の定義](#defining-the-event-attributes)を参照）。
1. イベントベースのトランザクションメッセージでは、受信者とメッセージコンテンツのパーソナライゼーションを定義するために、送信イベント内のデータのみを使用することが想定されています。

   ただし、Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージのコンテンツをエンリッチメントできます（[トランザクションメッセージのコンテンツのエンリッチメント](#enriching-the-transactional-message-content)を参照）。

1. イベントをプレビューして公開します（[イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照）。

   イベントをプレビューする場合、REST APIには、選択したチャネルに応じて、Eメールアドレス、携帯電話、またはプッシュ通知固有の属性を指定する属性が含まれます。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージを送信するトリガーになるには、作成したメッセージを[変更](../../channels/using/editing-transactional-message.md)および[公開](../../channels/using/publishing-transactional-message.md)する必要があります。

1. イベントをWebサイトに統合します（[イベントトリガーを統合する](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照）。

### プロファイルベースのトランザクションメッセージ {#profile-based-transactional-messages}

顧客プロファイルに基づいてトランザクションメッセージを送信し、マーケティングタイポロジルールを適用し、購読解除リンクを含めて、メッセージをグローバル配信レポートに追加して、カスタマージャーニーで活用できます。

プロファイルベースのトランザクションメッセージを送信するには、まずAdobe Campaignデータベース&#x200B;**の**&#x200B;データをターゲットとするイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Profile event]**&#x200B;ターゲティングディメンションを選択します（[イベントの作成](#creating-an-event)を参照）。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します（[イベント属性の定義](#defining-the-event-attributes)を参照）。 エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるので、**名**&#x200B;や&#x200B;**姓**&#x200B;など、他のフィールドを作成する必要はありません。
1. イベントを&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクするためにエンリッチメントを作成し（[イベントのエンリッチメント](#enriching-the-transactional-message-content)を参照）、このエンリッチメントを&#x200B;**[!UICONTROL Targeting enrichment]**&#x200B;として選択します。

   >[!IMPORTANT]
   >
   >この手順は、プロファイルベースのイベントでは必須です。

1. イベントをプレビューして公開します（[イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照）。

   イベントをプレビューする場合、REST APIには、Eメールアドレス、携帯電話、またはプッシュ通知固有の属性を指定する属性が含まれません。これは、 **[!UICONTROL Profile]**&#x200B;リソースから取得されるからです。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージを送信するトリガーに対して実行するには、作成したメッセージを[変更](../../channels/using/editing-transactional-message.md)および[公開](../../channels/using/publishing-transactional-message.md)する必要があります。

1. イベントをWebサイトに統合します（[イベントトリガーを統合する](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照）。

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### トランザクションプッシュ通知 {#transactional-push-notifications}

次の2種類のトランザクションプッシュ通知を送信できます。
* モバイルアプリケーションからの通知の受信をオプトインしたすべてのユーザーに対する匿名トランザクションプッシュ通知。 [イベントベースのトランザクションプッシュ通知の設定](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications)を参照してください。
* モバイルアプリケーションを購読したAdobe Campaignプロファイルへのトランザクションプッシュ通知。 [プロファイルベースのトランザクションプッシュ通知の設定](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications)を参照してください。

>[!IMPORTANT]
>
>トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。 [モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)を参照してください。

### フォローアップメッセージ {#follow-up-messages}

特定のトランザクションメッセージを受け取った顧客にフォローアップメッセージを送信できます。

フォローアップメッセージを送信するイベントを設定する手順については、[この節](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message)で詳しく説明します。
