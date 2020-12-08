---
solution: Campaign Standard
product: campaign
title: イベントトランザクションメッセージ
description: イベントトランザクションメッセージを作成して公開する方法について説明します。
page-status-flag: never-activated
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: caa41d6c727385bd6e77f64750872f191a5ad040
workflow-type: tm+mt
source-wordcount: '1488'
ht-degree: 60%

---


# トランザクションメッセージの編集{#editing-transactional-message}

イベント<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->を作成して公開すると、対応するトランザクションメッセージが自動的に作成されます。

イベントを設定および公開する手順は、「[トランザクションイベントの設定](../../channels/using/configuring-transactional-event.md)」および「[トランザクションイベントの公開](../../channels/using/publishing-transactional-event.md)」に記載されています。

このメッセージにアクセス、編集、パーソナライズする手順を以下に説明します。

>[!IMPORTANT]
>
>[管理](../../administration/using/users-management.md#functional-administrators)ロールを持つユーザーのみが、トランザクションメッセージにアクセスして編集できます。

メッセージの準備が整ったら、テストおよび発行が可能です。 [トランザクションメッセージ](../../channels/using/testing-transactional-message.md)と[トランザクションメッセージライフサイクル](../../channels/using/publishing-transactional-message.md)のテストを参照してください。

## トランザクションメッセージへのアクセス{#accessing-transactional-messages}

作成したトランザクションメッセージにアクセスするには：

1. 左上隅の&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;ロゴをクリックします。
1. **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**&#x200B;を選択します。

   ![](assets/message-center_4.png)

1. 編集するには、選択したメッセージをクリックします。

   ![](assets/message-center_message-board.png)

また、対応するイベント設定画面の左側の領域にあるリンクからトランザクションメッセージに直接アクセスすることもできます。 [イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照

## トランザクションメッセージのパーソナライズ機能{#personalizing-a-transactional-message}

トランザクションメッセージを編集してパーソナライズするには、次の手順に従います。

>[!NOTE]
>
>この節では、**イベントベースの**&#x200B;トランザクションメッセージを編集する方法を説明します。 **プロファイルベースの**&#x200B;トランザクションメッセージの特殊性は、[](#profile-transactional-message-specificities)の下に詳細に記載されています。
>
>イベントベースのトランザクションメッセージを作成するための設定手順は、[このセクション](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)に記載されています。

例えば、製品を買い物かごに追加し、購入を経ることなくサイトを離れたWebサイトユーザーに通知を送信するとします。 この例は、[トランザクションメッセージングの動作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)の節に示されています。

1. 「**[!UICONTROL Content]**」ブロックをクリックして、メッセージの件名と内容を変更します。この例では、画像とテキストを含む任意のテンプレートを選択します。電子メールコンテンツテンプレートについて詳しくは、[テンプレートを使用した電子メールのデザイン](../../designing/using/using-reusable-content.md#designing-templates)を参照してください。

   ![](assets/message-center_6.png)

1. 件名追加を入力し、必要に応じてメッセージの内容を編集します。

   >[!NOTE]
   >
   >放棄された買い物かごへのリンクは、ユーザーを買い物かごにリダイレクトする外部 URL へのリンクです。このパラメーターは、Adobe Campaign では管理されません。

1. この例では、[イベントの作成時](../../channels/using/configuring-transactional-event.md)に定義した、次の 3 つのフィールドを追加します。最初の名前、最後に問い合わせた製品、買い物かごの総数。これをおこなうには、メッセージコンテンツに[パーソナライゼーションフィールド](../../designing/using/personalization.md#inserting-a-personalization-field)を挿入します。

1. **[!UICONTROL Context]**／**[!UICONTROL Real-time event]**／**[!UICONTROL Event context]** を順に選択して、該当するフィールドを表示します。

   ![](assets/message-center_7.png)

1. メッセージの内容を拡張することもできます。 これを行うには、イベント設定にリンクしたテーブルからフィールドを追加します(「[イベントの強化](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)」を参照)。 この例では、**[!UICONTROL Profile]**&#x200B;テーブルから&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**&#x200B;までの&#x200B;**[!UICONTROL Title (salutation)]**&#x200B;フィールドを選択します。

   ![](assets/message-center_7-enrichment.png)

1. 必要なフィールドをすべて挿入します。

   ![](assets/message-center_8.png)

1. このイベント用に定義したプロファイルを選択して、メッセージをプレビューします。

   メッセージをプレビューする手順について詳しくは、[メッセージのプレビュー](../../sending/using/previewing-messages.md)の節を参照してください。

   ![](assets/message-center_9.png)

   パーソナライゼーションフィールドがテストプロファイルに入力された情報と一致しているかどうかを確認できます。詳しくは、[特定のテストプロファイルの定義](../../channels/using/testing-transactional-message.md#defining-specific-test-profile)を参照してください。

## トランザクションメッセージでの製品リストの使用{#using-product-listings-in-a-transactional-message}

トランザクション用の電子メールのコンテンツを編集する場合、1つ以上のデータコレクションを参照する製品リストを作成できます。 例えば、買い物かごの放棄の電子メールでは、ユーザがWebサイトを離れたときに買い物かごに含まれていたすべての商品のリストを、画像、価格、各商品へのリンクと共に含めることができます。

>[!IMPORTANT]
>
>製品リストは、[電子メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)インターフェイスを通じてトランザクション電子メールコンテンツを編集する場合に、電子メールチャネルでのみ使用できます。

トランザクションメッセージに放棄された製品のリストを追加するには、次の手順に従います。

また、[この一連のビデオ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails)を見て、トランザクション用電子メールでの製品リストの設定に必要な手順を説明することもできます。

>[!NOTE]
>
>Adobe Campaign は入れ子になった製品リストをサポートしていません。つまり、別の製品リストに製品を含めることはできません。

### 製品リストの定義{#defining-a-product-listing}

トランザクションメッセージ内の製品リストを使用する前に、表示するリストの各製品のリストとフィールドをイベントレベルで定義する必要があります。詳しくは、[データコレクションの定義](../../channels/using/configuring-transactional-event.md#defining-data-collections)を参照してください。

1. トランザクションメッセージで、「**[!UICONTROL Content]**」ブロックをクリックしてメールの内容を変更します。
1. 構造コンポーネントをワークスペースにドラッグ＆ドロップします。詳しくは、[電子メール構造の定義](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。

   例えば、1 列の構造コンポーネントを選択し、テキストコンポーネント、画像コンポーネント、ボタンコンポーネントを追加します。詳しくは、[コンテンツコンポーネントの使用](../../designing/using/designing-from-scratch.md#about-content-components)を参照してください。

1. 先ほど作成した構造コンポーネントを選択し、コンテキストツールバーの「**[!UICONTROL Enable product listing]**」アイコンをクリックします。

   ![](assets/message-center_loop_create.png)

   構造コンポーネントはオレンジ色のフレームでハイライト表示され、「**[!UICONTROL Product listing]**」設定は左側のパレットに表示されます。

   ![](assets/message-center_loop_palette.png)

1. コレクションの要素の表示方法を選択します。

   * **[!UICONTROL Row]**：水平方向とは、他の行の下の各要素を意味します。
   * **[!UICONTROL Column]**：垂直方向とは、同じ行で各要素が隣り合っていることを意味します。

   >[!NOTE]
   >
   >この **[!UICONTROL Column]** オプションは、複数列の構造コンポーネント（**[!UICONTROL 2:2 column]**、**[!UICONTROL 3:3 column]** および **[!UICONTROL 4:4 column]**）を使用する場合にのみ使用できます。製品リストを編集する場合は、最初の列にのみ入力します。他の列は考慮されません。構造コンポーネントの選択について詳しくは、[電子メール構造の定義](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。

1. トランザクションメッセージに関連するイベントを設定する際に作成したデータ収集を選択します。これは、**[!UICONTROL Context]**／**[!UICONTROL Real-time event]**／**[!UICONTROL Event context]** ノードの下にあります。

   ![](assets/message-center_loop_selection.png)

   イベントの設定について詳しくは、[データコレクションの定義](../../channels/using/configuring-transactional-event.md#defining-data-collections)を参照してください。

1. 「**[!UICONTROL First item]**」ドロップダウンリストを使用して、メールに表示されるリストを開始する要素を選択します。

   例えば、「2」を選択した場合、コレクションの最初のアイテムはメールに表示されません。2 つ目のアイテムは製品リストに開始されます。

1. リストに表示するアイテムの最大数を選択します。

   >[!NOTE]
   >
   >リストの要素を垂直に表示する場合（**[!UICONTROL Column]**）は、選択した構造コンポーネント（2、3、4 列）に応じて、アイテムの最大数が制限されます。構造コンポーネントの選択について詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。

### 製品リストへの入力{#populating-the-product-listing}

トランザクションメールにリンクされたイベントからの製品のリストを表示するには、次の手順に従います。

コレクションの設定時に、イベントおよび関連するフィールドを作成する方法について詳しくは、[データコレクションの定義](../../channels/using/configuring-transactional-event.md#defining-data-collections)を参照してください。

1. 挿入したイメージコンポーネントを選択し、「**[!UICONTROL Enable personalization]**」を選択して設定パネルで鉛筆をクリックします。

   ![](assets/message-center_loop_image.png)

1. 開いた「**[!UICONTROL Image source URL]**」ウィンドウで「**[!UICONTROL Add personalization field]**」を選択します。

   **[!UICONTROL Context]**／**[!UICONTROL Real-time event]**／**[!UICONTROL Event context]** ノードで、作成したコレクションに対応するノード（ここでは **[!UICONTROL Product list]**）を開き、定義した画像フィールド（ここでは **[!UICONTROL Product image]**）を選択します。「**[!UICONTROL Save]**」をクリックします。

   ![](assets/message-center_loop_product-image.png)

   選択したパーソナライゼーションフィールドが設定ペインに表示されます。

1. 目的の位置で、コンテキストツールバーから「**[!UICONTROL Insert personalization field]**」を選択します。

   ![](assets/message-center_loop_product.png)

1. **[!UICONTROL Context]**／**[!UICONTROL Real-time event]**／**[!UICONTROL Event context]** ノードで、作成したコレクションに対応するノード（ここでは **[!UICONTROL Product list]**）を開き、作成したフィールド（ここでは **[!UICONTROL Product name]**）を選択します。「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/message-center_loop_product_node.png)

   選択したパーソナライゼーションフィールドがメールコンテンツ内の目的の位置に表示されます。

1. 価格を挿入する場合と同様におこないます。
1. テキストを選択し、コンテキストツールバーから「**[!UICONTROL Insert link]**」を選択します。

   ![](assets/message-center_loop_link_insert.png)

1. 開いた「**[!UICONTROL Insert link]**」ウィンドウで「**[!UICONTROL Add personalization field]**」を選択します。

   **[!UICONTROL Context]**／**[!UICONTROL Real-time event]**／**[!UICONTROL Event context]** ノードで、作成したコレクションに対応するノード（ここでは **[!UICONTROL Product list]**）を開き、作成した URL フィールド（ここでは **[!UICONTROL Product URL]**）を選択します。「**[!UICONTROL Save]**」をクリックします。

   >[!IMPORTANT]
   >
   >セキュリティ上の理由から、適切な静的ドメイン名で始まるリンク内にパーソナライゼーションフィールドを挿入してください。

   ![](assets/message-center_loop_link_select.png)

   選択したパーソナライゼーションフィールドが設定ペインに表示されます。

1. 製品リストを適用する構造コンポーネントを選択し、デフォルトコンテンツを定義する場合に「**[!UICONTROL Show fallback]**」を選択します。

   ![](assets/message-center_loop_fallback_show.png)

1. 1 つまたは複数のコンテンツコンポーネントをドラッグし、必要に応じて編集します。

   ![](assets/message-center_loop_fallback.png)

   顧客が買い物かごに何も入れていない場合など、イベントがトリガーされたときにコレクションが空の場合、フォールバックのコンテンツが表示されます。

1. 設定ペインで、製品リストのスタイルを編集します。詳しくは、[電子メールスタイルの管理](../../designing/using/styles.md)を参照してください。
1. 関連するトランザクションイベントにリンクされ、収集データを定義したテストプロファイルを使用して、メールをプレビューします。例えば、使用するテストプロファイルの「**[!UICONTROL Event data]**」セクションに次の情報を追加します。

   ![](assets/message-center_loop_test-profile_payload.png)

   トランザクションメッセージでのテストプロファイルの定義について詳しくは、[この節](../../channels/using/testing-transactional-message.md#defining-specific-test-profile)を参照してください。

## プロファイルベースのトランザクションメッセージの特殊性{#profile-transactional-message-specificities}

顧客マーケティングプロファイルに基づいてトランザクションメッセージを送信できます。プロファイル情報をすべて活用して、メッセージコンテンツをパーソナライズし、購読解除リンクを使用して、[疲労ルール](../../sending/using/fatigue-rules.md)などのマーケティングタイポロジルールを適用できます。

* イベントベースのトランザクションメッセージとプロファイルベースのの違いについて詳しくは、[このセクション](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)を参照してください。

* プロファイルベースのトランザクションメッセージを作成するための設定手順については、[このセクション](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)で詳しく説明します。

<!--### Editing a profile transactional message {#editing-profile-transactional-message}-->

プロファイルトランザクションメッセージの作成、編集および個人設定の手順は、ほとんどイベントトランザクションメッセージの場合と同じです。

相違点を次に示します。

1. [作成したトランザクションメッセージに移動して編集します。](#accessing-transactional-messages)
1. トランザクションメッセージで、「**[!UICONTROL Content]**」セクションをクリックします。トランザクション電子メールテンプレートに加えて、**[!UICONTROL Profile]**&#x200B;リソースをターゲットとする任意の電子メールテンプレートを選択することもできます。

   ![](assets/message-center_marketing_templates.png)

1. デフォルトの E メールテンプレートを選択します。すべてのマーケティング電子メールと同様、**購読解除リンク**&#x200B;が含まれます。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   テンプレートの詳細については、[このセクション](../../designing/using/using-reusable-content.md#content-templates)を参照してください。

1. また、リアルタイムイベントに基づく設定とは異なり、**すべてのプロファイル情報**&#x200B;に直接アクセスして、メッセージをパーソナライズできます。 他の標準的なマーケティング用電子メールと同様に、[パーソナライゼーションフィールド](../../designing/using/personalization.md#inserting-a-personalization-field)を追加できます。

1. メッセージを発行する前に、変更を保存します。 詳しくは、[トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。

<!--### Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

Once the message is published and your site integration is done, you can monitor the delivery.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

1. Click the **[!UICONTROL Execution list]** tab.

   ![](assets/message-center_execution_tab.png)

1. Select the latest execution delivery.

   An **execution delivery** is a non-actionable and non-functional technical message created once a month for each transactional message, and each time a transactional message is edited and published again

1. Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

>[!NOTE]
>
>For more information on accessing and using the logs, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

For any profile that has opted out, the **[!UICONTROL Address on denylist]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Related topics**:

* [Integrate the event triggering](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)
* [About typologies and typology rules](../../sending/using/about-typology-rules.md)-->
