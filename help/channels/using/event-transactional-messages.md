---
title: イベントトランザクションメッセージ
seo-title: イベントトランザクションメッセージ
description: イベントトランザクションメッセージ
seo-description: イベントトランザクションメッセージを作成して公開する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: d747feb5-58fb-4e12- a176-404f0eca5391
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: トランザクションメッセージング
discoiquuid: 4f6317a1-9dfe-4714- bc1c-393629d855cd
context-tags: DeliveryTransactionalTemplate，概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e08b7e01956a9106937cb72ab790cb2e98999fcd

---


# Event transactional messages{#event-transactional-messages}

イベントをターゲティングするイベントトランザクションメッセージを送信できます。このタイプのトランザクションメッセージには、プロファイル情報は含まれていません。配信ターゲットは、イベント自体に含まれるデータによって定義されます。

Once you have created and published an event (the cart abandonment as explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send an transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. イベントトランザクションメッセージにはプロファイル情報は含まれません。したがって、プロファイルを使用した拡張の場合でも、疲労ルールと互換性がありません。[疲労ルール](../../administration/using/fatigue-rules.md#choosing-the-channel)を参照してください。

## Defining a test profile in a transactional message {#defining-a-test-profile-in-a-transactional-message}

最適化されたテストプロファイルを定義します。これにより、メッセージをプレビューして配達確認を送信して確認することができます。

### Creating a test profile within the transactional message {#creating-a-test-profile-within-the-transactional-----------message}

1. To access the message that you created, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. イベントにリンクされるテストプロファイルを作成します。

   ![](assets/message-center_test-profile.png)

1. **[!UICONTROL Event data used for personalization]** セクションでJSON形式で送信する情報を指定します。これは、メッセージのプレビュー時、およびテストプロファイルが配達確認を受け取るときに使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >プロファイルテーブルに関連する情報を入力することもできます。See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. 作成後、テストプロファイルはトランザクションメッセージで事前に指定されます。Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

### Creating a test profile outside the transactional message {#creating-a-test-profile-outside-the-transactional-----------message}

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section of the page of the test profile that you have chosen, select the event that you have just created. この例では、「買い物かごの放棄（eVCCartAndOnment）」を選択します。
1. **[!UICONTROL Event data]** テキストボックスでJSON形式で送信する情報を指定します。

   ![](assets/message-center_3.png)

1. 変更内容を保存します。

作成したメッセージにアクセスし、更新されたテストプロファイルを選択できるようになりました。

**関連トピック:**

* [テストプロファイルの管理](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [オーディエンスの定義](../../audiences/using/creating-audiences.md)

## Personalizing a transactional message {#personalizing-a-transactional-message}

トランザクションメッセージでパーソナライゼーションを設定するには、次の手順に従います。

1. **[!UICONTROL Content]** メッセージの件名とコンテンツを変更するには、ブロックをクリックします。この例では、画像、スタイルシートおよびHTMLファイルを含むHTMLテンプレートを読み込みます。Importing HTML templates is presented in the [Loading an existing content](../../designing/using/selecting-an-existing-content.md) section.

   ![](assets/message-center_6.png)

1. メッセージコンテンツを入力します。この例では、次の3つのパーソナライゼーションフィールドを追加しました。姓、最後に問い合わせた製品、買い物かごの総額。放棄された買い物かごへのリンクは、その人物を買い物かごにリダイレクトする外部URLへのリンクです。このパラメーターはAdobe Campaignでは管理されません。

   To add fields that you defined when you created your event (see [Configuring an event](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)), insert a personalization field in the message content. You can find the fields by selecting **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. メッセージの内容を充実させるには、イベントをリンクしたテーブルからフィールドを選択して追加します。In our example, select the **[!UICONTROL Title (salutation)]** field in the **[!UICONTROL Profile]** table.

   ![](assets/message-center_7-enrichment.png)

   The steps for inserting a personalization field are detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

   ![](assets/message-center_8.png)

1. このイベント用に定義したプロファイルを選択して、メッセージをプレビューします。

   The steps for previewing a message are detailed in the [Previewing messages](../../sending/using/preparing-the-send.md) section.

   ![](assets/message-center_9.png)

   パーソナライゼーションフィールドがテストプロファイルに入力された情報と一致することを確認できます。For more on this, see [Defining a test profile in a transactional message](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

トランザクション電子メールのコンテンツ内で1つまたは複数のデータコレクションを参照する製品リストを作成できます。例えば、買い物かごの放棄電子メールでは、ウェブサイトを離れたときにユーザーの買い物かごにあったすべての製品のリストを、画像、価格、各製品へのリンクと共に含めることができます。

>[!CAUTION]
>
>Product listings are only available when editing transactional email messages through the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) interface.

トランザクションメッセージで破棄された製品のリストを追加するには、次の手順に従います。

トランザクションの電子メールでの製品リストの設定に必要な手順について説明するビデオのセットも視聴できます。For more on this, see [this page](https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html).

>[!NOTE]
>
>Adobe Campaignではネストされた製品リストはサポートされていません。つまり、別の製品リスト内に製品リストを含めることはできません。

### Defining a product listing {#defining-a-product-listing}

トランザクションメッセージで製品一覧を使用するには、イベントレベルで、表示するリストの各製品のリストとフィールドを定義する必要があります。For more on this, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. 構造コンポーネントをワークスペースにドラッグ&amp;ドロップします。For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

   例えば、1列構造コンポーネントを選択し、テキストコンポーネント、画像コンポーネントおよびボタンコンポーネントを追加します。For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. コレクションの要素の表示方法を選択します。

   * **[!UICONTROL Row]**:水平方向に表示されます。つまり、ある行の各要素が他方の行の下にあることになります。
   * **[!UICONTROL Column]**:を垂直方向に設定します。つまり、同じ行上の各要素の横にあります。
   >[!NOTE]
   >
   >**[!UICONTROL Column]** このオプションは、複数列構造コンポーネント（ **[!UICONTROL 2:2 column]**&#x200B;および **[!UICONTROL 3:3 column]****[!UICONTROL 4:4 column]** ）を使用する場合にのみ使用できます。製品リストを編集するときは、最初の列にのみ入力してください。その他の列は考慮されません。For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. トランザクションメッセージに関連するイベントを設定するときに作成したデータ収集を選択します。You can find it under the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. **[!UICONTROL First item]** ドロップダウンリストを使用して、電子メールに表示されるリストを開始する要素を選択します。

   例えば、"2"を選択した場合、コレクションの最初のアイテムは電子メールに表示されません。製品リストは2番目のアイテムから開始します。

1. リストに表示する項目の最大数を選択します。

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

トランザクション電子メールにリンクされているイベントからの製品のリストを表示するには、次の手順に従います。

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** ノードから、作成したコレクション（ここで **[!UICONTROL Product list]** は）に対応するノードを開き、定義した画像フィールド（ここで **[!UICONTROL Product image]** は）を選択します。**[!UICONTROL Save]**&#x200B;をクリックします。

   ![](assets/message-center_loop_product-image.png)

   選択したパーソナライゼーションフィールドが、設定パネルに表示されるようになりました。

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** ノードから、作成したコレクション（ここで **[!UICONTROL Product list]** は）に対応するノードを開き、作成したフィールド（ここで **[!UICONTROL Product name]** は）を選択します。**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/message-center_loop_product_node.png)

   選択したパーソナライゼーションフィールドが、電子メールコンテンツ内の目的の位置に表示されるようになりました。

1. 同様に価格を挿入します。
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** ノードから、作成したコレクション（ここで **[!UICONTROL Product list]** は）に対応するノードを開き、作成したURLフィールドを選択します（ここで **[!UICONTROL Product URL]** ）。**[!UICONTROL Save]**&#x200B;をクリックします。

   >[!CAUTION]
   >
   >セキュリティ上の理由から、適切な静的ドメイン名で始まるリンクの中にパーソナライゼーションフィールドを挿入してください。

   ![](assets/message-center_loop_link_select.png)

   選択したパーソナライゼーションフィールドが、設定パネルに表示されるようになりました。

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. 1つまたは複数のコンテンツコンポーネントをドラッグし、必要に応じて編集します。

   ![](assets/message-center_loop_fallback.png)

   買い物かごに何も含まれていない場合など、イベントがトリガされると、そのイベントがトリガーされると代替コンテンツが表示されます。

1. 設定ウィンドウで、製品リストのスタイルを編集します。For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).
1. 関連するトランザクションイベントにリンクされているテストプロファイルを使用して電子メールをプレビューし、コレクションデータを定義します。For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Testing a transactional message {#testing-a-transactional-message}

トランザクションメッセージを保存したら、校正を送信してテストできるようになりました。

![](assets/message-center_10.png)

The steps for sending a proof are detailed in the [Sending a proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.

## Publishing a transactional message {#publishing-a-transactional-message}

トランザクションメッセージを確認したら、公開できます。

![](assets/message-center_12.png)

現在は、「買い物かごの放棄」イベントがトリガーされるとすぐに、受信者のタイトルと姓、買い物かごのURL、最後に問い合わせた製品、製品リストを定義した製品のリスト、合計買い物かごの金額を含むメッセージに、「買い物かごの放棄」イベントが表示されます。

To access reports concerning your transactional message, use the **[!UICONTROL Reports]** button. [レポート](../../reporting/using/about-dynamic-reports.md)を参照してください。

![](assets/message-center_13.png)

## Suspending a transactional message publication {#suspending-a-transactional-message-publication}

You can suspend publishing your transactional message by using the **[!UICONTROL Pause]** button, for example, to modify the data contained in the message. したがって、イベントは処理されなくなり、代わりにAdobe Campaignデータベースのキューに保持されます。

The queued events are kept during a period of time that is defined in the REST API (see [REST API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)) or in the trigger event if you are using the Triggers core service (see [Working with Campaign and Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

When clicking **[!UICONTROL Resume]**, all of the queued events (provided that they are not expired) are processed. テンプレートパブリケーションの停止中に実行されたすべての変更が含まれるようになりました。

## Unpublishing a transactional message {#unpublishing-a-transactional-message}

Clicking **[!UICONTROL Unpublish]** allows you to cancel the transactional message publication, but also the publication of the corresponding event, which deletes from the REST API the resource corresponding to the event that you previously created. これで、Webサイトでイベントがトリガーされても、対応するメッセージは送信されず、データベースに保存されません。

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>メッセージを再度公開するには、対応するイベント設定に戻り、公開してからメッセージを発行する必要があります。For more on this, see [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

一時停止したトランザクションメッセージの公開を取り消した場合、再度公開するまで最大24時間待機する必要があります。This is to let the **[!UICONTROL Database cleanup]** workflow clean all the events that were sent to the queue. The steps for pausing a message are detailed in the [Suspending a transactional message publication](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication) section.

**[!UICONTROL Database cleanup]** ワークフローは毎日午前4時に実行され、 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt;でアクセスでき **[!UICONTROL Workflows]**&#x200B;ます。

## Deleting a transactional message {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

By selecting a transactional message, you can delete it with the **[!UICONTROL Delete element]** button even if it has already been published. ただし、トランザクションメッセージの削除は、特定の状況でのみ実行できます。

* **トランザクションメッセージ**:トランザクションメッセージを削除するには、メッセージを非公開にして一時停止しないようにします。

   トランザクションメッセージが非公開の場合は、別のトランザクションメッセージが対応するイベントにリンクされていない限り、トランザクションメッセージを正常に削除するためにもイベント設定を非公開にする必要があります。For more information on how to unpublish a transactional message, refer to this [section](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

   >[!CAUTION]
   >
   >既に通知を送信しているトランザクションメッセージを削除すると、送信および追跡ログも削除されます。

* **標準的なイベントテンプレート（内部トランザクションメッセージ）からのトランザクションメッセージ**:内部トランザクションメッセージを削除するには、メッセージを非公開にして一時停止しないようにします。

   また、イベント内のトランザクションメッセージにすることもできません。その他のメッセージは、対応するイベントにリンクする必要があります。

## Transactional message retry process {#transactional-message-retry-process}

一時的に配信されていないトランザクションメッセージは、配信の期限が切れるまで実行される自動再試行の対象となります。For more on the delivery duration, see [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters).

トランザクションメッセージの送信に失敗した場合、次の2つの再試行システムがあります。

* トランザクションメッセージングレベルでは、イベントが実行配信に割り当てられてから、イベント受信と配信準備の間でトランザクションメッセージが失敗することがあります。[イベント処理の再試行プロセスを参照](../../channels/using/event-transactional-messages.md#event-processing-retry-process)してください。
* 送信プロセスレベルでは、イベントが実行配信に割り当てられた後、一時的なエラーが原因でトランザクションメッセージが失敗する可能性があります。[詳しくは、「再試行プロセス](../../channels/using/event-transactional-messages.md#message-sending-retry-process)の送信」を参照してください。

### Event processing retry process {#event-processing-retry-process}

イベントを実行配信に割り当てることができない場合、イベント処理が延期されます。再試行は、新しい実行配信に割り当てられるまで実行されます。

>[!NOTE]
>
>延期されたイベントは、まだ実行の配信に割り当てられていないので、トランザクションメッセージには表示されません。

例えば、イベントを実行配信に割り当てることができず、アクセス権やブランディングに問題があったので、タイポロジルールなどの適用時にエラーが検出されました。この場合、メッセージを一時停止して編集し、問題を修正して再度投稿することができます。次に、retryシステムはそれを新しい実行配信に割り当てます。

### Message sending retry process {#message-sending-retry-process}

イベントが実行配信に割り当てられた後、受信者のメールボックスがいっぱいになると、一時的なエラーが原因でトランザクションメッセージが失敗する可能性があります。For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>イベントが実行配信に割り当てられると、この実行配信の送信ログにはこのイベントが表示されます。The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message.

### Limitations {#limitations}

**ログの更新の送信**

再試行プロセスでは、新しい実行配信の送信ログは直ちに更新されません（更新はスケジュールされたワークフローによって実行されます）。It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**失敗した実行配信**

実行配信を停止することはできません。ただし、現在の実行配信が失敗した場合は、新しいイベントが受信されるとすぐに新しいイベントが作成され、新しいイベントがすべてこの新しい実行配信によって処理されます。失敗した実行配信によって新しいイベントが処理されることはありません。

既に実行配信に割り当てられているイベントが延期されている場合、その実行配信に失敗した場合、再試行システムは延期されたイベントを新しい実行配信に割り当てません。つまり、これらのイベントは失われます。
