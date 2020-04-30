---
title: 電子メールデザイナーの概要
description: 開始が電子メールデザイナーで電子メールコンテンツを作成する。
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
source-git-commit: 6aa48a9f36e0716b036288862d1a0064e489be92

---

# 電子メールデザイナーの概要 {#quick-start}

電子メールデザイナーでは、4つの方法で電子メールを作成できます。

電子メールデザイナーで、 [新規に電子メールを作成できます](#without-existing-content)。

1. 空白のキャン **バスから電子メールを作成するには** 、構造とコンテンツコンポーネントを簡単に追加し、コンテンツをパーソナライズして配信を迅速に送信します。 また、スタイル要素を完全に管理することもできます。 詳しくは、すばやく使い始め [るか](#from-scratch-email) 、完全なドキュメントを参 [照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. テンプレート **を選択し、ここから新しい電子メールコンテンツを作成することで** 、標準搭載のテンプレートから電子メールを作成できます。 [さらに詳しく](#building-content-from-an-out-of-the-box-template)

また、既存のコンテンツを使用して電子メ [ールを作成できます](#with-existing-content)。

1. 既存のHTMLコ **ンテンツ(外部で作成した** 、またはレガシーエディターで作成した)を変換できます。 [さらに詳しく](#converting-an-html-content)
1. 既存のHTMLコ **ンテンツは互換モードで** 、すぐに読み込むことができます。 [さらに詳しく](#compatibility-mode)

| コンテンツなし | コンテンツあり |
|---|---|
| [新規での電子メールの作成](#from-scratch-email) | [既存のHTMLコンテンツの変換](#converting-an-html-content) |
| [標準搭載のテンプレートからのコンテンツの作成](#building-content-from-an-out-of-the-box-template) | [既存のHTMLの読み込み](#compatibility-mode) |

## エディターを使用した電子メールのデザイン {#without-existing-content}

>[!NOTE]
>
>どちらの作成方法でも、電子メールを送信する前に件名を入力することが重要です。 件名を入力する [追加方法を説明します](#add-a-subject-line)。

### 新規での電子メールの作成 {#from-scratch-email}

電子メールの作成、コンポーネントの追加、コンテンツのパーソナライズを簡単に行い、配信を迅速に送信できます。 必要に応じて、コンテンツに合わせてスタイル設定オプションを調整できます。 スタイル設定とインライン属性の管理について詳しくは、「電子メールスタイルの編 [集」を参照してくださ](../../designing/using/styles.md)い。

1. 電子メールを作成します。
1. ホームページを閉じます。

### 件名行の追加 {#add-a-subject-line}

件名行は電子メールの送信時に必須です。 詳しくは、「電子メールの件 [名行の定義」を参照してください](../../designing/using/subject-line.md)。

1. 「電子メールデ **[!UICONTROL Properties]** ザイナ」ホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。

![](assets/subject-line-quick-start.png)

### 構造コンポーネントの追加 {#add-structure-components}

構造コンポーネントは、電子メールのレイアウトを定義します。 詳しくは、「電子メールの [構造の定義」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

構造コンポーネントで、使用するレイアウトのコンポーネントをドラッグ&amp;ドロップします。

>[!NOTE]
>
>電子メールに追加する異なるコンテンツレイアウトを選択できます。

![](assets/structure-components-quick-start.png)

### コンテンツコンポーネントの追加 {#add-content-components}

画像、テキスト、ボタンなど、複数のコンテンツコンポーネントを電子メールに追加できます。 詳しくは、「コンテンツコンポーネント」を [参照してくださ](../../designing/using/designing-from-scratch.md#about-content-components)い。

* **画像**

1. 「コンテ **ンツコンポーネント**」で、構造コンポーネントの1つに画像をドラッグ&amp;ドロップします。
1. 「参照」をク **リックしま**&#x200B;す。
1. コンピューターから画像ファイルを選択します。

![](assets/browse-image-quick-start.png)

* **パーソナライゼーションを含むテキスト**

1. 「コンテ **ンツコンポーネント**」で、テキストを構造コンポーネントの1つにドラッグ&amp;ドロップします。
1. コンポーネントをクリックし、テキストを入力します。
1. パーソナライゼーションフィールドを追加するには、ツールバ **ーの「パーソナライゼーション** ・フィールドを挿入」をクリックします。
1. 「名」など、必要なフィールドを選択します。

![](assets/edit-text-quick-start.png)

* **HTML**

1. 「コンテ **ンツコンポーネント**」で、HTMLを構造コンポーネントの1つにドラッグ&amp;ドロップします。
1. 「ソース **コードを表示」をクリックしま**&#x200B;す。
1. HTMLコンテンツを入力します。
1. 「**保存**」をクリックします。

![](assets/html-component-source-code.png)

HTMLに詳しい場合は、コンテンツコンポーネントを使用して、元のフッターからHTMLコードをコピー&amp;ペースト **[!UICONTROL Html]** できます。 For more on this, see [About content components](../../designing/using/designing-from-scratch.md#about-content-components).

![](assets/des_loading_compatible_fragment_9.png)

### 電子メールコンポーネントのスタイル設定

例えば、コンポーネントのパディングを変更することで、電子メールのスタイルを調整できます。 スタイル設定とインライン属性の管理について詳しくは、「電子メールスタイルの編 [集」を参照してくださ](../../designing/using/styles.md)い。

1. 「テキスト」コンポーネン **トをクリックしま**&#x200B;す。
1. 右側のパレットで、「パディング」に移動し **ます**。
1. 上下左右のパラメーターの同期を解除するには、ロックアイコンをクリックします。
1. 必要に応 **じて** 、パディングを調整します。
1. 「**保存**」をクリックします。

![](assets/padding-quick-start.png)

これで、電子メールを保存して送信できます。

### 標準搭載のテンプレートからのコンテンツの作成 {#building-content-from-an-out-of-the-box-template}

お客様のご案内のメッセージ、ニュースレター、再関与の電子メールなど、あらかじめ用意されているテンプレートから電子メールを作成し、それらをパーソナライズできます。

1. 電子メールを作成し、その内容を開きます。 For more on this, see [Creating an email](../../channels/using/creating-an-email.md).
1. ホームアイコンをクリックして、アイコンにアクセス **[!UICONTROL Email Designer]** します。
1. タブをクリッ **[!UICONTROL Templates]** クします。
1. 標準搭載のHTMLテンプレートを選択します。
様々なテンプレートには、複数の要素の様々な組み合わせが表示されます。 例えば、「Feather」テンプレートには余白があり、「Astro」テンプレートには余白がありません。 詳しくは、「コンテンツテンプレート」を参 [照してくださ](../../designing/using/using-reusable-content.md#content-templates)い。
1. 「電子メールデ **[!UICONTROL Properties]** ザイナ」ホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。
1. これらの要素を組み合わせて、多数の電子メールのバリエーションを作成できます。 例えば、構造コンポーネントを重複し、コンテキストツールバーからをクリックすることで、電子メ **[!UICONTROL Duplicate]** ールセクションを選択できます。
1. 左側の青い矢印を使用して、構造コンポーネントを別のコンポーネントの下または上にドラッグし、要素を移動できます。 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. また、構成部品を移動して、各構造要素の構成を変更することもできます。 詳しくは、フラグメントとコンポーネ [ントの追加を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 必要に応じて、各要素の内容を変更します。画像、テキスト、リンク。
1. 必要に応じて、コンテンツに合わせてスタイル設定オプションを調整します。 For more on this, see [Editing email styles](../../designing/using/styles.md).

## 既存の電子メールコンテンツの使用 {#with-existing-content}

複数の電子メールで再利用するために組み合わせることができるモジュール式のテンプレートとフラグメントのフレームワークを構築する場合は、電子メールのHTMLを電子メールデザイナーのテンプレートに変換することを検討してください。

### HTMLコンテンツの変換 {#converting-an-html-content}

この使用例では、オファーがHTML電子メールを電子メールデザイナーのコンポーネントに変換する簡単な方法を使用します。 このトピックについて詳しくは、HTMLコンテンツの変 [換を参照してください](../../designing/using/using-existing-content.md#converting-an-html-content)。

>[!CAUTION]
>
>この節は、HTMLコードに詳しいユーザーを対象としています。

>[!NOTE]
>
>互換性モードと同様に、HTMLコンポーネントは、次の制限付きオプションで編集できます。インプレースエディションのみ実行できます。


### HTML電子メールの読み込みと編集 {#compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナーのWYSIWYGエディターで完全に準拠し、編集できるように、特定のタグが含まれている必要があります。

既存の電子メールを電子メールデザイナー互換の電子メールに変換する方法について詳しくは、この節を参 [照してくださ](../../designing/using/using-existing-content.md#compatibility-mode)い。
