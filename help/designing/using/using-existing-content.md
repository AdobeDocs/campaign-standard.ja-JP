---
solution: Campaign Standard
product: campaign
title: '既存のコンテンツを使用した電子メールのデザイン '
description: 電子メールデザイナーで既存のコンテンツの電子メールコンテンツを使用して電子メールをデザインする方法を確認します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 6%

---

# 既存のコンテンツを使用したデザイン{#designing-using-existing-content}

## 既存のコンテンツの選択{#selecting-an-existing-content}

Adobe Campaignには、作業を開始する際に役立つ定義済みのコンテンツのセットが用意されています。 これらのいずれかを使用することも、送信する必要があるメッセージの内容がAdobe Campaign以外で準備されている場合は、コンピューターまたはURLから読み込むこともできます。

電子メールやランディングページを作成する場合、既存のコンテンツを別のソースから読み込むよう選択できます。

>[!NOTE]
>
>次の画像は、[電子メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)を使用して既存のコンテンツを読み込む方法を示しています。

1. 電子メールまたはランディングページを作成したら、その内容を開きます。
1. ホームアイコンをクリックして&#x200B;**[!UICONTROL Email Designer]**&#x200B;ホームページにアクセスします。

   ![](assets/des_loading_1.png)

1. 読み込むコンテンツのソースを選択します。

   * [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates):タ **[!UICONTROL Templates]** ブをクリックします。
   * [新規コンテンツ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)、新規開始コンテンツ：ボタンをクリックし **[!UICONTROL Create]** ます。
   * [コンピューター上のZIPまたはHTMLファイル](#importing-content-from-a-file):ボタンをクリックし **[!UICONTROL Upload]** ます。
   * [既存のURL](#importing-content-from-a-url) （電子メールのみ）のコンテンツ：ボタンをクリックし **[!UICONTROL Import from URL]** ます。

   ![](assets/des_loading_2.png)

1. コンテンツを読み込みます。 選択したコンテンツが現在のコンテンツを置き換えます。

   読み込んだコンテンツは、編集したり、パーソナライズしたりできます。

   >[!NOTE]
   >
   >[電子メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)は、特定のタグ付けを使用します。 キャンペーンにアップロードする標準のHTMLコンテンツは、電子メールデザイナーでの完全な互換性と編集が可能なタグと一致している必要があります。 一致しない場合、コンテンツは[互換モード](#compatibility-mode)にアップロードされます。 既存のコンテンツを互換性を持たせるには、[このセクション](#editing-existing-contents-with-the-email-designer)を参照してください。

**関連トピック：**

* [E メールの作成](../../channels/using/creating-an-email.md)
* [ランディングページの管理](../../channels/using/getting-started-with-landing-pages.md)

## 電子メールデザイナでの既存のコンテンツの編集{#editing-existing-contents-with-the-email-designer}

[電子メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)の編集機能を最大限に活用するには、アップロードしたHTMLに、WYSIWYGエディターに準拠する特定のタグを含める必要があります。

HTMLのすべてまたは一部にこのタグが付いていない場合、コンテンツは&#39;[互換モード](#compatibility-mode)&#39;に読み込まれます。

既存の外部コンテンツを電子メールデザイナー内で編集可能にするには、「[既存のコンテンツを使用した電子メールのデザイン](../../designing/using/using-existing-content.md)」の節を参照してください。

## 既存の電子メールコンテンツのインポート{#importing}

### ファイル{#importing-content-from-a-file}からのコンテンツの読み込み

電子メールデザイナーホームページで、「**[!UICONTROL Upload]**」ボタンをクリックしてコンピューターからファイルをアップロードし、確認します。

zipファイル構造に制限はありません。 ただし、HTMLファイルの参照は、zipフォルダーのツリー構造に従って相対パスで行う必要があります。

読み込みでは、次の形式がサポートされています。

* スタイルシートが組み込まれたHTMLファイル
* HTMLファイル、スタイルシート(.CSS)、画像を含む.zipフォルダー

>[!NOTE]
>
>電子メールコンテンツの場合は、スタイルシートを組み込んだ1つのHTMLファイルを読み込むことをお勧めします。

#### URLからのコンテンツの読み込み{#importing-content-from-a-url}

URLからコンテンツを読み込む前に、次の要件を満たしていることを確認してください。

* コンテンツは、このURLで公開されている必要があります。
* セキュリティ上の理由から、**[!UICONTROL https]**&#x200B;で始まるURLのみ使用できます。
* すべてのリソース（画像、CSS）が絶対リンクとHTTPSで設定されていることを確認します。 そうしないと、電子メールを送信した後、ミラーページにリソースが表示されません。 絶対リンク定義の例を次に示します。

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>URLからのコンテンツの読み込みは、電子メールチャネルでのみ可能です。

URLから既存のコンテンツを取得するには、次の手順に従います。

1. 電子メールデザイナホームページから&#x200B;**[!UICONTROL Import from URL]**&#x200B;ボタンを選択します。

   ![](assets/email_designer_importfromurl.png)

1. コンテンツの取得元となるURLを定義します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

この機能をビデオで確認.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)で参照できます。

### 準備時にURLからコンテンツを自動的に取得{#retrieving-content-from-a-url-automatically-at-preparation-time}

メッセージの準備中にURLからコンテンツを読み込むと、電子メールが準備されるたびに最新のHTMLコンテンツを取得できます。 これにより、定期的な電子メールのコンテンツは、送信時に常に最新の状態になります。 また、この機能を使用すると、コンテンツの準備ができていない場合でも、特定の日にスケジュールされたメッセージを作成できます。

準備時にコンテンツを取得するには、次の手順に従います。

1. **[!UICONTROL Content imported during preparation]**&#x200B;オプションを選択します。

   ![](assets/email_designer_importfromurl2.png)

1. URLコンテンツは、読み取り専用としてエディターに表示されます。

   >[!CAUTION]
   >
   >この手順では、コンテンツエディターでのHTML表示を考慮しないでください。 準備段階で取り出します。

1. 取得したURLコンテンツをプレビューするには、メッセージの作成後に開き、「**[!UICONTROL Preview]**」ボタンをクリックします。

コンテンツの取得元となるリモートURLをパーソナライズできます。 これをおこなうには、以下の手順に従います。

1. 画面上部の電子メールラベルをクリックして、「電子メールデザイナ&#x200B;**[!UICONTROL Properties]**」タブにアクセスします。
1. **[!UICONTROL Remote URL]**&#x200B;フィールドを探します。

   ![](assets/email_designer_importfromurl4.png)

1. 目的のパーソナライゼーションフィールド、コンテンツブロックまたは動的テキストを挿入します。

   例えば、**[!UICONTROL Current date - YYYYMMDD]**&#x200B;コンテンツブロックを使用すると、日付を挿入できます。

   >[!NOTE]
   >
   >使用可能なパーソナライゼーションフィールドは、**配信**&#x200B;属性にのみリンクされます(電子メール作成日、ステータス、キャンペーンラベル…)。

### 互換モード{#compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナのWYSIWYGエディターに完全に準拠し、編集できるように、コンテンツには特定のタグが含まれている必要があります。

アップロードされたHTMLのすべてまたは一部が期待されたタグに準拠していない場合は、コンテンツが「互換モード」で読み込まれ、UIでの編集が制限されます。

コンテンツが互換モードで読み込まれた場合でも、インターフェイスを通して次の変更を実行できます（使用できないアクションは非表示になります）。

* テキストの変更または画像の変更
* リンクとパーソナライゼーションフィールドの挿入
* 選択したHTMLブロックのスタイル設定オプションを編集します
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

電子メールに新しいセクションを追加したり、高度なスタイル設定を行ったりするなど、その他の変更は、電子メールのソースコードでHTMLモードを使用して直接行う必要があります。

既存の電子メールを電子メールデザイナーと互換性のある電子メールに変換する方法について詳しくは、[この節](../../designing/using/using-existing-content.md)を参照してください。

**関連トピック**：

* [E メールの作成](../../channels/using/creating-an-email.md)
* [電子メールデザイナーの概要ビデオ](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [電子メールコンテンツをゼロからデザインする](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## HTMLコンテンツの変換{#converting-an-html-content}

複数の電子メールで再利用できるモジュラー型テンプレートとフラグメントのフレームワークを構築する場合は、電子メールHTMLを電子メールデザイナーテンプレートに変換することを検討してください。

この使用例では、オファーがHTML電子メールをEmail Designerコンポーネントにすばやく変換できます。

>[!CAUTION]
>
>この節は、HTMLコードに詳しい上級ユーザー向けです。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントは次の制限付きオプションで編集できます。インプレースエディションのみ実行できます。

電子メールデザイナーの外部で、元のHTMLが再利用可能なセクションに分割されていることを確認します。

そうでない場合は、HTMLとは異なるブロックを切り抜いてください。 例：

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

すべてのブロックを識別したら、電子メールデザイナで、既存の電子メールの各セクションに対して次の手順を繰り返します。

1. 電子メールデザイナーを開き、空の電子メールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。
1. 構造追加コンポーネント。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. 追加HTMLコンポーネント。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. HTMLをそのコンポーネントにコピー&amp;ペーストします。
1. モバイル表示に切り替え. 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

   CSSが見つからないので、レスポンシブ表示が壊れています。

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
   >この後に、別のカスタムスタイルタグでスタイルを追加してください。
   >
   >電子メールデザイナで生成されたCSSは変更しないでください。
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. モバイル表示に戻って、コンテンツが正しく表示されていることを確認し、変更を保存します。
