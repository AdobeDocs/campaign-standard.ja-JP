---
title: E メールデザイナーの基本を学ぶ
description: メールDesignerを使用してメールコンテンツの作成を開始します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 47f53290-2190-4181-bcd5-e60287189c41
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 5%

---

# E メールデザイナーの基本を学ぶ {#quick-start}

E メールDesignerでは、4 とおりの方法でメールを作成できます。

メールを作成できます [&#x200B; メールDesignerで新しく開始します &#x200B;](#without-existing-content)。

1. 構造やコンテンツコンポーネントを簡単に追加し、コンテンツをパーソナライズして配信をすばやく送信することで **空のキャンバスからメールを作成** できます。 スタイル要素を完全に管理することもできます。 詳しくは、[&#x200B; すぐに使い始める &#x200B;](#from-scratch-email) または [&#x200B; 完全なドキュメント &#x200B;](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) を参照してください。

1. テンプレートを選択し、ここから新しいメールコンテンツを作成することで **標準テンプレートからメールを作成** できます。 [詳細情報](#building-content-from-an-out-of-the-box-template)

また、（既存のコンテンツを使用して [&#x200B; メールを作成することもでき &#x200B;](#with-existing-content) す。

1. （外部または従来のエディターで作成した **既存のHTMLコンテンツを変換** できます。 [詳細情報](#converting-an-html-content)
1. 互換モードでは、すぐに **既存のHTMLコンテンツを読み込む** ことができます。 [詳細情報](#compatibility-mode)

| コンテンツなし | コンテンツを使用 |
|---|---|
| [&#x200B; メールをゼロから作成 &#x200B;](#from-scratch-email) | [&#x200B; 既存のHTMLコンテンツの変換 &#x200B;](#converting-an-html-content) |
| [&#x200B; 標準テンプレートからのコンテンツの作成 &#x200B;](#building-content-from-an-out-of-the-box-template) | [&#x200B; 既存のHTMLの読み込み &#x200B;](#compatibility-mode) |

## エディターを使用したメールのデザイン {#without-existing-content}

>[!NOTE]
>
>どちらの作成戦略でも、メールを送信する前に件名を入力することが重要です。 詳細情報 [&#x200B; 件名行の追加 &#x200B;](#add-a-subject-line)

### メールをゼロから作成 {#from-scratch-email}

メールを簡単に作成し、コンポーネントを追加し、そのコンテンツをパーソナライズして、配信をすばやく送信できます。 必要に応じて、コンテンツに合わせてスタイルオプションを調整できます。 スタイル設定とインライン属性の管理について詳しくは、[&#x200B; メールスタイルの編集 &#x200B;](../../designing/using/styles.md) を参照してください。

1. メールを作成します。
1. ホームページを閉じます。

### 件名行の追加 {#add-a-subject-line}

件名は、メールを送信する際に必須です。 詳しくは、[&#x200B; メールの件名の定義 &#x200B;](../../designing/using/subject-line.md) を参照してください。

1. メールDesignerのホームページ（ホームアイコンからアクセスできます）の「**[!UICONTROL Properties]**」タブに移動し、「**[!UICONTROL Subject]**」セクションに入力します。

![](assets/subject-line-quick-start.png)

### 構造コンポーネントの追加 {#add-structure-components}

構造コンポーネントは、メールのレイアウトを定義します。 詳しくは、[&#x200B; メールの構造の定義 &#x200B;](../../designing/using/designing-from-scratch.md#defining-the-email-structure) を参照してください。

構造コンポーネントで、使用するレイアウトのコンポーネントをドラッグ&amp;ドロップします。

>[!NOTE]
>
>メールに追加される様々なコンテンツレイアウトを選択できます。

![](assets/structure-components-quick-start.png)

### コンテンツコンポーネントの追加 {#add-content-components}

画像、テキスト、ボタンなど、複数のコンテンツコンポーネントをメールに追加できます。 詳しくは、[&#x200B; コンテンツコンポーネント &#x200B;](../../designing/using/designing-from-scratch.md#about-content-components) を参照してください。

* **画像**

   1. **コンテンツコンポーネント** で、画像を構造コンポーネントのいずれかにドラッグ&amp;ドロップします。
   1. **参照** をクリックします。
   1. コンピューターから画像ファイルを選択します。

  ![](assets/browse-image-quick-start.png)

* **パーソナライゼーションを使用したテキスト**

   1. **コンテンツコンポーネント** で、テキストを構造コンポーネントのいずれかにドラッグ&amp;ドロップします。
   1. コンポーネントをクリックし、テキストを入力します。
   1. パーソナライゼーションフィールドを追加するには、ツールバーの **パーソナライゼーションフィールドを挿入** をクリックします。
   1. 必要なフィールド（「名」など）を選択します。

  ![](assets/edit-text-quick-start.png)

* **HTML**

   1. **コンテンツコンポーネント** で、HTMLを構造コンポーネントのいずれかにドラッグ&amp;ドロップします。
   1. **ソースコードを表示** をクリックします。
   1. HTMLコンテンツを入力します。
   1. 「**保存**」をクリックします。

  ![](assets/html-component-source-code.png)

  HTMLに詳しい場合は、**[!UICONTROL Html]** コンテンツコンポーネントを使用して、元のフッターからHTMLコードをコピーして貼り付けることができます。 詳しくは、[&#x200B; コンテンツコンポーネントについて &#x200B;](../../designing/using/designing-from-scratch.md#about-content-components) を参照してください。

  ![](assets/des_loading_compatible_fragment_9.png)

### メールコンポーネントのスタイル設定

コンポーネントのパディングを変更するなどして、メールのスタイル設定を調整できます。 スタイル設定とインライン属性の管理について詳しくは、[&#x200B; メールスタイルの編集 &#x200B;](../../designing/using/styles.md) を参照してください。

1. **テキストコンポーネント** をクリックします。
1. 右側のパレットで、**パディング** に移動します。
1. ロックアイコンをクリックすると、上下または左右のパラメーターの同期が解除されます。
1. 必要に応じて **パディング** を調整します。
1. 「**保存**」をクリックします。

![](assets/padding-quick-start.png)

これで、メールを保存して送信できます。

### 標準テンプレートからのコンテンツの作成 {#building-content-from-an-out-of-the-box-template}

顧客ウェルカムメッセージ、ニュースレター、リエンゲージメントメールなどの標準のテンプレートからメールを作成し、パーソナライズできます。

1. メールを作成し、そのコンテンツを開きます。 詳しくは、[&#x200B; メールの作成 &#x200B;](../../channels/using/creating-an-email.md) を参照してください。
1. ホームアイコンをクリックして、**[!UICONTROL Email Designer]** のホームページにアクセスします。
1. 「**[!UICONTROL Templates]**」タブをクリックします。
1. 標準のHTMLテンプレートを選択します。
様々なテンプレートには、複数のタイプの要素の様々な組み合わせが用意されています。 例えば、「羽」テンプレートには余白がありますが、「アストロ」テンプレートには余白がありません。 詳しくは、[&#x200B; コンテンツテンプレート &#x200B;](../../designing/using/using-reusable-content.md#content-templates) を参照してください。
1. メールDesignerのホームページ（ホームアイコンからアクセスできます）の「**[!UICONTROL Properties]**」タブに移動し、「**[!UICONTROL Subject]**」セクションに入力します。
1. これらの要素を組み合わせて、多数の E メールバリアントを作成できます。 例えば、構造コンポーネントを選択し、コンテキストツールバーから「複製」をクリックして、メールセクション **[!UICONTROL Duplicate]** 複製できます。
1. 左側の青い矢印を使用して要素を移動し、構造コンポーネントを別のコンポーネントの下または上にドラッグできます。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. また、コンポーネントを移動して、各構造要素の組織を変更することもできます。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. 必要に応じて、画像、テキスト、リンクの各要素のコンテンツを変更します。
1. 必要に応じて、コンテンツに合わせてスタイルオプションを調整します。 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。

## 既存のメールコンテンツの使用 {#with-existing-content}

複数のメールで再利用できるように組み合わせることができるモジュール型テンプレートおよびフラグメントのフレームワークを構築する場合は、メールテンプレートをメールDesignerHTMLに変換することを検討する必要があります。

### HTMLコンテンツの変換 {#converting-an-html-content}

このユースケースは、HTMLメールをメールDesignerコンポーネントに簡単に変換する方法を提供します。 このトピックについて詳しくは、[HTMLコンテンツの変換 &#x200B;](../../designing/using/using-existing-content.md#converting-an-html-content) を参照してください。

>[!CAUTION]
>
>この節は、HTMLコードを熟知しているユーザーを対象としています。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントも編集可能で、オプションは限られています。つまり、インプレース編集のみを実行できます。


### HTMLメールの読み込みと編集 {#compatibility-mode}

コンテンツをアップロードする場合、電子メールDesignerのWYSIWYG エディターに完全に準拠し編集可能にするには、特定のタグが含まれている必要があります。

既存のメールをメールDesigner互換のメールに変換する方法については、[&#x200B; この節 &#x200B;](../../designing/using/using-existing-content.md#compatibility-mode) を参照してください。
