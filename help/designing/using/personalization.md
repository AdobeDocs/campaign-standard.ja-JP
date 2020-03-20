---
title: 電子メールコンテンツのパーソナライズ
description: 電子メールデザイナで電子メールをパーソナライズする方法を確認します。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---


# 電子メールコンテンツのパーソナライズ {#personalization}

Adobe Campaignが配信するメッセージの内容と表示は、様々な方法でパーソナライズできます。 これらの方法は、プロファイルに応じて、条件に従って組み合わせることができます。 Adobe Campaign には、全体として次のようなパーソナライゼーション機能が備わっています。

* パーソナライゼーションフィールドの動的な挿入：See [Inserting a personalization field](#inserting-a-personalization-field).
* 定義済みパーソナライゼーションブロックの挿入：詳しくは、コ [ンテンツブロックの追加を参照してくださ](#adding-a-content-block)い。
* 電子メールの送信者をパーソナライズします。 詳しくは、送 [信者の個人設定を参照してくださ](#personalizing-the-sender)い。
* 電子メールの件名をパーソナライズします。 See [Personalizing the subject line of an email](../../designing/using/subject-line.md#subject-line).
* 条件付きコンテンツの作成：詳しくは、電 [子メール内の動的コンテンツの定義を参照してくださ](#defining-dynamic-content-in-an-email)い。

## 送信者の個人設定 {#personalizing-the-sender}

送信するメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナーのホームページのタブに移動します( **[!UICONTROL Properties]** ホームアイコンからアクセスできます)。 詳しくは、「電子メールの送 [信者の定義」を参照してください](../../designing/using/subject-line.md#email-sender)。

送信者名は、[送信者名]ブロックをクリックし **て変更できます** 。 フィールドが編集可能になり、使用する名前を入力できます。

このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

## URLのパーソナライズ{#personalizing-urls}

Adobe Campaignを使用すると、パーソナライゼーションフィールド、コンテンツブロックまたは動的コンテンツをメッセージに追加して、1つまたは複数のURLをパーソナライズできます。 手順は次のとおりです。

1. 外部URLを挿入し、そのパラメーターを指定します。 詳しくは、 [リンクの挿入を参照してくださ](../../designing/using/links.md#inserting-a-link)い。
1. 表示されない場合は、設定パネルで選択したURLの横にある鉛筆をクリックして、パーソナライゼーションオプションにアクセスします。
1. 使用するパーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

   ![](assets/des_personalize_links.png)

1. 変更を保存します。

>[!NOTE]
>
>パーソナライズするURLは、ドメイン名やURL拡張子に適用できません。 パーソナライゼーションが正しくない場合、メッセージ分析中にエラーメッセージが表示されます。 コンテンツブロックを選択する場合、「ミラーページにリンク」などの要素を選 **択することはできません**。 このタイプのブロックは、リンク内では禁止されています。

## パーソナライゼーションフィールドの挿入{#inserting-a-personalization-field}

Adobe Campaignでは、データベースのフィールド（プロファイルの名など）をページに挿入できます。

>[!NOTE]
>
>次の画像は、電子メール用に電子メールデザイナーを使用してパーソナライゼーションフィ [ールドを挿入する](../../designing/using/designing-content-in-adobe-campaign.md) 方法を示しています。

コンテンツにパーソナライゼーションフィールドを追加するには：

1. テキストブロック内をクリックし、コンテキストツ **[!UICONTROL Personalize]** ールバーのアイコンをクリックしてを選択しま **[!UICONTROL Insert personalization field]**&#x200B;す。 電子メールデザイナーのインターフェイスについて詳しくは、この節を [参照してくださ](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)い。

   ![](assets/email_perso_field_1.png)

1. ページのコンテンツに挿入するフィールドを選択します。

   ![](assets/email_perso_field_2.png)

1. クリック **[!UICONTROL Confirm]**.

フィールド名がエディターに表示され、ハイライト表示されます。

![](assets/email_perso_field_3.png)

パーソナライゼーションが生成され（例えば、電子メールをプレビューし、準備する場合）、このフィールドはターゲットプロファイルに対応する値に置き換えられます。

>[!NOTE]
>
>電子メールがワークフローから作成された場合は、ワークフローで計算された追加のデータもパーソナライゼーションフィールドで使用できます。 ワークフローから追加のデータを追加する方法について詳しくは、データの強化の節を参 [照してくだ](../../automating/using/targeting-data.md#enriching-data) さい。

## コンテンツブロックの追加{#adding-a-content-block}

Adobe Campaignには、事前設定済みのコンテンツブロックのリストが用意されています。 これらのコンテンツブロックは動的でパーソナライズされ、特定のレンダリングを持ちます。 例えば、ミラーページに挨拶やリンクを追加できます。

>[!NOTE]
>
>次の画像は、電子メール用に電子メールデザイナを使用してコンテンツブロ [ックを挿入する](../../designing/using/designing-content-in-adobe-campaign.md) 方法を示しています。

コンテンツブロックを追加するには：

1. テキストブロック内をクリックし、コンテキストツ **[!UICONTROL Personalize]** ールバーのアイコンをクリックしてを選択しま **[!UICONTROL Insert content block]**&#x200B;す。 電子メールデザイナーのインターフェイスについて詳しくは、この節を [参照してくださ](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)い。

   ![](assets/email_content_block_1.png)

1. 挿入するコンテンツブロックを選択します。 使用できるブロックは、コンテキスト（電子メールまたはランディングページ）によって異なります。

   ![](assets/email_content_block_2.png)

1. クリック **[!UICONTROL Save]**.

コンテンツブロックの名前がエディタに表示され、黄色でハイライト表示されます。 パーソナライゼーションが生成されると、自動的にプロファイルに適合します。

![](assets/email_content_block_3.png)

標準搭載のコンテンツブロックは次のとおりです。

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Link to mirror page (MirrorPage)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**:このコンテンツブロックはランディングページでのみ使 **用できます**。
* **[!UICONTROL Default sender name (DefaultSenderName)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### カスタムコンテンツブロックの作成 {#creating-custom-content-blocks}

メッセージまたはランディングページに挿入される新しいコンテンツブロックを定義できます。

コンテンツブロックを作成するには、次の手順に従います。

1. コンテン **[!UICONTROL Resources > Content blocks]** ツブロックのリストにアクセスするには、詳細メニューのをクリックします。
1. ボタンをクリッ **[!UICONTROL Create]** クするか、既存のコンテンツブロックを複製します。

   ![](assets/content_bloc_01.png)

1. ラベルを入力します。
1. ブロックのを選択しま **[!UICONTROL Content type]**&#x200B;す。 次の3つのオプションを使用できます。

   * **[!UICONTROL Shared]**:コンテンツブロックは、配信またはランディングページで使用できます。
   * **[!UICONTROL Delivery]**:コンテンツブロックは、配信でのみ使用できます。
   * **[!UICONTROL Landing page]**:コンテンツブロックはランディングページでのみ使用できます。
   ![](assets/content_bloc_02.png)

1. を選択できます **[!UICONTROL Targeting dimension]**。 For more on this, see [About targeting dimension](#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. 次の2つの異なるブロックを定 **[!UICONTROL Depends on format]** 義するオプションを選択できます。1つはHTML電子メール用、もう1つはテキスト形式の電子メール用です。 エディター（HTMLとテキスト）に2つのタブが表示され、対応するコンテンツが定義されます。

   ![](assets/content_bloc_03.png)

1. コンテンツブロックのコンテンツを入力し、ボタンをクリックし **[!UICONTROL Create]** ます。

メッセージやランディングページのコンテンツエディターでコンテンツブロックを使用できるようになりました。

>[!CAUTION]
>
>ブロックのコンテンツを編集する場合は、ifステートメントの先頭と末尾の間に余分な空白がないことを確認 *しま* す。 HTMLでは、空白が画面に表示されるので、コンテンツのレイアウトに影響します。

### ターゲットディメンションについて {#about-targeting-dimension}

ターゲットディメンションを使用すると、コンテンツブロックを使用できるメッセージのタイプを定義できます。 これは、エラーを引き起こす可能性のある、メッセージ内の不適切なブロックを使用しないようにするためです。

実際、メッセージを編集する場合は、そのメッセージのターゲットディメンションと互換性のあるターゲットディメンションを持つコンテンツブロックのみを選択できます。

例えば、ブロックのターゲ **[!UICONTROL Unsubscription link]** ットディメンションは、リソ **[!UICONTROL Profiles]** ースに固有のパーソナライゼーションフィールドが含まれているた **[!UICONTROL Profiles]** めです。 したがって、イベントトランザクション **[!UICONTROL Unsubscription link]** メッセージでブ [ロックを使用することはできません](../../channels/using/event-transactional-messages.md)。これは、そのタイプのメッセージのターゲットディメンションがであるためです **[!UICONTROL Real-time events]**。 ただし、そのタイプのメッセージのターゲ **ットディメンションは** Profilesであるので、 [Unsubscriptionリンクブロックをプロファイルトランザクションメッセージで使用することがで](../../channels/using/profile-transactional-messages.md)きます ****。 最後に、ブロッ **[!UICONTROL Link to mirror page]** クにターゲットディメンションがないので、任意のメッセージで使用できます。

このフィールドを空のままにすると、ターゲットディメンションが何であっても、コンテンツブロックはすべてのメッセージと互換性があります。 ターゲットディメンションを設定した場合、そのブロックは、同じターゲットディメンションを持つメッセージとのみ互換性があります。

詳しくは、ディメンションとリソースのターゲ [ット設定を参照してください](../../automating/using/query.md#targeting-dimensions-and-resources)。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](#inserting-a-personalization-field)
* [コンテンツブロックの追加](#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](#defining-dynamic-content-in-an-email)

## 画像ソースのパーソナライズ{#personalizing-an-image-source}

Adobe Campaignを使用すると、特定の条件に従ってメッセージ内の1つまたは複数の画像をパーソナライズしたり、追跡を使用したりできます。 これは、パーソナライゼーションフィールド、コンテンツブロックまたは動的コンテンツを画像ソースに挿入することで行います。 手順は次のとおりです。

1. メッセージの内容に画像を挿入するか、既に存在する画像を選択します。
1. 画像プロパティパレットで、オプションをオンに **[!UICONTROL Enable personalization]** します。

   ![](assets/des_personalize_images_1.png)

   フィー **[!UICONTROL Source]** ルドが表示され、選択した画像がパーソナライズされた画 **像として** 、エディターに表示されます。

1. フィールドボタンの横にある鉛筆をクリッ **[!UICONTROL Source]** クして、パーソナライゼーションオプションを表示します。
1. 画像ソースを追加したら、好みのパーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >ドメイン名(http://mydomain.com)をパーソナライズできないので、手動で入力する必要があります。 残りのURLはパーソナライズできます。 例：http://mydomain.com/`[Gender]`.jpg

1. 変更を確認します。

## 条件付きコンテンツ {#conditional-content}

### 表示条件の定義{#defining-a-visibility-condition}

任意の要素に対して表示条件を指定できます。 条件が考慮された場合にのみ表示されます。

表示条件を追加するには、ブロックを選択し、設定のフィールドに考慮する **[!UICONTROL Visibility condition]** 条件を入力します。

![](assets/delivery_content_5.png)

このオプションは、次の要素でのみ使用できます。住所、BLOCKQUOTE、CENTER、DIR、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

式エディターは、「式の詳細編集」セ [クションに表示されます](../../automating/using/editing-queries.md#about-query-editor) 。

これらの条件はXTK式の構文(例： **context.profile.email !=&quot;** ま **たはcontext.profile.status=&#39;0&#39;**)。 デフォルトでは、すべてのファイルが表示されます。

>[!NOTE]
>
>動的コンテンツを含むサブ要素を既に含むブロック、または既に動的コンテンツを構成するブロックに対しては、条件を定義できません。 コンボボックスのような非表示のダイナミックブロックは編集できません。

### 電子メールでの動的コンテンツの定義{#defining-dynamic-content-in-an-email}

電子メールでは、式エディターで定義した条件に従って、受信者に動的に表示される様々なコンテンツを定義できます。 例えば、同じ電子メールから、年齢の範囲に応じて各プロファイルが異なるメッセージを受け取るようにできます。

動的コンテンツの定義は、表示条件の [定義とは異なります](#defining-a-visibility-condition)。

1. フラグメント、コンポーネントまたは要素を選択します。 この例では、画像を選択します。
1. コンテキストツ **[!UICONTROL Dynamic content]** ールバーのアイコンをクリックします。

   ![](assets/dynamic_content_2.png)

   左側の **[!UICONTROL Dynamic content]** パレットにセクションが表示されます。

   ![](assets/dynamic_content_3.png)

   デフォルトでは、このセクションには2つの要素が含まれています。デフォルトのバリアントおよび新しいバリアント。

   >[!NOTE]
   >
   >コンテンツには常にデフォルトのバリアントが含まれている必要があります。 削除することはできません。

1. ボタンをクリ **[!UICONTROL Edit]** ックして、最初の代替バリアントの表示条件を定義します。

   ![](assets/dynamic_content_4.png)

1. ラベルを指定し、条件として設定するフィールドを選択します。 例えば、ノードから **[!UICONTROL General]** フィールドを選択し **[!UICONTROL Age]** ます

   ![](assets/dynamic_content_5.png)

1. フィルタリング条件を設定します。 例えば、18歳から25歳の間の訪問者に異なるコンテンツを表示するとします。

   ![](assets/dynamic_content_6.png)

1. すべての条件を設定したら、条件を適用する優先順位を定義し、変更を保存します。

   ![](assets/dynamic_content_7.png)

   コンテンツは、上から下の順にパレットに表示されます。 For more on priorities, refer to [this section](#defining-dynamic-content-in-an-email).

1. 先ほど定義したバリアントの新しい画像をアップロードします。

   ![](assets/dynamic_content_8.png)

   18歳から25歳の受信者に新しい画像が表示されます。

   ![](assets/dynamic_content_10.png)

1. をクリック **[!UICONTROL Add a condition]** して、新しいコンテンツとそのリンクされたルールを追加します。

   ![](assets/dynamic_content_9.png)

   例えば、26歳から35歳の間の年齢の人に表示する別の画像を追加できます。

1. 動的に表示する電子メールの他の要素についても同様に続行します。 テキスト、ボタン、フラグメントなどがあります。 変更を保存します。

>[!CAUTION]
>
>メッセージの準備が整ったら、送信する前に、証明を使用してテストします。 この操作を行わないと、一部のエラーが検出されず、電子メールが送信されない場合があります。

**関連トピック：**

* [配達確認の送信](../../sending/using/sending-proofs.md)
* [高度な式の編集](../../automating/using/editing-queries.md#about-query-editor)

### 優先順位 {#order-of-priority}

エクスプレッションエディターで動的コンテンツを定義する場合の優先順位は次のとおりです。

1. 例えば、2つの異なる条件で2つの異なる動 **的コンテンツを定義し**、次のようにします。

   **条件1:** プロフィールの性別は男性的だ

   **条件2:** プロフィールは20歳から30歳の間。

   ![](assets/delivery_content_61.png)

   データベース内の一部のプロファイルは、2つの条件に対応していますが、1つの動的コンテンツを持つ1つの電子メールのみ送信できます。

1. したがって、動的コンテンツの優先順位を定義する必要があります。 優先度が **1** （したがって、対応する動的コンテンツ）の条件は、優先度が **2** または **** 3の別の条件がこのプロファイルで満たされた場合でも、プロファイルに送信されます。

   ![](assets/delivery_content_62.png)

動的コンテンツごとに定義できる優先順位は1つだけです。

## 例：電子メールのパーソナライゼーション{#example-email-personalization}

この例では、マーケティングサービスチームのメンバーが、顧客に対してのみ特別なオファーがあることを顧客に通知する電子メールを作成しています。 チームのメンバーは、顧客のそれぞれの年齢に応じて電子メールをパーソナライズすることを決定しました。 18歳から27歳のクライアントには、異なる画像と27歳より前のクライアントが受け取るスローガンを含む電子メールが届きます。

電子メールは次のように作成されます。

* 動的コンテンツを画像に適用し、これら動的コンテンツを年齢範囲に応じて構成する。

   ![](assets/delivery_content_43.png)

   動的コンテンツの追加と設定について詳しくは、「電子メ [ールでの動的コンテンツの定義](#defining-dynamic-content-in-an-email) 」の節を参照してください。

* パーソナライゼーションフィールドと動的コンテンツがテキストに適用されます。 プロファイルの年齢の範囲に応じて、電子メールはプロファイルの名、またはプロファイルのタイトルと姓で始まります。

   ![](assets/delivery_content_44.png)

   パーソナライゼーションフィールドの追加と設定について詳しくは、「パーソナライゼ [ーションフィールドの挿入](#inserting-a-personalization-field) 」の節を参照してください。

### 画像の設定 {#configuring-images}

この例では、画像に適用される動的コンテンツは次のように設定されます。

**18～27歳をターゲットにするには：**

1. パレットで動的コンテンツを選択 **[!UICONTROL Properties]** し、ボタンをクリック **[!UICONTROL Edit]** します。

   ![](assets/delivery_content_48.png)

1. ラベルを編集し、ノードからフ **[!UICONTROL Age]** ィールドを選択 **[!UICONTROL Profile]** します。

   ![](assets/delivery_content_49.png)

1. 「次の値よ **り大きいか等しい** 」演算子を選択し、 **18** と入力して18より **古い式を作成します** 。

   ![](assets/delivery_content_50.png)

1. 新しい条件を追加 **[!UICONTROL Age]** します。

   「次より小 **さいか等しい** 」演算子を選択し、「27」より小さい数値を「値」フィールドで27 **と入力します** 。

   ![](assets/delivery_content_51.png)

1. 変更を確認します。

**27歳以上のプロファイルをターゲットにするには：**

1. パレットから動的コンテンツを選択し、編集します。
1. ラベルを編集し、ノードからフ **[!UICONTROL Age]** ィールドを選択 **[!UICONTROL Profile]** します。
1. 27より古い **式を作成するには** 、次に27を加えた後に「次の値より大きい **」演算子を値フィールド** に追加します。

   ![](assets/delivery_content_52.png)

1. 変更を確認します。

動的なコンテンツが正しく設定されている。

### テキストの設定 {#configuring-text}

この例では、テキストに適用される動的コンテンツは次のように設定されます。

**18 ～ 27才のプロファイルをターゲットにするには：**

1. 必要な構造コンポーネントを選択し、動的コンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット式を設定します。 詳しくは、画像の設 [定を参照してくださ](#configuring-images)い。
1. 構造コンポーネントで、目的の位置にあるコンテキストツールバ **[!UICONTROL Personalize]** ーのアイコンをクリックし、を選択しま **[!UICONTROL Insert personalization field]**&#x200B;す。

   ![](assets/delivery_content_53.png)

1. 表示されるリストで、フィールドを選択し **[!UICONTROL First name]** て確認します。

   ![](assets/delivery_content_54.png)

1. その後、選択した動的コンテンツにパーソナライゼーションフィールドが完全に挿入されます。

**27歳以上のプロファイルをターゲットにするには：**

1. 必要な構造コンポーネントを選択し、動的コンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット式を設定します。 詳しくは、画像の設 [定を参照してくださ](#configuring-images)い。
1. 構造コンポーネントで、目的の位置にあるコンテキストツールバ **[!UICONTROL Personalize]** ーのアイコンをクリックし、を選択しま **[!UICONTROL Insert personalization field]**&#x200B;す。
1. ドロッ **[!UICONTROL Title]** プダウンリストから選択します。
1. 同様にフィールドを追加 **[!UICONTROL Last name]** します。

   ![](assets/delivery_content_56.png)

これで、パーソナライゼーションフィールドが、選択した動的コンテンツに完全に挿入されます。

### 電子メールのプレビュー {#previewing-emails}

プレビューを使用すると、パーソナライゼーションフィールドと動的コンテンツが正しく設定されていることを確認してから、を送信できま **[!UICONTROL Proofs]**&#x200B;す。 プレビュー時に、電子メールターゲットに対応する様々なテストプロファイルを選択できます。

テストプロファイルがない場合、デフォルトで表示される電子メールは次のとおりです。

![](assets/delivery_content_45.png)

電子メールにはスローガン内にパーソナライゼーションフィールドがなく、デフォルトの画像が使用されます。

最初のテストプロファイルは、18歳から27歳のクライアントに対応します。 このプロファイルを選択すると、次の電子メールが表示されます。

![](assets/delivery_content_46.png)

18 ～ 27年の式（特にプロファイルの名）に対応するパーソナライゼーションフィールドが正しく設定され、プロファイルに従って画像も変更されました。

2つ目のプロファイルは27歳以上のクライアントに対応し、次の電子メールを生成します。

![](assets/delivery_content_47.png)

動的なコンテンツのおかげで画像が変わり、表示されるスローガンが、このターゲットを絞った一般向けのより正式なスローガンとなっています。

**関連トピック：**

* [オーディエンスの作成](../../audiences/using/creating-audiences.md)
* [送信の準備](../../sending/using/preparing-the-send.md)

