---
title: トランザクションメッセージの設定
description: トランザクションメッセージングを設定する方法を説明します。
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e62fdfba531bcfe18c147e7035c79e1ac6bca979

---


# トランザクションメッセージの設定{#configuring-transactional-messaging}

Adobe Campaignでトランザクションメッセージを送信するには、まずイベントデータの構造を記述する必要があります。

イベントの設定は、次の手順に従っ **て** 、管理者が実行する必要があります。

設定は、送信するトランザクションメッセージのタイプによって異なります。 詳しくは、トランザクションイベント固有の [設定を参照してください。](#transactional-event-specific-configurations)

イベントが発行されると、対応するトランザクションメッセージが自動的に作成されます。 For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## イベントの作成 {#creating-an-event}

まず、ニーズに応じたイベントを作成します。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を **[!UICONTROL Marketing plans]** 選択し **[!UICONTROL Transactional messages]** ます **[!UICONTROL Event configuration]**。
1. ボタンをクリッ **[!UICONTROL Create]** クします。
1. イベント **[!UICONTROL Label]** にとを **[!UICONTROL ID]** 渡します。 このフ **[!UICONTROL ID]** ィールドは必須で、プレフィックス「EVT」で始まる必要があります。 このプレフィックスを使用しない場合、をクリックすると自動的に追加されま **[!UICONTROL Create]**&#x200B;す。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >IDは、EVTプレフィックスを含めて64文字を超えてはなりません。

1. トランザクションメッセージの送信に使用するチャネル、または **[!UICONTROL Email]**(プッ **[!UICONTROL Mobile (SMS)]** シュ通 **[!UICONTROL Mobile application]** 知)を選択します。

   >[!NOTE]
   >
   >各イベント設定で使用できるチャネルは1つだけです。 イベントが作成された後は、チャネルを変更できません。

1. 目的のイベント設定に対応するターゲットディメンションを選択し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   イベントベースのトランザクションメッセージは、イベント自体に含まれるデータをターゲットにしますが、プロファイルベースのトランザクションメッセージは、Adobe Campaignデータベースに含まれるデータをターゲットにします。 詳しくは、トランザクションイベント固有の [設定を参照してください](#transactional-event-specific-configurations)。

## イベント属性の定義 {#defining-the-event-attributes}

このセクシ **[!UICONTROL Fields]** ョンで、イベントコンテンツに統合され、トランザクションメッセージをパーソナライズするために使用できる属性を定義します。

フィールドの追加と変更の手順は、カスタムリソースの場合と [同じです](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語のトランザクションメッセージを作成する場合は、 **[!UICONTROL AC_language]** IDを使用して追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ当てはまります。 イベントが発行された後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語標準の電子メールの手順と同じです。 See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## データコレクションの定義 {#defining-data-collections}

イベントコンテンツに、要素のコレクション（各要素自体に複数の属性を含む）を追加できます。

このコレクションは、トランザクション用の電子メールで使用して、製品のリスト（価格、参照番号、数量など）をメッセージの内容に追加できます。 をリストの各製品に対して設定します。

1. セクション **[!UICONTROL Collections]** で、ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/message-center_collection_create.png)

1. コレクションのラベルとIDを追加します。
1. リストの各製品のトランザクションメッセージに表示するすべてのフィールドを追加します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

イベントとメッセージが発行されると、このコレクションをトランザクションメッセージで使用できます。

次に、この例のAPIプレビューを示します。

![](assets/message-center_collection_api-preview.png)

**関連トピック：**

* [イベントのプレビューと公開](#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## トランザクションメッセージコンテンツの強化 {#enriching-the-transactional-message-content}

トランザクションメッセージのコンテンツをAdobe Campaignデータベースの情報で豊富にすることで、メッセージをパーソナライズできます。 例えば、各受信者の姓またはCRM IDから、住所や生年月日などのデータや、プロファイルテーブルに追加された他のカスタムフィールドなどのデータを回復して、送信する情報をパーソナライズできます。

トランザクションメッセージのコンテンツを、拡張されたまたはリソースの情報で拡張する **[!UICONTROL Profile]** ことが **[!UICONTROL Service]** できます。

この情報は、新しいリソースに保存することもできます。 この場合、リソースは、またはのリソースに直接、または別のテ **[!UICONTROL Profile]** ーブルを **[!UICONTROL Service]** 介してリンクされている必要があります。 例えば、以下の設定では、リソースがリソースにリンクされている場合、トランザクションメッセージのコンテンツを、製品カテゴリやIDなどのリソースの情報で **[!UICONTROL Product]** 拡張することがで **[!UICONTROL Product]****[!UICONTROL Profile]** きます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、このページを参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。

1. セクション **[!UICONTROL Enrichment]** で、ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. ボタンを使 **[!UICONTROL Create element]** 用して、選択したリソースのフィールドを、イベントに以前に追加したフィールドの1つにリンクします(「イベ [ント属性の定義](#defining-the-event-attributes)」を参照)。

   ![](assets/message-center_enrichment-join.png)

1. この例では、とのフィールドをリソ **[!UICONTROL Last name]** ース内の **[!UICONTROL First name]** 対応するフィールドと調整し **[!UICONTROL Profile]** ます。

   ![](assets/message-center_enrichment-join-fields.png)

   また、リソースを使用して、トランザクションメッセージのコンテンツを強化すること **[!UICONTROL Service]** もできます。 サービスについて詳しくは、この節を参照して [ください](../../audiences/using/creating-a-service.md)。

1. プロファイルベースのイベントを作成または編集する場合は、「」セクションで、配信の実 **[!UICONTROL Targeting enrichment]** 行中にメッセージターゲットとして使用するエンリッチメントを選択します。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >プロファイルベースのイベントでは、リソースに基づ **[!UICONTROL Profile]** いてターゲットエンリッチメントを選択する必要があります。

イベントとメッセージが発行されると、このリンクを使用して、トランザクションメッセージの内容を強化できます。

**関連トピック：**

* [イベントのプレビューと公開](#previewing-and-publishing-the-event)。
* [トランザクションメッセージのパーソナライズ](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## イベントのプレビューと公開 {#previewing-and-publishing-the-event}

イベントを使用する前に、プレビューして公開する必要があります。

1. ボタンをク **[!UICONTROL API preview]** リックすると、Webサイトの開発者が公開する前に使用するREST APIのシミュレーションが表示されます。 イベントが公開されると、このボタンを使用して実稼働環境でのAPIのプレビューを表示することもできます。 詳しくは、 [Webサイトでのイベントのトリガーの統合を参照してください](#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST APIは、選択したチャネルと選択したターゲットディメンションに応じて異なります。 各種設定について詳しくは、トランザクションイベント固有の設 [定を参照してください](#transactional-event-specific-configurations)。

1. クリックし **[!UICONTROL Publish]** て発行を開始します。

   ![](assets/message-center_pub.png)

1. 対応するタブでパブリケーションログを表示できます。

   ![](assets/message-center_logs.png)


>[!NOTE]
>
>イベントを変更するたびに、を再度クリックして、Web **[!UICONTROL Publish]** サイト開発者が使用する更新されたREST APIを生成する必要があります。

イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 このイベントでトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

左側の領域のリンクから直接作成されたトランザクションメッセージにアクセスできます。

![](assets/message-center_messagegeneration.png)

また、このトリガーイベントをWebサイトに統合する必要があります。 詳しくは、 [Webサイトでのイベントのトリガーの統合を参照してください](#integrating-the-triggering-of-the-event-in-a-website)。

<!-->>[!NOTE]
>前のパブリケーションが存在する場合は、そのパブ **[!UICONTROL Latest transactional events]** リケーションを参照す **[!UICONTROL History]** るには、左側の領域のセクションの下のリンクをクリックします。—>
>
### イベントの非公開 {#unpublishing-an-event}

このボ **[!UICONTROL Unpublish]** タンを使用すると、イベントの発行をキャンセルできます。これにより、以前に作成したイベントに対応するリソースがREST APIから削除されます。 現在は、Webサイトを通じてイベントがトリガーされても、対応するメッセージは送信されず、データベースには保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
対応するトランザクションメッセージを既に公開している場合は、トランザクションメッセージの公開もキャンセルされます。 トランザクシ [ョンメッセージの非公開を参照してくださ](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)い。

新しいREST APIを生 **[!UICONTROL Publish]** 成するには、ボタンをクリックします。

### イベントの削除 {#deleting-an-event}

イベントが非公開になった場合、またはイベントがまだ公開されていない場合は、イベント設定リストから削除できます。 手順は次のとおりです。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を **[!UICONTROL Marketing plans]** 選択し **[!UICONTROL Transactional messages]** ます **[!UICONTROL Event configuration]**。
1. 選択したイベント設定にマウスを移動し、ボタンを選択し **[!UICONTROL Delete element]** ます。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   イベント設定にステータスがあるこ **[!UICONTROL Draft]** とを確認してください。ステータスがない場合は、削除できません。 ステータス **[!UICONTROL Draft]** は、まだ公開されていない、または未公開のイベントに適用さ [れます](#unpublishing-an-event)。

1. ボタンをクリッ **[!UICONTROL Confirm]** クします。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
公開済みで既に使用されているイベント設定を削除すると、対応するトランザクションメッセージと、その送信および追跡ログも削除されます。

## Webサイトでのイベントのトリガーの統合 {#integrating-the-triggering-of-the-event-in-a-website}

イベントを作成したら、このイベントのトリガーをWebサイトに統合する必要があります。

「 [Transactional messaging operating principal](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) 」セクションで説明した例では、買い物かごに製品を購入する前に、顧客の1人がWebサイトを離れるたびに「買い物かごの放棄」イベントをトリガーする必要があります。 これを行うには、WebサイトのWeb開発者がAdobe Campaign Standard REST APIを使用する必要があります。

詳しくは、 [REST APIドキュメントを参照してください](../../api/using/managing-transactional-messages.md) 。

## トランザクションイベント固有の設定 {#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージのタイプ（イベントまたはプロファイル）と、使用するチャネルによって異なります。

以下の節では、目的のトランザクションメッセージに従って具体的な設定を行う必要がある設定について説明します。 イベントを設定する一般的な手順について詳しくは、「イベントの作成」を参 [照してください](#creating-an-event)。

### イベントベースのトランザクションメッセージ {#event-based-transactional-messages}

イベントベースのトランザクションメッセージを送信するには、まず、イベント自体に含まれるデータをターゲットにしたイベントを作成し、設定する必要があります。
詳しくは、トランザクションメッセージ [ングの利用を参照してくださ](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)い。

1. イベント設定を作成する際に、ターゲットディメ **[!UICONTROL Real-time event]** ンションを選択します( [イベントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します(イベン [ト属性の定義を参照](#defining-the-event-attributes))。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージコンテンツを拡張します(トランザクションメ [ッセージコンテンツの強化を参照](#enriching-the-transactional-message-content))。

   >[!NOTE]
   イベントベースのトランザクションメッセージングでは、送信されたイベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義します。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージのコンテンツを強化できます。

1. イベントをプレビューして公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする際、REST APIには、選択したチャネルに従って電子メールアドレスまたは携帯電話を指定する属性が含まれます。

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。詳しくは、イベントトランザクションメッセ [ージを参照してくださ](../../channels/using/event-transactional-messages.md)い。

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### プロファイルベースのトランザクションメッセージ {#profile-based-transactional-messages}

プロファイルベースのトランザクションメッセージを送信するには、まずAdobe Campaignデータベースに含まれるイベントターゲットデータを作成し、設定する必要があります。

1. イベント設定を作成する際に、ターゲットディメ **[!UICONTROL Profile event]** ンションを選択します( [イベントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します(イベン [ト属性の定義を参照](#defining-the-event-attributes))。 エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるので、 **First** Name（名）や **Last Name（姓）** （姓）など、他のフィールドを作成する必要はありません。
1. イベントをリソースにリンクするために、エンリッチメントを作成しま **[!UICONTROL Profile]** す(トランザクショ [ンメッセージコンテンツの強化を参照](#enriching-the-transactional-message-content))。 ターゲットディメンションを使用する場合は、エンリッチメントの作 **[!UICONTROL Profile]** 成が必須です。
1. イベントをプレビューして公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、リソースから取得される電子メールアドレスまたは携帯電話を指定する属性が含まれてい **[!UICONTROL Profile]** ません。

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。詳しくは、プロファイルトランザクションメ [ッセージの送信を参照してくださ](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)い。

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### イベントベースのトランザクションプッシュ通知 {#event-based-transactional-push-notifications}

トランザクションプッシュ通知を送信するには、それに応じてAdobe Campaignを設定する必要があります。 プッシュ [設定を参照してくださ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)い。

匿名のトランザクションプッシュ通知を、モバイルアプリケーションからの通知の受信を選択したすべてのユーザーに送信するには、まず、イベント自体に含まれるデータを対象としたイベントを作成し、設定する必要があります。 対応する手順を以下に示します。

イベントには、次の3つの要素を含める必要があります。

* 登録 **トークン**。1つのモバイルアプリケーションと1つのデバイスのユーザーIDです。 Adobe Campaignデータベースのどのプロファイルにも対応していない場合があります。
* モバイ **ルアプリケーション** (すべてのデバイス（AndroidおよびiOS）用)の名前。 これは、ユーザーのデバイスでプッシュ通知を受信するために使用される、Adobe Campaignで設定されたモバイルアプリのIDです。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* プッ **シュプラットフォ** ーム（Androidの場合は「gcm」、iOSの場合は「apns」）。

1. イベント設定を作成する際に、チャネルとタ **[!UICONTROL Mobile application]** ーゲティングディメ **[!UICONTROL Real-time event]** ンションを選択します(イベ [ントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します(イベン [ト属性の定義を参照](#defining-the-event-attributes))。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージコンテンツを拡張します(トランザクションメ [ッセージコンテンツの強化を参照](#enriching-the-transactional-message-content))。

   >[!NOTE]
   イベントベースのトランザクションメッセージングでは、送信されたイベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義します。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージのコンテンツを強化できます。

1. イベントをプレビューして公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、配信のターゲット設定に使用される「registrationToken」、「application」および「pushPlatform」属性が含まれます。

   ![](assets/message-center_push_api.png)

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成したメッセージを変更して発行する方法については、イベントを対象としたトランザクシ [ョンプッシュ通知の送信を参照してくださ](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)い。

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### プロファイルベースのトランザクションプッシュ通知 {#profile-based-transactional-push-notifications}

モバイルアプリケーションをサブスクライブしたAdobe Campaignプロファイルにトランザクションプッシュ通知を送信するには、まずAdobe Campaignデータベースをターゲットとするイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、チャネルとタ **[!UICONTROL Mobile application]** ーゲティングディメ **[!UICONTROL Profile]** ンションを選択します(イベ [ントの作成を参照](#creating-an-event))。

   デフォルトでは、トランザクションプッシュ通知は、受信者がサブスクライブしているすべてのモバイルアプリケーションに送信されます。 特定のモバイルアプリケーションにプッシュ通知を送信するには、リストでその通知を選択します。 その他のモバイルアプリはメッセージのターゲットになりますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. トランザクションメッセージをパーソナライズする場合は、イベントにフィールドを追加します(イベ [ント属性の定義を参照](#defining-the-event-attributes))。

   >[!NOTE]
   エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるので、 **First** Name（名）や **Last Name（姓）** （姓）など、他のフィールドを作成する必要はありません。

1. イベントをリソースにリンクするために、エンリッチメントを作成しま **[!UICONTROL Profile]** す(トランザクショ [ンメッセージコンテンツの強化を参照](#enriching-the-transactional-message-content))。 ターゲットディメンションを使用する場合は、エンリッチメントの作 **[!UICONTROL Profile]** 成が必須です。
1. イベントをプレビューして公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、登録トークン、アプリケーション名、およびプッシュプラットフォームを指定する属性が含まれません。これらの属性は、リソースから取得さ **[!UICONTROL Profile]** れます。

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成したメッセージを変更して公開する方法については、プロファイルを対象としたトランザク [ションプッシュ通知の送信を参照してくださ](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)い。

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### フォローアップメッセージを送信するイベントの設定 {#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージは、特定のトランザクションメッセージの受信者にメッセージを送信するためのワークフローで使用できる、事前定義されたマーケティング配信テンプレートです。 詳しくは、「フォローアップメッセ [ージ」を参照してください](../../channels/using/follow-up-messages.md)。

1. イベントトランザクションメッセージの送信には、作成したのと同じイベント設定を使用します。 イベントベ [ースのトランザクションメッセージを参照](#event-based-transactional-messages)。
1. イベントを設定する場合は、イベントを発行する前に **[!UICONTROL Create follow-up delivery template for this event]** チェックボックスをオンにしてください。

   ![](assets/message-center_follow-up-checkbox.png)

1. イベントをプレビューして公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントが公開されると、トランザクションメッセージと、新しいイベントにリンクされたフォローアップ配信テンプレートが自動的に作成されます。 フォローアップメッセージの使用について詳しくは、「フォロ [ーアップメッセージの送信」を参照してくださ](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)い。

## 使用例：トランザクションメッセージを送信するイベントの設定 {#use-case--configuring-an-event-to-send-a-transactional-message}

この例では、Webサイトでの各購入後に次の前提条件を満たして確認メッセージを送信するようにイベントを設定します。

このCRM IDを使用してクライアントを識別するには、まず、この新しいフィールドを使用してリソ **[!UICONTROL Profile]** ースが拡張されていることを確認します。

同様に、購入に対応するカスタムリソースが作成および発行され、リソースにリンクされている必要があり **[!UICONTROL Profile]** ます。 この方法を使用すると、このリソースから情報を取得して、メッセージの内容を強化できます。

リソースの作成と公開について詳しくは、このページを参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。

1. チャネルとターゲットディメンションを **[!UICONTROL Email]** 使用して新しいイベ **[!UICONTROL Profile]** ントを作成します(イベ [ントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズするために使用できる属性を定義します。 この場合、「CRM ID」と「製品識別子」フィールドを追加します(イベント属性の [定義を参照](#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. クライアントの以前の購入に関する情報でメッセージコンテンツを強化するには、リソースをターゲットとするリッチメントを作成します(トランザク **[!UICONTROL Purchase]** ションメッセージ [コンテンツの強化を参照](#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 以前にメッセージに追加した「製品識別子」フィールドと、リソースの対応するフィールドとの結合条件を作成しま **[!UICONTROL Purchase]** す。

   ![](assets/message-center_usecase3.png)

1. イベントをプレビューして公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。
1. Webサイトにイベントを統合します(Web [サイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

