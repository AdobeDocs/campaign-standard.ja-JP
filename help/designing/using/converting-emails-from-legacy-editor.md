---
title: 'レガシーエディターの電子メールの電子メールデザイナーへの変換 '
description: レガシーエディターの電子メールで作成した電子メールを電子メールデザイナーに送信する方法を確認します。
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
source-git-commit: 1de0f5362f3c77fec4b66e330a2d2723f4a0f212

---


# レガシーエディターの電子メールコンテンツの変換 {#converting-an-html-content}

開始は、電子メールデザイナーで作業し、レガシーエディターで作成した電子メールのHTMLから、再利用可能なテンプレートやフラグメントを作成します。

この使用例では、HTML電子メールを使用して電子メールデザイナーテンプレートを作成し、電子メールデザイナーでHTMLコンポーネントに分割できます。

>[!CAUTION]
>
>この節は、HTMLコードに詳しい上級ユーザーを対象としています。

>[!NOTE]
>
>互換性モードと同様に、HTMLコンポーネントは、次の制限付きオプションで編集できます。インプレースエディションのみ実行できます。

## 電子メールの内容の準備

1. HTML電子メールを選択します。
1. HTML電子メールを分割するセクションを指定します。
1. HTMLの様々なブロックを切り抜きます。

## 電子メールの構造を作成する

1. を開いて、空 **[!UICONTROL Email Designer]** の電子メールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など For more on this, see [Editing email styles](../../designing/using/styles.md).
1. 断追加面と同じ数の構造コンポーネント 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

## 追加HTMLコンテンツ

1. 各構追加造コンポーネントのHTMLコンポーネント。 詳しくは、フラグメントとコンポーネ [ントの追加を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. HTMLをすべてのコンポーネントにコピー&amp;ペーストします。

## 電子メールのスタイルを管理します {#manage-the-style-of-your-email}

1. Switch to **[!UICONTROL Mobile view]**. 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

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
   >電子メールデザイナーで生成されたCSSは変更しないでください。
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. モバイル表示に戻って、コンテンツが正しく表示されていることを確認し、変更を保存します。

## 使用例

レガシーエディターで作成したこの電子メールをテンプレートに変換してみま **[!UICONTROL Email Designer]** しょう。

## 電子メールのセクションを特定する

この電子メールの11のセクションを特定できます。

![](assets/html-dce-view-mail.png)

HTMLのどのセクションかを識別するために、要素を選択できます。

![](assets/breadcrumbs.png)

電子メールのHTMLバージョンを表示するには、をクリックしま **[!UICONTROL Show source]**&#x200B;す。

### 電子メールテンプレートとその構造を作成する

1. 電子メールのレイアウト **[!UICONTROL Structure Components]** を反映してドラッグ&amp;ドロップします。

11個の構造部品を作る必要があります

![](assets/structure-components-migration.png)

### HTMLコンテンツコンポーネントの挿入

1. の各内にを **[!UICONTROL HTML component]** 挿入しま **[!UICONTROL structure component]** す。

![](assets/html-components.png)

1. 各セクションのをクリックしま **[!UICONTROL Show source code]** す。

![](assets/show-source-code.png)

1. HTMLセクションを挿入します。

1. クリック **[!UICONTROL Save]** .

これで、電子メールのレンダリングを確認できます。

![](assets/migrated-email-result.png)

### モバイル表示

CSS要素を挿入して、電子メールがモバイル表示に適していることを確認します。

1. ソースコードに切り替え、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。

詳しくは、「電子メールのスタイ [ルの管理」を参照してください](#manage-the-style-of-your-email)。

従来の電子メールが電子メールデザイナーで使用できるようになりました。