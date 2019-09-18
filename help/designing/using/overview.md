---
title: 電子メールデザイナの使用
seo-title: 電子メールデザイナの使用
description: 電子メールデザイナの使用
seo-description: 電子メールデザイナーと、電子メールデザインコンテンツを有効にする方法を確認します。
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
source-git-commit: a7de545e9eec675444245576cddc6eaf8dce05f4

---


# 電子メールデザイナの使用 {#email-designer}

## 電子メールデザイナの概要 {#about-the-email-designer}

電子メールデザイナを使用すると、電子メールコンテンツと電子メールコンテンツテンプレートを作成できます。 シンプルなEメール、トランザクションEメール、A/BテストEメール、多言語Eメール、定期的なEメールとの互換性があります。

電子メールデザイナーの使い方を始めるには [](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) 、電子メールデザイナーの一般的な機能と、最初から電子メールをデザインする方法、またはテンプレートを使用する方法を説明した一連のビデオを見てください。

### 電子メールデザイナのホームページ {#email-designer-home-page}

電子メ [ールを作成すると](../../channels/using/creating-an-email.md)、電子メールの内容を **[!UICONTROL Email Designer]** 選択すると、ホームページが自動的に表示されます。

![](assets/email_designer_home_page.png)

このタ **[!UICONTROL Properties]** ブでは、ラベル、送信者のアドレスと名前、電子メールの件名などの電子メールの詳細を編集できます。 このタブには、画面の上部にある電子メールラベルをクリックしてアクセスすることもできます。

![](assets/email_designer_home_properties.png)

