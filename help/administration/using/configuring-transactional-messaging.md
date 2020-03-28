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
source-git-commit: ce55c5193e7944c65e0d9e6cc791ed2bc13b3509

---


# トランザクションメッセージの設定{#configuring-transactional-messaging}

Adobe Campaignでトランザクションメッセージを送信するには、まずデータの構造を記述する必要があります。イベントデータ

イベントの設定は、次の手順に従っ **て** 、管理者が実行する必要があります。

設定は、送信するトランザクションメッセージの種類によって異なります。 詳しくは、トランザクションイベント固有の設定 [を参照してください。](#transactional-event-specific-configurations)

イベントが公開されると、対応するトランザクションメッセージが自動的に作成されます。 For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## イベント {#creating-an-event}

開始を作成します。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を **[!UICONTROL Marketing plans]** 選択し **[!UICONTROL Transactional messages]** ます **[!UICONTROL Event configuration]**。
1. ボタンをクリッ **[!UICONTROL Create]** クします。
1. とを **[!UICONTROL Label]****[!UICONTROL ID]** イベント このフ **[!UICONTROL ID]** ィールドは必須で、プレフィックス「EVT」で始まる必要があります。 このプレフィックスを使用しない場合、をクリックすると自動的に追加されま **[!UICONTROL Create]**&#x200B;す。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >IDは、EVTプレフィックスを含めて64文字を超えてはなりません。

1. チャネルの送信に使用するトランザクションメッセージを選択するか、ま **[!UICONTROL Email]**&#x200B;たは **[!UICONTROL Mobile (SMS)]****[!UICONTROL Mobile application]** （プッシュ通知）。

   >[!NOTE]
   >
   >各チャネル設定で使用できるイベントは1つだけです。 一旦イベントが作成されると、変更はできません。チャネル

1. 目的のターゲティングディメンション設定に対応するイベントを選択し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   イベントベースのトランザクションメッセージターゲットデータはイベント自体に含まれ、プロファイルベースのトランザクションメッセージターゲットデータはAdobe Campaignデータベースに含まれます。 詳しくは、トランザクションイベント固有の設定 [を参照してください](#transactional-event-specific-configurations)。

## イベント属性の定義 {#defining-the-event-attributes}

このセクシ **[!UICONTROL Fields]** ョンで、イベントコンテンツに統合され、トランザクションメッセージのパーソナライズに使用できる属性を定義します。

フィールドの追加と変更の手順は、カスタムリソースの場合と [同じです](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は、 **[!UICONTROL AC_language]** IDを使用して追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ当てはまります。 イベントの公開後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語標準の電子メールの手順と同じです。 See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## データコレクションの定義 {#defining-data-collections}

要素のコレクションをイベントのコンテンツに追加し、各要素自体に複数の属性を含めることができます。

このコレクションは、トランザクション用の電子メールで使用し、製品のリスト（価格、参照番号、数量など）をメッセージの内容に追加できます。 をリストの

1. セクション **[!UICONTROL Collections]** で、ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/message-center_collection_create.png)

1. コレ追加クションのラベルとID。
1. トランザクションメッセージに表追加示するすべてのフィールドで、製品の各リストを表示します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

イベントとメッセージが公開されると、このコレクションを自分のトランザクションメッセージで使用できます。

次に、この例のAPIプレビューを示します。

![](assets/message-center_collection_api-preview.png)

**関連トピック：**

* [プレビューと公開イベント](#previewing-and-publishing-the-event)
* [製品リストのトランザクションメッセージ](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## トランザクションメッセージ内容の強化 {#enriching-the-transactional-message-content}

Adobe Campaignデータベースの情報を使用してトランザクションメッセージのコンテンツを豊富にすることで、メッセージをパーソナライズできます。 例えば、各受信者の姓またはCRM IDから、住所や生年月日などのデータや、プロファイルテーブルに追加された他のカスタムフィールドなどのデータを回復して、送信する情報をパーソナライズできます。

拡張リソースやトランザクションメッセージの情報を使用して、リソースの内容を強化す **[!UICONTROL Profile]** ることが **[!UICONTROL Service]** できます。

この情報は、新しいリソースに保存することもできます。 この場合、リソースは、またはのリソースに直接、または別のテ **[!UICONTROL Profile]** ーブルを **[!UICONTROL Service]** 介してリンクされている必要があります。 例えば、以下の設定では、トランザクションメッセージがリソースにリンクされている場合、カテゴリの内容を製品のやIDなどのリソースの情報で拡張する **[!UICONTROL Product]** ことができ **[!UICONTROL Product]****[!UICONTROL Profile]** ます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、このページを参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。

1. セクション **[!UICONTROL Enrichment]** で、ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. ボタンを使 **[!UICONTROL Create element]** 用して、選択したリソースのフィールドを、以前にイベントに追加したフィールドの1つにリンクします( [イベント属性の定義](#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. この例では、とのフィールドをリソ **[!UICONTROL Last name]** ース内の **[!UICONTROL First name]** 対応するフィールドと調整し **[!UICONTROL Profile]** ます。

   ![](assets/message-center_enrichment-join-fields.png)

   また、リソースを使用してトランザクションメッセージの内容を強化することも **[!UICONTROL Service]** できます。 サービスについて詳しくは、この節を参照して [ください](../../audiences/using/creating-a-service.md)。

1. プロファイルベースのイベントを作成または編集する場合は、「」セクションで、配信の実行時にメッセ **[!UICONTROL Targeting enrichment]** ージターゲットとして使用するエンリッチメントを選択します。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >リソースに基づくターゲットエンリッチメントの選択は、 **[!UICONTROL Profile]** プロファイルベースのイベントでは必須です。

イベントとメッセージが公開されると、このリンクを使用してメッセージの内容を強化できます。トランザクションメッセージ

**関連トピック：**

* [イベントのプレビュー](#previewing-and-publishing-the-event)。
* [トランザクションメッセージの個人化](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## プレビューと公開イベント {#previewing-and-publishing-the-event}

このイベントを使用する前に、プレビューして公開する必要があります。

1. ボタンをク **[!UICONTROL API preview]** リックすると、Webサイトの開発者が公開する前に使用するREST APIのシミュレーションが表示されます。 イベントが公開されると、このボタンを使用して実稼働環境のAPIのプレビューを確認することもできます。 詳しくは、 [Webサイトでのイベントのトリガーの統合を参照してください](#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST APIは、選択したチャネルと選択したターゲティングディメンションによって異なります。 各種設定の詳細については、「トランザクションイベント固有の設定」を参 [照してくださ](#transactional-event-specific-configurations)い。

1. クリックし **[!UICONTROL Publish]** て開始を作成

   ![](assets/message-center_pub.png)

1. 対応するタブで表示ログを作成できます。

   ![](assets/message-center_logs.png)


>[!NOTE]
>
>イベントを変更するたびに、を再度クリックして、Web **[!UICONTROL Publish]** サイト開発者が使用する更新されたREST APIを生成する必要があります。

イベントが公開されると、新しいトランザクションメッセージにリンクされたイベントが自動的に作成されます。 このイベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

作成されたトランザクションメッセージには、左側の領域のリンクから直接アクセスできます。

![](assets/message-center_messagegeneration.png)

また、このトリガーイベントをWebサイトに統合する必要があります。 詳しくは、 [Webサイトでのイベントのトリガーの統合を参照してください](#integrating-the-triggering-of-the-event-in-a-website)。

<!--
>[!NOTE]
>
>To consult the previous publications if any, click the **[!UICONTROL Latest transactional events]** link under the **[!UICONTROL History]** section in the left-hand side area.
-->

### 公開の取り消しイベント {#unpublishing-an-event}

このボ **[!UICONTROL Unpublish]** タンを使用すると、イベントの公開をキャンセルできます。これにより、以前に作成したイベントに対応するリソースがREST APIから削除されます。 現在は、Webサイトを通じてイベントがトリガーされても、対応するメッセージは送信されず、データベースには保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージを既に公開している場合は、トランザクションメッセージの公開もキャンセルされます。 詳しくは、公 [開の取り消しを参照してください](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)。

新しいREST APIを生 **[!UICONTROL Publish]** 成するには、ボタンをクリックします。

### 削除，イベント {#deleting-an-event}

イベントが非公開になった場合、またはイベントがまだ公開されていない場合は、イベント設定リストから削除できます。 手順は次のとおりです。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を **[!UICONTROL Marketing plans]** 選択し **[!UICONTROL Transactional messages]** ます **[!UICONTROL Event configuration]**。
1. 選択したイベント設定にマウスを移動し、ボタンを選択 **[!UICONTROL Delete element]** します。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >イベントの設定がステータスを持っ **[!UICONTROL Draft]** ていることを確認してください。そうしないと、削除できなくなります。 ステータス **[!UICONTROL Draft]** は、まだ公開されていないイベント、または未公開の画像に適用さ [れます](#unpublishing-an-event)。

1. ボタンをクリッ **[!UICONTROL Confirm]** クします。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>公開済みで既に使用されているイベント設定を削除すると、対応するトランザクションメッセージと、その送信およびトラッキングログも削除されます。

## Webサイトでのイベントのトリガーの統合 {#integrating-the-triggering-of-the-event-in-a-website}

作成したイベントは、Webサイトに統合する必要があります。

「 [Transactional messaging operating principal](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) 」セクションで説明した例では、買い物かごに商品を購入する前に、顧客の1人がWebサイトを離れるたびに「買い物かごの放棄」イベントをトリガーする必要があります。 これを行うには、WebサイトのWeb開発者がAdobe Campaign Standard REST APIを使用する必要があります。

詳しくは、 [REST APIドキュメントを参照してください](../../api/using/managing-transactional-messages.md) 。

## トランザクションイベント固有の設定 {#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージ(イベントまたはプロファイル)のタイプと、使用するチャネルによって異なります。

次の節では、目的の設定に従って具体的に設定する必要のある設定について詳しくトランザクションメッセージします。 イベントを設定する一般的な手順について詳しくは、「イベントの作成」を参 [照してくださ](#creating-an-event)い。

### イベントベースのトランザクションメッセージ {#event-based-transactional-messages}

イベントベースのトランザクションメッセージを送信するには、まず、イベント自体に含まれるデータをターゲットにしたイベントを作成し、設定する必要があります。
詳しくは、トランザクションメッセージ [ングの利用を参照してくださ](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)い。

1. イベント設定を作成する際に、 **[!UICONTROL Real-time event]** ターゲティングディメンションを選択します( [イベントの作成を参照](#creating-an-event))。
1. イベント追加に対するフィールド。トランザクションメッセージをパーソナライズできるようにするためです( [イベント属性の定義](#defining-the-event-attributes))。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージのコンテンツを拡張します( [トランザクションメッセージのコンテンツの強化](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージングは、送信イベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義する必要があります。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージのコンテンツを強化することができます。

1. プレビューしてイベントを公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、選択したオプションに従って電子メールアドレスまたは携帯電話を指定する属性が含まれています。チャネル

   イベントが公開されると、新しいトランザクションメッセージにリンクされたイベントが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して公開する必要があります。「 [イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)」

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### プロファイルベースのトランザクションメッセージ {#profile-based-transactional-messages}

プロファイルベースのトランザクションメッセージを送信するには、まず、Adobe Campaignデータベースに含まれるイベントターゲットデータを作成し、設定する必要があります。

1. イベント設定を作成する際に、 **[!UICONTROL Profile event]** ターゲティングディメンションを選択します( [イベントの作成を参照](#creating-an-event))。
1. イベント追加に対するフィールド。トランザクションメッセージをパーソナライズできるようにするためです( [イベント属性の定義](#defining-the-event-attributes))。 フィールドを作成するには、少なくとも1つのフィールドを追加する必要があります。エンリッチメント Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるように **、「** First name **」や「** Last name」など、他のフィールドを作成する必要はありません。
1. エンリッチメントを作成して、イベントをリソースにリンクします(リソ **[!UICONTROL Profile]** ースのコンテ [ンツの強化を参照](#enriching-the-transactional-message-content))。 エンリッチメントを使用する場合、作成は必須 **[!UICONTROL Profile]** です。
1. プレビューしてイベントを公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、リソースから取得される電子メールアドレスまたは携帯電話を指定する属性が含まれてい **[!UICONTROL Profile]** ません。

   イベントが公開されると、新しいトランザクションメッセージにリンクされたイベントが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。詳しくは、「プロファイル [トランザクションメッセージの送信」を参照してください](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### イベントベースのトランザクションプッシュ通知 {#event-based-transactional-push-notifications}

トランザクションプッシュ通知を送信するには、それに応じてAdobe Campaignを設定する必要があります。 プッシュ [設定を参照してくださ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)い。

匿名のトランザクションプッシュ通知を、モバイルアプリケーションからの通知の受信を選択したすべてのイベントに送信するには、まず、イベント自体に含まれるデータをターゲットにしたユーザーを作成し、設定する必要があります。 対応する手順を以下に示します。

このイベントには、次の3つの要素が含まれている必要があります。

* 登録 **トークン**。1つのモバイルアプリケーションと1つのデバイスのユーザーIDです。 Adobe Campaignデータベースのプロファイルに対応していない場合があります。
* モバイ **ルアプリケーション** (すべてのデバイス（AndroidおよびiOS）用)の名前。 これは、ユーザーのデバイスでプッシュ通知を受信するために使用される、Adobe Campaignで設定されたモバイルアプリのIDです。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* プッ **シュプラットフォ** ーム（Androidの場合は「gcm」、iOSの場合は「apns」）。

1. イベント設定を作成する際に、チャネルと **[!UICONTROL Mobile application]** ターゲティングディメンションを選択します( **[!UICONTROL Real-time event]** 「 [イベントの作成](#creating-an-event)」を参照)。
1. イベント追加に対するフィールド。トランザクションメッセージをパーソナライズできるようにするためです( [イベント属性の定義](#defining-the-event-attributes))。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージのコンテンツを拡張します( [トランザクションメッセージのコンテンツの強化](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージングは、送信イベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義する必要があります。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージのコンテンツを強化することができます。

1. プレビューしてイベントを公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、配信のターゲットに使用される「registrationToken」、「application」および「pushPlatform」属性が含まれます。

   ![](assets/message-center_push_api.png)

   イベントが公開されると、新しいトランザクションにリンクされたトランザクションプッシュ通知が自動的にイベントされます。 作成したメッセージを変更して公開する方法については、トランザクションを対象とし [たトランザクションプッシュ通知の送信を参照してください](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)。

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### プロファイルベースのトランザクションプッシュ通知 {#profile-based-transactional-push-notifications}

モバイルアプリケーションをサブスクライブしているAdobe Campaignプロファイルにトランザクションプッシュ通知を送信するには、まずAdobe Campaignデータベースをターゲットとするイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、チャネルと **[!UICONTROL Mobile application]** ターゲティングディメンションを選択します( **[!UICONTROL Profile]** 「 [イベントの作成](#creating-an-event)」を参照)。

   デフォルトでは、トランザクションのプッシュ通知は、トランザクションがサブスクライブしているすべてのモバイル受信者に送信されます。 特定のモバイルアプリケーションにプッシュ通知を送信するには、アプリケーションでその通知をリストします。 その他のモバイルアプリはメッセージのターゲットになりますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. イベントに対追加するフィールド。トランザクションメッセージをパーソナライズする場合( [イベント属性の定義](#defining-the-event-attributes))。

   >[!NOTE]
   >
   >フィールドを作成するには、少なくとも1つのフィールドを追加する必要があります。エンリッチメント Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるように **、「** First name **」や「** Last name」など、他のフィールドを作成する必要はありません。

1. エンリッチメントを作成して、イベントをリソースにリンクします(リソ **[!UICONTROL Profile]** ースのコンテ [ンツの強化を参照](#enriching-the-transactional-message-content))。 エンリッチメントを使用する場合、作成は必須 **[!UICONTROL Profile]** です。
1. プレビューしてイベントを公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、登録トークン、アプリケーション名、およびプッシュプラットフォームを指定する属性が含まれません。これらの属性は、リソースから取得さ **[!UICONTROL Profile]** れます。

   イベントが公開されると、新しいトランザクションにリンクされたトランザクションプッシュ通知が自動的にイベントされます。 作成したメッセージを変更して公開する方法については、トランザクションを対象と [したトランザクションプッシュ通知の送信を参照してください](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)。

1. イベントをWebサイトに統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### フォローアップイベントを送信するメッセージの設定 {#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージは、特定の配信テンプレートの受信者にメッセージを送信するためのワークフローで使用できる、事前定義されたマーケティングトランザクションメッセージです。 詳しくは、「フォローアップメッセ [ージ」を参照してください](../../channels/using/follow-up-messages.md)。

1. 作成したのと同じイベント設定を使用して、イベントトランザクションメッセージ。 詳しくは、 [イベントベースのトランザクションメッセージ](#event-based-transactional-messages)。
1. イベントの設定時に、イベントを公開する前に **[!UICONTROL Create follow-up delivery template for this event]** チェックボックスをオンにします。

   ![](assets/message-center_follow-up-checkbox.png)

1. プレビューしてイベントを公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントが公開されると、新しいトランザクションメッセージにリンクされた配信テンプレートとフォローアップイベントが自動的に作成されます。 フォローアップメッセージの使用について詳しくは、「フォロ [ーアップメッセージの送信」を参照してくださ](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)い。

## 使用例：送信するイベントの設定トランザクションメッセージ {#use-case--configuring-an-event-to-send-a-transactional-message}

この例では、Webサイトでの各購入後に次の前提条件を満たして確認メッセージを送信するようにイベントを設定します。

このCRM IDを使用してクライアントを識別するには、まず、この新しいフィールドを使用してリソ **[!UICONTROL Profile]** ースが拡張されていることを確認します。

同様に、購入に対応するカスタムリソースが作成および発行され、リソースにリンクされている必要があり **[!UICONTROL Profile]** ます。 この方法を使用すると、このリソースから情報を取得して、メッセージの内容を強化できます。

リソースの作成と公開について詳しくは、このページを参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。

1. 新しいイベントを作成します( **[!UICONTROL Email]** チャネルと **[!UICONTROL Profile]** ターゲティングディメンションを使用 [します](#creating-an-event))。
1. トランザクションメッセージのパーソナライズに使用できる属性を定義します。 この場合、「CRM ID」と「製品ID」フィールドを追加します(イベント属性の [定義を参照](#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. クライアントの以前の購入に関する情報でメッセージの内容を拡張するには、リソースをターゲットにしたエンリッチメントを作成します( **[!UICONTROL Purchase]** トランザクションメッセージの内 [容の強化を参照](#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 以前にメッセージに追加した「製品識別子」フィールドと、リソースの対応するフィールドとの結合条件を作成しま **[!UICONTROL Purchase]** す。

   ![](assets/message-center_usecase3.png)

1. プレビューしてイベントを公開します( [イベントのプレビューと公開を参照](#previewing-and-publishing-the-event))。
1. Webサイトにイベントを統合します( [Webサイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

