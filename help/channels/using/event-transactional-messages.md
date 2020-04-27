---
title: イベントトランザクションメッセージ
description: イベントトランザクションメッセージ
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# イベントトランザクションメッセージ{#event-transactional-messages}

イベントをターゲットにしてイベントトランザクションメッセージを送信できます。 このタイプのトランザクションメッセージには、次の情報は含まれていません。プロファイル情報：配信ターゲットは、そのデータ自体に含まれるデータによってイベントされます。

イベントを作成して公開すると(この節で説明する買い物かごの中断 [)](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)、対応するトランザクションメッセージが自動的に作成されます。

設定手順は、「送信するイベントの [設定」の節に示されています](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

イベントがメッセージの送信をトリガーするには、トランザクションメッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、セキュリティグループに属してい **[!UICONTROL Administrators (all units)]** る必要があります。
>
>イベントトランザクションメッセージにはプロファイル情報が含まれないので、疲労ルール(プロファイルとエンリッチメントした場合でも)との互換性がありません。 疲労ルー [ルを参照してくださ](../../sending/using/fatigue-rules.md#choosing-the-channel)い。

## テストプロファイルの定義 {#defining-a-test-profile-in-a-transactional-message}

適応したテストプロファイルを定義します。これにより、メッセージにプレビューを付け、配達確認を送信して確認できます。

### テストプロファイルのトランザクションメッセージ {#creating-a-test-profile-within-the-transactional-----------message}

1. 作成したメッセージにアクセスするには、左 **[!UICONTROL Adobe Campaign]** 上隅のロゴをクリックし、/を **[!UICONTROL Marketing plans]** 選択 **[!UICONTROL Transactional messages]** します **[!UICONTROL Transactional messages]**。

   ![](assets/message-center_4.png)

1. テストプロファイルを作成し、そのテストをイベントにリンクします。

   ![](assets/message-center_test-profile.png)

1. JSON形式で送信する情報をセクションで指定し **[!UICONTROL Event data used for personalization]** ます。 これは、メッセージのプレビュー時およびテストプロファイルがメッセージを受け取る際に使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >また、情報テーブルに関する情報を入力することもできます。プロファイルテーブル 詳しくは、 [トランザクションメッセージコンテンツの強化](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。

1. 作成後、テストプロファイルは事前にトランザクションメッセージに指定されます。 メッセージの **[!UICONTROL Test profiles]** ブロックをクリックして、メッセージのターゲットを確認します。

   ![](assets/message-center_5.png)

### テストプロファイルの外部作成トランザクションメッセージ {#creating-a-test-profile-outside-the-transactional-----------message}

また、新しいテストプロファイルを作成したり、既にメニューに存在するテストメニューを使用したりで **[!UICONTROL Test profiles]** きます。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、/を選択 **[!UICONTROL Profiles & audiences]** します **[!UICONTROL Test profiles]**。
1. 選択した **[!UICONTROL Event]** テストプロファイルのページのセクションで、作成したイベントを選択します。 この例では、「買い物かごの放棄(EVTcartAbaund)」を選択します。
1. JSON形式で送信する情報をテキストボックスに指 **[!UICONTROL Event data]** 定します。

   ![](assets/message-center_3.png)

1. 変更を保存します。

作成したメッセージにアクセスして、更新したテストオプションをプロファイルできます。

**関連トピック：**

* [テストプロファイル](../../audiences/using/managing-test-profiles.md)
* [定義オーディエンス](../../audiences/using/creating-audiences.md)

## 個人用トランザクションメッセージ {#personalizing-a-transactional-message}

パーソナライゼーションをトランザクションメッセージで設定するには、次の手順に従います。

1. ブロックをク **[!UICONTROL Content]** リックして、メッセージの件名と内容を変更します。 この例では、画像とテキストを含むテンプレートを選択します。 電子メールコンテンツテンプレートについて詳しくは、「テンプレートを使 [用したデザイン」を参照してくださ](../../designing/using/using-reusable-content.md#designing-templates)い。

   ![](assets/message-center_6.png)

1. 件追加名を入力し、必要に応じてメッセージの内容を編集します。

   >[メモ]
   >
   >放棄された買い物かごへのリンクは、買い物かごに人をリダイレクトする外部URLへのリンクです。 このパラメーターは、管理されていません。Adobe Campaign。

1. この例では、イベントの作成時に定義した3つのフィールドを追 [加します](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)。名、最後に問い合わせた製品、合計買い物かご金額。 これを行うには、メッセージ [コンテンツにパーソナライゼーション](../../designing/using/personalization.md#inserting-a-personalization-field) フィールドを挿入します。

1. > >を順に選択して、該当するフ **[!UICONTROL Context]** ィールド **[!UICONTROL Real-time event]** を表示しま **[!UICONTROL Event context]**&#x200B;す。

   ![](assets/message-center_7.png)

1. メッセージの内容を拡張するには、リンク先のテーブルからフィールドを選択して、フィールドを追加します。イベント この例では、> >からテ **[!UICONTROL Title (salutation)]** ーブル内のフ **[!UICONTROL Profile]** ィールドを **[!UICONTROL Context]** 選択し **[!UICONTROL Real-time event]** ます **[!UICONTROL Event context]**。

   ![](assets/message-center_7-enrichment.png)

1. 必要なすべてのフィールドを挿入します。

   ![](assets/message-center_8.png)

1. プレビューを行うには、このプロファイル用に定義したイベントを選択します。

   メッセージをプレビューする手順について詳しくは、「メッセージのプレビ [ュー](../../sending/using/previewing-messages.md) 」を参照してください。

   ![](assets/message-center_9.png)

   テスト用の情報とパーソナライゼーションフィールドが一致していることを確認できます。プロファイル 詳しくは、「トランザクションメッセージでのテスト [プロファイルの定義」を参照してください](#defining-a-test-profile-in-a-transactional-message)。

## 製品リストのトランザクションメッセージ {#using-product-listings-in-a-transactional-message}

トランザクション電子メールのコンテンツ内の1つ以上のデータコレクションを参照する製品リストを作成できます。 例えば、買い物かごの放棄の電子メールには、ユーザがWebサイトを離れたときに買い物かごに含まれていたすべての製品のリストを、画像、価格、各製品へのリンクと共に含めることができます。

>[!IMPORTANT]
>
>製品リストは、 [Email Designerインターフェイスを通じてトランザクション電子メールメッセージを編集する場合にのみ使用でき](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) ます。

破棄されたリストの製品をトランザクションメッセージに追加するには、次の手順に従います。

また、トランザクション用の電子メールで製品リストを設定するために必要な手順を説明する一連のビデオも視聴できます。 For more on this, see [this page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html).

>[!NOTE]
>
>Adobe Campaignは、入れ子になった製品リストをサポートしていません。つまり、別の製品リストの中に製品リストを含めることはできません。

### 製品リストの定義 {#defining-a-product-listing}

トランザクションメッセージ内の製品リストを使用する前に、イベントレベルで、表示するリストの製品のリストと各製品のフィールドを定義する必要があります。 詳しくは、データコレクションの定 [義を参照してください](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. トランザクションメッセージで、ブロックをクリックし **[!UICONTROL Content]** て電子メールの内容を変更します。
1. 構造コンポーネントをワークスペースにドラッグ&amp;ドロップします。 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

   例えば、1列の構造コンポーネントを選択し、テキストコンポーネント、画像コンポーネント、ボタンコンポーネントを追加します。 詳しくは、フラグメントとコンポーネ [ントの追加を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 先ほど作成した構造コンポーネントを選択し、コンテキストツー **[!UICONTROL Enable product listing]** ルバーのアイコンをクリックします。

   ![](assets/message-center_loop_create.png)

   構造コンポーネントがオレンジ色のフレームでハイライトされ、 **[!UICONTROL Product listing]** 左側のパレットに設定が表示されます。

   ![](assets/message-center_loop_palette.png)

1. コレクションの要素の表示方法を選択します。

   * **[!UICONTROL Row]**:水平方向。つまり、一方の行の他方の行の各要素を意味します。
   * **[!UICONTROL Column]**:垂直方向（同じ行で隣接する各要素を意味）。
   >[!NOTE]
   >
   >このオ **[!UICONTROL Column]** プションは、複数列の構造コンポーネント（、および）を使 **[!UICONTROL 2:2 column]**&#x200B;用する場 **[!UICONTROL 3:3 column]** 合にのみ使 **[!UICONTROL 4:4 column]** 用できます。 製品リストを編集する場合は、最初の列にのみ入力します。他の列は考慮されません。 構造コンポーネントの選択について詳しくは、電子メール [構造の編集を参照してくださ](../../designing/using/designing-from-scratch.md#defining-the-email-structure)い。

1. データに関連するデータを設定する際に作成したイベント収集をトランザクションメッセージします。 これは、 > > **[!UICONTROL Context]** nodeの下にあ **[!UICONTROL Real-time event]** りま **[!UICONTROL Event context]** す。

   ![](assets/message-center_loop_selection.png)

   データコレクションの設定について詳しくは、イベントの定義を [参照してください](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. ドロップダウ **[!UICONTROL First item]** ンリストを使用して、電子メールに表示する開始をリストにする要素を選択します。

   例えば、「2」を選択した場合、コレクションの最初の項目は電子メールに表示されません。 製品リストは2番目の開始に対して表示されます。

1. アイテムに表示する最大アイテム数をリストします。

   >[!NOTE]
   >
   >リストの要素を垂直に表示する場合( **[!UICONTROL Column]** )、選択した構造コンポーネント（2列、3列、4列）に応じて、項目の最大数が制限されます。 構造コンポーネントの選択について詳しくは、電子メール [構造の編集を参照してくださ](../../designing/using/designing-from-scratch.md#defining-the-email-structure)い。

### 製品リストへの入力 {#populating-the-product-listing}

トランザクションの電子メールにリストされたイベントからの製品のリンクを表示するには、次の手順に従います。

コレクションの設定時にコレクションと関連フィールドを作成する方法について詳しくは、イベントコレクションの定 [義を参照してくださ](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)い。

1. 挿入したイメージコンポーネントを選択し、 **[!UICONTROL Enable personalization]** を選択して、設定ペインの鉛筆をクリックします。

   ![](assets/message-center_loop_image.png)

1. 開いた **[!UICONTROL Add personalization field]** ウィンドウ **[!UICONTROL Image source URL]** でを選択します。

   > **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** nodeで、作成したコレクションに対応するノード(ここ **[!UICONTROL Event context]** )を開き、定義した画像フィールド（ここ）を選択し **[!UICONTROL Product list]****[!UICONTROL Product image]** ます。 クリック **[!UICONTROL Save]** .

   ![](assets/message-center_loop_product-image.png)

   選択したパーソナライゼーションフィールドが設定ペインに表示されます。

1. 目的の位置で、コンテキストツール **[!UICONTROL Insert personalization field]** バーからを選択します。

   ![](assets/message-center_loop_product.png)

1. > **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** nodeで、作成したコレクションに対応するノード(ここ **[!UICONTROL Event context]** )を開き、作成したフィールド(ここ **[!UICONTROL Product list]****[!UICONTROL Product name]** )を選択します。 クリック **[!UICONTROL Confirm]** .

   ![](assets/message-center_loop_product_node.png)

   選択したパーソナライゼーションフィールドが、電子メールコンテンツ内の目的の位置に表示されます。

1. 同様にして価格を挿入します。
1. テキストを選択し、コンテキストツ **[!UICONTROL Insert link]** ールバーからを選択します。

   ![](assets/message-center_loop_link_insert.png)

1. 開いた **[!UICONTROL Add personalization field]** ウィンドウ **[!UICONTROL Insert link]** でを選択します。

   > **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** nodeで、作成したコレクションに対応するノード(ここ **[!UICONTROL Event context]** )を開き、作成したURLフィールド（ここ）を選択し **[!UICONTROL Product list]****[!UICONTROL Product URL]** ます。 クリック **[!UICONTROL Save]** .

   >[!IMPORTANT]
   >
   >セキュリティ上の理由から、パーソナライゼーションフィールドは、適切な静的ドメイン名で始まるリンク内に挿入してください。

   ![](assets/message-center_loop_link_select.png)

   選択したパーソナライゼーションフィールドが設定ペインに表示されます。

1. 製品リストを適用する構造コンポーネントを選択し、デフォルトコンテ **[!UICONTROL Show fallback]** ンツを定義する場合に選択します。

   ![](assets/message-center_loop_fallback_show.png)

1. 1つまたは複数のコンテンツコンポーネントをドラッグし、必要に応じて編集します。

   ![](assets/message-center_loop_fallback.png)

   イベントがトリガーされたときにコレクションが空の場合（例えば、顧客が買い物かごに何も入っていない場合）、フォールバックコンテンツが表示されます。

1. [設定]ペインで、製品リストのスタイルを編集します。 For more on this, see [Editing email styles](../../designing/using/styles.md).
1. 関連するトランザクションプロファイルにリンクされ、収集データを定義したテストイベントを使用して電子メールをプレビューします。 例えば、使用するテストプロファイルのセク **[!UICONTROL Event data]** ションに次の情報を追加します。

   ![](assets/message-center_loop_test-profile_payload.png)

   テストプロファイルの定義について詳しくは、この節を参 [照してください](#defining-a-test-profile-in-a-transactional-message)。

## テストトランザクションメッセージ {#testing-a-transactional-message}

保存したトランザクションメッセージをテストする配達確認を送信できます。

![](assets/message-center_10.png)

配達確認の送信手順の詳細は、「 [配達確認の送信](../../sending/using/sending-proofs.md) 」を参照。

## 公開，トランザクションメッセージ {#publishing-a-transactional-message}

チェックしたトランザクションメッセージは、公開できます。

![](assets/message-center_12.png)

現在は、「買い物かごの放棄」イベントがトリガーされるとすぐに、受信者のタイトルと姓、買い物かごのURL、最後に問い合わされた商品、または商品のリスト（商品リストを定義した場合）、送信される買い物かごの合計数を含むメッセージが自動的に表示されます。

ご使用のレポートにアクセスするには、トランザクションメッセージのボタンを使用 **[!UICONTROL Reports]** します。 レポートを参 [照してくださ](../../reporting/using/about-dynamic-reports.md)い。

![](assets/message-center_13.png)

## トランザクションメッセージ文書の停止 {#suspending-a-transactional-message-publication}

例えば、メッセージに含まれるトランザクションメッセージを変更す **[!UICONTROL Pause]** るためのボタンを使用して、メッセージの公開を中止することができます。 そのため、イベントは処理されず、代わりにデータベースのキューに保持されます。

キューに格納されたイベントは、REST API( [REST APIのドキュメントを参照](../../api/using/about-campaign-standard-apis.md))またはTriggersコアサービス(キャンペーンとExperience Cloud Triggersの操作を参照 [](../../integrating/using/about-adobe-experience-cloud-triggers.md))を使用している場合は、トリガーイベントで定義された期間中に保持されます。

![](assets/message-center_pause.png)

をクリックす **[!UICONTROL Resume]**&#x200B;ると、（期限切れでない限り）キューに格納されているイベントがすべて処理されます。 テンプレートの発行が停止された間に行われたすべての変更が含まれるようになりました。

## 公開の取り消しトランザクションメッセージ {#unpublishing-a-transactional-message}

をクリ **[!UICONTROL Unpublish]** ックすると、トランザクションメッセージのパブリケーションをキャンセルできますが、対応するイベントのパブリケーションもキャンセルできます。これにより、REST APIから、以前に作成したイベントに対応するリソースが削除されます。

![](assets/message-center_unpublish-template.png)

現在は、Webサイトを通じてイベントがトリガーされても、対応するメッセージは送信されず、データベースには保存されません。

>[!NOTE]
>
>メッセージを再度公開するには、対応するイベント設定に戻り、公開してから、メッセージを公開する必要があります。 詳しくは、公開を参照し [てください](#publishing-a-transactional-message)。

一時停止したトランザクションメッセージの公開を取り消す場合は、再度公開するまで24時間待たなければならない場合があります。 これは、キューに送信されたす **[!UICONTROL Database cleanup]** べてのイベントをワークフローで消去するためです。

メッセージを一時停止する手順について詳しくは、「メッセージの [発行を停止する](#suspending-a-transactional-message-publication) 」を参照してください。

毎日 **[!UICONTROL Database cleanup]** 午前4時に実行されるワークフローは、 > >からアクセ **[!UICONTROL Administration]** スで **[!UICONTROL Application settings]** きます **[!UICONTROL Workflows]**。

## 削除，トランザクションメッセージ {#deleting-a-transactional-message}

トランザクションメッセージが非公開になった場合、またはトランザクションメッセージがまだ公開されていない場合は、トランザクションメッセージリストから削除できます。 手順は次のとおりです。

1. 左上隅 **[!UICONTROL Adobe Campaign]** のロゴをクリックし、//を **[!UICONTROL Marketing plans]** 選択し **[!UICONTROL Transactional messages]** ます **[!UICONTROL Transactional messages]**。
1. 選択したメッセージにマウスを重ねます。
1. ボタンをクリッ **[!UICONTROL Delete element]** クします。

![](assets/message-center_delete-template.png)

ただし、トランザクションメッセージの削除は、次の特定の条件でのみ実行できます。

* トランザクションメッセージのステータスが **[!UICONTROL Draft]** あることを確認してください。そうしないと、削除できません。 ステータス **[!UICONTROL Draft]** は、まだ公開されていないメッセージ、または未公開である [(一時停止されていない](#unpublishing-a-transactional-message) )メッセージに [](#suspending-a-transactional-message-publication)適用されます。

* **トランザクションメッセージ**:別のトランザクションメッセージが対応するイベントにリンクされていない限り、トランザクションメッセージが非公開の場合は、イベントを正常に削除するために、トランザクションメッセージ設定も非公開にする必要があります。 詳しくは、非公開と公開を参 [照してください](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。

   >[!IMPORTANT]
   >
   >既に通知を送信したトランザクションメッセージを削除すると、その送信とトラッキングログも削除されます。

* **トランザクションメッセージテンプレート(内部トランザクションメッセージ)**:内部トランザクションメッセージが、対応する内部イベントに関連付けられた唯一のものである場合、削除できません。 最初に、複製するか、//トランザクションメッセージを使用して、別のメニューを作成 **[!UICONTROL Resources]** する必要 **[!UICONTROL Templates]** があ **[!UICONTROL Transactional message templates]** ります。

## トランザクションメッセージ再試行プロセス {#transactional-message-retry-process}

一時的に未配信のトランザクションメッセージは、その再試行が期限切れになるまで自動的に実行される配信の対象となります。 配信期間について詳しくは、有効期間パラメ [ーターを参照してくださ](../../administration/using/configuring-email-channel.md#validity-period-parameters)い。

トランザクションメッセージの送信に失敗した場合は、2つの再試行システムがあります。

* トランザクション・メッセージング・レベルでは、イベントが実行配信(イベント受信と配信準備の間)に割り当てられる前に、トランザクションメッセージが失敗する可能性があります。 詳しくは、 [イベント処理の再試行プロセスを参照してくださ](#event-processing-retry-process)い。
* 送信プロセスレベルでは、イベントが実行配信に割り当てられると、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。 詳しくは、メ [ッセージ送信の再試行プロセスを参照してくださ](#message-sending-retry-process)い。

### イベント処理の再試行プロセス {#event-processing-retry-process}

イベントを実行配信に割り当てられない場合、イベント処理は延期されます。 再試行は、新しい実行配信に割り当てられるまで実行されます。

>[!NOTE]
>
>延期されたイベントは、まだ実行トランザクションメッセージに割り当てられていないので、配信送信ログに表示されません。

例えば、イベントの内容が正しくない、アクセス権やブランドに問題があった、タイポロジルールの適用時にエラーが検出されたなど、実行配信にを割り当てることができませんでした。 この場合、メッセージを一時停止し、編集して問題を修正し、再度公開できます。 再試行システムは、その後、新しい実行システムに割り当てます。配信

### メッセージ送信の再試行プロセス {#message-sending-retry-process}

イベントが実行配信に割り当てられると、たとえば受信者のメールボックスがいっぱいになった場合、一時エラーが発生してトランザクションメッセージが失敗する可能性があります。 For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>イベントが実行配信に割り当てられると、その配信はこの実行の送信ログに表示され、この時点でのみ表示されます。 失敗した配信は、トランザクションメッセージのタブに表 **[!UICONTROL Execution list]** 示されます。

### 制限事項 {#limitations}

**ログの更新を送信しています**

再試行プロセスでは、新しい実行配信の送信ログは直ちに更新されません（更新はスケジュールされたワークフローを通じて実行されます）。 つまり、トランザクションイベントが新しい実行 **[!UICONTROL Pending]** 配信で処理された場合でも、メッセージがステータスになる可能性があります。

**失敗した実行配信**

実行配信を停止 ただし、現在の実行配信が失敗した場合、新しいイベントを受け取るとすぐに新しいイベントが作成され、新しい配信はすべてこの新しい実行イベントで処理されます。 新しいイベントは、失敗した実行によって処理されません。配信

既に実行配信に割り当てられているイベントの一部が延期され、その実行配信に失敗した場合、再試行システムは、延期されたイベントを新しい実行配信に割り当てません。つまり、これらのイベントは失われます。
