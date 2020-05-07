---
title: イベントトランザクションメッセージ
description: イベントトランザクションメッセージを作成して公開する方法について説明します。
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '2479'
ht-degree: 0%

---


# イベントトランザクションメッセージ{#event-transactional-messages}

イベントをターゲットにしたイベントトランザクションメッセージを送信できます。 この種類のトランザクションメッセージには、プロファイル情報が含まれません。 配信ターゲットは、イベント自体に含まれるデータによって定義されます。

イベントを作成して公開すると( [この節で説明する買い物かごの放棄](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle))、対応するトランザクションメッセージが自動的に作成されます。

設定手順は、「トランザクションメッセージを送信するためのイベントの [設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」の節に記載されています。

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、 **[!UICONTROL Administrators (all units)]** セキュリティグループに属している必要があります。
>
>イベントトランザクションメッセージにはプロファイル情報が含まれないので、疲労ルールとの互換性はありません(プロファイルとのエンリッチメントの場合でも)。 「 [疲労ルール](../../sending/using/fatigue-rules.md#choosing-the-channel)」を参照してください。

## トランザクションメッセージでのテストプロファイルの定義 {#defining-a-test-profile-in-a-transactional-message}

メッセージをプレビューし、配達確認を送信して確認できる、適応したテストプロファイルを定義します。

### トランザクションメッセージ内でのテストプロファイルの作成 {#creating-a-test-profile-within-the-transactional-----------message}

1. 作成したメッセージにアクセスするには、 **[!UICONTROL Adobe Campaign]** ロゴをクリックし、左上隅にある **[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** /を選択し **[!UICONTROL Transactional messages]**&#x200B;ます。

   ![](assets/message-center_4.png)

1. イベントにリンクするテストプロファイルを作成します。

   ![](assets/message-center_test-profile.png)

1. JSON形式で送信する情報を **[!UICONTROL Event data used for personalization]** セクションに指定します。 これは、メッセージをプレビューするとき、およびテストプロファイルが配達確認を受け取るときに使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >プロファイルテーブルに関連する情報を入力することもできます。 詳しくは、トランザクションメッセージコンテンツの [富化を参照してください](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。

1. 作成後、テストプロファイルはトランザクションメッセージで事前に指定されます。 配達確認のターゲットを確認するには、メッセージの **[!UICONTROL Test profiles]** ブロックをクリックします。

   ![](assets/message-center_5.png)

### トランザクションメッセージ外でのテストプロファイルの作成 {#creating-a-test-profile-outside-the-transactional-----------message}

新しいテストプロファイルを作成するか、既にメニューにあるテストを使用することもでき **[!UICONTROL Test profiles]** ます。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、「/」を選択し **[!UICONTROL Profiles & audiences]** ま **[!UICONTROL Test profiles]**&#x200B;す。
1. 選択したテストプロファイルのページの **[!UICONTROL Event]** セクションで、先ほど作成したイベントを選択します。 この例では、「買い物かごの放棄(EVTcartAbandant)」を選択します。
1. JSON形式で送信する情報を **[!UICONTROL Event data]** テキストボックスに指定します。

   ![](assets/message-center_3.png)

1. 変更を保存します。

これで、作成したメッセージにアクセスし、更新されたテストプロファイルを選択できます。

**関連トピック：**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [オーディエンスの定義](../../audiences/using/creating-audiences.md)

## トランザクションメッセージの個人設定 {#personalizing-a-transactional-message}

トランザクションメッセージでパーソナライゼーションを設定するには、次の手順に従います。

1. メッセージの件名と内容を変更するには、 **[!UICONTROL Content]** ブロックをクリックします。 この例では、画像とテキストを含む任意のテンプレートを選択します。 電子メールコンテンツテンプレートについて詳しくは、「テンプレートを使用した [デザイン](../../designing/using/using-reusable-content.md#designing-templates)」を参照してください。

   ![](assets/message-center_6.png)

1. 件名追加を入力し、必要に応じてメッセージの内容を編集します。

   >[注意]
   >
   >破棄された買い物かごへのリンクは、人を買い物かごにリダイレクトする外部URLへのリンクです。 このパラメーターは、Adobe Campaignでは管理されません。

1. この例では、イベントの [作成時に定義した3つのフィールドを追加します](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)。 名、最後に問い合わせた製品、買い物かごの総数 これを行うには、メッセージコンテンツにパーソナライゼーションフィールド [](../../designing/using/personalization.md#inserting-a-personalization-field) を挿入します。

1. > >を順に選択して、該当するフィールドを表示 **[!UICONTROL Context]** し **[!UICONTROL Real-time event]** ま **[!UICONTROL Event context]**&#x200B;す。

   ![](assets/message-center_7.png)

1. メッセージの内容を拡張するには、イベントをリンクしたテーブルからフィールドを選択して追加します。 この例では、テー **[!UICONTROL Title (salutation)]** ブル内の> **[!UICONTROL Profile]** >を順に選択してい **[!UICONTROL Context]****[!UICONTROL Real-time event]****[!UICONTROL Event context]**&#x200B;ます。

   ![](assets/message-center_7-enrichment.png)

1. 必要なフィールドをすべて挿入します。

   ![](assets/message-center_8.png)

1. このイベント用に定義したプロファイルを選択して、メッセージをプレビューします。

   メッセージをプレビューする手順について詳しくは、「メッセージの [プレビュー](../../sending/using/previewing-messages.md) 」の項を参照してください。

   ![](assets/message-center_9.png)

   パーソナライゼーションフィールドがテストプロファイルに入力された情報と一致しているかどうかを確認できます。 詳しくは、「トランザクションメッセージでのテストプロファイルの [定義](#defining-a-test-profile-in-a-transactional-message)」を参照してください。

## トランザクションメッセージでの製品リストの使用 {#using-product-listings-in-a-transactional-message}

トランザクション用電子メールのコンテンツ内の1つ以上のデータコレクションを参照する製品リストを作成できます。 例えば、買い物かごの放棄に関する電子メールでは、ユーザがWebサイトを離れたときにユーザの買い物かごに含まれていたすべての商品のリストを、画像、価格、各商品へのリンクと共に含めることができます。

>[!IMPORTANT]
>
>製品リストは、 [電子メールデザイナーインターフェイスを通じてトランザクション電子メールメッセージを編集する場合にのみ使用でき](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) ます。

トランザクションメッセージに破棄された商品のリストを追加するには、次の手順に従います。

また、トランザクション用の電子メールで製品リストを設定するために必要な手順を説明するビデオを一連視聴することもできます。 For more on this, see [this page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html).

>[!NOTE]
>
>Adobe Campaignは入れ子になった製品リストをサポートしていません。つまり、別の製品リストに製品を含めることはできません。

### 製品リストの定義 {#defining-a-product-listing}

トランザクションメッセージ内の商品リストを使用する前に、表示するリストの各商品のリストとフィールドをイベントレベルで定義する必要があります。 詳しくは、データコレクションの [定義を参照してください](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. トランザクションメッセージで、ブロックをクリックして電子メールの内容を変更し **[!UICONTROL Content]** ます。
1. 構造コンポーネントをワークスペースにドラッグ&amp;ドロップします。 詳しくは、「電子メール構造の [編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」を参照してください。

   例えば、1列の構造コンポーネントを選択し、テキストコンポーネント、画像コンポーネント、ボタンコンポーネントを追加します。 詳しくは、「フラグメントとコンポーネントの [追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」を参照してください。

1. 先ほど作成した構造コンポーネントを選択し、コンテキストツールバーの **[!UICONTROL Enable product listing]** アイコンをクリックします。

   ![](assets/message-center_loop_create.png)

   構造コンポーネントはオレンジ色のフレームでハイライト表示され、 **[!UICONTROL Product listing]** 設定は左側のパレットに表示されます。

   ![](assets/message-center_loop_palette.png)

1. コレクションの要素の表示方法を選択します。

   * **[!UICONTROL Row]**: horizontally（水平方向）とは、他の行の下の各要素を意味します。
   * **[!UICONTROL Column]**: 垂直方向。同じ行で、各要素が隣り合っていることを意味します。
   >[!NOTE]
   >
   >この **[!UICONTROL Column]** オプションは、複数列の構造コンポーネント(およ **[!UICONTROL 2:2 column]**&#x200B;び **[!UICONTROL 3:3 column]****[!UICONTROL 4:4 column]** )を使用する場合にのみ使用できます。 製品リストを編集する場合は、最初の列にのみ入力します。 他の列は考慮されません。 構造コンポーネントの選択について詳しくは、「電子メール構造の [編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」を参照してください。

1. トランザクションメッセージに関連するイベントを設定する際に作成したデータ収集を選択します。 これは、 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** ノードの下にあります。

   ![](assets/message-center_loop_selection.png)

   イベントの設定について詳しくは、データコレクションの [定義を参照してください](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. ドロップダウン **[!UICONTROL First item]** リストを使用して、電子メールに表示されるリストを開始する要素を選択します。

   例えば、「2」を選択した場合、コレクションの最初のアイテムは電子メールに表示されません。 2つ目の商品は商品リストに開始されます。

1. リストに表示する項目の最大数を選択します。

   >[!NOTE]
   >
   >リストの要素を垂直に表示する場合( **[!UICONTROL Column]** )は、選択した構造コンポーネント（2、3、4列）に応じて、項目の最大数が制限されます。 構造コンポーネントの選択について詳しくは、「電子メール構造の [編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」を参照してください。

### 製品リストへの入力 {#populating-the-product-listing}

トランザクション電子メールにリンクされたイベントからの商品のリストを表示するには、次の手順に従います。

コレクションの設定時に、イベントおよび関連するフィールドを作成する方法について詳しくは、データコレクションの [定義を参照してください](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 挿入したイメージコンポーネントを選択し、設定パネルで鉛筆 **[!UICONTROL Enable personalization]** を選択します。

   ![](assets/message-center_loop_image.png)

1. 開い **[!UICONTROL Add personalization field]** た **[!UICONTROL Image source URL]** ウィンドウでを選択します。

   > **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** nodeで、作成したコレクションに対応するノード(ここ **[!UICONTROL Product list]** では **[!UICONTROL Product image]** )を開き、定義した画像フィールド（ここでは）を選択します。 クリック **[!UICONTROL Save]** .

   ![](assets/message-center_loop_product-image.png)

   選択したパーソナライゼーションフィールドが設定ペインに表示されます。

1. 目的の位置で、コンテキストツールバー **[!UICONTROL Insert personalization field]** からを選択します。

   ![](assets/message-center_loop_product.png)

1. > **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** nodeで、作成したコレクションに対応するノード(ここ **[!UICONTROL Product list]** では **[!UICONTROL Product name]** )を開き、作成したフィールド（ここでは）を選択します。 クリック **[!UICONTROL Confirm]** .

   ![](assets/message-center_loop_product_node.png)

   選択したパーソナライゼーションフィールドが電子メールコンテンツ内の目的の位置に表示されます。

1. 価格を挿入する場合と同様に行います。
1. テキストを選択し、コンテキストツールバー **[!UICONTROL Insert link]** からを選択します。

   ![](assets/message-center_loop_link_insert.png)

1. 開い **[!UICONTROL Add personalization field]** た **[!UICONTROL Insert link]** ウィンドウでを選択します。

   > **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** nodeで、作成したコレクションに対応するノード(ここ **[!UICONTROL Product list]** では **[!UICONTROL Product URL]** )を開き、作成したURLフィールド（ここでは）を選択します。 クリック **[!UICONTROL Save]** .

   >[!IMPORTANT]
   >
   >セキュリティ上の理由から、リンク内にパーソナライゼーションフィールドを挿入し、適切な静的ドメイン名で始めてください。

   ![](assets/message-center_loop_link_select.png)

   選択したパーソナライゼーションフィールドが設定ペインに表示されます。

1. 製品リストを適用する構造コンポーネントを選択し、デフォルトコンテンツ **[!UICONTROL Show fallback]** を定義する場合に選択します。

   ![](assets/message-center_loop_fallback_show.png)

1. 1つまたは複数のコンテンツコンポーネントをドラッグし、必要に応じて編集します。

   ![](assets/message-center_loop_fallback.png)

   顧客が買い物かごに何も入れていない場合など、イベントがトリガーされたときにコレクションが空の場合、フォールバックのコンテンツが表示されます。

1. 設定ペインで、製品リストのスタイルを編集します。 For more on this, see [Editing email styles](../../designing/using/styles.md).
1. 関連するトランザクションイベントにリンクされ、収集データを定義したテストプロファイルを使用して、電子メールをプレビューします。 例えば、使用するテストプロファイルの **[!UICONTROL Event data]** 節に次の情報を追加します。

   ![](assets/message-center_loop_test-profile_payload.png)

   トランザクションメッセージでのテストプロファイルの定義について詳しくは、 [この節を参照してください](#defining-a-test-profile-in-a-transactional-message)。

## トランザクションメッセージのテスト {#testing-a-transactional-message}

トランザクションメッセージを保存すると、配達確認を送信してテストできるようになります。

![](assets/message-center_10.png)

配達確認の送信手順について詳しくは、「配達確認の [送信](../../sending/using/sending-proofs.md) 」を参照してください。

## トランザクションメッセージの公開 {#publishing-a-transactional-message}

トランザクションメッセージをチェックしたら、それを公開できます。

![](assets/message-center_12.png)

現在は、「買い物かごの放棄」イベントがトリガーされるとすぐに、受信者のタイトルと姓、買い物かごのURL、最後に問い合わせた商品、または商品のリスト（商品リストを定義した場合）と送信される合計買い物かご数を含むメッセージが自動的に表示されます。

トランザクションメッセージに関するレポートにアクセスするには、 **[!UICONTROL Reports]** ボタンを使用します。 「 [レポート](../../reporting/using/about-dynamic-reports.md)」を参照してください。

![](assets/message-center_13.png)

## トランザクションメッセージパブリケーションの一時停止 {#suspending-a-transactional-message-publication}

トランザクションメッセージに含まれるデータを変更する場合など、 **[!UICONTROL Pause]** ボタンを使用してメッセージの公開を中止できます。 したがって、イベントは処理されず、Adobe Campaignデータベースのキューに保持されます。

キューに格納されたイベントは、REST API( [REST APIのドキュメントを参照](../../api/using/get-started-apis.md))またはTriggersコアサービス(Triggersコアサービスの [使用(キャンペーンとExperience Cloud Triggersの操作を参照](../../integrating/using/about-adobe-experience-cloud-triggers.md))で定義された期間、保持されます。

![](assets/message-center_pause.png)

クリック **[!UICONTROL Resume]**&#x200B;すると、キューに格納されているすべてのイベント（期限切れでない場合）が処理されます。 現在は、テンプレートのパブリケーションが停止されている間に行われたすべての変更が含まれます。

## トランザクションメッセージの非公開 {#unpublishing-a-transactional-message}

をクリックす **[!UICONTROL Unpublish]** ると、トランザクションメッセージのパブリケーションをキャンセルできますが、対応するイベントのパブリケーションもキャンセルできます。これにより、REST APIから、以前に作成したイベントに対応するリソースが削除されます。

![](assets/message-center_unpublish-template.png)

現在は、Webサイトを通じてイベントがトリガーされた場合でも、対応するメッセージは送信されなくなり、データベースには保存されません。

>[!NOTE]
>
>メッセージを再度公開するには、対応するイベント設定に戻り、公開してから、メッセージを公開する必要があります。 詳しくは、「トランザクションメッセージの [公開](#publishing-a-transactional-message)」を参照してください。

一時停止したトランザクションメッセージを非公開にする場合は、再度公開するまで24時間待たなければならない場合があります。 これは、キューに送信されたすべてのイベントを **[!UICONTROL Database cleanup]** ワークフローで消去するためです。

メッセージを一時停止する手順について詳しくは、「トランザクションメッセージの発行を [停止する](#suspending-a-transactional-message-publication) 」の節を参照してください。

毎日午前4時に実行される **[!UICONTROL Database cleanup]** ワークフローは、 > **[!UICONTROL Administration]** >からアクセスでき **[!UICONTROL Application settings]****[!UICONTROL Workflows]**&#x200B;ます。

## トランザクションメッセージの削除 {#deleting-a-transactional-message}

トランザクションメッセージが未公開になった場合、またはトランザクションメッセージがまだ公開されていない場合は、トランザクションメッセージリストからその画像を削除できます。 手順は次のとおりです。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、 **[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** /を選択し **[!UICONTROL Transactional messages]**&#x200B;ます。
1. 選択したメッセージにマウスを合わせます。
1. ボタンをクリックし **[!UICONTROL Delete element]** ます。

![](assets/message-center_delete-template.png)

ただし、トランザクションメッセージの削除は、次の特定の状況でのみ実行できます。

* トランザクションメッセージのステータスが **[!UICONTROL Draft]** あることを確認してください。そうしないと、削除できません。 この **[!UICONTROL Draft]** ステータスは、まだ公開されていないメッセージ、または [未公開(または](#unpublishing-a-transactional-message) 一時停止されていない [](#suspending-a-transactional-message-publication))メッセージに適用されます。

* **トランザクションメッセージ**: 対応するイベントに別のトランザクションメッセージがリンクされている場合を除き、トランザクションメッセージが非公開の場合は、イベントを正常に削除するために、トランザクションメッセージ設定も非公開にする必要があります。 詳しくは、イベントの [非公開を参照してください](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。

   >[!IMPORTANT]
   >
   >既に通知を送信したトランザクションメッセージを削除すると、その送信およびトラッキングログも削除されます。

* **標準搭載のイベントテンプレート(内部トランザクションメッセージ)**: 内部トランザクションメッセージが、対応する内部イベントに関連付けられている唯一のものである場合、その内部は削除できません。 別のトランザクションメッセージを作成する場合は、まず複製するか、 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Transactional message templates]** メニューを使用します。

## トランザクションメッセージの再試行プロセス {#transactional-message-retry-process}

一時的に配信されないトランザクションメッセージは、配信が期限切れになるまで自動再試行が実行される場合があります。 配信期間について詳しくは、 [有効期間パラメーターを参照してください](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

トランザクションメッセージの送信に失敗した場合は、2つの再試行システムがあります。

* トランザクションメッセージングレベルでは、トランザクションメッセージが実行配信に割り当てられる前(イベントの受信と配信の準備の間)に、イベントが失敗する可能性があります。 「 [イベント処理の再試行プロセス](#event-processing-retry-process)」を参照してください。
* 送信プロセスレベルでは、イベントが実行配信に割り当てられると、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。 詳しくは、 [メッセージ送信再試行プロセス](#message-sending-retry-process)を参照してください。

### イベント処理の再試行プロセス {#event-processing-retry-process}

イベントを実行配信に割り当てられない場合、イベント処理は延期されます。 再試行は、新しい実行配信に割り当てられるまで実行されます。

>[!NOTE]
>
>延期されたイベントは、まだ実行配信に割り当てられていないので、トランザクションメッセージ送信ログに表示されません。

例えば、イベントの内容が正しくない、アクセス権やブランディングに問題がある、タイポロジルールの適用時にエラーが検出されたなどの理由で、実行配信にを割り当てることができませんでした。 この場合、メッセージを一時停止し、編集して問題を修正し、再度公開できます。 再試行システムは、その後、新しい実行配信に割り当てます。

### メッセージ送信の再試行プロセス {#message-sending-retry-process}

イベントが実行配信に割り当てられると、受信者のメールボックスがいっぱいになった場合など、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。 For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>イベントが実行配信に割り当てられると、その配信はこの実行の送信ログに表示され、現時点でのみ表示されます。 失敗した配信は、トランザクションメッセージの **[!UICONTROL Execution list]** タブに表示されます。

### 制限事項 {#limitations}

**ログの更新を送信中**

再試行プロセスでは、新しい実行配信の送信ログは直ちに更新されません（更新はスケジュールされたワークフローを介して実行されます）。 つまり、トランザクションイベントが新しい実行配信で処理されている場合でも、メッセージの **[!UICONTROL Pending]** ステータスが変わる可能性があります。

**失敗した実行配信**

実行配信を停止することはできません。 ただし、現在の実行配信が失敗した場合、新しいイベントを受け取るとすぐに新しいイベントが作成され、新しい実行配信で新しいすべての実行が処理されます。 失敗した実行配信で新しいイベントが処理されることはありません。

実行配信に既に割り当てられている一部のイベントが延期され、その実行配信に失敗した場合、再試行システムは、延期されたイベントを新しい実行配信に割り当てません。これは、これらのイベントが失われたことを意味します。
