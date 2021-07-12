---
solution: Campaign Standard
product: campaign
title: '従来のエディターによるEメールからEメールデザイナーへの変換 '
description: 従来のエディター電子メールで作成された電子メールを電子メールデザイナーに使用する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Eメールデザイン
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 8%

---

# レガシーエディターのEメールコンテンツの変換 {#converting-an-html-content}

Eメールデザイナーと連携し、レガシーエディターで作成したEメールHTMLから、再利用可能なテンプレートやフラグメントを構築します。

この使用例では、HTML Eメールを使用し、EメールデザイナーでHTMLコンポーネントに分割することで、Eメールデザイナーテンプレートを作成できます。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントは制限付きオプションで編集できます。インプレース編集のみ実行できます。

>[!IMPORTANT]
>
>この節は、HTMLコードに詳しい上級ユーザー向けです。

## Eメールコンテンツの準備

1. HTML電子メールを選択します。
1. HTML Eメールを分割するセクションを特定します。
1. HTMLから様々なブロックを切り出します。

## Eメール構造の作成

1. **[!UICONTROL Email Designer]**&#x200B;を開いて、空のEメールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。
1. 構造コンポーネントをセクションと同じ数だけ追加します。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。

## HTMLコンテンツの追加

1. 各構造コンポーネントにHTMLコンポーネントを追加します。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. HTMLをすべてのコンポーネントにコピー&amp;ペーストします。

## Eメールのスタイルを管理する {#manage-the-style-of-your-email}

1. **[!UICONTROL Mobile view]**&#x200B;に切り替えます。 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

1. これを修正するには、ソースコードモードに切り替えて、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。 例：

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
   >別のカスタムスタイルタグで、この後にスタイルを追加してください。
   >
   >Eメールデザイナーで生成されるCSSを変更しないでください。
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. モバイルビューに戻って、コンテンツが正しく表示されていることを確認し、変更を保存します。

## 使用例

レガシーエディターで作成したこのEメールを&#x200B;**[!UICONTROL Email Designer]**&#x200B;テンプレートに変換してみましょう。

### Eメールのセクションを特定する

このEメールで11のセクションを特定できます。

![](assets/html-dce-view-mail.png)

HTMLのどのセクションかを識別するには、要素を選択します。

![](assets/breadcrumbs.png)

EメールのHTMLバージョンを確認するには、**[!UICONTROL Show source]**&#x200B;をクリックします。

### Eメールテンプレートとその構造の作成

1. **[!UICONTROL Structure components]**&#x200B;をドラッグ&amp;ドロップして、電子メールのレイアウトを反映します。

1. 必要な回数だけ繰り返します。 11個の構造コンポーネントを作成する必要があります。

   ![](assets/structure-components-migration.png)

### HTMLコンテンツコンポーネントの挿入

1. 各&#x200B;**[!UICONTROL Structure component]**&#x200B;に&#x200B;**[!UICONTROL HTML component]**&#x200B;を挿入します。

   ![](assets/html-components.png)

1. 各セクションで、「 **[!UICONTROL Show source code]** 」をクリックします。

   ![](assets/show-source-code.png)

1. HTMLセクションを挿入します。

1. 「**[!UICONTROL Save]**」をクリックします。

これで、Eメールのレンダリングを確認できます。

![](assets/migrated-email-result.png)

### モバイルビューに合わせたスタイルの管理

1. CSS要素を挿入して、電子メールがモバイル表示に適していることを確認します。

1. ソースコードに切り替え、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。

詳しくは、[Eメールのスタイルの管理](#manage-the-style-of-your-email)を参照してください。

従来のEメールがEメールデザイナーで使用できるようになりました。
