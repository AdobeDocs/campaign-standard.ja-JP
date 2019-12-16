---
title: Adobe Campaignでのコンテンツのデザイン
description: Adobe Campaignでコンテンツに定義できるすべての要素について説明します。
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
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# Campaign 電子メールデザイナー{#designing-content-in-adobe-campaign}

Adobe Campaignで電子メールを作成したら、そのコンテンツを定義する必要があります。

電子メールデザイナーを使用すると、ネイティブのCreative cloud統合によって拡張されたドラッグ&amp;ドロップインターフェイスを通じて、個別にカスタマイズした魅惑的な電子メールを作成できます。 空白の段階から始める場合でも、既存のコンテンツフラグメントやテンプレートを活用する場合でも、プロモーションやトランザクションに関わらず、すべての電子メールのすべてのコンテンツをデザインし、精緻化します。

レスポンシブデザインに最適化されたHTMLを配信するために設計された電子メールデザイナーを使用すると、ユーザーインターフェイスを介して、表示条件と動的コンテンツを簡単に定義し、電子メール、テンプレートまたはフラグメントに適用できます。 ボタンのクリック時に、ドラッグ&amp;ドロップインターフェイスとHTMLコードをシームレスに切り替えることができます。

電子メールデザイナーを使用すると、電子メールコンテンツと電子メールコンテンツテンプレートを作成できます。 シンプルな電子メール、トランザクション電子メール、A/Bテスト電子メール、多言語電子メール、繰り返し電子メールと互換性があります。

電子メールデザイナーを使い始めるには [、このビデオセットで電子メールデザイナーの一般的な機能と](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) 、最初から電子メールをデザインしたり、テンプレートを使用して電子メールをデザインしたりする方法を説明します。

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* 電子メールコンテンツの作成方法について詳しくは、電子メールデザ [イナーの使い始めに](../../designing/using/quick-start.md)。
* 電子メールデザイナーの概要については、「電子メールデザ [イナーの使用](../../designing/using/designing-content-in-adobe-campaign.md)」を参照してください。
* コンテンツの作成の詳細：
   * 新規での電子メールのデザ [インを参照してください](../../designing/using/designing-from-scratch.md)。
   * 既存のコンテンツを使用する場合は、既存のコンテ [ンツを使用したデザインを参照してくださ](../../designing/using/using-existing-content.md)い。
   * 統合の使用については、マルチソリュ [ーション電子メールデザインを参照してくださ](../../designing/using/using-integrations.md)い。
* パーソナライゼーションについて詳しくは、「パーソナライゼーション」を参 [照してくださ](../../designing/using/personalization.md)い。

