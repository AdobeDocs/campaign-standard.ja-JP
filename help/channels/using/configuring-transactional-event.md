---
solution: Campaign Standard
product: campaign
title: トランザクションイベントの設定
description: Adobe Campaignでトランザクションイベントを設定する方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 6%

---


# トランザクションイベントの設定{#configuring-transactional-event}

Adobe Campaign付きのトランザクションメッセージを送信するには、まずイベントを作成し、設定してイベントデータの構造を説明する必要があります。

>[!IMPORTANT]
>
>[機能的な管理者](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->のみが、イベント設定を作成および編集する適切な権限を持っています。

設定は、送信するトランザクションメッセージ](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)の[タイプ、および使用するチャネルによって異なります。 詳しくは、[固有の設定](#transactional-event-specific-configurations)を参照してください。

設定が完了したら、イベントを公開する必要があります。 詳しくは、[トランザクションイベントの公開](../../channels/using/publishing-transactional-event.md)を参照してください。

## イベントの作成 {#creating-an-event}

開始するには、必要に応じてイベントを作成します。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** を選択します。
1. 「**[!UICONTROL Create]**」ボタンをクリックします。
1. イベントの&#x200B;**[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL ID]**&#x200B;を入力します。 **[!UICONTROL ID]**&#x200B;フィールドは必須で、プレフィックス「EVT」で始まる必要があります。 このプレフィックスを使用しない場合は、**[!UICONTROL Create]**&#x200B;をクリックすると自動的に追加されます。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >IDは、EVTプレフィックスを含めて64文字以下にする必要があります。

1. トランザクションメッセージ&#x200B;**[!UICONTROL Email]**、**[!UICONTROL Mobile (SMS)]**、または&#x200B;**[!UICONTROL Push notification]**&#x200B;の送信に使用するチャネルを選択します。 各イベントに使用できるチャネルは1つだけで、後で変更することはできません。

1. 目的のイベント設定に対応するターゲティングディメンションを選択し、**[!UICONTROL Create]**&#x200B;をクリックします。

   イベント自体に含まれるイベントベースのトランザクションメッセージターゲットデータに対し、Adobe Campaignデータベースに含まれるプロファイルベースのトランザクションメッセージターゲットデータに対して、 詳しくは、[具体的な設定](#transactional-event-specific-configurations)を参照してください。

>[!NOTE]
>
>トランザクションイベントの数がプラットフォームに影響を与える可能性があります。 最適なパフォーマンスを得るために、未使用のイベントは必ず削除してください。 「[イベントの削除](../../channels/using/publishing-transactional-event.md#deleting-an-event)」を参照してください。

## イベント属性の定義{#defining-the-event-attributes}

**[!UICONTROL Fields]**&#x200B;セクションで、イベントコンテンツに統合され、トランザクションメッセージをパーソナライズするために使用できる属性を定義します。

フィールドの追加と変更の手順は、[カスタムリソース](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)の場合と同じです。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は、**[!UICONTROL AC_language]** IDを使用して追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ適用されます。 イベントの公開後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語標準の電子メールの手順と同じです。 [多言語電子メールの作成](../../channels/using/creating-a-multilingual-email.md)を参照してください。

## データコレクションの定義{#defining-data-collections}

イベントコンテンツに、要素の集まりを追加できます。各要素には、複数の属性が含まれます。

このコレクションは、メッセージの内容に[商品リスト](../../channels/using/editing-transactional-message.md#using-product-listings-in-a-transactional-message)を追加するためのトランザクション用電子メールで使用できます。例えば、商品のリスト（価格、参照番号、数量など）が含まれます。 をリストの各製品に対して設定します。

1. 「**[!UICONTROL Collections]**」セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_collection_create.png)

1. コレ追加クションのラベルとID。
1. トランザクションメッセージに表示するす追加べてのフィールドで、リストの各製品を表示します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

1. 「**[!UICONTROL Enrichment]**」タブを使用すると、コレクションの各項目を拡張できます。 これにより、対応する製品リストの要素を、Adobe Campaignデータベースや作成した他のリソースの情報と共にパーソナライズできます。

>[!NOTE]
>
>コレクションの要素を富化する手順は、「[イベントの富化](#enriching-the-transactional-message-content)」の節で説明した手順と同じです。 イベントを強化しても、コレクションを強化することはできません。**[!UICONTROL Collections]**&#x200B;セクション内のコレクション自体にエンリッチメントを追加する必要があります。

イベントとメッセージが公開されると、このコレクションをトランザクションメッセージで使用できるようになります。

この例のAPIプレビューを次に示します。

![](assets/message-center_collection_api-preview.png)

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](../../channels/using/editing-transactional-message.md#using-product-listings-in-a-transactional-message)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## イベントを強化{#enriching-the-transactional-message-content}

トランザクションメッセージのコンテンツをAdobe Campaignデータベースの情報と共に拡張して、メッセージをパーソナライズすることができます。 例えば、各受信者の姓またはCRM IDから、住所や生年月日などのデータや、プロファイルテーブルに追加された他のカスタムフィールドなどのデータを回復し、送信する情報をパーソナライズできます。

拡張&#x200B;**[!UICONTROL Profile and services Ext API]**&#x200B;からの情報でトランザクションメッセージの内容を拡張することができます。 詳しくは、[APIの拡張を参照してください。拡張機能の公開](../../developing/using/step-2--publish-the-extension.md)

この情報は、新しいリソースにも保存できます。 この場合、リソースは&#x200B;**[!UICONTROL Profile]**&#x200B;または&#x200B;**[!UICONTROL Service]**&#x200B;リソースに直接リンクするか、別のテーブルを介してリンクする必要があります。 例えば、以下の設定では、**[!UICONTROL Product]**&#x200B;リソースが&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクされている場合、トランザクションメッセージの内容を製品のカテゴリやIDなどの&#x200B;**[!UICONTROL Product]**&#x200B;リソースからの情報で拡張できます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、[このセクション](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

1. 「**[!UICONTROL Enrichment]**」セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 この場合は、**[!UICONTROL Profile]**&#x200B;リソースを選択します。

   ![](assets/message-center_new-enrichment.png)

1. **[!UICONTROL Create element]**&#x200B;ボタンを使用して、選択したリソースのフィールドを、以前にイベントに追加したフィールドの1つにリンクします(「[イベント属性の定義](#defining-the-event-attributes)」を参照)。

   ![](assets/message-center_enrichment-join.png)

1. この例では、**[!UICONTROL Last name]**&#x200B;と&#x200B;**[!UICONTROL First name]**&#x200B;のフィールドを&#x200B;**[!UICONTROL Profile]**&#x200B;リソースの対応するフィールドと紐付けます。

   ![](assets/message-center_enrichment-join-fields.png)

   **[!UICONTROL Service]**&#x200B;リソースを使用して、トランザクションメッセージの内容を拡張することもできます。 サービスの詳細については、[このセクション](../../audiences/using/creating-a-service.md)を参照してください。

1. [プロファイルベースのイベント](#profile-based-transactional-messages)を作成または編集する場合は、**[!UICONTROL Targeting enrichment]**&#x200B;セクションで、配信の実行時にメッセージターゲットとして使用するエンリッチメントを選択します。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >エンリッチメントを作成し、**[!UICONTROL Profile]**&#x200B;リソースに基づいてターゲットエンリッチメントを選択することは、プロファイルベースのイベントには必須です。

イベントとメッセージが公開されると、このリンクを使用してトランザクションメッセージのコンテンツを拡充できます。

**関連トピック：**

* [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [トランザクションメッセージのパーソナライズ機能](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## トランザクションイベントの検索{#searching-transactional-events}

作成済みのトランザクションイベントにアクセスして検索するには、次の手順に従います。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** を選択します。
1. 「**[!UICONTROL Show search]**」ボタンをクリックします。

   ![](assets/message-center_search-events.png)

1. **[!UICONTROL Publication status]**&#x200B;をフィルタリングできます。 これにより、例えば、公開済みのイベントのみを表示できます。
1. **[!UICONTROL Last event received]**&#x200B;を使用してイベントをフィルタリングすることもできます。 例えば、10と入力した場合、最後に受け取ったイベントが10日以上前にイベントされた設定のみが表示されます。 これにより、特定の期間非アクティブだったイベントを表示できます。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >デフォルト値は0です。 すべてのイベントが表示されます。

## 特定の構成{#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージ[のタイプ(イベントまたはプロファイル)と、使用するチャネルによって異なります。](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)

以下の節では、目的のトランザクションメッセージに応じて具体的な設定を行う必要がある場合について説明します。 イベントを設定する一般的な手順については、[イベントの作成](#creating-an-event)を参照してください。

### イベントベースのトランザクションメッセージ{#event-based-transactional-messages}

イベントをターゲットにしたイベントトランザクションメッセージを送信できます。この種類のトランザクションメッセージには、プロファイル情報が含まれません。配信ターゲットは、イベント自体に含まれるデータによって定義されます。

イベントベースのトランザクションメッセージを送信するには、まず、イベント自体&#x200B;**に含まれる**&#x200B;データをターゲットにしたイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Real-time event]**&#x200B;ターゲティングディメンションを選択します(「[イベントの作成](#creating-an-event)」を参照)。
1. イベントに追加対するフィールド。トランザクションメッセージをパーソナライズできるようにするために使用します(「[イベント属性の定義](#defining-the-event-attributes)」を参照)。
1. イベントベースのトランザクションメッセージでは、受信者とメッセージコンテンツのパーソナライゼーションを定義するために、送信イベント内のデータのみを使用することが想定されています。

   ただし、Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージの内容を拡張できます(「[トランザクションメッセージの内容を強化する](#enriching-the-transactional-message-content)」を参照)。

1. イベントをプレビューして公開します([イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照)。

   イベントをプレビューする場合、REST APIには、選択したチャネルに従って、電子メールアドレス、携帯電話、またはプッシュ通知の固有の属性を指定する属性が含まれます。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを[modify](../../channels/using/editing-transactional-message.md)および[publish](../../channels/using/publishing-transactional-message.md)に変更する必要があります。

1. イベントをWebサイトに統合します([イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照)。

### プロファイルベースのトランザクションメッセージ{#profile-based-transactional-messages}

顧客プロファイルに基づいてトランザクションメッセージを送信できます。これにより、マーケティングタイポロジルールの適用、登録解除リンクの含め、グローバル配信レポートにメッセージを追加し、顧客の遍歴で活用できます。

プロファイルベースのトランザクションメッセージを送信するには、まず、Adobe Campaignデータベース&#x200B;**の**&#x200B;データをターゲットにしたイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Profile event]**&#x200B;ターゲティングディメンションを選択します(「[イベントの作成](#creating-an-event)」を参照)。
1. イベントに追加対するフィールド。トランザクションメッセージをパーソナライズできるようにするために使用します(「[イベント属性の定義](#defining-the-event-attributes)」を参照)。 エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 **名**&#x200B;や&#x200B;**姓**&#x200B;など、Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるフィールドを作成する必要はありません。
1. イベントを&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクするエンリッチメントを作成し(「[イベントの強化](#enriching-the-transactional-message-content)」を参照)、このエンリッチメントを&#x200B;**[!UICONTROL Targeting enrichment]**&#x200B;として選択します。

   >[!IMPORTANT]
   >
   >この手順は、プロファイルベースのイベントでは必須です。

1. イベントをプレビューして公開します([イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照)。

   イベントをプレビューする場合、REST APIには、電子メールアドレス、携帯電話、またはプッシュ通知の固有の属性を指定する属性が含まれません。この属性は&#x200B;**[!UICONTROL Profile]**&#x200B;リソースから取得されます。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを[modify](../../channels/using/editing-transactional-message.md)および[publish](../../channels/using/publishing-transactional-message.md)に変更する必要があります。

1. イベントをWebサイトに統合します([イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照)。

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### トランザクションプッシュ通知 {#transactional-push-notifications}

2種類のトランザクションプッシュ通知を送信できます。
* モバイルアプリケーションからの通知の受信を選択しているすべてのユーザーに対する匿名トランザクションプッシュ通知。 [イベントベースのトランザクションプッシュ通知の設定](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications)を参照してください。
* モバイルアプリケーションをサブスクライブしたAdobe Campaignプロファイルへのトランザクションプッシュ通知。 [プロファイルベースのトランザクションプッシュ通知の設定](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications)を参照してください。

>[!IMPORTANT]
>
>トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。 「[モバイルアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md)」を参照してください。

### フォローアップメッセージ {#follow-up-messages}

特定のトランザクションメッセージを受け取った顧客にフォローアップメッセージを送信できます。

フォローアップメッセージの送信を許可するイベントを設定する手順については、[このセクション](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message)で詳しく説明します。
