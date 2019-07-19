---
title: ランディングページコンテンツエディタのインターフェイス
seo-title: ランディングページコンテンツエディタのインターフェイス
description: ランディングページコンテンツエディタのインターフェイス
seo-description: アクションバーなどのエディターの様々なセクションを使用してランディングページのコンテンツを変更する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 53729a68- eed2-4c5d- bc14-02c80e897c44
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: editing- landing- page- content
discoiquuid: 08e2bda- e409-467f- b462- d74256dc6ebc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 76c3d473f6cc7e825fdabadeec2405cb5c13abd1

---


# Landing page content editor interface{#landing-page-content-editor-interface}

ランディングページのコンテンツエディターを使用すると、Adobe Campaignのコンテンツを簡単に定義、変更およびパーソナライズできます。To access it, click the **[!UICONTROL Content]** block in a landing page dashboard.

コンテンツエディターは3つのセクションに分かれています。これらのセクションでは、コンテンツを表示して編集することができます。

![](assets/des_lp_content_8.png)

1. The **palette** on the left-hand side of the screen allows you to modify the general options linked to a selected block. 変更できるオプションは次のとおりです。背景色、境界線、テキスト揃え、視認性条件などSee [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).
1. **アクションバー** には、ページの一般的なオプションが表示されます。テンプレートを選択して、表示モードを変更できます。[ランディングページエディタアクションバーを](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar)参照してください。
1. The main **editing zone** allows you to directly interact with the content using the contextual toolbar: insert a link into an image, change the font, delete a field, etc. [ランディングページエディタツールバーを](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar)参照してください。

## Landing page editor action bar {#landing-page-editor-action-bar}

アクションバーには、作成中のコンテンツを操作できる様々なボタンがあります。

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Icon<br /> </th> 
   <th> Button name<br /> </th> 
   <th> Channel<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">コンテンツの変更</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> あらかじめ用意されているコンテンツを選択したり、独自のHTMLコンテンツをインポートしたりできます。Refer to <a href="../../designing/using/selecting-an-existing-content.md">Loading an existing content</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">元に戻す</span><br /> </td> 
   <td> すべて<br /> </td> 
   <td> Cancels the last action carried out.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">やり直し</span><br /> </td> 
   <td> すべて<br /> </td> 
   <td> Redoes the last action that you canceled.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">ブロックを表示</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> Allows you to show the boxes around the content blocks (corresponds to the <strong>&lt;div&gt;</strong> HTML tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">ソースを表示</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> Allows you to show the HTML source code of the page.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Landing page editor toolbar {#landing-page-editor-toolbar}

The toolbar is a **contextual element** of the editor interface that offers various functionalities depending on the zone selected. テキストのスタイルを変更できるアクションボタンおよびボタンが含まれています。実行される変更は、常に選択したゾーンに適用されます。ブロックを選択すると、そのブロックを削除または複製できます。ブロック内のテキストを選択した後、そのブロックをリンクに変換したり、太字にしたりできます。

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>一部のツールバー関数では、HTMLコンテンツをフォーマットできます。However, if the page contains a CSS style sheet, the **instructions** from the style sheet may prove to take **priority** over the instructions specified via the toolbar.

<table> 
 <thead> 
  <tr> 
   <th> Icon<br /> </th> 
   <th> Button name<br /> </th> 
   <th> Context<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">外部 URL へのリンク</span> <br /> </td> 
   <td> Any element<br /> </td> 
   <td> URLへのリンクを追加できます。Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">ランディングページへのリンク</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> Adobe Campaignランディングページへのアクセスを許可します。Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">購読リンク</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> サービス購読リンクを挿入できます。Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">購読解除リンク</span> <br /> </td> 
   <td> Any element<br /> </td> 
   <td> サービスの購読解除リンクを挿入できます。Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">リンクを削除</span><br /> </td> 
   <td> リンク<br /> </td> 
   <td> Allows you to delete the link, as well as all the configurations linked to it, after confirming.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">パーソナライゼーションフィールドの挿入</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> データベースからコンテンツにフィールドを追加できます。Refer to <a href="../../designing/using/inserting-a-personalization-field.md">Inserting a personalization field</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">コンテンツブロックの挿入</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> コンテンツにパーソナライゼーションブロックを追加できます。Refer to <a href="../../designing/using/adding-a-content-block.md">Adding a content block</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">動的コンテンツの有効化</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> コンテンツに動的コンテンツを挿入できます。Refer to <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">Defining dynamic content</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">動的コンテンツの無効化</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to delete dynamic content.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Enlarge font</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Increases the size of the selected text (adds <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">フォントを減らす</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Reduces the size of the selected text (adds <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Bold</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Adds the bold style to the selected text (wraps the text with the <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> tags).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">斜体</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Adds the italic style to the selected text (wraps the text with the <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> tags).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">下線</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Underlines the selected text (wraps the selected text with the <strong>&lt;span style="text-decoration: underline;"&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">背景色の変更</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to change the background color of the block selected (adds style="background-color: rgba(170, 86, 255, 0.87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">フォントカラーの変更</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to change the color of all the text in the block or just the text selected in the block (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">画像</span><br /> </td> 
   <td> Block containing an image<br /> </td> 
   <td> Allows you to insert an image from a file saved locally.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">削除</span><br /> </td> 
   <td> Any block<br /> </td> 
   <td> Deletes the block and its content.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">複製</span><br /> </td> 
   <td> Any block<br /> </td> 
   <td> Duplicates the block including any styles linked to it.<br /> </td> 
  </tr> 
 </tbody> 
</table>