電子メールを作成する場合は、定義済みのテンプレートを使用するか、別のソースから既存のコンテンツを読み込むかを選択できます。 詳しくは、 [既存のコンテンツの選択を参照してください](../../designing/using/using-existing-content.md#selecting-an-existing-content)。

マーケティングキャンペーンの効率を高めるには、コンテンツをパーソナライズします。 詳しくは、パーソ [ナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field) およびコン [テンツブロックの追加を参照してくださ](../../designing/using/personalization.md#adding-a-content-block)い。

また、各プロファイルに応じて異なる動的コンテンツを定義することもできます。 詳しくは、電 [子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) およびランデ [ィングページでの動的コンテンツの定義を参照してください](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page)。

リンクや画像を使用して、メッセージやランディングページの効果を高めます。 詳しくは、 [リンクの挿入と](../../designing/using/links.md#inserting-a-link) 、画像の挿 [入を参照してください](../../designing/using/images.md#inserting-images)。

## 電子メールデザイナーインターフェイス {#email-designer-interface}

電子メールデザイナーには、コンテンツのあらゆる側面を作成、編集、カスタマイズできる多くのオプションが用意されています。

インターフェイスは、様々な機能を提供する複数の領域で構成されています。

![](assets/email_designer_overview.png)

パレット(1)で使用可能な **要素から** 、構造コンポーネントとコンテンツフラグメントをメインの **Workspace** (2)にドラッグ&amp;ドロップします。 **Workspace** (2)でコンポーネントまたは要素を選択し、設定パネル(3)でその主なスタイル設定と表示特性 **** をカスタマイズします。

メインツールバー(4)からその他の一般的なオプシ **ョン** /設定にアクセスします。

>[!NOTE]
>
>設定 **ペインは** 、画面の解像度と表示に従って左に移動できます。

![](assets/email_designer_toolbar.png)

エディタ **ーインターフェイスのContextual** （コンテキスト）ツールバーは、選択したゾーンに応じて様々な機能を提供します。 テキストのスタイルを変更できるアクションボタンとボタンが含まれます。 実行された変更は、常に選択したゾーンに適用されます。

### 電子メールデザイナのホームページ {#email-designer-home-page}

電子メ [ールを作成する場合](../../channels/using/creating-an-email.md)、電子メール **[!UICONTROL Email Designer]** コンテンツを選択すると、ホームページが自動的に表示されます。

![](assets/email_designer_home_page.png)

このタ **[!UICONTROL Properties]** ブでは、ラベル、送信者の住所、名前、電子メールの件名などの電子メールの詳細を編集できます。 画面の上部にある電子メールラベルをクリックして、このタブにアクセスすることもできます。

![](assets/email_designer_home_properties.png)

このタ **[!UICONTROL Templates]** ブでは、標準搭載されたHTMLコンテンツや、作成済みのテンプレートから選択して、電子メールのデザインをすばやく開始できます。 コンテンツテ [ンプレートを参照してくださ](../../designing/using/using-reusable-content.md#content-templates)い。

![](assets/email_designer_home_templates.png)

このタ **[!UICONTROL Learn & support]** ブから、関連するドキュメントやチュートリアルに簡単にアクセスできます。

![](assets/email_designer_home_support.png)

テンプレートを選択しない場合は、電子メールデザイナーのホームページで、コンテンツのデザインを開始する方法を選択することもできます。

* 新しいコンテンツ **[!UICONTROL Create]** を最初から開始するには、このボタンをクリックします。 詳しくは、 [ゼロからの電子メールコンテンツのデザインを参照してくださ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)い。
* このボタンをクリ **[!UICONTROL Upload]** ックして、コンピュータからファイルをアップロードします。 詳しくは、 [ファイルからのコンテンツの読み込みを参照してくださ](../../designing/using/using-existing-content.md#importing-content-from-a-file)い。
* URLから既存のコ **[!UICONTROL Import from URL]** ンテンツを取得するには、このボタンをクリックします。 URLから [のコンテンツの読み込みを参照してください](../../designing/using/using-existing-content.md#importing-content-from-a-url)。

## 用語 {#terminology}

**テンプレート**:テンプレートは電子メールの構造で、複数の配信用に作成して再利用できます。

**フラグメント**:フラグメントは、1つ以上の電子メールで参照できる再利用可能なコンポーネントです。

**構造コンポーネント**:電子メールのレイアウトを定義する構造要素。

**コンテンツコンポーネント**:コンテンツコンポーネントは、電子メールに配置した後に編集できる生の空のコンポーネントです。

## コンテンツデザインのベストプラクティス {#content-design-best-practices}

電子メールデザイナーを適切に使用し、できるだけ簡単に最良の電子メールを作成するには、次の原則を適用することをお勧めします。

* HTMLの&lt;head&gt;セクションでは、個別のCSSとCSSではなく、インラインスタイルを使用します。 インラインスタイルを使用すると、コンテンツフラグメントの保存と再利用を最適化できます。

   詳しくは、イ [ンラインスタイル属性の追加を参照してくださ](../../designing/using/styles.md#adding-inline-styling-attributes)い。

* HTMLコンテンツを含むZIPファイルを読み込む場合は、通常のCSSを使用します。 SCSSスタイルシートはサポートされていません。

* コンテンツフラグメントを作成して再利用し、マーケティングキャンペーン全体で一貫性を保つことで、ブランドを簡単に設定できます。

   詳しくは、コ [ンテンツフラグメントの作成を参照してくださ](../../designing/using/using-reusable-content.md#creating-a-content-fragment)い。

* 電子メールコ **ンテンツの編集**:

   メッセージを送信する前にプレビューします。 Adobe Campaignでは、Litmusを使用した電子メールのレンダリングをテストする方法を提供しています。 For more on this, see [Email rendering](../../sending/using/email-rendering.md).

メッセージに関するより多くのデザインと一般的なベストプラクティスは、以下のAdobe Campaignのステップバイステップガイドに記載されています。Adobe Campaignの [配信のベストプラクティス](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)。

### フラグメントの更新 {#email-designer-updates}

電子メールデザイナーは継続的に強化されています。 標準搭載のテンプレートから電子メールコンテンツを新規作成した場合や、フラグメントを作成した場合は、次回コンテンツを開いたときに次の更新メッセージが表示される場合があります。

![](assets/email_designer_fragment_patch_message.png)

CSSの衝突の問題などの問題を避けるため、コンテンツを最新バージョンに更新することをお勧めします。 Click **[!UICONTROL Update now]**.

コンテンツの更新中にエラーが発生した場合は、HTMLを確認して修正してから、この更新を再度実行してください。

フラグメントに関しては、次の点に注意してください。

* 新しい電子メールまたはテンプレートにフラグメントを追加する場合、このメッセージが表示されたら、最初にこのフラグメントを更新する必要があります。

* 複数のフラグメントがある場合は、電子メールコンテンツで使用する各フラグメントを更新する必要があります。

* まだ準備されていない現在の電子メールメッセージに影響を与えないように、一部のフラグメントを更新しないように選択できます。

* 更新されていないフラグメントが既に使用されているが、そのフラグメントを編集できない場合でも、電子メールを送信できます。

* 既に準備済みの電子メールで使用されているフラグメントの更新は、その電子メールに影響を与えません。

## 電子メールデザイナの制限 {#email-designer-limitations}

* フラグメント内でパーソナライゼーションフィールドを使用することはできません。 フラグメントについて詳しくは、この節を参 [照してください](../../designing/using/using-reusable-content.md#about-fragments)。

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* スタイルを編集する場合、ほとんどの電子メールクライアントが正式にサポートしているWebフォントのみが使用できます。
* スタイルは、将来再利用するためにテーマとして保存できません。 ただし、CSSスタイルはコンテンツテンプレートまたは電子メールに保存できます。 スタイルについて詳しくは、この節を参 [照してください](../../designing/using/styles.md)。

**関連トピック**：

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [ランディングページのデザイン](../../channels/using/designing-a-landing-page.md)
* [SMS メッセージの作成](../../channels/using/creating-an-sms-message.md)
* [プッシュ通知の作成と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
