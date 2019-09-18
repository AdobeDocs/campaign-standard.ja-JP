---
title: 個人用設定
seo-title: 個人用設定
description: 個人用設定
seo-description: 電子メールデザイナで電子メールをパーソナライズする方法を説明します。
page-status-flag: 未活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: 編集，電子メールの内容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# 個人用設定 {#personalization}

Adobe Campaignが配信するメッセージのコンテンツと表示は、さまざまな方法でカスタマイズできます。 これらの方法は、縦断に応じた基準に従って組み合わせることができます。 一般に、Adobe Campaignでは次の操作を実行できます。

* 動的パーソナライズフィールドを挿入します。 「個人用設 [定フィールドの挿入」を参照してくださ](../../designing/using/personalization.md#inserting-a-personalization-field)い。
* 定義済みの個人用設定ブロックを挿入します。 「コンテンツ [ブロックの追加」を参照してくださ](../../designing/using/personalization.md#adding-a-content-block)い。
* 電子メールの送信者をカスタマイズします。 「送信者の [個人化」を参照してください](../../designing/using/personalization.md#personalizing-the-sender)。
* 電子メールの件名をカスタマイズします。 詳しくは、 [電子メールの件名行のパーソナライズを参照してください](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email)。
* 条件付きコンテンツを作成します。 「電子メ [ールでの動的コンテンツの定義」を参照](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 送信者の個人用設定 {#personalizing-the-sender}

送信されたメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナのホームページの **[!UICONTROL Properties]** タブ（「ホーム」アイコンからアクセス可能）に移動します。 詳細については、「電子メールの送 [信者を定義する」を参照してください。](../../designing/using/subject-line.md#email-sender)

送信者名を変更するには、[送信者名]ブロックをク **リックし** ます。 フィールドが編集可能になり、使用する名前を入力できます。

このフィールドは個人用に設定できます。 これを行うには、送信者名の下のアイコンをクリックして、個人用設定フィールド、コンテンツブロック、および動的コンテンツを追加します。

>[!NOTE]
>
>ヘッダーパラメーターを空にすることはできません。 送信者のアドレスは、電子メールの送信を許可するために必須です（RFC標準）。 Adobe Campaignは、入力した電子メールアドレスの構文を確認します。

## URLのパーソナライズ{#personalizing-urls}

Adobe Campaignでは、個人用設定フィールド、コンテンツブロック、または動的コンテンツを追加して、メッセージ内の1つまたは複数のURLを個人用に設定できます。 これを行うには、次の手順に従います。

1. 外部URLを挿入し、そのパラメータを指定します。 「リン [クの挿入」を参照](../../designing/using/links.md#inserting-a-link)。
1. 表示されない場合は、[設定]ペインで選択したURLの横の鉛筆をクリックして、個人用設定オプションにアクセスします。
1. 使用する個人用設定フィールド、コンテンツブロック、および動的コンテンツを追加します。

   ![](assets/des_personalize_links.png)

1. 変更を保存します。

>[!NOTE]
>
>個人用化URLは、ドメイン名やURL拡張子に適用できません。 パーソナライズが正しくない場合は、メッセージ分析中にエラーメッセージが表示されます。 コンテンツブロックを選択する場合、[ミラーページにリンク]などの要素を選 **択することはできません**。 この種類のブロックは、リンク内では使用できません。

## 個人用設定フィールドの挿入{#inserting-a-personalization-field}

Adobe Campaignでは、プロファイルの名など、データベースのフィールドをページに挿入できます。

>[!NOTE]
>
>次の図は、電子メールの電子メールデザイナを使用して個人用設定フィ [ールドを挿入する](../../designing/using/overview.md) 方法を示しています。

個人用設定フィールドをコンテンツに追加するには、次の手順に従います。

1. テキストブロック内をクリックし、コンテキストツ **[!UICONTROL Personalize]** ールバーのアイコンをクリックしてを選択しま **[!UICONTROL Insert personalization field]**&#x200B;す。 電子メールデザイナのインタフェースの詳細については、このセクションを [参照してくださ](../../designing/using/overview.md#email-designer-interface)い。

   ![](assets/email_perso_field_1.png)

1. ページコンテンツに挿入するフィールドを選択します。

   ![](assets/email_perso_field_2.png)

1. Click **[!UICONTROL Confirm]**.

フィールド名がエディタに表示され、ハイライト表示されます。

![](assets/email_perso_field_3.png)

個人用設定が生成されると（たとえば、電子メールのプレビューと準備を行う場合）、このフィールドは、ターゲットプロファイルに対応する値に置き換えられます。

>[!NOTE]
>
>ワークフローから電子メールを作成する場合は、ワークフローで計算された追加データも個人用設定フィールドで使用できます。 ワークフローから追加データを追加する方法の詳細については、「データの強化」の項を [参照してくださ](../../automating/using/targeting-data.md#enriching-data) い。

## コンテンツブロックを追加する{#adding-a-content-block}

Adobe Campaignは、事前に設定されたコンテンツブロックのリストを提供します。 これらのコンテンツブロックは、動的でパーソナライズされ、特定のレンダリングを行います。 たとえば、あいさつ文やミラーページへのリンクを追加できます。

>[!NOTE]
>
>次の図は、電子メールの電子メールデザイナを使用してコンテンツ [ブロックを挿入する](../../designing/using/overview.md) 方法を示しています。

コンテンツブロックを追加するには、次の手順に従います。

1. テキストブロック内をクリックし、コンテキストツ **[!UICONTROL Personalize]** ールバーのアイコンをクリックしてを選択しま **[!UICONTROL Insert content block]**&#x200B;す。 電子メールデザイナのインタフェースの詳細については、このセクションを [参照してくださ](../../designing/using/overview.md#email-designer-interface)い。

   ![](assets/email_content_block_1.png)

1. 挿入するコンテンツブロックを選択します。 使用可能なブロックは、コンテキスト（電子メールまたはランディング·ページ）によって異なります。

   ![](assets/email_content_block_2.png)

1. Click **[!UICONTROL Save]**.

コンテンツブロックの名前がエディタに表示され、黄色でハイライト表示されます。 個人用設定が生成されると、プロファイルに自動的に適応します。

![](assets/email_content_block_3.png)

既存のコンテンツブロックは次のとおりです。

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Link to mirror page (MirrorPage)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**:このコンテンツブロックは、ランディングページでのみ使 **用できます**。
* **[!UICONTROL Default sender name (DefaultSenderName)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**:このコンテンツブロックは、配信でのみ使用で **きます**。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### カスタムコンテンツブロックを作成する {#creating-custom-content-blocks}

メッセージまたはランディング·ページに挿入する新しいコンテンツ·ブロックを定義できます。

コンテンツブロックを作成するには、次の手順に従います。

1. 詳細メニ **[!UICONTROL Resources > Content blocks]** ューからをクリックして、コンテンツブロックのリストにアクセスします。
1. ボタンをクリック **[!UICONTROL Create]** するか、既存のコンテンツブロックを複製します。

   ![](assets/content_bloc_01.png)

1. ラベルを入力します。
1. ブロックを選択します **[!UICONTROL Content type]**。 次の3つのオプションを使用できます。

   * **[!UICONTROL Shared]**:コンテンツ·ブロックは、配信またはランディング·ページで使用できます。
   * **[!UICONTROL Delivery]**:コンテンツブロックは、配信でのみ使用できます。
   * **[!UICONTROL Landing page]**:コンテンツブロックは、ランディングページでのみ使用できます。
   ![](assets/content_bloc_02.png)

1. を選択できます **[!UICONTROL Targeting dimension]**。 詳細は、「ターゲットディメンションにつ [いて」を参照してくださ](../../designing/using/personalization.md#about-targeting-dimension)い。

   ![](assets/content_bloc_04.png)

1. 次の2つの異なるブロッ **[!UICONTROL Depends on format]** クを定義するオプションを選択できます。1つはHTML電子メール用、もう1つはテキスト形式の電子メール用です。 2つのタブがエディタ（HTMLとテキスト）に表示され、対応するコンテンツが定義されます。

   ![](assets/content_bloc_03.png)

1. コンテンツブロックの内容を入力し、ボタンをクリックし **[!UICONTROL Create]** ます。

これで、コンテンツブロックをメッセージのコンテンツエディタまたはランディングページで使用できるようになりました。

>[!CAUTION]
>
>ブロックの内容を編集する場合は、 *if文の先頭と末尾の間に余分な空白がないことを確認し* ます。 HTMLでは、ホワイトスペースが画面に表示されるため、コンテンツレイアウトに影響を与えます。

### ターゲットディメンションについて {#about-targeting-dimension}

ターゲットディメンションを使用すると、コンテンツブロックを使用できるメッセージの種類を定義できます。 これは、エラーを引き起こす可能性のある、メッセージ内の不適切なブロックを使用しないようにするためです。

実際に、メッセージを編集する場合は、そのメッセージのターゲットディメンションと互換性のあるターゲットディメンションを持つコンテンツブロックのみを選択できます。

たとえば、ブロックのターゲ **[!UICONTROL Unsubscription link]** ットディメンションには、リソー **[!UICONTROL Profiles]** スに固有の個人用設定フィールドが含まれてい **[!UICONTROL Profiles]** るためです。 したがって、そのタイプのメッセ **[!UICONTROL Unsubscription link]** ージのターゲットディメ [ンションは](../../channels/using/event-transactional-messages.md)、であるため、イベントトランザクションメッセージでブロックを使用できませ **[!UICONTROL Real-time events]**&#x200B;ん。 ただし、そのタイプのメッセージのターゲッ **トディメンションが** Profilesであるため [、プロファイルトランザクションメッセージではUnsubscriptionリンクブロックを使用で](../../channels/using/profile-transactional-messages.md)きます ****。 最後に、ブロッ **[!UICONTROL Link to mirror page]** クにターゲットディメンションがないため、任意のメッセージで使用できます。

このフィールドを空のままにすると、ターゲットディメンションが何であっても、コンテンツブロックはすべてのメッセージと互換性があります。 ターゲットディメンションを設定した場合、そのブロックは、同じターゲットディメンションを持つメッセージとのみ互換性があります。

詳細は、「ディメンションとリソースをターゲ [ット化する」を参照してください](../../automating/using/query.md#targeting-dimensions-and-resources)。

**関連トピック：**

* [個人用設定フィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックを追加する](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## イメージソースのカスタマイズ{#personalizing-an-image-source}

Adobe Campaignでは、特定の基準に従って、メッセージ内の1つまたは複数の画像をカスタマイズしたり、追跡を使用したりできます。 これを行うには、個人用設定フィールド、コンテンツブロック、または動的コンテンツをイメージソースに挿入します。 これを行うには、次の手順に従います。

1. メッセージの内容にイメージを挿入するか、既に存在するイメージを選択します。
1. イメージプロパティパレットで、オプションをチェック **[!UICONTROL Enable personalization]** します。

   ![](assets/des_personalize_images_1.png)

   フィールド **[!UICONTROL Source]** が表示され、選択したイメージがエディタに個別 **に表示** されます。

1. フィールド·ボタンの横の鉛筆をクリッ **[!UICONTROL Source]** クして、パーソナライズ·オプションにアクセスします。
1. イメージソースを追加した後、必要な個人用設定フィールド、コンテンツブロック、および動的コンテンツを追加します。

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >ドメイン名(http://mydomain.com)は個人用に設定できません。手動で入力する必要があります。 残りのURLは個人用に設定できます。 例：http://mydomain.com/`[Gender]`.jpg

1. 変更を確認します。

## 条件付きコンテンツ {#conditional-content}

### 表示条件の定義{#defining-a-visibility-condition}

任意の要素に対して表示条件を指定できます。 条件が尊重される場合にのみ表示されます。

表示条件を追加するには、ブロックを選択し、設定のフィールドに適用する条 **[!UICONTROL Visibility condition]** 件を入力します。

![](assets/delivery_content_5.png)

このオプションは、次の要素に対してのみ使用できます。ADDRESS、BLOCKQUOTE、CENTER、DIR、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

式エディタは、「≪拡張式編集| [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor) |Whdev≫」セクションに表示されます。

これらの条件は、XTK式の構文を採用します(例： **context.profile.email !)。="** または **context.profile.status='0'**)。 既定では、すべてのフィールドが表示されます。

>[!NOTE]
>
>既にダイナミックコンテンツを含むサブ要素を含むブロック、または既にダイナミックコンテンツを構成するブロックを含むブロックに対しては、条件を定義できません。 ドロップダウンリストのような非表示のダイナミックブロックは編集できません。

### 電子メールでの動的コンテンツの定義{#defining-dynamic-content-in-an-email}

電子メールでは、式エディタで定義した条件に従って、受信者に動的に表示されるさまざまな内容を定義できます。 たとえば、同じ電子メールから、各プロファイルが、年齢の範囲に応じて異なるメッセージを受け取るようにできます。

ダイナミックコンテンツの定義は、表示条件を定 [義する場合とは異なります](../../designing/using/personalization.md#defining-a-visibility-condition)。

1. フラグメント、コンポーネント、または要素を選択します。 この例では、イメージを選択します。
1. コンテキストツー **[!UICONTROL Dynamic content]** ルバーのアイコンをクリックします。

   ![](assets/dynamic_content_2.png)

   左側の **[!UICONTROL Dynamic content]** パレットにセクションが表示されます。

   ![](assets/dynamic_content_3.png)

   デフォルトでは、このセクションには次の2つの要素が含まれます。既定のバリアント型と新しいバリアント型。

   >[!NOTE]
   >
   >コンテンツには、常に既定のバリアントが必要です。 削除できません。

1. ボタンをクリ **[!UICONTROL Edit]** ックして、第1の代替バリアントの表示条件を定義します。

   ![](assets/dynamic_content_4.png)

1. ラベルを指定し、条件として設定するフィールドを選択します。 たとえば、ノードから **[!UICONTROL General]** フィールドを選択し **[!UICONTROL Age]** ます

   ![](assets/dynamic_content_5.png)

1. フィルタ条件を設定します。 たとえば、18歳から25歳の人に別のコンテンツを表示する場合です。

   ![](assets/dynamic_content_6.png)

1. すべての条件を設定したら、条件を適用する優先順位を定義し、変更を保存します。

   ![](assets/dynamic_content_7.png)

   内容は、上から下の順に、優先順位に従ってパレットに表示されます。 For more on priorities, refer to [this section](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

1. 定義したバリアントの新しいイメージをアップロードします。

   ![](assets/dynamic_content_8.png)

   18歳から25歳の受け取り人は新しいイメージを見る。

   ![](assets/dynamic_content_10.png)

1. 新しいコ **[!UICONTROL Add a condition]** ンテンツとそのリンクルールを追加する場合にクリックします。

   ![](assets/dynamic_content_9.png)

   たとえば、26歳から35歳の人に別のイメージを追加して表示することができます。

1. 同様に、動的に表示する電子メールの他の要素についても同様に処理を行います。 テキスト、ボタン、フラグメントなどを指定できます。 変更を保存します。

>[!CAUTION]
>
>メッセージを準備したら、送信する前に、証明を使ってテストします。 この操作を行わないと、エラーが検出されず、電子メールが送信されない場合があります。

**関連トピック：**

* [校正の送信](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)
* [高度な式の編集](../../automating/using/editing-queries.md#about-query-editor)

### 優先順位 {#order-of-priority}

エクスプレッションエディタで、ダイナミックコンテンツを定義する場合、優先順位は次のとおりです。

1. 2つの異なる動的コンテンツを2つの異な **る条件で定義します**。たとえば、次のようにします。

   **** 条件1:プロフィールの性別は男性的だ

   **** 条件2:縦断面は20〜30歳である。

   ![](assets/delivery_content_61.png)

   データベース内の一部のプロファイルは2つの条件に対応していますが、1つの動的コンテンツを持つ1つの電子メールのみ送信できます。

1. したがって、動的コンテンツの優先順位を定義する必要があります。 優先順位が **1** （したがって、対応する動的コンテンツ）の条件は、優先順位が **2** または **3** の別の条件もこのプロファイルで満たされている場合でも、プロファイルに送信されます。

   ![](assets/delivery_content_62.png)

動的コンテンツごとに優先順位を1つだけ定義できます。

## 例：電子メールの個人用設定{#example-email-personalization}

この例では、マーケティング·サービス·チームのメンバーが、顧客に対して、顧客に対してだけ特別なオファーがあることを通知する電子メールを作成しました。 チームメンバーは、顧客の年齢に応じて電子メールをパーソナライズすることを決めました。 18歳から27歳のクライアントは、27歳を超えるクライアントが受け取るイメージとスローガンが異なるメールを受け取ります。

電子メールは次のように作成されます。

* 動的コンテンツを画像に適用し、これらの動的コンテンツを年齢範囲に応じて構成する。

   ![](assets/delivery_content_43.png)

   動的コンテンツの追加と構成の詳細については、「電子メ [ールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 」を参照してください。

* テキストには、パーソナライズフィールドと動的コンテンツが適用されます。 プロファイルの有効期間に応じて、電子メールはプロファイルの名、またはプロファイルのタイトルと姓で始まります。

   ![](assets/delivery_content_44.png)

   個人用設定フィールドの追加と構成の詳細については、「個人用設定フ [ィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field) 」を参照してください。

### イメージの構成 {#configuring-images}

この例では、イメージに適用される動的コンテンツを次のように設定します。

**18~27歳を対象にする場合：**

1. パレットでダイナミックコンテンツを **[!UICONTROL Properties]** 選択し、ボタンをクリック **[!UICONTROL Edit]** します。

   ![](assets/delivery_content_48.png)

1. ラベルを編集し、ノードからフ **[!UICONTROL Age]** ィールドを選択 **[!UICONTROL Profile]** します。

   ![](assets/delivery_content_49.png)

1. 「次の値以 **上」演算子を選択し** 、「 **18** 」と入力して、18より古い式 **を作成します** 。

   ![](assets/delivery_content_50.png)

1. 新しい条件を追加 **[!UICONTROL Age]** します。

   値フィールド **で「次の値以下」演算子と「** 27」演算子を選択し、27よりも若い式 **を作成します** 。

   ![](assets/delivery_content_51.png)

1. 変更を確認します。

**27歳以上のプロファイルをターゲットにするには：**

1. パレットからダイナミックコンテンツを選択し、編集します。
1. ラベルを編集し、ノードからフ **[!UICONTROL Age]** ィールドを選択 **[!UICONTROL Profile]** します。
1. 値フィールドに **「より大きい」演算子の後に** 「27」を付けて、27より古い式を **作成します** 。

   ![](assets/delivery_content_52.png)

1. 変更を確認します。

ダイナミックコンテンツが正しく設定されています。

### テキストの設定 {#configuring-text}

この例では、テキストに適用される動的な内容は次のように設定されます。

**18 ~ 27の間の古いプロファイルをターゲットにするには：**

1. 必要な構造コンポーネントを選択し、ダイナミックコンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット式を構成します。 「イメージの設 [定」を参照](../../designing/using/personalization.md#configuring-images)。
1. 構造コンポーネントで、目的の位置でコンテキストツールバーのア **[!UICONTROL Personalize]** イコンをクリックし、を選択しま **[!UICONTROL Insert personalization field]**&#x200B;す。

   ![](assets/delivery_content_53.png)

1. 表示されるリストで、フィールドを選択し、確 **[!UICONTROL First name]** 認を行います。

   ![](assets/delivery_content_54.png)

1. 次に、選択した動的なコンテンツに、パーソナライズフィールドが完全に挿入されます。

**27歳以上のプロファイルをターゲットにするには：**

1. 必要な構造コンポーネントを選択し、ダイナミックコンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット式を構成します。 「イメージの設 [定」を参照](../../designing/using/personalization.md#configuring-images)。
1. 構造コンポーネントで、目的の位置でコンテキストツールバーのア **[!UICONTROL Personalize]** イコンをクリックし、を選択しま **[!UICONTROL Insert personalization field]**&#x200B;す。
1. ドロップ **[!UICONTROL Title]** ダウンリストからを選択します。
1. 同様に、フィールドを追加 **[!UICONTROL Last name]** します。

   ![](assets/delivery_content_56.png)

選択した動的コンテンツに、パーソナライズフィールドが完全に挿入されます。

### 電子メールのプレビュー {#previewing-emails}

プレビューを使用すると、を送信する前に、個人用設定フィールドと動的コンテンツが正しく構成されているかどうかを確認できま **[!UICONTROL Proofs]**&#x200B;す。 プレビュー中に、電子メールターゲットに対応する別のテストプロファイルを選択できます。

テストプロファイルがない場合、既定で表示される電子メールは次のとおりです。

![](assets/delivery_content_45.png)

電子メールには、スローガンに個人用設定フィールドがなく、既定のイメージが使用されます。

最初のテストプロファイルは、18 ~ 27歳のクライアントに対応します。 このプロファイルを選択すると、次の電子メールが表示されます。

![](assets/delivery_content_46.png)

18 ~ 27歳の式、特にプロファイルの名に対応する個人用設定フィールドが正しく設定され、プロファイルに従ってイメージも変更されています。

2番目のプロファイルは、27歳を超えるクライアントに対応し、次の電子メールを生成します。

![](assets/delivery_content_47.png)

動的なコンテンツのおかげでイメージが変わり、表示されるスローガンは、このターゲットとなる人々に対して定義されたより正式なスローガンです。

**関連トピック：**

* [対象ユーザーの作成](../../audiences/using/creating-audiences.md)
* [送信の準備](../../sending/using/preparing-the-send.md)

