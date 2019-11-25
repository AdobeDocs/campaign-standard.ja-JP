---
title: トランザクションメッセージの設定
description: トランザクションメッセージングを設定する方法について説明します。
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
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# トランザクションメッセージの設定{#configuring-transactional-messaging}

Adobe Campaignでトランザクションメッセージを送信するには、まずイベントデータの構造を記述する必要があります。

イベントの設定は、次の手順に従っ **て** 、管理者が実行する必要があります。

設定は、送信するトランザクションメッセージの種類に応じて異なる場合があります。 詳しくは、トランザクションイベント固有 [の設定を参照してください](#transactional-event-specific-configurations)

イベントが発行されると、対応するトランザクションメッセージが自動的に作成されます。 For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## イベントの作成 {#creating-an-event}

まず、ニーズに応じたイベントを作成します。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を選 **[!UICONTROL Marketing plans]** 択し **[!UICONTROL Transactional messages]** ます **[!UICONTROL Event configuration]**。
1. Click the **[!UICONTROL Create]** button.
1. イベント **[!UICONTROL Label]** にとと **[!UICONTROL ID]** を指定します。 このフ **[!UICONTROL ID]** ィールドは必須で、先頭にプレフィックス「EVT」を付ける必要があります。 このプレフィックスを使用しない場合は、をクリックすると自動的に追加されま **[!UICONTROL Create]**&#x200B;す。

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >IDは、EVTプレフィックスを含めて64文字以内にする必要があります。

1. トランザクションメッセージの送信に使用するチャネルを選択す **[!UICONTROL Email]**&#x200B;るか、 **[!UICONTROL Mobile (SMS)]** ま **[!UICONTROL Mobile application]** たは（プッシュ通知）。

   >[!NOTE]
   >
   >各イベント設定には1つのチャネルのみを使用できます。 イベントが作成されると、チャネルを変更できなくなります。

1. 目的のイベント設定に対応するターゲットディメンションを選択し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   イベントベースのトランザクションメッセージは、イベント自体に含まれるデータをターゲットにしますが、プロファイルベースのトランザクションメッセージは、Adobe Campaignデータベースに含まれるデータをターゲットにします。 詳しくは、トランザクションイベント固有 [の設定を参照してください](#transactional-event-specific-configurations)。

## イベント属性の定義 {#defining-the-event-attributes}

このセクシ **[!UICONTROL Fields]** ョンで、イベントコンテンツに統合され、トランザクションメッセージをパーソナライズするために使用できる属性を定義します。

フィールドの追加と変更の手順は、カスタムリソースの場合と [同じです](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は、 **[!UICONTROL AC_language]** IDを使用して追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ適用されます。 イベントが発行された後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語標準の電子メールの場合と同じです。 See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## データコレクションの定義 {#defining-data-collections}

イベントコンテンツに、要素のコレクションを追加し、各要素に複数の属性を追加できます。

このコレクションは、メッセージの内容に製品リスト（価格、参照番号、数量など）を追加するために、トランザクション用の電子メールで使用できます。 をリストの各製品に対して設定します。

1. セクション **[!UICONTROL Collections]** で、ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/message-center_collection_create.png)

1. コレクションのラベルとIDを追加します。
1. リストの各製品のトランザクションメッセージに表示するすべてのフィールドを追加します。

   この例では、次のフィールドを追加しました。

   ![](assets/message-center_collection_fields.png)

イベントとメッセージが発行されると、このコレクションをトランザクションメッセージで使用できるようになります。

この例のAPIプレビューを次に示します。

![](assets/message-center_collection_api-preview.png)

**関連トピック：**

* [イベントのプレビューと公開](#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](#using-product-listings-in-a-transactional-message)

## トランザクションメッセージコンテンツの強化 {#enriching-the-transactional-message-content}

Adobe Campaignデータベースの情報を使用してトランザクションメッセージのコンテンツを強化することで、メッセージをパーソナライズできます。 例えば、各受信者の姓またはCRM IDから、住所や生年月日などのデータや、プロファイルテーブルに追加された他のカスタムフィールドを復元して、受信者に送信する情報をパーソナライズできます。

トランザクションメッセージのコンテンツを、拡張された情報やリソースの情報で拡張する **[!UICONTROL Profile]** ことが **[!UICONTROL Service]** できます。

この情報は、新しいリソースにも保存できます。 この場合、リソースは、またはリソースに直接、または別のテ **[!UICONTROL Profile]** ーブルを **[!UICONTROL Service]** 介してリンクする必要があります。 例えば、以下の設定では、リソースがリソースにリンクされている場合、トランザクションメッセージコンテンツを製品カテゴリやIDなどのリソースからの情報 **[!UICONTROL Product]** で拡張でき **[!UICONTROL Product]****[!UICONTROL Profile]** ます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、このページを参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。

1. セクション **[!UICONTROL Enrichment]** で、ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 この場合は、リソースを選択し **[!UICONTROL Profile]** ます。

   ![](assets/message-center_new-enrichment.png)

1. ボタンを使 **[!UICONTROL Create element]** 用して、選択したリソースのフィールドを、イベントに以前追加したフィールドの1つにリンクさせます(「イベ [ント属性の定義](#defining-the-event-attributes)」を参照)。

   ![](assets/message-center_enrichment-join.png)

1. この例では、とのフィールドをリソ **[!UICONTROL Last name]** ース内の **[!UICONTROL First name]** 対応するフィールドと調整し **[!UICONTROL Profile]** ます。

   ![](assets/message-center_enrichment-join-fields.png)

   また、リソースを使用して、トランザクションメッセージコンテンツを強化することも **[!UICONTROL Service]** できます。 詳しくは、を参照してください。

1. 「」セクシ **[!UICONTROL Targeting enrichment]** ョンで、配信の実行中にメッセージターゲットとして使用するエンリッチメントを選択します。 この例では、を選択しま **[!UICONTROL Profile]**&#x200B;す。 プロファイルベースのイベントでは、ターゲットエンリッチメントの選択は必須です。

   ![](assets/message-center_marketing_targeting_enrichment.png)

イベントとメッセージが発行されると、リソースとのリンクによっ **[!UICONTROL Profile]** て、トランザクションメッセージのコンテンツを強化できます。

**関連トピック：**

* [イベントのプレビューと公開](#previewing-and-publishing-the-event)。
* [トランザクションメッセージのパーソナライズ](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## イベントのプレビューと公開 {#previewing-and-publishing-the-event}

このイベントを使用する前に、プレビューして公開する必要があります。

1. ボタンをク **[!UICONTROL API preview]** リックすると、Webサイトの開発者が公開する前に使用するREST APIのシミュレーションが表示されます。 イベントが公開されると、このボタンを使用して実稼働環境でのAPIのプレビューを表示することもできます。 詳しく [は、Webサイトでのイベントのトリガーの統合を参照してください](#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST APIは、選択したチャネルと選択したターゲットディメンションに応じて異なります。 各種設定について詳しくは、トランザクションイベント固有 [の設定を参照してください](#transactional-event-specific-configurations)。

1. クリックし **[!UICONTROL Publish]** て発行を開始します。

   ![](assets/message-center_pub.png)

1. 対応するタブを選択して、パブリケーションログを表示できます。

   ![](assets/message-center_logs.png)

   タブを選択して、前のパブリケーションを参照することもできます。

>[!NOTE]
>
>イベントを変更するたびに、を再度クリックして、Web **[!UICONTROL Publish]** サイト開発者が使用する更新されたREST APIを生成する必要があります。

イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 このイベントでトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

作成されたトランザクションメッセージには、左側の領域のリンクから直接アクセスできます。

![](assets/message-center_messagegeneration.png)

また、このトリガーイベントをWebサイトに統合する必要があります。 詳しく [は、Webサイトでのイベントのトリガーの統合を参照してください](#integrating-the-triggering-of-the-event-in-a-website)。

### イベントの非公開 {#unpublishing-an-event}

このボ **[!UICONTROL Unpublish]** タンを使用すると、イベントの公開をキャンセルできます。これにより、以前に作成したイベントに対応するリソースがREST APIから削除されます。 現在は、Webサイトを通じてイベントがトリガーされても、対応するメッセージは送信されず、データベースに保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージを既に公開している場合は、トランザクションメッセージの公開もキャンセルされます。 詳しくは、ト [ランザクションメッセージの非公開を参照してくださ](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)い。

新しいREST APIを生 **[!UICONTROL Publish]** 成するには、ボタンをクリックします。

## Webサイトでのイベントのトリガーの統合 {#integrating-the-triggering-of-the-event-in-a-website}

イベントを作成したら、このイベントのトリガーをWebサイトに統合する必要があります。

「 [Transactional messaging operating principal](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) 」セクションで説明した例では、買い物かごに製品を購入する前に、顧客の1人がWebサイトを離れるたびに「買い物かごの中断」イベントをトリガーする必要があります。 これを行うには、WebサイトのWeb開発者がAdobe Campaign Standard REST APIを使用する必要があります。

詳しくは、 [REST APIドキュメントを参照してください](../../api/using/managing-transactional-messages.md) 。

## トランザクションイベント固有の設定 {#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージのタイプ（イベントまたはプロファイル）と、使用するチャネルによって異なる場合があります。

以下の節では、目的のトランザクションメッセージに従って具体的な設定を行う必要がある設定について説明します。 イベントを設定する一般的な手順について詳しくは、「イベントの作成」を参 [照してください](#creating-an-event)。

### イベント・ベースのトランザクション・メッセージ {#event-based-transactional-messages}

イベントベースのトランザクションメッセージを送信するには、まず、イベント自体に含まれるデータをターゲットにしたイベントを作成し、設定する必要があります。
詳しくは、トランザクションメッセージ [ングの利用を参照してくださ](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)い。

1. イベント設定を作成する際に、ターゲットディメンシ **[!UICONTROL Real-time event]** ョンを選択します(イベ [ントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します(イベ [ント属性の定義を参照](#defining-the-event-attributes))。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージコンテンツを拡張します(トランザクシ [ョンメッセージコンテンツの強化](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージングは、送信されたイベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義する必要があります。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージのコンテンツを強化できます。

1. イベントをプレビューして公開します(イベ [ントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする際、REST APIには、選択したチャネルに従って電子メールアドレスまたは携帯電話を指定する属性が含まれます。

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成されたメッセージを変更して発行する必要があります。イベントトランザクションメッセージを [参照してくださ](../../channels/using/event-transactional-messages.md)い。

1. イベントをWebサイトに統合します(Web [サイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### プロファイルベースのトランザクションメッセージ {#profile-based-transactional-messages}

プロファイルベースのトランザクションメッセージを送信するには、まずAdobe Campaignデータベースに含まれるイベントターゲットデータを作成し、設定する必要があります。

1. イベント設定を作成する際に、ターゲットディメンシ **[!UICONTROL Profile event]** ョンを選択します(イベ [ントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します(イベ [ント属性の定義を参照](#defining-the-event-attributes))。 エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるので、 **First name** （名）や **Last name** （姓）などの他のフィールドを作成する必要はありません。
1. イベントをリソースにリンクするために、エンリッチメントを作成します( **[!UICONTROL Profile]** トランザクシ [ョンメッセージコンテンツの強化](#enriching-the-transactional-message-content))。 ターゲットディメンションを使用する場合は、エンリッチメントの作 **[!UICONTROL Profile]** 成は必須です。
1. イベントをプレビューして公開します(イベ [ントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、リソースから取得される電子メールアドレスまたは携帯電話を指定する属性が含まれま **[!UICONTROL Profile]** せん。

   イベントが発行されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。詳しくは、 [Sending a profile transactional messageを参照してください](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. イベントをWebサイトに統合します(Web [サイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### イベントベースのトランザクションプッシュ通知 {#event-based-transactional-push-notifications}

トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。 プッシュ [設定を参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

匿名トランザクションプッシュ通知を、モバイルアプリケーションからの通知の受信をオプトインしているすべてのユーザーに送信するには、まず、イベント自体に含まれるデータを対象としたイベントを作成し、設定する必要があります。 対応する手順を以下に示します。

イベントには、次の3つの要素を含める必要があります。

* 登録 **トークン**。1つのモバイルアプリケーションと1つのデバイスのユーザーIDです。 Adobe Campaignデータベースのどのプロファイルにも対応していない場合があります。
* モバイ **ルアプリケーション** (すべてのデバイス（AndroidおよびiOS）用の名前)。 これは、ユーザーのデバイスでのプッシュ通知の受信に使用される、Adobe Campaignで設定されたモバイルアプリケーションのIDです。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* プッ **シュプラットフォーム** （Androidの場合は「gcm」、iOSの場合は「apns」）。

1. イベント設定を作成する際に、チャネルとターゲ **[!UICONTROL Mobile application]** ットディメンショ **[!UICONTROL Real-time event]** ンを選択します(イベ [ントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズできるように、イベントにフィールドを追加します(イベ [ント属性の定義を参照](#defining-the-event-attributes))。
1. Adobe Campaignデータベースの追加情報を使用する場合は、トランザクションメッセージコンテンツを拡張します(トランザク [ションメッセージコンテンツの強化](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージングは、送信されたイベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義する必要があります。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージのコンテンツを強化できます。

1. イベントをプレビューして公開します(イベ [ントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、配信のターゲット設定に使用される「registrationToken」、「application」および「pushPlatform」属性が含まれます。

   ![](assets/message-center_push_api.png)

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成されたメッセージを変更して発行するには、イベントを対象としたトランザク [ションプッシュ通知の送信を参照してください](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)。

1. イベントをWebサイトに統合します(Web [サイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### プロファイルベースのトランザクションプッシュ通知 {#profile-based-transactional-push-notifications}

モバイルアプリケーションをサブスクライブしたAdobe Campaignプロファイルにトランザクションプッシュ通知を送信するには、まずAdobe Campaignデータベースを対象としたイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、チャネルとターゲ **[!UICONTROL Mobile application]** ットディメンショ **[!UICONTROL Profile]** ンを選択します(イベ [ントの作成を参照](#creating-an-event))。

   デフォルトでは、受信者がサブスクライブしているすべてのモバイルアプリケーションにトランザクションプッシュ通知が送信されます。 特定のモバイルアプリケーションにプッシュ通知を送信するには、リストでそのアプリケーションを選択します。 その他のモバイルアプリはメッセージの対象になりますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. トランザクションメッセージをパーソナライズする場合は、イベントにフィールドを追加します(イベ [ント属性の定義を参照](#defining-the-event-attributes))。

   >[!NOTE]
   >
   >エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるので、 **First name** （名）や **Last name** （姓）などの他のフィールドを作成する必要はありません。

1. イベントをリソースにリンクするために、エンリッチメントを作成します( **[!UICONTROL Profile]** トランザクシ [ョンメッセージコンテンツの強化](#enriching-the-transactional-message-content))。 ターゲットディメンションを使用する場合は、エンリッチメントの作 **[!UICONTROL Profile]** 成は必須です。
1. イベントをプレビューして公開します(イベ [ントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントをプレビューする場合、REST APIには、登録トークン、アプリケーション名、およびプッシュプラットフォームを指定する属性が含まれず、リソースから取得さ **[!UICONTROL Profile]** れます。

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成されたメッセージを変更して発行するには、プロファイルを対象としたトランザク [ションプッシュ通知の送信を参照してください](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)。

1. イベントをWebサイトに統合します(Web [サイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

### フォローアップメッセージを送信するイベントの設定 {#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージは、特定のトランザクションメッセージの受信者にメッセージを送信するためのワークフローで使用できる、事前定義されたマーケティング配信テンプレートです。 詳しくは、「フォローアップメッ [セージ」を参照してください](../../channels/using/follow-up-messages.md)。

1. イベントトランザクションメッセージを送信する場合は、作成したのと同じイベント設定を使用します。 イベントベ [ースのトランザクションメッセージを参照](#event-based-transactional-messages)。
1. イベントを設定する場合は、イベントを発行する前に **[!UICONTROL Create follow-up delivery template for this event]** ボックスをオンにしてください。

   ![](assets/message-center_follow-up-checkbox.png)

1. イベントをプレビューして公開します(イベ [ントのプレビューと公開を参照](#previewing-and-publishing-the-event))。

   イベントが公開されると、トランザクションメッセージと、新しいイベントにリンクされたフォローアップ配信テンプレートが自動的に作成されます。 フォローアップメッセージの使用について詳しくは、「フォローア [ップメッセージの送信」を参照してくださ](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)い。

## 使用例：トランザクションメッセージを送信するイベントの設定 {#use-case--configuring-an-event-to-send-a-transactional-message}

この例では、Webサイトでの購入のたびに次の前提条件を満たした確認メッセージを送信するようにイベントを設定します。

このCRM IDを使用してクライアントを識別するには、まず、この新しいフィールドを使用してリソ **[!UICONTROL Profile]** ースが拡張されていることを確認します。

同様に、購入に対応するカスタムリソースが作成および発行され、リソースにリンクされている必要があり **[!UICONTROL Profile]** ます。 これにより、このリソースから情報を取得して、メッセージの内容を拡張できます。

リソースの作成と公開について詳しくは、このページを参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。

1. チャネルとターゲットディメンションを使 **[!UICONTROL Email]** 用して新しいイベ **[!UICONTROL Profile]** ントを作成します(イ [ベントの作成を参照](#creating-an-event))。
1. トランザクションメッセージをパーソナライズするために使用できる属性を定義します。 この例では、「CRM ID」フィールドと「製品識別子」フィールドを追加します(イベ [ント属性の定義](#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. クライアントの以前の購入に関する情報でメッセージコンテンツを強化するには、リソースをターゲットにしたリンチメ **[!UICONTROL Purchase]** ットを作成します( [トランザクションメッセージコンテンツの強化](#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 以前にメッセージに追加された「製品識別子」フィールドと、リソースから対応するフィールドとの結合条件を作成しま **[!UICONTROL Purchase]** す。

   ![](assets/message-center_usecase3.png)

1. イベントをプレビューして公開します(イベ [ントのプレビューと公開を参照](#previewing-and-publishing-the-event))。
1. Webサイトにイベントを統合します(Web [サイトでのイベントのトリガーの統合を参照](#integrating-the-triggering-of-the-event-in-a-website))。

