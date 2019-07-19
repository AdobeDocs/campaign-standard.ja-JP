---
title: トランザクションメッセージの設定
seo-title: トランザクションメッセージの設定
description: トランザクションメッセージの設定
seo-description: トランザクションメッセージを設定する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 4ceadbe- f4a7-43ce-986d- e99fa9ca0d0d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: configuring- channels
discoiquuid: 3f968556- e774-43dc- a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring transactional messaging{#configuring-transactional-messaging}

Adobe Campaignでトランザクションメッセージを送信するには、まずイベントデータの構造を記述する必要があります。

Event configuration must be performed by an **administrator** by following the steps below:

設定は、送信するトランザクションメッセージの種類によって異なります。For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

イベントが発行されると、対応するトランザクションメッセージが自動的に作成されます。For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## Creating an event {#creating-an-event}

まず、ニーズに対応するイベントを作成します。

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Click the **[!UICONTROL Create]** button.
1. Give a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to the event. **[!UICONTROL ID]** フィールドは必須で、プリフィックス"EVT"で始まる必要があります。If you do not use this prefix, it is automatically added once you click **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

1. Select the channel that will be used to send your transactional messages **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** (push notification).

   >[!NOTE]
   >
   >各イベント設定に使用できるチャネルは1つだけです。イベントが作成されると、チャネルを変更することはできません。

1. Select the targeting dimension corresponding to the desired event configuration and click **[!UICONTROL Create]**.

   イベントベースのトランザクションメッセージは、Adobe Campaignデータベースに格納されているデータに基づいて、イベント自体に含まれるデータをターゲットにしたトランザクションメッセージです。For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Defining the event attributes {#defining-the-event-attributes}

**[!UICONTROL Fields]** セクションで、イベントコンテンツに統合される属性を定義し、トランザクションメッセージをパーソナライズするために使用できるようにします。

The steps for adding and modifying fields are the same as for [custom resources](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>If you want to create a multilingual transactional message, define an additional event attribute with the **[!UICONTROL AC_language]** ID. これはイベントトランザクションメッセージにのみ適用されます。イベントが発行された後、多言語トランザクションメッセージの編集手順は多言語標準電子メールと同じです。See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## Defining data collections {#defining-data-collections}

イベントコンテンツに追加して、複数の属性を含む各要素自体に要素を追加できます。

このコレクションをトランザクション電子メールで使用して、製品のリスト（価格、参照番号、数量など）に製品リストを追加することができます。をクリックします。

1. **[!UICONTROL Collections]** セクションで、ボタンを **[!UICONTROL Create element]** クリックします。

   ![](assets/message-center_collection_create.png)

1. コレクションにラベルとIDを追加します。
1. リストの各製品のトランザクションメッセージに表示するすべてのフィールドを追加します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

イベントが公開されると、トランザクションメッセージでこのコレクションを使用できるようになります。

以下に、この例のAPIプレビューを示します。

![](assets/message-center_collection_api-preview.png)

**関連トピック:**

* [イベントのプレビューと公開](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enriching the transactional message content {#enriching-the-transactional-message-content}

Adobe Campaignデータベースの情報を使用してトランザクションメッセージコンテンツを充実させることで、メッセージをパーソナライズできます。例えば、各受信者の姓またはCRM IDから、ユーザーに送信される情報をパーソナライズするために、自分の住所や生年月日などのデータを元に戻したり、プロファイルテーブルに追加されたその他のカスタムフィールドを使用したりできます。

It is possible to enrich the transactional message content with information from extended **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources.

この情報は、新しいリソースにも保存できます。In that case, the resource must be linked to the **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources either directly, or via another table. For example, in the configuration below, it is possible to enrich the transactional message content with information from the **[!UICONTROL Product]** resource like the product category or ID, if the **[!UICONTROL Product]** resource is linked to the **[!UICONTROL Profile]** resource.

![](assets/message-center_usecaseschema.png)

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-of-adding-a-resource.md).

1. **[!UICONTROL Enrichment]** セクションで、ボタンを **[!UICONTROL Create element]** クリックします。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use the **[!UICONTROL Create element]** button to link a field from the selected resource to one of the fields you previously added to the event (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In this example, we reconcile the **[!UICONTROL Last name]** and the **[!UICONTROL First name]** fields with the corresponding fields in the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_enrichment-join-fields.png)

1. **[!UICONTROL Targeting enrichment]** セクションで、配信の実行中にメッセージターゲットとして使用されるエンリッチメントを選択します。In this example, select **[!UICONTROL Profile]**. プロファイルベースのイベントには、ターゲット化の強化を選択する必要があります。

   ![](assets/message-center_marketing_targeting_enrichment.png)

Once the event and the message are published, the link with the **[!UICONTROL Profile]** resource will allow you to enrich the content of the transactional message.

**関連トピック:**

* [イベント](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)のプレビューと公開
* [トランザクションメッセージをパーソナライズ](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)します。

## Previewing and publishing the event {#previewing-and-publishing-the-event}

イベントを使用するには、プレビューして公開する必要があります。

1. Click the **[!UICONTROL API preview]** button to see a simulation of the REST API that will be used by your website developer before it is published. イベントが公開されると、このボタンによって、本番環境でのAPIのプレビューも表示できます。See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST APIは、選択したチャネルと選択したターゲットディメンションによって異なります。For more details on the various configurations, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Click **[!UICONTROL Publish]** to start publication.

   ![](assets/message-center_pub.png)

1. 対応するタブを選択して、パブリケーションログを表示できます。

   ![](assets/message-center_logs.png)

   また、タブを選択して前のパブリケーションを参照することもできます。

>[!NOTE]
>
>Each time you modify the event, you must click **[!UICONTROL Publish]** again to generate the updated REST API that will be used by your website developer.

イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。このイベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

左側の領域のリンクから直接作成されたトランザクションメッセージにアクセスできます。

![](assets/message-center_messagegeneration.png)

このトリガーイベントをWebサイトに統合する必要もあります。See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Unpublishing an event {#unpublishing-an-event}

**[!UICONTROL Unpublish]** このボタンを使用すると、イベントの発行をキャンセルできます。これは、以前に作成したイベントに対応するリソースに対応するREST APIから削除されます。これで、Webサイトでイベントがトリガーされても、対応するメッセージは送信されず、データベースに保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージを既に発行している場合、トランザクションメッセージのパブリケーションもキャンセルされます。See [Unpublishing a transactional message](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Click the **[!UICONTROL Publish]** button to generate a new REST API.

## Integrating the triggering of the event in a website {#integrating-the-triggering-of-the-event-in-a-website}

イベントを作成したら、このイベントのトリガーをWebサイトに統合する必要があります。

[«トランザクションメッセージングの運用»の原則](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) で説明した例では、買い物かごの製品を購入する前に、顧客がWebサイトを離れるたびに«買い物かごの放棄»イベントをトリガーしたいと考えています。これを行うには、WebサイトWeb開発者がAdobe Campaign Standard REST APIを使用する必要があります。

[REST APIドキュメント](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) を参照してください。

## Transactional event specific configurations {#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージのタイプ（イベントまたはプロファイル）と使用するチャネルによって異なる場合があります。

以下の節では、目的のトランザクションメッセージに従って設定する必要のある具体的な設定について説明します。For more on the general steps to configure an event, refer to [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Event-based transactional messages {#event-based-transactional-messages}

イベントベースのトランザクションメッセージを送信するには、まずイベント自体に含まれるデータを作成して設定する必要があります。

1. When creating the event configuration, select the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from the Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージでは、送信イベント内のデータのみを使用して受信者およびメッセージコンテンツのパーソナライゼーションを定義します。ただし、Adobe Campaignデータベースの情報を使用してトランザクションメッセージのコンテンツを充実させることができます。

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   イベントをプレビューする場合、REST APIには選択したチャネルに従って電子メールアドレスまたは携帯電話を指定する属性が含まれます。

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional messages {#profile-based-transactional-messages}

プロファイルベースのトランザクションメッセージを送信するには、まずAdobe Campaignデータベースに含まれるイベントターゲティングデータを作成して設定する必要があります。

1. When creating the event configuration, select the **[!UICONTROL Profile event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). 拡張を作成するには、少なくとも1つのフィールドを追加する必要があります。You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.
1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). **[!UICONTROL Profile]** ターゲットディメンションを使用する場合、エンリッチメントの作成は必須です。
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the email address or the mobile phone as it will be retrieved from the **[!UICONTROL Profile]** resource.

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Sending a profile transactional message](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Event-based transactional push notifications {#event-based-transactional-push-notifications}

トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。[プッシュ設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)を参照してください。

モバイルアプリケーションから通知を受信することをオプトインしているすべてのユーザーに匿名トランザクションプッシュ通知を送信するには、まずイベント自体に含まれるデータを作成および設定する必要があります。対応する手順を以下に示します。

イベントには、次の3つの要素を含める必要があります。

* **登録トークン**。1つのモバイルアプリケーションと1つのデバイスのユーザーIDです。Adobe Campaignデータベースのプロファイルに対応していない可能性があります。
* **モバイルアプリケーション名** （AndroidおよびiOSのすべてのデバイス用）。これは、ユーザーのデバイスでプッシュ通知を受信するために使用されるAdobe Campaignで設定されるモバイルアプリケーションのIDです。For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* **プッシュプラットフォーム** （Androidの場合は"GCM"、iOSの場合は"apns"）。

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージでは、送信イベント内のデータのみを使用して受信者およびメッセージコンテンツのパーソナライゼーションを定義します。ただし、Adobe Campaignデータベースの情報を使用してトランザクションメッセージのコンテンツを充実させることができます。

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   このイベントをプレビューすると、REST APIには、配信のターゲット設定に使用される"registrationToken"、"application"および"pushPlatform"属性が含まれます。

   ![](assets/message-center_push_api.png)

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。To modify and publish the message that was just created, see [Sending a transactional push notification targeting an event](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional push notifications {#profile-based-transactional-push-notifications}

モバイルアプリケーションをサブスクライブしているAdobe Campaignプロファイルにトランザクションプッシュ通知を送信するには、まずAdobe Campaignデータベースを作成し、イベントを設定する必要があります。

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   デフォルトでは、トランザクションプッシュ通知は、受信者が登録したすべてのモバイルアプリケーションに送信されます。特定のモバイルアプリケーションにプッシュ通知を送信するには、リストでそのプッシュ通知を選択します。他のモバイルアプリケーションはメッセージによってターゲット設定されますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. Add fields to the event, if you want to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >拡張を作成するには、少なくとも1つのフィールドを追加する必要があります。You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.

1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). **[!UICONTROL Profile]** ターゲットディメンションを使用する場合、エンリッチメントの作成は必須です。
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the registration token, the application name and the push platform as they will be retrieved from the **[!UICONTROL Profile]** resource.

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。To modify and publish the message that was just created, see [Sending a transactional push notification targeting a profile](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configuring an event to send a follow-up message {#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージは事前定義済みのマーケティング配信テンプレートで、特定のトランザクションメッセージの受信者にメッセージを送信するためのワークフローで使用できます。For more on this, see [Follow-up messages](../../channels/using/follow-up-messages.md).

1. イベントトランザクションメッセージを送信するために作成したものと同じイベント設定を使用します。[イベントベースのトランザクションメッセージ](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages)を参照してください。
1. When configuring your event, check the **[!UICONTROL Create follow-up delivery template for this event]** box before publishing the event.

   ![](assets/message-center_follow-up-checkbox.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   イベントが公開されると、トランザクションメッセージと新しいイベントにリンクされたフォローアップ配信テンプレートが自動的に作成されます。For more on using follow-up messages, see [Sending a follow-up message](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Use case: configuring an event to send a transactional message {#use-case--configuring-an-event-to-send-a-transactional-message}

この例では、Webサイトでの各購入後に確認メッセージを送信するために、次の前提条件を使用してイベントを設定します。

As we want to identify our client via his CRM ID, first make sure that the **[!UICONTROL Profile]** resource has been extended with this new field.

In the same way, a custom resource corresponding to purchases must have been created and published, and must be linked to the **[!UICONTROL Profile]** resource. これにより、このリソースから情報を取得してメッセージコンテンツを充実させることができます。

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-of-adding-a-resource.md).

1. **[!UICONTROL Email]** チャネルと **[!UICONTROL Profile]** ターゲットディメンションを使用して新しいイベントを作成します（イベント [](../../administration/using/configuring-transactional-messaging.md#creating-an-event)の作成を参照）。
1. トランザクションメッセージをパーソナライズするために使用できる属性を定義します。In our case, add the "CRM ID" and the "Product identifier" fields (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. To enrich the message content with information regarding the client's previous purchases, create an enrichment targeting the **[!UICONTROL Purchase]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Create a join condition between the "Product identifier" field that was previously added to the message, and the corresponding field from the **[!UICONTROL Purchase]** resource

   ![](assets/message-center_usecase3.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integrate the event in your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

