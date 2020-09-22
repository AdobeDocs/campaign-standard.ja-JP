---
title: E メールデザイナーの概要
description: 電子メールデザイナーでの電子メールコンテンツの作成開始。
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
source-git-commit: b95a1990cfd8b4ce667c7cb2905af33a261c574b
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 5%

---

# E メールデザイナーの概要 {#quick-start}

電子メールデザイナーには、電子メールを作成する4つの方法があります。

電子メールデザイナーで、 [最初から次のように電子メールを作成できます](#without-existing-content)。

1. 構造とコンテンツコンポーネントを簡単に追加し **、コンテンツをパーソナライズして配信をすばやく送信することで、空白のキャンバスから電子メールを** 作成できます。 スタイル要素を完全に管理することもできます。 詳しくは、す [ぐに使い始めるか](#from-scratch-email) 、 [完全なドキュメントを参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. テンプレートを選択し、ここから新しい電子メールコンテンツを作成することで **、標準搭載のテンプレートから電子メールを** 作成できます。 [詳細情報](#building-content-from-an-out-of-the-box-template)

また、既存のコンテンツを [含む電子メールを作成することもできます](#with-existing-content)。

1. 既存のHTMLコンテンツ **を変換できます** （外部またはレガシーエディターで作成）。 [詳細情報](#converting-an-html-content)
1. 既存のHTMLコンテンツは、互換モードですぐに **読み込むことができます** 。 [詳細情報](#compatibility-mode)

| コンテンツなし | 内容付き |
|---|---|
| [ゼロからの電子メールの作成](#from-scratch-email) | [既存のHTMLコンテンツの変換](#converting-an-html-content) |
| [標準搭載のテンプレートからのコンテンツの作成](#building-content-from-an-out-of-the-box-template) | [既存のHTMLの読み込み](#compatibility-mode) |

## エディターを使用した電子メールのデザイン {#without-existing-content}

>[!NOTE]
>
>どちらの作成方法でも、電子メールを送信する前に件名を入力することが重要です。 件名を入力する方法 [追加を説明します](#add-a-subject-line)。

### ゼロからの電子メールの作成 {#from-scratch-email}

電子メールの作成、コンポーネントの追加、コンテンツのパーソナライズを簡単に行え、配信をすばやく送信できます。 必要に応じて、スタイル設定オプションをコンテンツに合わせることができます。 スタイル設定とインライン属性の管理について詳しくは、「電子メールスタイルの [編集](../../designing/using/styles.md)」を参照してください。

1. E メールの作成.
1. ホームページを閉じます。

### 件名行の追加 {#add-a-subject-line}

電子メールを送信する場合、件名行は必須です。 詳しくは、「電子メールの件名行の [定義](../../designing/using/subject-line.md)」を参照してください。

1. 「電子メールデザイナ」ホームページの **[!UICONTROL Properties]** タブ（ホームアイコンからアクセス可能）に移動し、 **[!UICONTROL Subject]** セクションに入力します。

![](assets/subject-line-quick-start.png)

### 構造コンポーネントの追加 {#add-structure-components}

構造コンポーネントは、電子メールのレイアウトを定義します。 詳しくは、「電子メールの構造の [定義](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」を参照してください。

構造コンポーネントで、使用するレイアウトのコンポーネントをドラッグ&amp;ドロップします。

>[!NOTE]
>
>電子メールに追加する様々なコンテンツレイアウトを選択できます。

![](assets/structure-components-quick-start.png)

### コンテンツコンポーネントの追加 {#add-content-components}

画像、テキスト、ボタンなど、電子メールに複数のコンテンツコンポーネントを追加できます。 詳しくは、「 [コンテンツコンポーネント](../../designing/using/designing-from-scratch.md#about-content-components)」を参照してください。

* **Image**

   1. 「 **Content Components**」で、構造コンポーネントの1つに画像をドラッグ&amp;ドロップします。
   1. 「 **参照**」をクリックします。
   1. コンピューターから画像ファイルを選択します。

   ![](assets/browse-image-quick-start.png)

* **パーソナライゼーションを含むテキスト**

   1. 「 **Content Components**」で、テキストを構造コンポーネントの1つにドラッグ&amp;ドロップします。
   1. コンポーネントをクリックし、テキストを入力します。
   1. 個人設定フィールドを追加するには、ツールバーの「個人設定フィールドを **挿入** 」をクリックします。
   1. 「名」など、必要なフィールドを選択します。

   ![](assets/edit-text-quick-start.png)

* **HTML**

   1. 「 **Content Components**」で、HTMLを構造コンポーネントの1つにドラッグ&amp;ドロップします。
   1. Click **Show the source code**.
   1. HTMLコンテンツを入力します。
   1. 「**保存**」をクリックします。

   ![](assets/html-component-source-code.png)

   HTMLに詳しい場合は、 **[!UICONTROL Html]** contentコンポーネントを使用して、元のフッターからHTMLコードをコピー&amp;ペーストできます。 For more on this, see [About content components](../../designing/using/designing-from-scratch.md#about-content-components).

   ![](assets/des_loading_compatible_fragment_9.png)

### 電子メールコンポーネントのスタイル設定

電子メールのスタイル設定は、例えば、コンポーネントのパディングを変更することで調整できます。 スタイル設定とインライン属性の管理について詳しくは、「電子メールスタイルの [編集](../../designing/using/styles.md)」を参照してください。

1. 「 **テキスト」コンポーネントをクリックします**。
1. 右側のパレットで「 **パディング**」に移動します。
1. ロックアイコンをクリックして、top、bottom、rightまたはleftの各パラメータ間の同期を解除します。
1. 必要に応じて **パディングを調整** 。
1. 「**保存**」をクリックします。

![](assets/padding-quick-start.png)

これで、電子メールを保存して送信できます。

### 標準搭載のテンプレートからのコンテンツの作成 {#building-content-from-an-out-of-the-box-template}

お客様のお知らせメッセージ、ニュースレター、電子メールの再エンゲージメントやパーソナライズなど、標準搭載されたテンプレートから電子メールを作成できます。

1. 電子メールを作成し、その内容を開きます。 For more on this, see [Creating an email](../../channels/using/creating-an-email.md).
1. ホームアイコンをクリックして、 **[!UICONTROL Email Designer]** ホームページにアクセスします。
1. タブをクリックし **[!UICONTROL Templates]** ます。
1. 標準搭載のHTMLテンプレートを選択します。
様々なテンプレートによって、複数の要素タイプの様々な組み合わせが表示されます。 例えば、「Feather」テンプレートには余白があり、「Astro」テンプレートには余白がありません。 詳しくは、「 [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates)」を参照してください。
1. 「電子メールデザイナ」ホームページの **[!UICONTROL Properties]** タブ（ホームアイコンからアクセス可能）に移動し、 **[!UICONTROL Subject]** セクションに入力します。
1. これらの要素を組み合わせて、多数の電子メールバリアントを作成できます。 例えば、構造コンポーネントを選択し、コンテキストツールバーからをクリックすることで、電子メールセクション **[!UICONTROL Duplicate]** を重複できます。
1. 左側の青い矢印を使用して要素を移動し、構造コンポーネントを別のコンポーネントの下または上にドラッグできます。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. また、構成部品を移動して各構造要素の構成を変更することもできます。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. 必要に応じて、各要素の内容を変更します。画像、テキスト、リンク。
1. 必要に応じて、スタイル設定オプションをコンテンツに合わせます。 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。

## 既存の電子メールコンテンツの使用 {#with-existing-content}

複数の電子メールで再利用できるモジュラー型テンプレートとフラグメントのフレームワークを構築する場合は、電子メールHTMLを電子メールデザイナーテンプレートに変換することを検討してください。

### HTMLコンテンツの変換 {#converting-an-html-content}

この使用例では、オファーがHTML電子メールをEmail Designerコンポーネントにすばやく変換できます。 このトピックについて詳しくは、「HTMLコンテンツの [変換](../../designing/using/using-existing-content.md#converting-an-html-content)」を参照してください。

>[!CAUTION]
>
>この節は、HTMLコードに詳しいユーザーを対象としています。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントは次の制限付きオプションで編集できます。インプレースエディションのみ実行できます。


### HTML電子メールの読み込みと編集 {#compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナのWYSIWYGエディターに完全に準拠し、編集できるように、コンテンツには特定のタグが含まれている必要があります。

既存の電子メールをDesigner互換の電子メールに変換する方法について詳しくは、 [この節を参照してください](../../designing/using/using-existing-content.md#compatibility-mode)。
