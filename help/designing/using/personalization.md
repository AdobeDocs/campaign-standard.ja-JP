---
solution: Campaign Standard
product: campaign
title: E メールコンテンツのパーソナライズ
description: 電子メールデザイナーで電子メールをパーソナライズする方法を検出します。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '2573'
ht-degree: 5%

---


# E メールコンテンツのパーソナライズ {#personalization}

Adobe Campaignが配信するメッセージの内容と表示は、様々な方法でパーソナライズできます。 これらの方法は、プロファイルに応じて条件に従って組み合わせることができます。 Adobe Campaign には、全体として次のようなパーソナライゼーション機能が備わっています。

* パーソナライゼーションフィールドの動的な挿入：[パーソナライゼーションフィールドの挿入](#inserting-a-personalization-field)を参照してください。
* 定義済みパーソナライゼーションブロックの挿入：[コンテンツブロックの追加](#adding-a-content-block)を参照してください。
* 電子メールの送信者をパーソナライズします。 詳しくは、送信者の [個人設定を参照してください](#personalizing-the-sender)。
* 電子メールの件名をパーソナライズします。 See [Personalizing the subject line of an email](../../designing/using/subject-line.md#subject-line).
* 条件付きコンテンツの作成：詳しくは、電子メール内での動的コンテンツの [定義を参照してください](#defining-dynamic-content-in-an-email)。

## 送信者の個人設定 {#personalizing-the-sender}

送信されるメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナーホームページの **[!UICONTROL Properties]** タブに移動します（ホームアイコンからアクセスできます）。 詳しくは、「電子メールの送信者の [定義](../../designing/using/subject-line.md#email-sender)」を参照してください。

送信者の名前は、 **送信者の名前** ブロックをクリックして変更できます。 フィールドが編集可能になり、使用する名前を入力できます。

このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

## URLの個人設定{#personalizing-urls}

Adobe Campaignを使用すると、メッセージ、コンテンツブロックまたは動的コンテンツをメッセージに追加して、パーソナライゼーションフィールド内の1つまたは複数のURLをパーソナライズできます。 手順は次のとおりです。

1. 外部URLを挿入し、そのパラメーターを指定します。 See [Inserting a link](../../designing/using/links.md#inserting-a-link).
1. 表示されない場合は、設定パネルで選択したURLの横にある鉛筆をクリックして、パーソナライズオプションにアクセスします。
1. 使用する追加パーソナライゼーションフィールド、コンテンツブロック、動的コンテンツ。

   ![](assets/des_personalize_links.png)

1. 変更を保存します。

>[!NOTE]
>
>個人用のURLをドメイン名やURL拡張子に適用することはできません。 パーソナライゼーションが正しくない場合、メッセージ分析中にエラーメッセージが表示されます。 コンテンツブロックを選択する場合、「ミラーページに **リンク**」などの要素を選択することはできません。 この種類のブロックは、リンク内では禁止されています。

## パーソナライゼーションフィールドの挿入{#inserting-a-personalization-field}

Adobe Campaignを使用すると、プロファイルの名など、データベースのフィールドをページに挿入できます。

>[!NOTE]
>
>以下の画像は、電子メール用の [電子メールデザイナーを使用してパーソナライゼーションフィールドを挿入する方法を示しています](../../designing/using/designing-content-in-adobe-campaign.md) 。

コンテンツにパーソナライゼーションフィールドを追加するには：

1. テキストブロック内をクリックし、コンテキストツールバーの **[!UICONTROL Personalize]** アイコンをクリックしてを選択し **[!UICONTROL Insert personalization field]**&#x200B;ます。 電子メールデザイナーインターフェイスについて詳しくは、 [この節を参照してください](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_perso_field_1.png)

1. ページコンテンツに挿入するフィールドを選択します。

   ![](assets/email_perso_field_2.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

エディターにフィールド名が表示され、ハイライト表示されます。

![](assets/email_perso_field_3.png)

パーソナライゼーションが生成されると（例えば、電子メールをプレビューし、準備する場合）、このフィールドはターゲットプロファイルに対応する値に置き換えられます。

>[!NOTE]
>
>電子メールがワークフローから作成された場合は、ワークフローで計算された追加のデータもパーソナライゼーションフィールドで使用できます。 ワークフローから追加のデータを追加する方法の詳細については、「データを [富化](../../automating/using/about-targeting-activities.md#enriching-data) 」の項を参照してください。

## Adding a content block{#adding-a-content-block}

Adobe Campaignオファーは、事前設定済みのコンテンツブロックのリストです。 これらのコンテンツブロックは動的でパーソナライズされ、特定のレンダリングを持ちます。 例えば、ミラーページにあいさつ文やリンクを追加できます。

>[!NOTE]
>
>次の画像は、電子メール用に [電子メールデザイナを使用してコンテンツブロックを挿入する方法を示しています](../../designing/using/designing-content-in-adobe-campaign.md) 。

コンテンツブロックを追加するには：

1. テキストブロック内をクリックし、コンテキストツールバーの **[!UICONTROL Personalize]** アイコンをクリックしてを選択し **[!UICONTROL Insert content block]**&#x200B;ます。 電子メールデザイナーインターフェイスについて詳しくは、 [この節を参照してください](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_content_block_1.png)

1. 挿入するコンテンツブロックを選択します。 使用できるブロックは、コンテキスト(電子メールまたはランディングページ)によって異なります。

   ![](assets/email_content_block_2.png)

1. 「**[!UICONTROL Save]**」をクリックします。

コンテンツブロックの名前がエディタに表示され、黄色でハイライト表示されます。 パーソナライゼーションが生成されると、プロファイルに自動的に適応します。

![](assets/email_content_block_3.png)

そのまま使用できるコンテンツブロックは次のとおりです。

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Link to mirror page (MirrorPage)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**:このコンテンツブロックは **ランディングページでのみ使用できます**。
* **[!UICONTROL Default sender name (DefaultSenderName)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**:このコンテンツブロックは **配信でのみ使用できます**。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### カスタムコンテンツブロックの作成 {#creating-custom-content-blocks}

メッセージまたはランディングページに挿入する新しいコンテンツブロックを定義できます。

コンテンツブロックを作成するには、次の手順に従います。

1. 詳細メニュー **[!UICONTROL Resources > Content blocks]** のをクリックして、コンテンツブロックのリストにアクセスします。
1. 既存のコンテンツブロックの **[!UICONTROL Create]** ボタンまたは重複をクリックします。

   ![](assets/content_bloc_01.png)

1. ラベルを入力します。
1. ブロックのを選択し **[!UICONTROL Content type]**&#x200B;ます。 次の 3 つのオプションを使用できます。

   * **[!UICONTROL Shared]**:コンテンツブロックは、配信またはランディングページで使用できます。
   * **[!UICONTROL Delivery]**:コンテンツブロックは配信でのみ使用できます。
   * **[!UICONTROL Landing page]**:コンテンツブロックはランディングページでのみ使用できます。

   ![](assets/content_bloc_02.png)

1. を選択でき **[!UICONTROL Targeting dimension]**&#x200B;ます。 For more on this, see [About targeting dimension](#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. 次の2つの異なるブロックを定義する **[!UICONTROL Depends on format]** オプションを選択できます。1つはHTML電子メール用、もう1つはテキスト形式の電子メール用です。 次に、エディターに2つのタブ（HTMLとテキスト）が表示され、対応するコンテンツが定義されます。

   ![](assets/content_bloc_03.png)

1. コンテンツブロックのコンテンツを入力し、 **[!UICONTROL Create]** ボタンをクリックします。

これで、メッセージやランディングページのコンテンツエディタでコンテンツブロックを使用できるようになります。

>[!CAUTION]
>
>ブロックのコンテンツを編集する場合は、 *ifステートメントの先頭と末尾の間に余分な空白がないことを確認します* 。 HTMLでは、空白が画面に表示されるので、コンテンツのレイアウトに影響します。

### ターゲティングディメンションについて {#about-targeting-dimension}

ターゲティングディメンションを使用して、コンテンツブロックを使用できるメッセージのタイプを定義できます。 これは、エラーを引き起こす可能性のある、メッセージ内で不適切なブロックを使用しないようにするためです。

実際、メッセージを編集する場合は、そのメッセージのターゲティングディメンションと互換性のあるターゲティングディメンションを持つコンテンツブロックのみを選択できます。

たとえば、 **[!UICONTROL Unsubscription link]** ブロックのターゲティングディメンションは、リソースに固有のパーソナライゼーションフィールドが含まれ **[!UICONTROL Profiles]** ているためで **[!UICONTROL Profiles]** す。 したがって、 **[!UICONTROL Unsubscription link]** イベントトランザクションメッセージでは [ブロックを使用できません](../../channels/using/event-transactional-messages.md)。このタイプのメッセージのターゲティングディメンションは **[!UICONTROL Real-time events]**&#x200B;です。 ただし、 **購読解除リンクブロックは** プロファイルトランザクションメッセージで使用できます [。このタイプのメッセージのターゲティングディメンションは](../../channels/using/profile-transactional-messages.md)プロファイルなので ****&#x200B;す。 最後に、ブロックにターゲティングディメンションがないので、 **[!UICONTROL Link to mirror page]** 任意のメッセージで使用できます。

このフィールドを空のままにすると、ターゲティングディメンションが何であろうと、コンテンツブロックはすべてのメッセージと互換性があります。 ターゲティングディメンションを設定した場合、そのブロックは同じターゲティングディメンションを持つメッセージとのみ互換性があります。

詳しくは、[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)を参照してください。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](#inserting-a-personalization-field)
* [コンテンツブロックの追加](#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](#defining-dynamic-content-in-an-email)

## 画像ソースのパーソナライズ{#personalizing-an-image-source}

Adobe Campaignを使用すると、特定の条件に従ってメッセージ内の1つまたは複数の画像をパーソナライズしたり、トラッキングを使用したりできます。 これは、パーソナライゼーションフィールド、コンテンツブロックまたは動的コンテンツを画像ソースに挿入することで行います。 手順は次のとおりです。

1. メッセージの内容に画像を挿入するか、既に存在する画像を選択します。
1. 画像プロパティパレットで、 **[!UICONTROL Enable personalization]** オプションをオンにします。

   ![](assets/des_personalize_images_1.png)

   フィールドが表示され **[!UICONTROL Source]** 、選択した画像が **パーソナライズされた状態でエディターに表示されます** 。

1. フィールドボタンの横にある鉛筆をクリックして、パーソナライゼーションオプションを表示し **[!UICONTROL Source]** ます。
1. 画像ソースを追加したら、必要なパーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >ドメイン名(http://mydomain.com)はパーソナライズできないので、手動で入力する必要があります。 残りのURLはパーソナライズできます。 次に例を示します。http://mydomain.com/ `[Gender]` .jpg

1. 変更を確認します。

## 条件付きコンテンツ {#conditional-content}

### 表示条件の定義{#defining-a-visibility-condition}

任意の要素に対して表示条件を指定できます。 条件が考慮される場合にのみ表示されます。

表示条件を追加するには、ブロックを選択し、設定の **[!UICONTROL Visibility condition]** フィールドに考慮する条件を入力します。

![](assets/delivery_content_5.png)

このオプションは、次の要素に対してのみ使用できます。アドレス、BLOCKQUOTE、中心、ディレクトリ、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

式エディターは、 [詳細式編集](../../automating/using/editing-queries.md#about-query-editor) セクションに表示されます。

これらの条件はXTK式構文(例： **context.プロファイル.email !=&quot;** または **context.プロファイル.status=&#39;0&#39;**)。 デフォルトでは、すべてのファイルが表示されます。

>[!NOTE]
>
>動的コンテンツを含むサブ要素が既に含まれているブロック、または既に動的コンテンツを構成しているブロックに対しては、条件を定義できません。 ドロップダウンリストなど、表示されないダイナミックブロックは編集できません。

### 電子メールでの動的コンテンツの定義{#defining-dynamic-content-in-an-email}

>[!CONTEXTUALHELP]
>id="ac_dynamic_content"
>title="動的コンテンツの定義"
>abstract="一部のプロファイルに表示される異なるコンテンツを、定義する条件に従ってのみ定義します。"

電子メールでは、式エディターで定義した条件に従って受信者に動的に表示される様々なコンテンツを定義できます。 例えば、同じ電子メールから、各プロファイルが年齢の範囲に応じて異なるメッセージを受け取るように設定できます。

動的なコンテンツの定義は、表示条件の [定義とは異なります](#defining-a-visibility-condition)。

1. フラグメント、コンポーネントまたは要素を選択します。 この例では、画像を選択します。
1. コンテキストツールバーの **[!UICONTROL Dynamic content]** アイコンをクリックします。

   ![](assets/dynamic_content_2.png)

   左側のパレットに **[!UICONTROL Dynamic content]** セクションが表示されます。

   ![](assets/dynamic_content_3.png)

   デフォルトでは、この節には2つの要素が含まれています。デフォルトのバリアントと新しいバリアント。

   >[!NOTE]
   >
   >コンテンツには常にデフォルトのバリアントが必要です。 削除することはできません。

1. 1つ目の代替バリアントの表示条件を定義するには、 **[!UICONTROL Edit]** ボタンをクリックします。

   ![](assets/dynamic_content_4.png)

1. ラベルを指定し、条件として設定するフィールドを選択します。 例えば、 **[!UICONTROL General]** ノードから **[!UICONTROL Age]** フィールドを選択します

   ![](assets/dynamic_content_5.png)

1. フィルター条件を設定します。 例えば、18歳から25歳の間のユーザーに異なるコンテンツを表示する場合などです。

   ![](assets/dynamic_content_6.png)

1. すべての条件が設定されたら、条件を適用する優先順位を定義し、変更を保存します。

   ![](assets/dynamic_content_7.png)

   コンテンツは、上から下に順番にパレットに表示されます。 For more on priorities, refer to [this section](#defining-dynamic-content-in-an-email).

1. 先ほど定義したバリアント用に新しい画像をアップロードします。

   ![](assets/dynamic_content_8.png)

   18歳から25歳の受信者は、新しいイメージを見る。

   ![](assets/dynamic_content_10.png)

1. をクリック **[!UICONTROL Add a condition]** して、新しいコンテンツとそのリンクされたルールを追加します。

   ![](assets/dynamic_content_9.png)

   例えば、26歳から35歳の間の人に表示する別の画像を追加できます。

1. 動的に表示する電子メールの他の要素についても同様に処理を続けます。 テキスト、ボタン、フラグメントなどがあります。 変更を保存します。

>[!CAUTION]
>
>メッセージを準備し、送信する前に、配達確認を使用してテストします。 この操作を行わないと、一部のエラーが検出されず、電子メールが送信されない場合があります。

**関連トピック：**

* [配達確認の送信](../../sending/using/sending-proofs.md)
* [高度な式の編集](../../automating/using/editing-queries.md#about-query-editor)

### 優先順位 {#order-of-priority}

式エディターでは、動的コンテンツを定義する場合の優先順位は次のとおりです。

1. 例えば、次の **2つの異なる条件で2つの異なる動的コンテンツを定義します**。

   **条件1:** プロファイルの性別は男性的だ

   **条件2:** そのプロファイルは20歳から30歳の間だ。

   ![](assets/delivery_content_61.png)

   データベース内の一部のプロファイルは2つの条件に対応しますが、1つの動的コンテンツを持つ1つの電子メールのみを送信できます。

1. したがって、動的コンテンツの優先度を定義する必要があります。 優先度が **1** （したがって、対応する動的コンテンツ）の順序を持つ条件は、優先順位が **2** または **** 3の別の条件がこのプロファイルで満たされた場合でも、プロファイルに送信されます。

   ![](assets/delivery_content_62.png)

動的コンテンツごとに定義できる優先順位は1つだけです。

## 例：電子メールのパーソナライゼーション{#example-email-personalization}

この例では、マーケティングサービスチームのメンバーが電子メールを作成し、一部の顧客に対して、その顧客に対してのみ特別なオファーがあることを知らせます。 チームのメンバーは、顧客のそれぞれの年齢に応じて電子メールをパーソナライズすることを決定しました。 18歳から27歳のクライアントは、異なる画像と27歳より前のクライアントが受け取るスローガンを含む電子メールを受信します。

電子メールは次のように作成されます。

* 画像に動的コンテンツを与え、これら動的コンテンツを年齢範囲に応じて構成する。

   ![](assets/delivery_content_43.png)

   動的コンテンツの追加と設定について詳しくは、「電子メール内の動的コンテンツの [定義](#defining-dynamic-content-in-an-email) 」の節を参照してください。

* パーソナライゼーションフィールドと動的なコンテンツがテキストに適用されます。 プロファイルの年齢範囲に応じて、プロファイルの名、またはプロファイルのタイトルと姓を持つ電子メール開始。

   ![](assets/delivery_content_44.png)

   パーソナライゼーションフィールドの追加と設定について詳しくは、「パーソナライゼーションフィールドの [挿入](#inserting-a-personalization-field) 」セクションを参照してください。

### 画像の設定 {#configuring-images}

>[!CONTEXTUALHELP]
>id="ac_dynamic_image"
>title="動的画像の管理"
>abstract="定義する条件に従って、電子メールを動的な画像でパーソナライズします。"

この例では、画像に適用する動的コンテンツを次のように設定します。

**ターゲット18～27歳まで：**

1. パレットで動的コンテンツを選択し、 **[!UICONTROL Properties]** ボタンをクリックし **[!UICONTROL Edit]** ます。

   ![](assets/delivery_content_48.png)

1. ラベルを編集し、 **[!UICONTROL Age]****[!UICONTROL Profile]** ノードからフィールドを選択します。

   ![](assets/delivery_content_49.png)

1. 「 **次よりも大きいか等しい** 」演算子を選択し、「18」を入力して18 **式より****** 古いを作成します。

   ![](assets/delivery_content_50.png)

1. 追加新しい **[!UICONTROL Age]** 条件。

   「次より **小さいか等しい** 」演算子を選択し、「値」フィールドに「27」を入力して、27 **式** より小さい値を作成します。

   ![](assets/delivery_content_51.png)

1. 変更を確認します。

**27歳以上のターゲットプロファイルを作成するには：**

1. パレットから動的なコンテンツを選択し、編集します。
1. ラベルを編集し、 **[!UICONTROL Age]****[!UICONTROL Profile]** ノードからフィールドを選択します。
1. 27追加 **より** 古い式を作成するには、値フィールドに27を後に付けた **** 「次の値より大きい」演算子を入力します。

   ![](assets/delivery_content_52.png)

1. 変更を確認します。

動的コンテンツが正しく設定されている。

### テキストの設定 {#configuring-text}

この例では、テキストに適用する動的コンテンツを次のように設定します。

**18 ～ 27才のターゲットプロファイルを作成するには：**

1. 必要な構造コンポーネントを選択し、動的コンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット設定の式を設定します。 詳しくは、「イメージの [設定](#configuring-images)」を参照してください。
1. 構造コンポーネントで、目的の位置に、コンテキストツールバーの **[!UICONTROL Personalize]** アイコンをクリックし、を選択し **[!UICONTROL Insert personalization field]**&#x200B;ます。

   ![](assets/delivery_content_53.png)

1. 表示されるリストで、フィールドを選択して確認 **[!UICONTROL First name]** します。

   ![](assets/delivery_content_54.png)

1. 次に、パーソナライゼーションフィールドが選択した動的コンテンツに完全に挿入されます。

**27歳以上のターゲットプロファイルを作成するには：**

1. 必要な構造コンポーネントを選択し、動的コンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット設定の式を設定します。 詳しくは、「イメージの [設定](#configuring-images)」を参照してください。
1. 構造コンポーネントで、目的の位置に、コンテキストツールバーの **[!UICONTROL Personalize]** アイコンをクリックし、を選択し **[!UICONTROL Insert personalization field]**&#x200B;ます。
1. ドロップダウン **[!UICONTROL Title]** リストからを選択します。
1. 同様にして、 **[!UICONTROL Last name]** フィールドを追加します。

   ![](assets/delivery_content_56.png)

これで、パーソナライゼーションフィールドは選択した動的コンテンツに完全に挿入されます。

### 電子メールのプレビュー {#previewing-emails}

プレビュー機能を使用すると、パーソナライゼーションフィールドと動的なコンテンツが正しく設定されていることを確認してから、コンテンツを送信でき **[!UICONTROL Proofs]**&#x200B;ます。 プレビュー中に、電子メールターゲットに対応する別のテストプロファイルを選択できます。

テストプロファイルを使用しない場合、デフォルトで表示される電子メールは次のとおりです。

![](assets/delivery_content_45.png)

電子メールにはスローガン内にパーソナライゼーションフィールドが含まれておらず、デフォルトの画像が使用されます。

最初のテストプロファイルは、18歳から27歳のクライアントに対応しています。 このプロファイルを選択すると、次の電子メールが表示されます。

![](assets/delivery_content_46.png)

18 ～ 27歳の式(特にプロファイルの名)に対応するパーソナライズフィールドは正しく設定され、プロファイルに従って画像も変更されています。

2つ目のプロファイルは、27歳を超えるクライアントに対応し、次の電子メールを生成します。

![](assets/delivery_content_47.png)

動的なコンテンツのおかげで画像が変わりました。表示されるスローガンは、このターゲットを絞った一般向けのスローガンとしてより正式に定義されています。

**関連トピック：**

* [オーディエンスの作成](../../audiences/using/creating-audiences.md)
* [送信の準備](../../sending/using/preparing-the-send.md)

