---
title: 電子メールデザイナーの使用
description: 電子メールデザイナーを見つけ、電子メールデザインコンテンツを有効にする方法を確認します。
page-status-flag: 非活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 電子メールデザイナーの使用 {#email-designer}

## 電子メールデザイナーの概要 {#about-the-email-designer}

電子メールデザイナーを使用すると、電子メールコンテンツと電子メールコンテンツテンプレートを作成できます。 シンプルな電子メール、トランザクション電子メール、A/Bテスト電子メール、多言語電子メール、繰り返し電子メールと互換性があります。

電子メールデザイナーを使い始めるには [、このビデオセットで電子メールデザイナーの一般的な機能と](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) 、最初から電子メールをデザインしたり、テンプレートを使用して電子メールをデザインしたりする方法を説明します。

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

### 電子メールデザイナーインターフェイス {#email-designer-interface}

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

### 用語 {#terminology}

**テンプレート**:テンプレートは電子メールの構造で、複数の配信用に作成して再利用できます。

**フラグメント**:フラグメントは、1つ以上の電子メールで参照できる再利用可能なコンポーネントです。

**構造コンポーネント**:電子メールのレイアウトを定義する構造要素

**コンテンツコンポーネント**:コンテンツコンポーネントは、電子メールに配置した後に編集できる生の空のコンポーネントです。

### コンテンツデザインのベストプラクティス {#content-design-best-practices}

電子メールデザイナーを適切に使用し、できるだけ簡単に最良の電子メールを作成するには、次の原則を適用することをお勧めします。

* HTMLの&lt;head&gt;セクションでは、個別のCSSとCSSではなく、インラインスタイルを使用します。 インラインスタイルを使用すると、コンテンツフラグメントの保存と再利用を最適化できます。

   詳しくは、イ [ンラインスタイル属性の追加を参照してくださ](../../designing/using/styles.md#adding-inline-styling-attributes)い。

* HTMLコンテンツを含むZIPファイルを読み込む場合は、通常のCSSを使用します。 SCSSスタイルシートはサポートされていません。

* コンテンツフラグメントを作成して再利用し、マーケティングキャンペーン全体で一貫性を保つことで、ブランドを簡単に設定できます。

   詳しくは、コ [ンテンツフラグメントの作成を参照してくださ](../../designing/using/using-reusable-content.md#creating-a-content-fragment)い。

* 電子メールコ **ンテンツの編集**:

   メッセージを送信する前にプレビューします。 Adobe Campaignでは、Litmusを使用した電子メールのレンダリングをテストする方法を提供しています。 For more on this, see [Email rendering](../../sending/using/email-rendering.md).

メッセージに関するより多くのデザインと一般的なベストプラクティスは、以下のAdobe Campaignのステップバイステップガイドに記載されています。Adobe Campaignの [配信のベストプラクティス](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)。

### 電子メールデザイナの制限 {#email-designer-limitations}

* フラグメント内でパーソナライゼーションフィールドを使用することはできません。 フラグメントについて詳しくは、この節を参 [照してください](../../designing/using/using-reusable-content.md#about-fragments)。
<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* スタイルを編集する場合、ほとんどの電子メールクライアントが正式にサポートしているWebフォントのみが使用できます。
* スタイルは、将来再利用するためにテーマとして保存できません。 ただし、CSSスタイルはコンテンツテンプレートまたは電子メールに保存できます。 スタイルについて詳しくは、この節を参 [照してください](../../designing/using/styles.md)。

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