---
title: 電子メールデザイナーを使い始める
description: 電子メールデザイナーで電子メールコンテンツの作成を開始します。
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
source-git-commit: f8b763ab70514563ab48b0233300e9dda0fba18c

---

# 電子メールデザイナーを使い始める {#quick-start}

電子メールデザイナーでは、4つの方法で電子メールを作成できます。

電子メールデザイナーで、 [新規に電子メールを作成できます](#without-existing-content)。

* 空白のキャンバスから電子メールを作成するには、構造やコンテンツコンポーネントを簡単に追加し、コンテンツをパーソナライズしてすばやく配信を送信します。 また、スタイル要素を完全に管理することもできます。 詳しくは、すばやく使い始める [か、完全なドキュメント](#from-scratch-email) を参照 [してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

* テンプレートを選択し、ここから新しい電子メールコンテンツを作成することで、標準搭載されたテンプレートから電子メールを作成できます。 [さらに詳しく](#building-content-from-an-out-of-the-box-template)

また、既存のコンテンツを使用して電子メ [ールを作成できます](#with-existing-content)。

* 既存のHTMLコンテンツは、（外部で作成したり、レガシーエディターで作成した）変換できます。 [さらに詳しく](#converting-an-html-content)
* 既存のHTMLコンテンツは、互換モードですぐに読み込むことができます。 [さらに詳しく](#compatibility-mode)

| コンテンツなし | コンテンツあり |
|---|---|
| [新規での電子メールの作成](#from-scratch-email) | [既存のHTMLコンテンツの変換](#converting-an-html-content) |
| [標準搭載のテンプレートからのコンテンツの作成](#building-content-from-an-out-of-the-box-template) | [既存のHTMLの読み込み](#compatibility-mode) |

## エディターを使用した電子メールのデザイン {#without-existing-content}

### 新規での電子メールの作成 {#from-scratch-email}

簡単に電子メールを作成し、コンポーネントを追加し、コンテンツをパーソナライズして、すばやく配信できます。 必要に応じて、コンテンツに合わせてスタイル設定オプションを調整できます。 スタイル設定とインライン属性の管理について詳しくは、「電子メールスタイルの編 [集」を参照してくださ](../../designing/using/styles.md)い。

### 件名行の追加 {#add-a-subject-line}

件名は電子メールの送信時に必須です。 詳しくは、「電子メールの件 [名行の定義」を参照してください](../../designing/using/subject-line.md)。

1. 電子メールを作成します。
1. ホームページを閉じます。
1. 電子メールデ **[!UICONTROL Properties]** ザイナのホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。

![](assets/subject-line-quick-start.png)

### 構造コンポーネントの追加 {#add-structure-components}

構造コンポーネントは、電子メールのレイアウトを定義します。 詳しくは、「電子メール [の構造の定義」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

構造コンポーネントで、使用するレイアウトのコンポーネントをドラッグ&amp;ドロップします。

>[!NOTE]
>
>電子メールに追加する様々なコンテンツレイアウトを選択できます。

![](assets/structure-components-quick-start.png)

### コンテンツコンポーネントの追加 {#add-content-components}

画像、テキスト、ボタンなど、電子メールに複数のコンテンツコンポーネントを追加できます。 詳しくは、「コンテンツコンポーネント」を [参照してくださ](../../designing/using/designing-from-scratch.md#about-content-components)い。

* **画像**

1. 「コンテ **ンツコンポーネント**」で、構造コンポーネントの1つに画像をドラッグ&amp;ドロップします。
1. 「参照」をク **リックしま**&#x200B;す。
1. コンピューターから画像ファイルを選択します。

![](assets/browse-image-quick-start.png)

* **パーソナライゼーションを含むテキスト**

1. 「コンテ **ンツコンポーネント**」で、構造コンポーネントの1つにテキストをドラッグ&amp;ドロップします。
1. コンポーネントをクリックし、テキストを入力します。
1. パーソナライゼーションフィールドを追加するには、ツールバー **の「パーソナライゼーション** ・フィールドの挿入」をクリックします。
1. 「名」など、必要なフィールドを選択します。

![](assets/edit-text-quick-start.png)

* **HTML**

1. 「 **Content Components**」で、HTMLを構造コンポーネントの1つにドラッグ&amp;ドロップします。
1. 「ソース **コードを表示」をクリックします**。
1. HTMLコンテンツを入力します。
1. 「**保存**」をクリックします。

![](assets/html-component-source-code.png)

HTMLに詳しい場合は、コンテンツコンポーネントを使用して、元のフッターからHTMLコードをコピー&amp;ペースト **[!UICONTROL Html]** できます。 For more on this, see [About content components](../../designing/using/designing-from-scratch.md#about-content-components).

![](assets/des_loading_compatible_fragment_9.png)

### 電子メールコンポーネントのスタイル設定

例えば、コンポーネントのパディングを変更することで、電子メールのスタイルを調整できます。 スタイル設定とインライン属性の管理について詳しくは、「電子メールスタイルの編 [集」を参照してくださ](../../designing/using/styles.md)い。

1. 「テキスト」コンポーネン **トをクリックしま**&#x200B;す。
1. 右側のパレットで「パディング」に移動し **ます**。
1. 上下左右のパラメーターの同期を解除するには、ロックアイコンをクリックします。
1. 必要に応 **じて** 、パディングを調整します。
1. 「**保存**」をクリックします。

![](assets/padding-quick-start.png)

これで、電子メールを保存して送信できます。

### 標準搭載のテンプレートからのコンテンツの作成 {#building-content-from-an-out-of-the-box-template}

お客様のお知らせメッセージ、ニュースレター、再契約の電子メールなど、すぐに使えるテンプレートから電子メールを作成し、それらをパーソナライズすることができます。

1. 電子メールを作成し、その内容を開きます。 詳しくは、「電子メールの作成」を [参照してください](../../channels/using/creating-an-email.md)。
1. ホームアイコンをクリックして、ホームページに **[!UICONTROL Email Designer]** アクセスします。
1. Click the **[!UICONTROL Templates]** tab.
1. 標準搭載のHTMLテンプレートを選択します。
様々なテンプレートは、複数の要素の様々な組み合わせを表します。 例えば、「Feather」テンプレートには余白があり、「Astro」テンプレートには余白がありません。 詳しくは、「コンテンツテンプレート」を参 [照してください](../../designing/using/using-reusable-content.md#content-templates)。
1. 電子メールデ **[!UICONTROL Properties]** ザイナのホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。
1. これらの要素を組み合わせて、多くの電子メールバリアントを作成できます。 例えば、構造コンポーネントを選択し、コンテキストツールバーからをクリックして、電子メールセク **[!UICONTROL Duplicate]** ションを複製できます。
1. 左側の青い矢印を使用して要素を移動し、構造コンポーネントを別のコンポーネントの下または上にドラッグできます。 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. また、コンポーネントを移動して、各構造要素の構成を変更することもできます。 詳しくは、フラグメントとコンポーネ [ントの追加を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 必要に応じて、各要素の内容を変更します。画像、テキスト、リンク。
1. 必要に応じて、スタイル設定オプションをコンテンツに合わせます。 For more on this, see [Editing email styles](../../designing/using/styles.md).

## 既存の電子メールコンテンツの使用 {#with-existing-content}

複数の電子メールで再利用できるモジュラー型テンプレートとフラグメントのフレームワークを構築する場合は、電子メールHTMLを電子メールデザイナーテンプレートに変換することを検討してください。

### HTMLコンテンツの変換 {#converting-an-html-content}

この使用例では、HTML電子メールを電子メールデザイナーコンポーネントにすばやく変換できます。

>[!CAUTION]
>
>この節は、HTMLコードに詳しいユーザーを対象としています。

>[!NOTE]
>
>互換性モードと同様に、HTMLコンポーネントは次の制限付きオプションで編集できます。インプレースエディションのみを実行できます。

電子メールデザイナーの外部で、元のHTMLが再利用可能なセクションに分割されていることを確認します。

1. 電子メールデザイナーを開いて、空の電子メールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など For more on this, see [Editing email styles](../../designing/using/styles.md).

そうでない場合は、HTMLの異なるブロックを切り取ってください。 例えば、次の節は明確に識別されます。

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

すべてのブロックを特定したら、電子メールデザイナで、既存の電子メールの各セクションに対して次の手順を繰り返します。

1. 構造コンポーネントを追加します。 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. HTMLコンポーネントを追加します。 詳しくは、フラグメントとコンポーネ [ントの追加を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. HTMLをそのコンポーネントにコピー&amp;ペーストします。
1. モバイルビューに切り替えます。 For more on this, see [this section](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   CSSが見つからないので、レスポンシブビューが壊れています。

1. これを修正するには、ソースコードモードに切り替えて、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。 次に例を示します。

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
   >この後に、別のカスタムスタイルタグでスタイルを追加してください。
   >
   >電子メールデザイナーが生成したCSSは変更しないでください。
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. モバイルビューに戻って、コンテンツが正しく表示されていることを確認し、変更を保存します。

### HTML電子メールの読み込みと編集 {#compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナーのWYSIWYGエディターに完全に準拠し、編集可能な特定のタグがコンテンツに含まれている必要があります。

アップロードされたHTMLのすべてまたは一部が期待されたタグ付けに準拠していない場合、コンテンツは「互換性モード」で読み込まれ、UIを使用した編集の可能性が制限されます。

コンテンツが互換モードで読み込まれても、インターフェイスを通じて次の変更を行うことができます（使用できないアクションは非表示になります）。

* テキストの変更または画像の変更
* リンクとパーソナライゼーションフィールドの挿入
* 選択したHTMLブロックのスタイル設定オプションの一部を編集
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

電子メールに新しいセクションを追加したり、高度なスタイル設定を行ったりするなど、その他の変更は、電子メールのソースコードでHTMLモードを使用して直接行う必要があります。
互換性モードではドラッグ&amp;ドロップを使用できませんが、レガシーエディターと同じ機能セットが保証されます。

既存の電子メールを電子メールデザイナー互換の電子メールに変換する方法について詳しくは、この節を参 [照してくださ](../../designing/using/using-existing-content.md)い。
