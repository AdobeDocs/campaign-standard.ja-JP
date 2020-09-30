---
title: Adobe Campaignでのコンテンツのデザイン
description: 最初からHTMLの読み込みや既存のテンプレートの活用を行って、電子メールコンテンツを作成します。
page-status-flag: never-activated
uuid: 8f73407f-ab90-46bc-aeb6-bd87fcb0404c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: about-content-design
discoiquuid: 20800cde-50ad-4d2b-a2f9-812258bec665
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 97760e8b5fe0eb4905dcae69e8bbbefa837a461f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Campaign E メールデザイナー{#designing-content-in-adobe-campaign}

Adobe Campaignで電子メールを作成したら、その内容を定義する必要があります。

電子メールデザイナを使用すると、ドラッグ&amp;ドロップインターフェイスを介して、個別にカスタマイズした魅惑的な電子メールを作成できます。 空白の石版から始める場合でも、既存のコンテンツのフラグメントやテンプレートを活用する場合でも、プロモーションやトランザクションなど、あらゆる電子メールのすべてのコンテンツを設計して洗練させます。

レスポンシブデザインに最適化されたHTMLを配信するように設計された電子メールデザイナーを使用すると、ユーザーインターフェイスを介して、表示条件と動的コンテンツを簡単に定義し、電子メール、テンプレートまたはフラグメントに適用できます。 ボタンをクリックすると、ドラッグ&amp;ドロップインターフェイスとHTMLコードをシームレスに切り替えることができます。

電子メールデザイナーでは、電子メールコンテンツと電子メールコンテンツテンプレートを作成できます。 シンプルな電子メール、トランザクション電子メール、A/Bテスト用電子メール、多言語電子メール、および定期的な電子メールと互換性があります。

電子メールデザイナーの使い方を習得するには、次のビデオ [セットに従って、電子メールデザイナーの一般的な機能と](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) 、ゼロから電子メールをデザインする方法、またはテンプレートを使用する方法を説明します。

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* 電子メールコンテンツの作成方法について詳しくは、電子メールデザイナーの使い始めにを参照して [ください](../../designing/using/quick-start.md)。
* 電子メールデザイナの概要については、電子メールデザイナの [使用を参照してください](../../designing/using/designing-content-in-adobe-campaign.md)。
* コンテンツの作成の詳細：
   * 新規に電子メールを [デザインするを参照してください](../../designing/using/designing-from-scratch.md)。
   * 既存のコンテンツを使用する場合は、「既存のコンテンツを使用した [デザイン](../../designing/using/using-existing-content.md)」を参照してください。
   * Creative Cloud統合の使用については、 [マルチソリューション電子メールデザインを参照してください](../../designing/using/using-integrations.md)。
* パーソナライゼーションについて詳しくは、「 [パーソナライゼーション](../../designing/using/personalization.md)」を参照してください。

電子メールを作成する場合、定義済みのテンプレートを使用するか、別のソースから既存のコンテンツを読み込むかを選択できます。 詳しくは、既存のコンテンツの [選択を参照してください](../../designing/using/using-existing-content.md#selecting-an-existing-content)。

マーケティングキャンペーンの効率を高めるには、コンテンツをパーソナライズします。 詳しくは、パーソナライゼーションフィールドの [挿入](../../designing/using/personalization.md#inserting-a-personalization-field) 、およびコンテンツブロックの [追加を参照してください](../../designing/using/personalization.md#adding-a-content-block)。

また、プロファイルに応じて変化する動的コンテンツを定義することもできます。 詳しくは、電子メールでの動的コンテンツの [定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) およびランディングページでの動的コンテンツの [定義を参照してください](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page)。

リンクや画像を使用して、メッセージやランディングページを強化します。 詳しくは、リンクの [挿入](../../designing/using/links.md#inserting-a-link) および画像の [挿入を参照してください](../../designing/using/images.md#inserting-images)。

## Email Designerインターフェイス {#email-designer-interface}

電子メールデザイナには、コンテンツのあらゆる要素を作成、編集、カスタマイズできる多くのオプションが用意されています。

インターフェイスは、様々な機能を提供する複数の領域で構成されています。

![](assets/email_designer_overview.png)

「 **パレット** (1)」で使用可能な要素から、構造コンポーネントとコンテンツフラグメントをメインの **ワークスペース** (2)にドラッグ&amp;ドロップします。 **Workspace** (2)でコンポーネントまたは要素を選択し、 **Settings** (3)ウィンドウから主なスタイルおよび表示特性をカスタマイズします。

メイン **ツールバー** (4)から、より一般的なオプションや設定にアクセスできます。

>[!NOTE]
>
>設定 **パネルは** 、画面の解像度と表示に応じて左に移動できます。

![](assets/email_designer_toolbar.png)

エディタインタフェースの **Contextualツールバー** (Contextual toolbar)には、選択したゾーンに応じて様々な機能がオファーされます。 テキストのスタイルを変更するためのアクションボタンと各ボタンが含まれています。実行された変更は、常に選択したゾーンに適用されます。

### 電子メールデザイナホームページ {#email-designer-home-page}

電子メール [を](../../channels/using/creating-an-email.md)作成する場合 **[!UICONTROL Email Designer]** 、電子メールのコンテンツを選択すると、ホームページが自動的に表示されます。

![](assets/email_designer_home_page.png)

この **[!UICONTROL Properties]** タブでは、ラベル、送信者のアドレスと名前、電子メールの件名などの電子メールの詳細を編集できます。 画面上部の電子メールラベルをクリックして、このタブにアクセスすることもできます。

![](assets/email_designer_home_properties.png)

この **[!UICONTROL Templates]** タブでは、標準搭載されたHTMLコンテンツまたは作成済みのテンプレートから選択して、電子メールのデザインをすばやく開始できます。 詳しくは、 [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates)を参照してください。

![](assets/email_designer_home_templates.png)

この **[!UICONTROL Learn & support]** タブから、関連するドキュメントやチュートリアルに簡単にアクセスできます。

![](assets/email_designer_home_support.png)

テンプレートを選択しない場合、電子メールデザイナーのホームページでは、コンテンツのデザインを開始する方法も選択できます。

* 新しいコンテンツを最初から開始するには、 **[!UICONTROL Create]** ボタンをクリックします。 詳しくは、ゼロからの電子メールコンテンツの [デザインを参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
* この **[!UICONTROL Upload]** ボタンをクリックして、コンピュータからファイルをアップロードします。 詳しくは、ファイルからのコンテンツの [読み込みを参照してください](../../designing/using/using-existing-content.md#importing-content-from-a-file)。
* URLから既存のコンテンツを取得するには、 **[!UICONTROL Import from URL]** ボタンをクリックします。 URLからのコンテンツの [読み込みを参照してください](../../designing/using/using-existing-content.md#importing-content-from-a-url)。

## 用語 {#terminology}

**テンプレート**:テンプレートは、複数の配信で作成および再利用できる電子メールの構造です。

**フラグメント**:フラグメントは、1つ以上の電子メールで参照できる再利用可能なコンポーネントです。

**構造コンポーネント**:電子メールのレイアウトを定義する構造要素。

**コンテンツコンポーネント**:コンテンツコンポーネントは生の空のコンポーネントで、一度電子メールに配置すれば編集できます。

## Content design best practices {#content-design-best-practices}

電子メールデザイナーを適切に使用し、できるだけ簡単に最適な電子メールを作成するには、次の原則を適用することをお勧めします。

* HTMLの&lt;head>セクションで、個別のCSSとCSSではなく、インラインスタイルを使用します。 インラインスタイルを使用すると、コンテンツフラグメントの保存と再利用を最適化できます。

   インラインスタイル属性の [追加を参照してください](../../designing/using/styles.md#adding-inline-styling-attributes)。

* HTMLコンテンツを含むZIPファイルを読み込む場合は、通常のCSSを使用します。 SCSSスタイルシートはサポートされていません。

* コンテンツフラグメントを作成および再利用してマーケティングキャンペーン間の一貫性を保ち、ブランディングを簡単に解決します。

   コンテンツフラグメントの [作成を参照してください](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

* When editing **email content**:

   メッセージを送信する前に、メッセージをプレビューします。 Adobe Campaignオファーは、Litmusを使用した電子メールレンダリングのテスト方法です。 For more on this, see [Email rendering](../../sending/using/email-rendering.md).

メッセージに関するより多くのデザインと一般的なベストプラクティスを次の節に示します。 [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)。

### フラグメントの更新 {#email-designer-updates}

電子メールデザイナーは継続的に機能強化を行っています。 電子メールコンテンツを最初から作成した場合、あらかじめ用意されているテンプレートから作成した場合、またはフラグメントを作成した場合は、次回コンテンツを開いたときに次の更新メッセージが表示される場合があります。

![](assets/email_designer_fragment_patch_message.png)

Adobeでは、CSSの衝突の問題などの問題を回避するために、コンテンツを最新バージョンに更新することをお勧めします。 「**[!UICONTROL Update now]**」をクリックします。

コンテンツの更新中にエラーが発生した場合は、HTMLを確認して修正してから、この更新を再度実行してください。

フラグメントについては、次の点に注意してください。

* 新しい電子メールまたはテンプレートにフラグメントを追加する場合、このメッセージが表示されたら、最初にこのフラグメントを更新する必要があります。

* 複数のフラグメントがある場合は、電子メールコンテンツで使用する各フラグメントを更新する必要があります。

* 現在の電子メールメッセージにまだ準備されていない影響を回避するために、一部のフラグメントを更新しないように選択できます。

* 更新されていないフラグメントが既に使用されていて、そのフラグメントを編集できない場合でも、電子メールを送信できます。

* 既に準備済みの電子メールで使用されているフラグメントを更新しても、その電子メールには影響しません。

## 電子メールデザイナの制限 {#email-designer-limitations}

* フラグメント内でパーソナライゼーションフィールドを使用することはできません。 For more on fragments, see [this section](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* スタイルを編集する場合、ほとんどの電子メールクライアントで正式にサポートされているWebフォントのみが使用できます。
* スタイルは、後で再利用するためにテーマとして保存することはできません。 ただし、CSSスタイルは、コンテンツテンプレートまたは電子メールに保存できます。 For more on styles, see [this section](../../designing/using/styles.md).
* 転送者のmetaタグは電子メールデザイナーではサポートされていません。
* サロゲートペア（Unicode文字セットの基本多言語面に含まれない文字）は、2バイト（16ビット）で格納できず、2つのUTF-16文字にエンコードする必要があります。 これらの文字には、CJKイデオグラフ、ほとんどの絵文字、一部の言語が含まれます。<br>これらの文字は、動的テキストで非互換性の問題の原因となる場合があります。 メッセージを送信する前に、強力なテストを実行する必要があります。

**関連トピック**

* [E メールの作成](../../channels/using/creating-an-email.md)
* [ランディングページのデザイン](../../channels/using/designing-a-landing-page.md)
* [SMS メッセージの作成](../../channels/using/creating-an-sms-message.md)
* [プッシュ通知の作成と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
