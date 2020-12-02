---
solution: Campaign Standard
product: campaign
title: トランザクションメッセージの設定
description: トランザクションメッセージを設定する方法について説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '3169'
ht-degree: 7%

---


# トランザクションメッセージの設定{#configuring-transactional-messaging}

トランザクションメッセージにAdobe Campaignを送信するには、まずイベントデータの構造を説明する必要があります。

以下の手順に従って、[管理者](../../administration/using/users-management.md#functional-administrators)がイベントの設定を行う必要があります。

>[!NOTE]
>
>設定は、送信するトランザクションメッセージの種類に応じて異なる場合があります。 詳しくは、[トランザクションイベント固有の設定](#transactional-event-specific-configurations)を参照してください。

イベントが公開されたら、次の操作を行います。

* Webサイト開発者が使用するAPIがデプロイされ、トランザクションイベントを送信できるようになりました。 詳しくは、[Webサイト](#integrating-the-triggering-of-the-event-in-a-website)でのイベントのトリガーの統合を参照してください。

* 対応するトランザクションメッセージが自動的に作成されます。 詳しくは、[トランザクションメッセージの使用の手引き](../../channels/using/getting-started-with-transactional-msg.md)を参照してください。

## イベントの作成{#creating-an-event}

開始するには、必要に応じてイベントを作成します。

>[!IMPORTANT]
>
>**[!UICONTROL Administration]**&#x200B;の役割を持ち、**[!UICONTROL All]** [組織単位](../../administration/using/organizational-units.md)に属しているユーザーだけが、イベント設定を作成する適切な権限を持ちます。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** を選択します。
1. 「**[!UICONTROL Create]**」ボタンをクリックします。
1. イベントに&#x200B;**[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL ID]**&#x200B;を渡します。 **[!UICONTROL ID]**&#x200B;フィールドは必須で、プレフィックス「EVT」で始まる必要があります。 このプレフィックスを使用しない場合は、**[!UICONTROL Create]**&#x200B;をクリックすると自動的に追加されます。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >IDは、EVTプレフィックスを含めて64文字以下にする必要があります。

1. トランザクションメッセージ&#x200B;**[!UICONTROL Email]**、**[!UICONTROL Mobile (SMS)]**、または&#x200B;**[!UICONTROL Mobile application]** （プッシュ通知）の送信に使用するチャネルを選択します。

   >[!NOTE]
   >
   >各イベント設定で使用できるチャネルは 1 つだけです。イベントを作成した後は、チャネルを変更できません。

1. 目的のイベント設定に対応するターゲティングディメンションを選択し、**[!UICONTROL Create]**&#x200B;をクリックします。

   イベント自体に含まれるイベントベースのトランザクションメッセージターゲットデータに対し、Adobe Campaignデータベースに含まれるプロファイルベースのトランザクションメッセージターゲットデータに対して、 詳しくは、[トランザクションイベント固有の設定](#transactional-event-specific-configurations)を参照してください。

>[!NOTE]
>
>作成されたリアルタイムイベントの数は、プラットフォームに影響を与える可能性があります。 最適なパフォーマンスを確保するために、不要になったリアルタイムイベントを削除してください。 「[イベントの削除](#deleting-an-event)」を参照してください。

## イベント属性の定義{#defining-the-event-attributes}

**[!UICONTROL Fields]**&#x200B;セクションで、イベントコンテンツに統合され、トランザクションメッセージをパーソナライズするために使用できる属性を定義します。

フィールドの追加と変更の手順は、[カスタムリソース](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)の場合と同じです。

![](assets/message-center_2.png)

>[!NOTE]
>
>多言語トランザクションメッセージを作成する場合は、**[!UICONTROL AC_language]** IDを使用して追加のイベント属性を定義します。 これは、イベントトランザクションメッセージにのみ適用されます。 イベントの公開後、多言語トランザクションメッセージのコンテンツを編集する手順は、多言語標準の電子メールの手順と同じです。 [多言語電子メールの作成](../../channels/using/creating-a-multilingual-email.md)を参照してください。

## データコレクションの定義{#defining-data-collections}

イベントコンテンツに、要素の集まりを追加できます。各要素には、複数の属性が含まれます。

このコレクションは、メッセージの内容に[商品リスト](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)を追加するためのトランザクション用電子メールで使用できます。例えば、商品のリスト（価格、参照番号、数量など）が含まれます。 をリストの各製品に対して設定します。

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

* [イベントのプレビューと公開](#previewing-and-publishing-the-event)
* [トランザクションメッセージでの製品リストの使用](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## イベントを強化{#enriching-the-transactional-message-content}

トランザクションメッセージのコンテンツをAdobe Campaignデータベースの情報と共に拡張して、メッセージをパーソナライズすることができます。 例えば、各受信者の姓またはCRM IDから、住所や生年月日などのデータや、プロファイルテーブルに追加された他のカスタムフィールドなどのデータを回復し、送信する情報をパーソナライズできます。

拡張&#x200B;**[!UICONTROL Profile and services Ext API]**&#x200B;からの情報でトランザクションメッセージの内容を拡張することができます。 詳しくは、[APIの拡張を参照してください。拡張機能の公開](../../developing/using/step-2--publish-the-extension.md)

この情報は、新しいリソースにも保存できます。 この場合、リソースは&#x200B;**[!UICONTROL Profile]**&#x200B;または&#x200B;**[!UICONTROL Service]**&#x200B;リソースに直接リンクするか、別のテーブルを介してリンクする必要があります。 例えば、以下の設定では、**[!UICONTROL Product]**&#x200B;リソースが&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクされている場合、トランザクションメッセージの内容を製品のカテゴリやIDなどの&#x200B;**[!UICONTROL Product]**&#x200B;リソースからの情報で拡張できます。

![](assets/message-center_usecaseschema.png)

リソースの作成と公開について詳しくは、[このページ](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

1. 「**[!UICONTROL Enrichment]**」セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/message-center_addenrichment.png)

1. メッセージをリンクするリソースを選択します。 この場合は、**[!UICONTROL Profile]**&#x200B;リソースを選択します。

   ![](assets/message-center_new-enrichment.png)

1. **[!UICONTROL Create element]**&#x200B;ボタンを使用して、選択したリソースのフィールドを、以前にイベントに追加したフィールドの1つにリンクします(「[イベント属性の定義](#defining-the-event-attributes)」を参照)。

   ![](assets/message-center_enrichment-join.png)

1. この例では、**[!UICONTROL Last name]**&#x200B;と&#x200B;**[!UICONTROL First name]**&#x200B;のフィールドを&#x200B;**[!UICONTROL Profile]**&#x200B;リソースの対応するフィールドと紐付けます。

   ![](assets/message-center_enrichment-join-fields.png)

   **[!UICONTROL Service]**&#x200B;リソースを使用して、トランザクションメッセージの内容を拡張することもできます。 サービスについて詳しくは、[](../../audiences/using/creating-a-service.md)を参照してください。

1. プロファイルベースのイベントを作成または編集する場合は、「**[!UICONTROL Targeting enrichment]**」セクションで、配信の実行中にメッセージターゲットとして使用するエンリッチメントを選択します。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >**[!UICONTROL Profile]**&#x200B;リソースに基づくターゲットエンリッチメントの選択は、プロファイルベースのイベントに対して必須です。

イベントとメッセージが公開されると、このリンクを使用してトランザクションメッセージのコンテンツを拡充できます。

**関連トピック：**

* [イベントのプレビューと公開](#previewing-and-publishing-the-event)。
* [トランザクションメッセージの個人化](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## イベントのプレビューと公開{#previewing-and-publishing-the-event}

イベントを使用する前に、プレビューして公開する必要があります。

1. **[!UICONTROL API preview]**&#x200B;ボタンをクリックすると、Webサイト開発者が公開前に使用するREST APIのシミュレーションが表示されます。 イベントが公開されると、このボタンをクリックして実稼働中のAPIのプレビューも表示できます。 詳しくは、[Webサイト](#integrating-the-triggering-of-the-event-in-a-website)でのイベントのトリガーの統合を参照してください。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST APIは、選択したチャネルと選択したターゲティングディメンションに応じて異なります。 様々な設定について詳しくは、[トランザクションイベント固有の設定](#transactional-event-specific-configurations)を参照してください。

1. **[!UICONTROL Publish]**&#x200B;をクリックして開始パブリケーションを作成します。

   ![](assets/message-center_pub.png)

   Webサイト開発者が使用するAPIがデプロイされ、トランザクションイベントを送信できるようになりました。

1. 対応するタブで、パブリケーションログを表示できます。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >イベントを変更するたびに、**[!UICONTROL Publish]**&#x200B;を再度クリックして、Webサイト開発者が使用する更新されたREST APIを生成する必要があります。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。

1. このトランザクションメッセージには、左側の領域にあるリンクから直接アクセスできます。

   ![](assets/message-center_messagegeneration.png)

イベントがトランザクションメッセージの送信をトリガーするには、作成したばかりのメッセージを変更して発行する必要があります。 [イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

また、このトリガーイベントをWebサイトに統合する必要があります。 詳しくは、[Webサイト](#integrating-the-triggering-of-the-event-in-a-website)でのイベントのトリガーの統合を参照してください。

Adobe Campaign開始がこのイベント設定に関連するイベントを受け取ると、**[!UICONTROL History]**&#x200B;セクションの&#x200B;**[!UICONTROL Latest transactional events]**&#x200B;リンクを使用して、サードパーティのサービスから送信され、Adobe Campaignで処理された最新のイベントにアクセスできます。

![](assets/message-center_latest-events.png)

イベント（JSON形式）は、最新のものから最も古いものへと順に表示されます。 このリストを使用すると、イベントの内容やステータスなどのデータを調べ、制御およびデバッグの目的で確認できます。

### イベントの非公開{#unpublishing-an-event}

**[!UICONTROL Unpublish]**&#x200B;ボタンを使用すると、イベントの公開をキャンセルできます。これにより、以前に作成したイベントに対応するリソースがREST APIから削除されます。 これで、Web サイトを通じてイベントがトリガーされた場合でも、対応するメッセージは送信されなくなり、データベースには保存されません。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>対応するトランザクションメッセージを既に公開している場合は、トランザクションメッセージの公開もキャンセルされます。 [トランザクションメッセージの非公開](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)を参照してください。

**[!UICONTROL Publish]**&#x200B;ボタンをクリックして、新しいREST APIを生成します。

### トランザクションメッセージの公開プロセス {#transactional-messaging-pub-process}

次の図は、トランザクションメッセージの公開プロセスを示しています。

![](assets/message-center_pub-process.png)

トランザクションメッセージの公開、一時停止、非公開について詳しくは、[このセクション](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)を参照してください。

### イベントの削除{#deleting-an-event}

イベントが未公開になった場合、またはイベントがまだ公開されていない場合は、イベント設定リストから削除できます。 手順は次のとおりです。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** を選択します。
1. 選択したイベント構成にマウスを移動し、**[!UICONTROL Delete element]**&#x200B;ボタンを選択します。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >イベント構成のステータスが&#x200B;**[!UICONTROL Draft]**&#x200B;であることを確認してください。そうしないと、削除できません。 **[!UICONTROL Draft]**&#x200B;ステータスは、まだ公開されていないイベント、または[未公開](#unpublishing-an-event)の画像に適用されます。

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>公開済みで既に使用されているイベント設定を削除すると、対応するトランザクションメッセージとその送信およびトラッキングログも削除されます。

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

## Webサイト{#integrating-the-triggering-of-the-event-in-a-website}でのイベントのトリガーの統合

イベントを作成したら、このイベントのトリガーをWebサイトに組み込む必要があります。

[トランザクションメッセージングの動作原理](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)の節で説明した例では、「買い物かごに商品を購入する前に、顧客の1人がWebサイトを離れるたびに「買い物かごの放棄」イベントをトリガーする必要があります。 これを行うには、WebサイトのWeb開発者がAdobe Campaign StandardREST APIを使用する必要があります。

[REST APIドキュメント](../../api/using/managing-transactional-messages.md)を参照してください。

## トランザクションイベント固有の構成{#transactional-event-specific-configurations}

トランザクションイベントの設定は、送信するトランザクションメッセージ(イベントまたはプロファイル)の種類と、使用するチャネルによって異なります。

以下の節では、目的のトランザクションメッセージに応じて具体的な設定を行う必要がある場合について説明します。 イベントを設定する一般的な手順については、[イベントの作成](#creating-an-event)を参照してください。

### イベントベースのトランザクションメッセージ{#event-based-transactional-messages}

イベントベースのトランザクションメッセージを送信するには、まず、イベント自体に含まれるデータをターゲットにしたイベントを作成および設定する必要があります。
詳しくは、[トランザクションメッセージの利用](https://helpx.adobe.com/jp/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)を参照してください。

1. イベント設定を作成する際に、**[!UICONTROL Real-time event]**&#x200B;ターゲティングディメンションを選択します(「[イベントの作成](#creating-an-event)」を参照)。
1. イベントに追加対するフィールド。トランザクションメッセージをパーソナライズできるようにするために使用します(「[イベント属性の定義](#defining-the-event-attributes)」を参照)。
1. トランザクションメッセージデータベースの追加情報を使用する場合は、Adobe Campaignコンテンツを拡張します(「[トランザクションメッセージコンテンツの強化](#enriching-the-transactional-message-content)」を参照)。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージでは、受信者とメッセージコンテンツのパーソナライゼーションを定義するために、送信イベント内のデータのみを使用することが想定されています。ただし、Adobe Campaign データベースの情報を使用して、トランザクションメッセージの内容をエンリッチメントすることができます。

1. イベントをプレビューして公開します([イベントのプレビューと公開](#previewing-and-publishing-the-event)を参照)。

   イベントをプレビューする場合、REST APIには、選択したチャネルに従って電子メールアドレスまたは携帯電話を指定する属性が含まれます。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

1. イベントをWebサイトに統合します([Webサイトでのイベントのトリガーの統合](#integrating-the-triggering-of-the-event-in-a-website)を参照)。

### プロファイルベースのトランザクションメッセージ{#profile-based-transactional-messages}

プロファイルベースのトランザクションメッセージを送信するには、まず、Adobe Campaignデータベースに含まれるイベントターゲットデータを作成し、設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Profile event]**&#x200B;ターゲティングディメンションを選択します(「[イベントの作成](#creating-an-event)」を参照)。
1. イベントに追加対するフィールド。トランザクションメッセージをパーソナライズできるようにするために使用します(「[イベント属性の定義](#defining-the-event-attributes)」を参照)。 エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 **名**&#x200B;や&#x200B;**姓**&#x200B;など、Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるフィールドを作成する必要はありません。
1. イベントを&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクするエンリッチメントを作成します(「[トランザクションメッセージコンテンツの強化](#enriching-the-transactional-message-content)」を参照)。 **[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを使用する場合、エンリッチメントの作成は必須です。
1. イベントをプレビューして公開します([イベントのプレビューと公開](#previewing-and-publishing-the-event)を参照)。

   イベントをプレビューする場合、REST APIには、**[!UICONTROL Profile]**&#x200B;リソースから取得される電子メールアドレスまたは携帯電話を指定する属性が含まれません。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージが自動的に作成されます。 イベントがトランザクションメッセージの送信をトリガーするには、作成したメッセージを変更して発行する必要があります。「[プロファイルトランザクションメッセージの送信](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)」を参照してください。

1. イベントをWebサイトに統合します([Webサイトでのイベントのトリガーの統合](#integrating-the-triggering-of-the-event-in-a-website)を参照)。

### イベントベースのトランザクションプッシュ通知{#event-based-transactional-push-notifications}

トランザクションプッシュ通知を送信できるようにするには、それに応じてAdobe Campaignを設定する必要があります。 [プッシュ構成](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.translate.html)を参照してください。

匿名トランザクションプッシュ通知を、モバイルアプリケーションからの通知の受信をオプトインしているすべてのイベントに送信するには、まず、ユーザー自体に含まれるデータをターゲットにしたイベントを作成し、設定する必要があります。 対応する手順を以下に示します。

イベントには、次の3つの要素を含める必要があります。

* **登録トークン**。これは、1つのモバイルアプリケーションと1つのデバイスのユーザーIDです。 Adobe Campaignデータベースのプロファイルに対応していない場合があります。
* **モバイルアプリケーション名**（すべてのデバイス用のアプリケーション名 — AndroidおよびiOS）。 これは、Adobe Campaignで設定されたモバイルアプリケーションのIDで、ユーザーのデバイスでのプッシュ通知の受信に使用されます。 詳しくは、この[ページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)を参照してください。
* **プッシュプラットフォーム**（Androidの場合は「gcm」、iOSの場合は「apns」）。

1. イベント設定を作成する際に、**[!UICONTROL Mobile application]**&#x200B;チャネルと&#x200B;**[!UICONTROL Real-time event]**&#x200B;ターゲティングディメンションを選択します(「[イベントの作成](#creating-an-event)」を参照)。
1. イベントに追加対するフィールド。トランザクションメッセージをパーソナライズできるようにするために使用します(「[イベント属性の定義](#defining-the-event-attributes)」を参照)。
1. トランザクションメッセージデータベースの追加情報を使用する場合は、Adobe Campaignコンテンツを拡張します(「[トランザクションメッセージコンテンツの強化](#enriching-the-transactional-message-content)」を参照)。

   >[!NOTE]
   >
   >イベントベースのトランザクションメッセージでは、受信者とメッセージコンテンツのパーソナライゼーションを定義するために、送信イベント内のデータのみを使用することが想定されています。ただし、Adobe Campaign データベースの情報を使用して、トランザクションメッセージの内容をエンリッチメントすることができます。

1. イベントをプレビューして公開します([イベントのプレビューと公開](#previewing-and-publishing-the-event)を参照)。

   イベントをプレビューする場合、REST APIには、配信のターゲットに使用される「registrationToken」、「application」および「pushPlatform」属性が含まれます。

   ![](assets/message-center_push_api.png)

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成されたメッセージを変更して公開する方法については、[イベントを対象としたトランザクションプッシュ通知の送信](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)を参照してください。

1. イベントをWebサイトに統合します([Webサイトでのイベントのトリガーの統合](#integrating-the-triggering-of-the-event-in-a-website)を参照)。

### プロファイルベースのトランザクションプッシュ通知{#profile-based-transactional-push-notifications}

モバイルアプリケーションをサブスクライブしているAdobe Campaignプロファイルにトランザクションプッシュ通知を送信するには、まずAdobe Campaignデータベースをターゲットにしたイベントを作成し、設定する必要があります。

1. イベント設定を作成する際に、**[!UICONTROL Mobile application]**&#x200B;チャネルと&#x200B;**[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを選択します(「[イベントの作成](#creating-an-event)」を参照)。

   デフォルトでは、トランザクションプッシュ通知は、受信者がサブスクライブしているすべてのモバイルアプリケーションに送信されます。 特定のモバイルアプリケーションにプッシュ通知を送信するには、リストでそのアプリケーションを選択します。 その他のモバイルアプリはメッセージの対象になりますが、送信から除外されます。

   ![](assets/message-center_push_appfilter.png)

1. イベント追加のフィールドに値を入力します。トランザクションメッセージをパーソナライズする場合は、[イベント属性の定義](#defining-the-event-attributes)を参照してください。

   >[!NOTE]
   >
   >エンリッチメントを作成するには、少なくとも1つのフィールドを追加する必要があります。 **名**&#x200B;や&#x200B;**姓**&#x200B;など、Adobe Campaignデータベースのパーソナライゼーションフィールドを使用できるフィールドを作成する必要はありません。

1. イベントを&#x200B;**[!UICONTROL Profile]**&#x200B;リソースにリンクするエンリッチメントを作成します(「[トランザクションメッセージコンテンツの強化](#enriching-the-transactional-message-content)」を参照)。 **[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを使用する場合、エンリッチメントの作成は必須です。
1. イベントをプレビューして公開します([イベントのプレビューと公開](#previewing-and-publishing-the-event)を参照)。

   イベントをプレビューする場合、REST APIには、登録トークン、アプリケーション名、プッシュプラットフォームを指定する属性が含まれず、**[!UICONTROL Profile]**&#x200B;リソースから取得されます。

   イベントが発行されると、新しいイベントにリンクされたトランザクションプッシュ通知が自動的に作成されます。 作成されたメッセージを変更して公開する方法については、[プロファイルを対象としたトランザクションプッシュ通知の送信](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)を参照してください。

1. イベントをWebサイトに統合します([Webサイトでのイベントのトリガーの統合](#integrating-the-triggering-of-the-event-in-a-website)を参照)。

### フォローアップメッセージを送信するイベントの設定{#configuring-an-event-to-send-a-follow-up-message}

フォローアップメッセージは、定義済みのマーケティング配信テンプレートで、特定のトランザクションメッセージの受信者にメッセージを送信するためにワークフローで使用できます。 詳しくは、[フォローアップメッセージ](../../channels/using/follow-up-messages.md)を参照してください。

1. イベントトランザクションメッセージの送信に作成したのと同じイベント設定を使用します。 [イベントベースのトランザクションメッセージ](#event-based-transactional-messages)を参照してください。
1. イベントを設定する場合は、イベントを公開する前に&#x200B;**[!UICONTROL Create follow-up delivery template for this event]**&#x200B;ボックスをオンにします。

   ![](assets/message-center_follow-up-checkbox.png)

1. イベントをプレビューして公開します([イベントのプレビューと公開](#previewing-and-publishing-the-event)を参照)。

   イベントが公開されると、新しいイベントにリンクされたトランザクションメッセージとフォローアップ配信テンプレートが自動的に作成されます。 フォローアップメッセージの使用について詳しくは、[フォローアップメッセージの送信](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)を参照してください。

## 使用例：トランザクションメッセージを送信するイベントの設定{#use-case--configuring-an-event-to-send-a-transactional-message}

この例では、Webサイトでの購入のたびに次の前提条件を満たした確認メッセージを送信するようにイベントを設定します。

CRM IDを使用してクライアントを識別するには、まず&#x200B;**[!UICONTROL Profile]**&#x200B;リソースがこの新しいフィールドで拡張されていることを確認します。

同様に、購入に対応するカスタムリソースが作成および発行され、**[!UICONTROL Profile]**&#x200B;リソースにリンクされている必要があります。 この方法を使用すると、このリソースから情報を取得して、メッセージの内容を拡張できます。

リソースの作成と公開について詳しくは、[このページ](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

1. **[!UICONTROL Email]**&#x200B;チャネルと&#x200B;**[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを使用して新しいイベントを作成します([イベントの作成](#creating-an-event)を参照)。
1. トランザクションメッセージをパーソナライズするために使用できる属性を定義します。 この場合、「CRM ID」と「イベントID」フィールドを追加します（「[製品属性の定義](#defining-the-event-attributes)」を参照）。

   ![](assets/message-center_usecase1.png)

1. クライアントの以前の購入に関する情報でメッセージコンテンツを拡張するには、**[!UICONTROL Purchase]**&#x200B;リソースをターゲットにしたエンリッチメントを作成します(「[トランザクションメッセージコンテンツの強化](#enriching-the-transactional-message-content)」を参照)。

   ![](assets/message-center_usecase2.png)

1. 以前にメッセージに追加した「製品識別子」フィールドと、**[!UICONTROL Purchase]**&#x200B;リソースの対応するフィールドとの結合条件を作成します。

   ![](assets/message-center_usecase3.png)

1. イベントをプレビューして公開します([イベントのプレビューと公開](#previewing-and-publishing-the-event)を参照)。
1. イベントをWebサイトに統合します([Webサイトでのイベントのトリガーの統合](#integrating-the-triggering-of-the-event-in-a-website)を参照)。