このタ **[!UICONTROL Templates]** ブでは、標準のHTMLコンテンツや、電子メールのデザインを素早く開始するために作成したテンプレートを選択できます。 「コンテンツテ [ンプレート」を参照](../../designing/using/using-reusable-content.md#content-templates)。

![](assets/email_designer_home_templates.png)

このタブ **[!UICONTROL Learn & support]** から、関連するドキュメントやチュートリアルに簡単にアクセスできます。

![](assets/email_designer_home_support.png)

テンプレートを選択しない場合は、電子メール·デザイナのホームページで、コンテンツのデザインを開始する方法を選択することもできます。

* 新しいコンテンツ **[!UICONTROL Create]** を最初から開始するには、ボタンをクリックします。 詳しくは、 [Eメール·コンテンツをゼロからデザインするを参照してくださ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)い。
* ボタンをクリック **[!UICONTROL Upload]** して、コンピュータからファイルをアップロードします。 「ファイル [からのコンテンツのインポート」を参照してくださ](../../designing/using/using-existing-content.md#importing-content-from-a-file)い。
* URLから既存のコ **[!UICONTROL Import from URL]** ンテンツを取得するには、ボタンをクリックします。 「URLか [らのコンテンツのインポート」を参照](../../designing/using/using-existing-content.md#importing-content-from-a-url)。

### 電子メールデザイナーインターフェイス {#email-designer-interface}

電子メールデザイナには、コンテンツのあらゆる側面を作成、編集、およびカスタマイズするための多くのオプションが用意されています。

インタフェースは、次の機能を提供する複数の領域で構成されています。

![](assets/email_designer_overview.png)

「パレット」( **Palette** ) (1)で使用可能な要素から、構造コンポーネントとコンテンツフラグメントをメインの **Workspace** (2)にドラッグ&amp;ドロップします。 ワークスペース(2)でコンポーネントまたは要素を選択し、 **[設定]ペイン****** (3)でその主なスタイルと表示特性をカスタマイズします。

メインのツールバー( **** 4)から、より一般的なオプションと設定にアクセスします。

>[!NOTE]
>
>[設 **定** ]ペインは、画面の解像度と表示に応じて左に移動できます。

![](assets/email_designer_toolbar.png)

エディタイ **ンタフェースの** [コンテキスト]ツールバーには、選択したゾーンに応じてさまざまな機能が用意されています。 テキストのスタイルを変更するアクションボタンとボタンが含まれています。 実行された変更は、常に選択したゾーンに適用されます。

### 用語 {#terminology}

**テンプレート**:テンプレートは、複数の配信に対して構築および再利用できる電子メールの構造です。

**フラグメント**:フラグメントは、1つ以上の電子メールで参照できる再利用可能なコンポーネントです。

**構造コンポーネント**:電子メールのレイアウトを定義する構造要素

**コンテンツコンポーネント**:コンテンツコンポーネントは、Eメールに配置した後で編集できる未加工の空のコンポーネントです。

### コンテンツ設計のベスト·プラクティス {#content-design-best-practices}

電子メールデザイナーを適切に使用し、最適な電子メールをできるだけ簡単に作成するには、次の原則を適用することをお勧めします。

* HTMLの&lt;head&gt;セクションでは、個別のCSSとCSSではなく、インラインスタイルを使用します。 インラインスタイルを使用すると、コンテンツフラグメントの保存と再利用を最適化できます。

   「インラインス [タイル属性の追加」を参照してくださ](../../designing/using/styles.md#adding-inline-styling-attributes)い。

* HTMLコンテンツを含むZIPファイルをインポートする場合は、通常のCSSを使用します。 SCSSスタイルシートはサポートされていません。

* コンテンツの断片を作成して再利用し、マーケティングキャンペーン全体の一貫性を保つことで、ブランド化を容易に解決できます。

   「コンテンツ [フラグメントの作成」を参照してくださ](../../designing/using/using-reusable-content.md#creating-a-content-fragment)い。

* 電子メールのコ **ンテンツの編集**:

   メッセージを送信する前に、メッセージをプレビューします。 Adobe Campaignは、Litmusを使用して電子メールレンダリングをテストする方法を提供します。 詳細については、「電子メールレンダリング」を [参照してください](../../sending/using/email-rendering.md)。

メッセージに関するより多くの設計と一般的なベストプラクティスは、次のAdobe Campaignのステップバイステップガイドに記載されています。Adobe Campaign [を使用したベストプラクティス](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)。

### 電子メールデザイナの制限 {#email-designer-limitations}

* フラグメント内で個人用設定フィールドを使用することはできません。 フラグメントの詳細については、この節を [参照してください](../../designing/using/using-reusable-content.md#about-fragments)。
<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* スタイルを編集する場合、ほとんどの電子メールクライアントで正式にサポートされているWebフォントのみが使用できます。
* スタイルは、今後再利用するためのテーマとして保存できません。 ただし、CSSスタイルは、コンテンツテンプレートまたは電子メールに保存できます。 スタイルの詳細については、このセクションを [参照してくださ](../../designing/using/styles.md)い。

### フラグメントの更新 {#email-designer-updates}

Eメールデザイナーは継続的に改善されています。 メールコンテンツを最初から作成した場合、既存のテンプレートから作成した場合、またはフラグメントを作成した場合は、次にコンテンツを開くときに次の更新メッセージが表示される場合があります。

![](assets/email_designer_fragment_patch_message.png)

CSSの衝突の問題などの問題を回避するため、コンテンツを最新バージョンに更新することをお勧めします。 Click **[!UICONTROL Update now]**.

コンテンツの更新中にエラーが発生した場合は、HTMLを確認して修正してから、この更新を再度実行してください。

断片に関しては、次の点に注意してください。

* 新しい電子メールまたはテンプレートにフラグメントを追加する場合、このメッセージが表示された場合は、まずこのフラグメントを更新する必要があります。

* 複数のフラグメントがある場合は、電子メールコンテンツで使用する各フラグメントを更新する必要があります。

* まだ準備されていない現在の電子メールメッセージに影響を与えないように、一部のフラグメントを更新しないように選択できます。

* 更新されていないフラグメントが既に使用されているが、そのフラグメントは編集できない場合でも、電子メールを送信できます。

* 既に準備されている電子メールで使用されているフラグメントを更新しても、その電子メールには影響しません。