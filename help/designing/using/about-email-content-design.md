---
title: 電子メールコンテンツデザインについて
seo-title: 電子メールコンテンツデザインについて
description: 電子メールコンテンツデザインについて
seo-description: 電子メールのコンテンツをデザインできるようにする電子メールDesignerを作成します。
page-status-flag: 常にアクティブ化されていない
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: edit- email- content
discoiquuid: 39b86fda-7766-4e5f- ab48- bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 電子メールコンテンツデザインについて{#about-email-content-design}

電子メールデザイナーのドラッグ&amp;ドロップインターフェイスを使用して、Adobe Campaignで電子メールのコンテンツを作成および変更します。

ここでは、電子メールデザイナーの特異性について説明します。

* [電子メールデザイナーについて](../../designing/using/about-email-content-design.md#about-the-email-designer)
* [電子メール構造の定義](../../designing/using/defining-the-email-structure.md)
* [電子メールスタイルの編集](../../designing/using/editing-email-styles.md)

1つまたは複数のマーケティングアクティビティに共通のアクションについて詳しくは、以下の節を参照してください。

* 電子メールコンテンツのパーソナライズについて詳しくは、「パーソナライゼーションフィールド [の挿入](../../designing/using/inserting-a-personalization-field.md) 」および「コンテンツブロック [の追加](../../designing/using/adding-a-content-block.md)」を参照してください。
* 別の電子メールコンテンツのインポートについて詳しくは、既存のコンテンツ [の選択を参照](../../designing/using/selecting-an-existing-content.md)してください。
* 電子メールで動的コンテンツを定義する方法について詳しくは、電子メールでの動的コンテンツ [の定義](../../designing/using/defining-dynamic-content-in-an-email.md)を参照してください。
* 電子メールへのリンクの挿入について詳しくは、リンク [の挿入を参照](../../designing/using/inserting-a-link.md)してください。
* 電子メールに画像を挿入する方法について詳しくは、画像 [の挿入](../../designing/using/inserting-images.md)を参照してください。

コンテンツデザインの [一般的なベストプラクティスも確認](../../designing/using/content-design-best-practices.md)してください。

## 電子メールデザイナーについて {#about-the-email-designer}

電子メールデザイナーを使用すると、電子メールコンテンツや電子メールコンテンツテンプレートを作成できます。これは、単純な電子メール、トランザクション電子メール、A/Bテスト電子メール、多言語電子メール、繰り返し電子メールと互換性があります。

電子メールDesignerを使い始めるには、電子メールDesignerの一般的な機能について説明するビデオ [](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) セットと、最初からの電子メールのデザイン方法やテンプレートを使用する方法について説明しています。

### Designerのホームページ {#email-designer-home-page}

電子メールを [作成する場合、](../../channels/using/creating-an-email.md)電子メールコンテンツを選択する際に **[!UICONTROL Email Designer]** ホームページが自動的に表示されます。

![](assets/email_designer_home_page.png)

**[!UICONTROL Properties]** このタブでは、ラベル、送信者のアドレスや名前、電子メールの件名などの電子メールの詳細を編集できます。画面上部の電子メールラベルをクリックして、このタブにアクセスすることもできます。

![](assets/email_designer_home_properties.png)

**[!UICONTROL Templates]** このタブでは、あらかじめ用意されたHTMLコンテンツまたは作成済みのテンプレートから選択して、電子メールのデザインを簡単に開始できます。[コンテンツテンプレート](../../start/using/about-templates.md#content-templates)を参照してください。

![](assets/email_designer_home_templates.png)

**[!UICONTROL Learn & support]** このタブを使用すると、関連するドキュメントやチュートリアルに簡単にアクセスできます。

![](assets/email_designer_home_support.png)

テンプレートを選択しない場合、電子メールデザイナーのホームページでは、コンテンツのデザインの開始方法を選択できます。

* **[!UICONTROL Create]** 新しいコンテンツを最初から開始するには、ボタンをクリックします。詳しくは、最初から電子メールコンテンツの [デザイン](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)を参照してください。
* **[!UICONTROL Upload]** コンピューターからファイルをアップロードするには、ボタンをクリックします。詳しくは、ファイルからのコンテンツ [の読み込みを](../../designing/using/importing-content-from-a-file.md)参照してください。
* **[!UICONTROL Import from URL]** 既存のコンテンツを取得するには、ボタンをクリックします。詳しくは、URLからのコンテンツ [の読み込みを](../../designing/using/importing-content-from-a-url.md)参照してください。

### 電子メールデザイナーインターフェイス {#email-designer-interface}

電子メールDesignerには、コンテンツのすべてのアスペクトを作成、編集、カスタマイズできる数多くのオプションが用意されています。

インターフェイスは、様々な機能を提供する複数の領域で構成されています。

![](assets/email_designer_overview.png)

**パレット** （1）で使用できる要素から、構造コンポーネントとコンテンツフラグメントをメイン **Workspace** （2）にドラッグ&amp;ドロップします。**ワークスペース** でコンポーネントまたは要素を選択し、 **設定** ペイン（3）からのメインスタイルと表示の特性をカスタマイズします（3）。

メイン **ツールバー** （4）から、より一般的なオプションと設定にアクセスします。

>[!NOTE]
>
>**設定** ペインは、画面解像度と表示に応じて左方向に移動できます。

![](assets/email_designer_toolbar.png)

エディターインターフェイスの **コンテキストツールバー** には、選択したゾーンに応じて様々な機能が用意されています。テキストのスタイルを変更できるアクションボタンおよびボタンが含まれています。実行される変更は、常に選択したゾーンに適用されます。

### 電子メールデザイナーの一般的な推奨事項 {#general-recommendations-for-using-the-email-designer}

電子メールDesignerを適切に使用し、できるだけ適切な電子メールを作成するには、以下の原則を適用することをお勧めします。

* HTMLの&lt; head&gt;セクションに個別のCSSやCSSではなくインラインスタイリングを使用します。インラインスタイリングを使用することで、コンテンツフラグメントの保存と再利用を最適化できます。

   インラインスタイル属性 [の追加を参照](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes)してください。

* コンテンツフラグメントを作成および再利用して、マーケティングキャンペーン全体の一貫性を維持することで、ブランディングを容易に調整できます。

   コンテンツフラグメント [の作成を参照](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment)してください。

コンテンツデザインの [一般的なベストプラクティスも確認](../../designing/using/content-design-best-practices.md)してください。

### 電子メールDesignerの互換モード {#email-designer-compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナーのWYSIWYGエディターで完全に準拠し、編集可能な特定のタグを含める必要があります。

アップロードされたHTMLの全部または一部が予期したタグ付けに準拠していない場合、コンテンツは「互換モード」に読み込まれ、UIを介してエディションの可能性を制限します。

コンテンツが互換モードで読み込まれると、インターフェイスによって次の変更を実行できます（使用できないアクションは非表示になります）。

* テキストの変更または画像の変更
* リンクおよびパーソナライゼーションフィールドの挿入
* 選択したHTMLブロックでのいくつかのスタイル設定オプションの編集
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

電子メールまたは高度なスタイル設定に新しいセクションを追加するなどの変更は、HTMLモードを使用して電子メールのソースコードで直接行う必要があります。

既存の電子メールを電子メールデザイナーと互換性のある電子メールに変換する方法については、こちらを [](../../designing/using/about-email-content-design.md#designing-an-email-using-existing-contents)参照してください。

### 電子メールデザイナーの制限事項 {#email-designer-limitations}

* フラグメントでパーソナライゼーションフィールドを使用することはできません。フラグメントについて詳しくは、 [この節](../../designing/using/defining-the-email-structure.md#about-fragments)を参照してください。
* スタイルを編集する場合、ほとんどの電子メールクライアントで正式にサポートされているWebフォントのみが使用できます。
* スタイルは、今後再利用するためにテーマとして保存することはできません。ただし、CSSスタイルはコンテンツテンプレートまたは電子メールで保存できます。スタイルについて詳しくは、 [この節](../../designing/using/editing-email-styles.md)を参照してください。

### 電子メールDesignerの更新 {#email-designer-updates}

電子メールデザイナーは継続的に改善されています。最初から電子メールコンテンツを作成して、すぐに使用できるテンプレートから、またはフラグメントを作成した場合、次にコンテンツを開いたときに、次の更新メッセージが表示されることがあります。

![](assets/email_designer_fragment_patch_message.png)

CSSの衝突の問題などの問題を回避するために、コンテンツを最新バージョンに更新することをお勧めします。**[!UICONTROL Update now]**&#x200B;をクリックします。

コンテンツの更新中にエラーが発生した場合は、HTMLをチェックして、この更新を再度実行する前に修正してください。

フラグメントについては、次の点に注意してください。

* 新しい電子メールまたはテンプレートにフラグメントを追加する場合は、このフラグメントを最初に更新する必要があります。

* 複数のフラグメントがある場合は、電子メールコンテンツで使用する各フラグメントを更新する必要があります。

* まだ準備されていない現在の電子メールメッセージに影響を与えないように、一部のフラグメントを更新しないように選択できます。

* 更新されていないフラグメントが既に使用されている電子メールを送信できますが、そのフラグメントは編集できません。

* 既に準備されている電子メールで使用されているフラグメントを更新しても、それらの電子メールには影響しません。

## 電子メールコンテンツの新規作成 {#designing-an-email-content-from-scratch}

電子メールデザイナーを使用して、最初から電子メールコンテンツを作成してデザインする主な手順を次に示します。

1. 電子メールを作成して、そのコンテンツを開きます。
1. 電子メールを形成する構造コンポーネントを追加します。詳しくは、電子メール構造 [の編集](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)を参照してください。
1. コンポーネントコンポーネントにコンテンツコンポーネントとフラグメントを挿入します。フラグメントとコンテンツコンポーネント [の追加](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components)を参照してください。
1. 画像を追加し、電子メールのテキストを編集します。詳しくは、画像 [の挿入を](../../designing/using/inserting-images.md)参照してください。
1. パーソナライゼーションフィールドやリンクなどを追加して、電子メールをパーソナライズします。詳しくは、パーソナライゼーションフィールド [の挿入](../../designing/using/inserting-a-personalization-field.md)、 [リンク](../../designing/using/inserting-a-link.md) の挿入、電子メールでの動的コンテンツ [の定義を参照](../../designing/using/defining-dynamic-content-in-an-email.md)してください。
1. 電子メールの件名を定義します。電子メールの件名の [パーソナライズを参照](../../designing/using/personalizing-the-subject-line-of-an-email.md)してください。
1. 電子メールをプレビューします。
1. コンテンツを保存し、オーディエンスを定義して送信を適切にスケジュールしたことを確認してから、メッセージに進んでください。

[この紹介ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)を確認することもできます。

>[!NOTE]
>
>電子メールコンテンツをゼロからデザインしないように、あらかじめ用意されているコンテンツテンプレートを使用できます。詳しくは [、コンテンツテンプレート](../../start/using/about-templates.md#content-templates)を参照してください。

**関連トピック**:

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [既存のコンテンツの選択](../../designing/using/selecting-an-existing-content.md)
* [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
* [メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [電子メールレンダリング](../../sending/using/email-rendering.md)
* [HTMLを必要とせずにパーソナライズした電子メールを作成する](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Createcompellingcontenttailoredtoeveryindividual)

## 既存のコンテンツを使用した電子メールのデザイン {#designing-an-email-using-existing-contents}

ここでは、既存の電子メールを電子メールデザイナー互換の電子メールに変換する方法について説明します。

デフォルトでは、HTMLをアップロードするだけで（ファイルからコンテンツ [の読み込み](../../designing/using/importing-content-from-a-file.md)を参照）、コンテンツは«[互換モード](../../designing/using/about-email-content-design.md#email-designer-compatibility-mode)»に読み込まれます。このモードは、UI経由でのエディションの可能性を制限します（インプレース版のみ、ドラッグアンドドロップなし）。

ただし、複数の電子メールで再利用できるように構成されたモジュールテンプレートとフラグメントのフレームワークを作成する場合は、電子メールのHTMLを電子メールデザイナーテンプレートに変換することを検討してください。

電子メールデザイナーを使用してコンテンツをデザインする場合、次の3つのオプションがあります。

* [あらかじめ用意されているテンプレートからコンテンツを作成する](../../designing/using/about-email-content-design.md#building-content-from-an-out-of-the-box-template)
* [フラグメントとコンポーネント](../../designing/using/about-email-content-design.md#using-fragments-and-components)の使用、最初から開始、HTMLデザインの再作成
* [HTMLコンテンツ](../../designing/using/about-email-content-design.md#converting-an-html-content) 電子メールのモジュール化電子メールデザイナーコンテンツへの変換

### あらかじめ用意されているテンプレートからコンテンツを作成する {#building-content-from-an-out-of-the-box-template}

1. 電子メールを作成して、そのコンテンツを開きます。詳しくは、電子メールの [作成](../../channels/using/creating-an-email.md)を参照してください。
1. ホームページにアクセスするには、ホームアイコン **[!UICONTROL Email Designer]** をクリックします。
1. タブを **[!UICONTROL Templates]** クリックします。
1. あらかじめ用意されているHTMLテンプレートを選択します。

   異なるテンプレートには、複数のタイプの要素の様々な組み合わせがあります。例えば、"Feather"テンプレートにはマージンがありますが、「アトラス」テンプレートはありません。詳しくは [、コンテンツテンプレート](../../start/using/about-templates.md#content-templates)を参照してください。

1. これらの要素を組み合わせて、多数の電子メールバリアントを作成できます。例えば、構造コンポーネントを選択し、コンテキストツールバーからをクリック **[!UICONTROL Duplicate]** して、電子メールセクションを複製できます。
1. 左側の青い矢印を使用して要素を移動すると、構造コンポーネントを下または上にドラッグすることができます。これについて詳しくは、電子メール構造 [の編集](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)を参照してください。
1. コンポーネントを移動して、各構造要素の組織を変更することもできます。これについて詳しくは、フラグメントとコンポーネント [の追加](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components)を参照してください。
1. 必要に応じて各要素のコンテンツを変更します。画像、テキスト、リンク
1. 必要に応じて、スタイル設定オプションをコンテンツに合わせて調整します。これについて詳しくは、電子メールスタイル [の編集](../../designing/using/editing-email-styles.md)を参照してください。

### フラグメントとコンポーネントの使用 {#using-fragments-and-components}

単に電子メールデザイナーに外部コンテンツを準拠させるには、最初からメッセージを作成し、既存の電子メールからフラグメントやコンポーネントにコンテンツをコピーすることをお勧めします。

再作成できないコンテンツがある場合は、 **[!UICONTROL Html]** コンテンツコンポーネントを使用して、元の電子メールからHTMLコードをコピー&amp;ペーストできます。先に進む前に、HTMLに精通していることを確認してください。

完全な例を以下に示します。

>[!NOTE]
>
>新しいコンテンツは元の電子メールのコピーにはなりませんが、以下の手順では、できるだけ近いメッセージを作成します。

Adobe Campaign以外で作成した既存のニュースレターを使用するとします。

Adobe Campaignと共に送信するすべての電子メールに同じヘッダーとフッターを設定する必要があります。各ニュースレターに表示するコンテンツに応じて、電子メールの本文が変更されます。

**前提条件**

1. 元の電子メールで、送信する各電子メールに固有のセクションから再利用可能なセクションを特定します。
1. 使用するすべての画像とアセットを保存します。
1. HTMLに精通している場合は、元のHTMLコンテンツを別の部分に分割します。

**再利用可能なコンテンツのフラグメントの作成**

電子メールデザイナーを使用して、再利用可能な各セクションのフラグメントを作成します。この例では、次の2つのフラグメントを作成します。1つはヘッダー用、もう1つはフッター用です。その後、既存のコンテンツからこれらのフラグメントに関連するパーツをコピーできます。

これを行うには、次の手順に従います。

1. Adobe Campaignで **[!UICONTROL Resources]** 、&gt; **[!UICONTROL Content templates & fragments]** に移動し、ヘッダーのフラグメントを作成します。詳しくは、コンテンツフラグメント [の作成](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment)を参照してください。
1. フラグメントに必要な数のコンポーネントを追加します。

   ![](assets/des_loading_compatible_fragment_1.png)

1. 画像コンポーネントとテキストコンポーネントを構造に挿入します。

   ![](assets/des_loading_compatible_fragment_2.png)

1. 対応する画像をアップロードし、テキストを入力して設定を調整します。

   スタイル設定とインライン属性の管理について詳しくは、電子メールスタイル [の編集](../../designing/using/editing-email-styles.md)を参照してください。

   ![](assets/des_loading_compatible_fragment_3.png)

1. フラグメントを保存します。
1. フッターを作成して保存する場合も同様に実行します。

   ![](assets/des_loading_compatible_fragment_4.png)

   HTMLに精通している場合は **[!UICONTROL Html]** 、コンテンツコンポーネントを使用して元のフッターからHTMLコードをコピー&amp;ペーストできます。これについて詳しくは、コンテンツコンポーネント [について](../../designing/using/defining-the-email-structure.md#about-content-components)を参照してください。

   ![](assets/des_loading_compatible_fragment_9.png)

これで、フラグメントをテンプレートで使用できるようになりました。

**フラグメントとコンポーネントのテンプレートへの挿入**

電子メールデザイナーを使用して電子メールテンプレートを作成できるようになりました。コンテンツコンポーネントを使用して、電子メールの様々なセクションを反映し、設定を調整して、元のニュースレターにできるだけ近くにします。最後に、作成したフラグメントを挿入します。

1. Email Designerを使用してテンプレートを作成します。詳しくは [、コンテンツテンプレート](../../start/using/about-templates.md#content-templates)を参照してください。
1. テンプレートに複数の構造コンポーネントを挿入し、電子メールのヘッダー、フッター、本文に対応します。構造コンポーネントの追加について詳しくは、電子メールDesignerでの電子メール構造 [の編集](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)を参照してください。
1. 必要な数のコンテンツコンポーネントを挿入して、ニュースレター本文を作成します。毎月更新する電子メールの編集可能コンテンツになります。

   ![](assets/des_loading_compatible_fragment_5.png)

   HTMLコードに精通している場合は **[!UICONTROL Html]** 、元の電子メールのより複雑な要素をコピー&amp;ペーストできるコンポーネントを活用することをお勧めします。他のコンポーネントや **[!UICONTROL Button]**&#x200B;その他 **[!UICONTROL Image]** のコンテンツ **[!UICONTROL Text]** を使用します。これについて詳しくは、コンテンツコンポーネント [について](../../designing/using/defining-the-email-structure.md#about-content-components)を参照してください。

   >[!NOTE]
   >
   >**[!UICONTROL Html]** コンポーネントを使用すると、限られたオプションで編集可能なコンポーネントが作成されます。このコンポーネントを選択する前に、HTMLコードの処理方法を確認してください。

1. コンテンツコンポーネントを、元の電子メールに合わせて調整します。

   ![](assets/des_loading_compatible_fragment_6.png)

   スタイル設定とインライン属性の管理について詳しくは、電子メールスタイル [の編集](../../designing/using/editing-email-styles.md)を参照してください。

1. 以前に作成した2つのフラグメント（ヘッダーとフッター）を目的の構造コンポーネントに挿入します。

   ![](assets/des_loading_compatible_fragment_10.png)

1. テンプレートを保存します。

電子メールデザイナー内でこのテンプレートを完全に管理し、毎月送信するニュースレターを受信者に作成して更新できるようになりました。

これを使用するには、電子メールを作成して、作成したコンテンツテンプレートを選択します。

**関連トピック**:

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [電子メールデザイナー向けの紹介ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)
* [電子メールコンテンツの新規作成](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)

### HTMLコンテンツの変換 {#converting-an-html-content}

この使用例では、HTML電子メールを電子メールデザイナーコンポーネントに簡単に変換できます。

>[!CAUTION]
>
>この節は、HTMLコードに精通している上級ユーザー向けです。

>[!NOTE]
>
>互換モードと同様、HTMLコンポーネントは、限定的なオプションで編集できます。インプレースエディションのみを実行できます。

電子メールデザイナーの外部で、元のHTMLが再利用可能なセクションに分割されていることを確認します。

その場合は、HTMLから別のブロックをカットアウトします。次に例を示します。

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

すべてのブロックを特定したら、電子メールDesignerで、既存の電子メールのセクションごとに次の手順を繰り返します。

1. 電子メールデザイナーを開き、空の電子メールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅などこれについて詳しくは、電子メールスタイル [の編集](../../designing/using/editing-email-styles.md)を参照してください。
1. 構造コンポーネントを追加します。これについて詳しくは、電子メール構造 [の編集](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)を参照してください。
1. HTMLコンポーネントを追加します。これについて詳しくは、フラグメントとコンポーネント [の追加](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components)を参照してください。
1. そのコンポーネントにHTMLをコピー&amp;ペーストします。
1. モバイルビューに切り替えます。これについて詳しくは、 [この節](../../designing/using/about-email-content-design.md#switching-to-mobile-view)を参照してください。

   CSSが見つからないため、レスポンシブビューが壊れています。

1. これを修正するには、ソースコードモードに切り替えて、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。次に例を示します。

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Email Designerで生成されたCSSを変更しないでください。 `<style acrite-template-css="true">` および`<style acrite-custom-styles="" type="text/css">`この後にスタイルを追加してください。

1. モバイルビューに戻って、コンテンツが正しく表示されていることを確認し、変更内容を保存します。

## モバイルビューへの切り替え {#switching-to-mobile-view}

モバイルディスプレイのすべてのスタイルオプションを個別に編集することで、電子メールのレスポンシブデザインを微調整できます。例えば、マージンやパディングを適用したり、フォントサイズを小さくまたは大きくしたり、ボタンを変更したり、モバイルバージョンの電子メールに固有の背景色を適用したりできます。

モバイルビューでは、すべてのスタイルオプションを使用できます。電子メールデザイナースタイルの設定は、「電子メールの [編集スタイル](../../designing/using/editing-email-styles.md) 」セクションに表示されます。

1. 電子メールを作成し、コンテンツの編集を開始します。詳しくは、「最初から電子メールコンテンツを [デザイン](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)する」を参照してください。
1. 専用のモバイルビューにアクセスするには **[!UICONTROL Switch to mobile view]** 、ボタンを選択します。

   ![](assets/email_designer_mobile_view_switch.png)

   電子メールのモバイルバージョンが表示されます。デスクトップビューで定義されていたすべてのコンポーネントとスタイルが含まれています。

1. 背景色、整列、パディング、マージン、フォントファミリー、テキストカラーなど、すべてのスタイル設定を個別に編集します。

   ![](assets/email_designer_mobile_view.png)

1. モバイルビューのスタイル設定を編集する場合、変更はモバイルディスプレイにのみ適用されます。

   例えば、画像のサイズを小さくし、緑の背景を追加して、モバイルビューでパディングを変更します。

   ![](assets/email_designer_mobile_view_change.png)

1. コンポーネントを非表示にするには、モバイルデバイスに表示します。これを行うには、から選択 **[!UICONTROL Show only on desktop devices]****[!UICONTROL Display options]**します。
また、デスクトップデバイスでこのコンポーネントを非表示にすることもできます。つまり、モバイルデバイスでのみ表示されます。これを行うには、を選択 **[!UICONTROL Show only on mobile devices]**します。
例えば、このオプションを使用すると、モバイルデバイスに特定の画像を表示したり、デスクトップデバイス上で別の画像を表示したりできます。
このオプションは、モバイルビューまたはデスクトップビューから設定できます。

   ![](assets/email_designer_mobile_hide.png)

1. ボタンを **[!UICONTROL Switch to mobile view]** もう一度クリックすると、標準のデスクトップビューに戻ります。行ったスタイル変更は反映されません。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一の例外は **[!UICONTROL Style inline]** 設定です。インラインでのスタイル設定の変更は、標準のデスクトップビューにも適用されます。

1. テキスト編集、新しい画像のアップロード、新しいコンポーネントの追加など、電子メールの構造やコンテンツに対するその他の変更。は標準ビューにも適用されます。

   例えば、モバイルビューに戻り、テキストを編集して画像を置換します。

   ![](assets/email_designer_mobile_view_change_content.png)

   ボタンを **[!UICONTROL Switch to mobile view]** もう一度クリックすると、標準のデスクトップビューに戻ります。変更が反映されます。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. モバイルビューのスタイルを削除すると、デスクトップモードで適用されたスタイルに戻ります。

   例えば、モバイルビューで、ボタンに緑色の背景色を適用します。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. デスクトップビューに切り替えて、グレーの背景を同じボタンに適用します。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. もう一度モバイルビューに切り替えて **[!UICONTROL Background color]** 、設定を無効にします。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   デスクトップビューで定義されている背景色が適用されるようになりました。灰色で表示されます（空白ではありません）。

   唯一の例外は **[!UICONTROL Border color]** 設定です。モバイルビューで無効にした場合、デスクトップビューで境界線の色が定義されていても、境界線は適用されなくなります。

## プレーンテキストモードとHTMLモード {#plain-text-and-html-modes}

### 電子メールのテキストバージョンの生成 {#generating-a-text-version-of-the-email}

デフォルトでは、電子メールの **[!UICONTROL Plain text]** バージョンは自動的に生成され **[!UICONTROL Edit]** 、バージョンと同期されます。

HTMLバージョンに追加されたパーソナライゼーションフィールドとコンテンツブロックも、プレーンテキストバージョンと同期されます。

>[!NOTE]
>
>プレーンテキストバージョンのコンテンツブロックを使用するには、HTMLコードが含まれていないことを確認します。

HTMLバージョンとは異なるプレーンテキストバージョンを使用するには、電子メールの表示から **[!UICONTROL Sync with HTML]** 切り替えをクリックしてこの同期 **[!UICONTROL Plain text]** を無効にします。

![](assets/email_designer_textversion.png)

必要に応じてプレーンテキストバージョンを編集できます。

>[!NOTE]
>
>同期が無効になって **[!UICONTROL Plain text]** いるときにバージョンを編集する場合、次回 **[!UICONTROL Sync with HTML]** オプションを有効にすると、プレーンテキストバージョンで行ったすべての変更がHTMLバージョンに置き換えられます。ビューで **[!UICONTROL Plain text]** 行われた変更は、ビューに **[!UICONTROL HTML]** 反映できません。

### HTMLでの電子メールコンテンツソースの編集 {#editing-an-email-content-source-in-html}

最も高度なユーザーおよびデバッグの場合は、HTMLで直接電子メールコンテンツを表示および編集できます。

電子メールのHTMLバージョンを編集するには、次の2つの方法があります。

* 電子メール全体のHTMLバージョンを開くには、 **[!UICONTROL Edit]** / **[!UICONTROL HTML]** を選択します。

   ![](assets/email_designer_html1.png)

* WYSIWYGインターフェイスから要素を選択し、アイコンを **[!UICONTROL Source code]** クリックします。

   選択した要素のソースのみが表示されます。選択した要素がコンテンツコンポーネントで **[!UICONTROL HTML]** ある場合は、ソースコードを編集できます。その他のコンポーネントは読み取り専用モードになっていますが、完全なHTMLバージョンの電子メールで編集できます。

   ![](assets/email_designer_html2.png)

HTMLを変更すると、電子メールの応答性が断ち切れることがあります。**[!UICONTROL Preview]** 必ずボタンを使用してテストしてください。詳しくは、メッセージ [のプレビューを](../../sending/using/previewing-messages.md)参照してください。

## Adobe Campaign統合によるデザイン {#design-through-adobe-campaign-integrations}

### Dreamweaverでのコンテンツの編集 {#editing-content-in-dreamweaver}

DreamweaverとAdobe Campaign Standardの統合により、Dreamweaverインターフェイスで電子メールのコンテンツを編集できます。レスポンシブ電子メールコンテンツを設計および開発するために、Dreamweaverの強力なインターフェイスにアクセスできます。

* **双方向同期**

   1つの製品で編集が行われると、その製品は他の製品のリアルタイムで更新されます。Dreamweaverのテキストの色を変更する場合は、編集を行うと、テキストの色がキャンペーンに反映されます。また、行番号は同じであるため、Dreamweaverまたはキャンペーンのコードを選択すると、その行番号が2つの製品の間に残り、コード内の特定のものを探すときに非常に便利です。

* **Dreamweaverでのローカル画像のACへのアップロード**

   Dreamweaver内で電子メールを作成または編集するときに、デスクトップまたはローカルマシンから画像を選択するだけです。Dreamweaverでは常に、DreamweaverとCampaignが接続されているときに、ローカルファイルがAdobe Campaignサーバーにアップロードされます。コンテンツの変更として手動で画像をアップロードする必要はありません。さらに、最新の画像が常にCampaignに配信されます。

* **DreamweaverでのCampaignのパーソナライゼーションの追加**

   電子メール開発者は、データモデルの表のようなテキストを追加し ```[[FIRSTNAME_PLACEHOLDER]]``` たり参照したりする必要がなくなりました。Dreamweaverのキャンペーンツールバーは、キャンペーンインスタンスのデータモデルに直接接続します。つまり、「名」に「名」という名前のデータを取り込むことができます。キャンペーン内でコンテンツブロックを作成した場合は、それらを直接Dreamweaverに取り込むことができます。

この機能は、ここでアクセス [できるDreamweaverドキュメントで説明](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html)しています。デモ [ビデオ](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) も利用できます。

### Experience Managerでのコンテンツの編集 {#editing-content-in-experience-manager}

電子メールコンテンツは、Experience Managerで編集して、Adobe Campaign Standardの1つまたは複数の電子メールメッセージに使用できます。このドキュメント [](../../integrating/using/integrating-with-experience-manager.md)を参照してください。

### 電子メールデザインオプションの比較 {#email-design-options-comparison}

Adobe Campaignには、複数の電子メールオーサリングオプションがあります。以下の表に、それぞれの主な可能性、それぞれのメリットおよび制限を示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> 電子メールデザイナー<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>空白の電子メールを開始</strong><br /> </td> 
   <td> サポートされる<br /> </td> 
   <td> サポートされる<br /> </td> 
   <td> サポートされる<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLの書き込み</strong><br /> </td> 
   <td> サポートされる<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされる<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLの更新</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされる<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本的なパーソナライゼーション</strong><br /> </td> 
   <td> サポートされる<br /> </td> 
   <td> サポートされる<br /> </td> 
   <td> サポートされる<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高度なパーソナライゼーション</strong><br /> </td> 
   <td> サポートされる<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校正/プレビュー</strong><br /> </td> 
   <td> サポートされる<br /> </td> 
   <td> CampaignでのAEM<br /> 校正のプレビュー<br /> </td> 
   <td> キャンペーンでのプレビューと校正<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>製品リスト</strong><br /> </td> 
   <td> 電子メールトランザクションメッセージでサポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>メリット</strong><br /> </td> 
   <td> 
     - ドラッグ&amp;ドロップ操作による簡単な電子メール作成<br/>-レガシーコンテンツエディターと同様<br/>-フラグメントを使用した再利用可能なコンテンツ
  </td> 
   <td> 
     - 電子メール内のWebサイトからのアセットの再利用<br/>-電子メールコンテンツのExperience
 Managerの活用
    </td> 
   <td> 
    - 開発者が電子メールを直接コーディングするための機能<br/>-双方向の同期<br/>-
 Dreamweaverでのオフライン編集および後で同期<br/>-
 Dreamweaver経由での画像のAdobe Campaignへのアップロード
  </td> 
  </tr> 
  <tr> 
   <td> <strong>制限事項</strong><br /> </td> 
   <td> 
     - フラグメント内に条件付きコンテンツがない<br/>-
 Experience Managerフラグメントを使用できない
  </td> 
   <td> 
     - 高度なパーソナライゼーションの実装<br/>-
 Adobe Campaignでのテストの送信が必要
  </td> 
   <td> 動的コンテンツはサポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>オーディエンス</strong><br /> </td> 
   <td> ドラッグ&amp;ドロップ機能と組み合わせてHTMLコンポーネントを使用する柔軟性を保ちたいマーケティング担当者<br /> </td> 
   <td> ほとんどパーソナライゼーションのない標準の電子メールテンプレートを使用するExperience Managerを既に使用しているマーケティング担当者<br /> </td> 
   <td> 電子メールコンテンツをコード化し、Adobe Campaignと直接統合する開発者<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>詳しくは、</strong><br /> </td> 
   <td> 電子メールデザイナー <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">についてを参照してください</a><br /> </td> 
   <td> Experience Managerと <a href="../../integrating/using/integrating-with-experience-manager.md">の統合を参照してください</a><br /> </td> 
   <td> <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">DreamweaverとCampaignを参照</a> して、このビデオをご覧 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">ください</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

