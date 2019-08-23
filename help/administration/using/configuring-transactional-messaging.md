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
source-git-commit: 8800562922e68d33cca93cd838c294198b630684

---


# トランザクションメッセージの設定{#configuring-transactional-messaging}

Adobe Campaignでトランザクションメッセージを送信するには、まずイベントデータの構造を記述する必要があります。

イベント設定は、次の手順に従って **管理者** が実行する必要があります。

設定は、送信するトランザクションメッセージの種類によって異なります。これについて詳しくは [、トランザクションイベント固有の設定を参照してください](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

イベントが発行されると、対応するトランザクションメッセージが自動的に作成されます。トランザクションメッセージングについて詳しくは、このページ [](../../channels/using/about-transactional-messaging.md)を参照してください。

## イベントの作成 {#creating-an-event}

まず、ニーズに対応するイベントを作成します。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、 **[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**&#x200B;を選択します。
1. ボタンを **[!UICONTROL Create]** クリックします。
1. イベントに **[!UICONTROL Label]** およびイベント **[!UICONTROL ID]** を付与します。**[!UICONTROL ID]** フィールドは必須で、プリフィックス"EVT"で始まる必要があります。このプレフィックスを使用しない場合、クリック **[!UICONTROL Create]**&#x200B;すると自動的に追加されます。

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >IDは、EDTプレフィックスを含め、64文字以内にする必要があります。

1. トランザクションメッセージ **[!UICONTROL Email]**&#x200B;の送信に使用するチャネルまた **[!UICONTROL Mobile (SMS)]** は **[!UICONTROL Mobile application]** （プッシュ通知）を選択します。

   >[!NOTE]
   >
   >各イベント設定に使用できるチャネルは1つだけです。イベントが作成されると、チャネルを変更することはできません。

1. 目的のイベント設定に対応するターゲットディメンションを選択し、をクリック **[!UICONTROL Create]**&#x200B;します。

   イベントベースのトランザクションメッセージは、Adobe Campaignデータベースに格納されているデータに基づいて、イベント自体に含まれるデータをターゲットにしたトランザクションメッセージです。これについて詳しくは [、トランザクションイベント固有の設定](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)を参照してください。

## イベント属性の定義 {#defining-the-event-attributes}

**[!UICONTROL Fields]** セクションで、イベントコンテンツに統合される属性を定義し、トランザクションメッセージをパーソナライズするために使用できるようにします。

フィールドの追加と変更手順は、カスタムリソースと [同じ](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)です。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は **[!UICONTROL AC_language]** 、IDを使用して追加のイベント属性を定義します。これはイベントトランザクションメッセージにのみ適用されます。イベントが発行された後、多言語トランザクションメッセージの編集手順は多言語標準電子メールと同じです。多言語電子メールの [作成を参照](../../channels/using/creating-a-multilingual-email.md)してください。

## データコレクションの定義 {#defining-data-collections}

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

## トランザクションメッセージコンテンツの合理化 {#enriching-the-transactional-message-content}

Adobe Campaignデータベースの情報を使用してトランザクションメッセージコンテンツを充実させることで、メッセージをパーソナライズできます。例えば、各受信者の姓またはCRM IDから、ユーザーに送信される情報をパーソナライズするために、自分の住所や生年月日などのデータを元に戻したり、プロファイルテーブルに追加されたその他のカスタムフィールドを使用したりできます。

拡張 **[!UICONTROL Profile]** または **[!UICONTROL Service]** リソースの情報を使用してトランザクションメッセージコンテンツを拡張できます。

この情報は、新しいリソースにも保存できます。その場合、リソースは、直接、または別のテーブル **[!UICONTROL Profile]** から **[!UICONTROL Service]** リソースにリンクする必要があります。例えば、以下の設定では、リソースがリソースにリンクされている場合、リソースのカテゴリやIDなど **[!UICONTROL Product]** リソースの情報を使用してトランザクションメッセージコンテンツ **[!UICONTROL Product]** を充実 **[!UICONTROL Profile]** させることができます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、このページ [](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

1. **[!UICONTROL Enrichment]** セクションで、ボタンを **[!UICONTROL Create element]** クリックします。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。この場合、 **[!UICONTROL Profile]** リソースを選択します。

   ![](assets/message-center_new-enrichment.png)

1. ボタンを **[!UICONTROL Create element]** 使用して、選択したリソースのフィールドを、以前にイベントに追加したフィールドのいずれかにリンクします（イベント属性 [](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)の定義を参照）。

   ![](assets/message-center_enrichment-join.png)

1. この例では、フィールドと **[!UICONTROL Last name]** フィールド **[!UICONTROL First name]** を **[!UICONTROL Profile]** リソース内の対応するフィールドに調整します。

   ![](assets/message-center_enrichment-join-fields.png)

1. **[!UICONTROL Targeting enrichment]** セクションで、配信の実行中にメッセージターゲットとして使用されるエンリッチメントを選択します。この例では、を選択 **[!UICONTROL Profile]**&#x200B;します。プロファイルベースのイベントには、ターゲット化の強化を選択する必要があります。

   ![](assets/message-center_marketing_targeting_enrichment.png)

イベントが発行されると **[!UICONTROL Profile]** 、リソースとのリンクによってトランザクションメッセージの内容を充実させることができます。

**関連トピック:**

* [イベント](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)のプレビューと公開
* [トランザクションメッセージをパーソナライズ](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)します。

## イベントのプレビューと公開 {#previewing-and-publishing-the-event}

イベントを使用するには、プレビューして公開する必要があります。

1. ボタンを **[!UICONTROL API preview]** クリックすると、Webサイト開発者が公開する前に使用するREST APIのシミュレーションが表示されます。イベントが公開されると、このボタンによって、本番環境でのAPIのプレビューも表示できます。Webサイトでのイベントのトリガーの [統合を参照](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)してください。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST APIは、選択したチャネルと選択したターゲットディメンションによって異なります。様々な設定について詳しくは [、トランザクションイベント固有の設定](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)を参照してください。

1. をクリック **[!UICONTROL Publish]** してパブリケーションを開始します。

   ![](assets/message-center_pub.png)

1. 対応するタブを選択して、パブリケーションログを表示できます。

   ![](assets/message-center_logs.png)

   また、タブを選択して前のパブリケーションを参照することもできます。

>[!NOTE]
>
>イベントを変更するたびに、 **[!UICONTROL Publish]** 再度クリックして、Webサイト開発者が使用する更新されたREST APIを生成する必要があります。

イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。このイベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

左側の領域のリンクから直接作成されたトランザクションメッセージにアクセスできます。

![](assets/message-center_messagegeneration.png)

このトリガーイベントをWebサイトに統合する必要もあります。Webサイトでのイベントのトリガーの [統合を参照](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)してください。

### イベントの非公開 {#unpublishing-an-event}

**[!UICONTROL Unpublish]** このボタンを使用すると、イベントの発行をキャンセルできます。これは、以前に作成したイベントに対応するリソースに対応するREST APIから削除されます。これで、Webサイトでイベントがトリガーされても、対応するメッセージは送信されず、データベースに保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージを既に発行している場合、トランザクションメッセージのパブリケーションもキャンセルされます。トランザクションメッセージ [の非公開を参照](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)してください。

ボタンを **[!UICONTROL Publish]** クリックすると、新しいREST APIが生成されます。

## Webサイトでのイベントのトリガーの統合 {#integrating-the-triggering-of-the-event-in-a-website}

イベントを作成したら、このイベントのトリガーをWebサイトに統合する必要があります。

[«トランザクションメッセージングの運用»の原則](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) で説明した例では、買い物かごの製品を購入する前に、顧客がWebサイトを離れるたびに«買い物かごの放棄»イベントをトリガーしたいと考えています。これを行うには、WebサイトWeb開発者がAdobe Campaign Standard REST APIを使用する必要があります。

[REST APIドキュメント](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) を参照してください。

## トランザクションイベント固有の設定 {#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージのタイプ（イベントまたはプロファイル）と使用するチャネルによって異なる場合があります。

以下の節では、目的のトランザクションメッセージに従って設定する必要のある具体的な設定について説明します。イベントを設定する一般的な手順について詳しくは、イベント [の作成](../../administration/using/configuring-transactional-messaging.md#creating-an-event)を参照してください。

### イベントベースのトランザクションメッセージ {#event-based-transactional-messages}

イベントベースのトランザクションメッセージを送信するには、まずイベント自体に含まれるデータを作成して設定する必要があります。
詳しくは、トランザクションメッセージの [操作](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)を参照してください。

1. イベント設定を作成するときに **[!UICONTROL Real-time event]** 、ターゲットディメンションを選択します（イベント [](../../administration/using/configuring-transactional-messaging.md#creating-an-event)の作成を参照）。
1. トランザクションメッセージをパーソナライズするために、イベントにフィールドを追加します（イベント属性 [](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)の定義を参照）。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージコンテンツを強化します（トランザクションメッセージコンテンツ [](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)の絞り込みを参照）。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージでは、送信イベント内のデータのみを使用して受信者およびメッセージコンテンツのパーソナライゼーションを定義します。ただし、Adobe Campaignデータベースの情報を使用してトランザクションメッセージのコンテンツを充実させることができます。

1. イベントをプレビューして公開します（イベントの [プレビューと公開を参照](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)）。

   イベントをプレビューする場合、REST APIには選択したチャネルに従って電子メールアドレスまたは携帯電話を指定する属性が含まれます。

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。イベントがトランザクションメッセージの送信をトリガーするには、作成されたメッセージを変更して発行する必要があります。また、イベントトランザクションメッセージを参照 [](../../channels/using/event-transactional-messages.md)してください。

1. イベントをWebサイトに統合します（Webサイトでのイベントのトリガーの [統合を参照](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)）。

### プロファイルベースのトランザクションメッセージ {#profile-based-transactional-messages}

プロファイルベースのトランザクションメッセージを送信するには、まずAdobe Campaignデータベースに含まれるイベントターゲティングデータを作成して設定する必要があります。

1. イベント設定を作成するときに **[!UICONTROL Profile event]** 、ターゲットディメンションを選択します（イベント [](../../administration/using/configuring-transactional-messaging.md#creating-an-event)の作成を参照）。
1. トランザクションメッセージをパーソナライズするために、イベントにフィールドを追加します（イベント属性 [](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)の定義を参照）。拡張を作成するには、少なくとも1つのフィールドを追加する必要があります。Adobe Campaignデータベースからパーソナライゼーションフィールドを使用できるようになるため、 **名前** や **姓** などの他のフィールドを作成する必要はありません。
1. イベントを **[!UICONTROL Profile]** リソースにリンクするための拡張を作成します（トランザクションメッセージコンテンツ [](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)の絞り込みを参照）。**[!UICONTROL Profile]** ターゲットディメンションを使用する場合、エンリッチメントの作成は必須です。
1. イベントをプレビューして公開します（イベントの [プレビューと公開を参照](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)）。

   イベントをプレビューする場合、REST APIに **[!UICONTROL Profile]** は、リソースから取得される電子メールアドレスまたは携帯電話を指定する属性は含まれません。

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。イベントがトランザクションメッセージの送信をトリガーするようにトリガーするには、作成したメッセージを変更して発行する必要があります。詳しくは、プロファイルトランザクションメッセージ [の送信](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)を参照してください。

1. イベントをWebサイトに統合します（Webサイトでのイベントのトリガーの [統合を参照](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)）。

### イベントベースのトランザクションプッシュ通知 {#event-based-transactional-push-notifications}

トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。[プッシュ設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)を参照してください。

モバイルアプリケーションから通知を受信することをオプトインしているすべてのユーザーに匿名トランザクションプッシュ通知を送信するには、まずイベント自体に含まれるデータを作成および設定する必要があります。対応する手順を以下に示します。

イベントには、次の3つの要素を含める必要があります。

* **登録トークン**。1つのモバイルアプリケーションと1つのデバイスのユーザーIDです。Adobe Campaignデータベースのプロファイルに対応していない可能性があります。
* **モバイルアプリケーション名** （AndroidおよびiOSのすべてのデバイス用）。これは、ユーザーのデバイスでプッシュ通知を受信するために使用されるAdobe Campaignで設定されるモバイルアプリケーションのIDです。これについて詳しくは、このページを参照 [してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* **プッシュプラットフォーム** （Androidの場合は"GCM"、iOSの場合は"apns"）。

1. イベント設定を作成するときに **[!UICONTROL Mobile application]** 、チャネルと **[!UICONTROL Real-time event]** ターゲットディメンションを選択します（イベント [](../../administration/using/configuring-transactional-messaging.md#creating-an-event)の作成を参照）。
1. トランザクションメッセージをパーソナライズするために、イベントにフィールドを追加します（イベント属性 [](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)の定義を参照）。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージコンテンツを強化します（トランザクションメッセージコンテンツ [](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)の絞り込みを参照）。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージでは、送信イベント内のデータのみを使用して受信者およびメッセージコンテンツのパーソナライゼーションを定義します。ただし、Adobe Campaignデータベースの情報を使用してトランザクションメッセージのコンテンツを充実させることができます。

1. イベントをプレビューして公開します（イベントの [プレビューと公開を参照](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)）。

   このイベントをプレビューすると、REST APIには、配信のターゲット設定に使用される"registrationToken"、"application"および"pushPlatform"属性が含まれます。

   ![](assets/message-center_push_api.png)

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。作成したメッセージを変更して発行するには、「イベントのトランザクションプッシュ通知の [送信」を参照](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)してください。

1. イベントをWebサイトに統合します（Webサイトでのイベントのトリガーの [統合を参照](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)）。

### プロファイルベースのトランザクションプッシュ通知 {#profile-based-transactional-push-notifications}

モバイルアプリケーションをサブスクライブしているAdobe Campaignプロファイルにトランザクションプッシュ通知を送信するには、まずAdobe Campaignデータベースを作成し、イベントを設定する必要があります。

1. イベント設定を作成するときに **[!UICONTROL Mobile application]** 、チャネルと **[!UICONTROL Profile]** ターゲットディメンションを選択します（イベント [](../../administration/using/configuring-transactional-messaging.md#creating-an-event)の作成を参照）。

   デフォルトでは、トランザクションプッシュ通知は、受信者が登録したすべてのモバイルアプリケーションに送信されます。特定のモバイルアプリケーションにプッシュ通知を送信するには、リストでそのプッシュ通知を選択します。他のモバイルアプリケーションはメッセージによってターゲット設定されますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. トランザクションメッセージをパーソナライズする場合は、イベントにフィールドを追加します（イベント属性 [](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)の定義を参照）。

   >[!NOTE]
   >
   >拡張を作成するには、少なくとも1つのフィールドを追加する必要があります。Adobe Campaignデータベースからパーソナライゼーションフィールドを使用できるようになるため、 **名前** や **姓** などの他のフィールドを作成する必要はありません。

1. イベントを **[!UICONTROL Profile]** リソースにリンクするための拡張を作成します（トランザクションメッセージコンテンツ [](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)の絞り込みを参照）。**[!UICONTROL Profile]** ターゲットディメンションを使用する場合、エンリッチメントの作成は必須です。
1. イベントをプレビューして公開します（イベントの [プレビューと公開を参照](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)）。

   イベントをプレビューする場合、REST APIには登録トークン、アプリケーション名、および **[!UICONTROL Profile]** リソースから取得されるプッシュプラットフォームを指定する属性は含まれません。

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。作成したメッセージを変更して発行するには、プロファイルを使用したトランザクションプッシュ通知の [送信を参照](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)してください。

1. イベントをWebサイトに統合します（Webサイトでのイベントのトリガーの [統合を参照](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)）。

### フォローアップメッセージを送信するためのイベントの設定 {#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージは事前定義済みのマーケティング配信テンプレートで、特定のトランザクションメッセージの受信者にメッセージを送信するためのワークフローで使用できます。これについて詳しくは、 [フォローアップメッセージ](../../channels/using/follow-up-messages.md)を参照してください。

1. イベントトランザクションメッセージを送信するために作成したものと同じイベント設定を使用します。[イベントベースのトランザクションメッセージ](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages)を参照してください。
1. イベントを設定する場合は、イベントを発行する前に **[!UICONTROL Create follow-up delivery template for this event]** ボックスをチェックしてください。

   ![](assets/message-center_follow-up-checkbox.png)

1. イベントをプレビューして公開します（イベントの [プレビューと公開を参照](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)）。

   イベントが公開されると、トランザクションメッセージと新しいイベントにリンクされたフォローアップ配信テンプレートが自動的に作成されます。フォローアップメッセージの使用について詳しくは、フォローアップメッセージ [の送信を](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)参照してください。

## 使用例:トランザクションメッセージを送信するイベントの設定 {#use-case--configuring-an-event-to-send-a-transactional-message}

この例では、Webサイトでの各購入後に確認メッセージを送信するために、次の前提条件を使用してイベントを設定します。

CRM IDを通じて弊社のクライアントを識別するには、まずこの新しいフィールドで **[!UICONTROL Profile]** リソースが拡張されていることを確認してください。

同様に、購入に対応するカスタムリソースを作成して発行し、 **[!UICONTROL Profile]** リソースにリンクする必要があります。これにより、このリソースから情報を取得してメッセージコンテンツを充実させることができます。

リソースの作成と公開について詳しくは、このページ [](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

1. **[!UICONTROL Email]** チャネルと **[!UICONTROL Profile]** ターゲットディメンションを使用して新しいイベントを作成します（イベント [](../../administration/using/configuring-transactional-messaging.md#creating-an-event)の作成を参照）。
1. トランザクションメッセージをパーソナライズするために使用できる属性を定義します。この場合、"CRM ID"フィールドと「製品識別子」フィールドを追加します（イベント属性 [](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)の定義を参照）。

   ![](assets/message-center_usecase1.png)

1. クライアントの以前の購入に関する情報でメッセージコンテンツを強化するには、リソースを **[!UICONTROL Purchase]** エンリッチメントする方法を作成します（トランザクションメッセージコンテンツ [](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)のエンリッチメントを参照）。

   ![](assets/message-center_usecase2.png)

1. メッセージに以前に追加された「製品識別子」フィールドと、リソースからの対応するフィールドの間に結合条件を作成します **[!UICONTROL Purchase]**

   ![](assets/message-center_usecase3.png)

1. イベントをプレビューして公開します（イベントの [プレビューと公開を参照](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)）。
1. Webサイトにイベントを統合します [（Webサイト](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)でのイベントのトリガーを参照）。

