---
title: '既存のコンテンツを使用した電子メールのデザイン '
description: Eメールデザイナーで既存のコンテンツEメールコンテンツを使用してEメールをデザインする方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 6%

---

# 既存のコンテンツを使用したデザイン {#designing-using-existing-content}

## 既存のコンテンツの選択{#selecting-an-existing-content}

Adobe Campaignには、使い始めるのに役立つ、事前定義済みのコンテンツのセットが付属しています。 これらのいずれかを使用するか、送信する必要があるメッセージのコンテンツがAdobe Campaign以外で準備されている場合は、コンピューターまたはURLから読み込むことができます。

Eメールまたはランディングページを作成する際に、別のソースから既存のコンテンツを読み込むよう選択できます。

>[!NOTE]
>
>以下の画像は、[Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)を使用して既存のコンテンツを読み込む方法を示しています。

1. Eメールまたはランディングページを作成したら、そのコンテンツを開きます。
1. ホームアイコンをクリックして、**[!UICONTROL Email Designer]**&#x200B;ホームページにアクセスします。

   ![](assets/des_loading_1.png)

1. 読み込むコンテンツのソースを選択します。

   * [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates):「 」タブをクリ **[!UICONTROL Templates]** ックします。
   * [コンテンツを一から](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)、新規に開始するには、次の手順を実行します。「 」ボタンをクリ **[!UICONTROL Create]** ックします。
   * [コンピューターからZIPまたはHTMLファイルとしてのコンテンツ](#importing-content-from-a-file):「 」ボタンをクリ **[!UICONTROL Upload]** ックします。
   * [既存のURLからのコンテンツ](#importing-content-from-a-url) （Eメールの場合のみ）:「 」ボタンをクリ **[!UICONTROL Import from URL]** ックします。

   ![](assets/des_loading_2.png)

1. コンテンツを読み込みます。 選択したコンテンツが現在のコンテンツを置き換えます。

   読み込まれたコンテンツは、編集およびパーソナライズできます。

   >[!NOTE]
   >
   >[Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)は特定のタグ付けを使用します。 Campaignにアップロードされる標準HTMLコンテンツは、Eメールデザイナーから完全に互換性を持ち、編集可能なタグと一致する必要があります。 一致しない場合、コンテンツは[互換モード](#compatibility-mode)でアップロードされます。 既存のコンテンツに互換性を持たせるには、[この節](#editing-existing-contents-with-the-email-designer)を参照してください。

**関連トピック：**

* [E メールの作成](../../channels/using/creating-an-email.md)
* [ランディングページの管理](../../channels/using/getting-started-with-landing-pages.md)

## Eメールデザイナーでの既存のコンテンツの編集{#editing-existing-contents-with-the-email-designer}

[Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)の編集機能を最大限に活用するには、アップロードしたHTMLにWYSIWYGエディターに準拠する特定のタグ付けを含める必要があります。

HTMLのすべてまたは一部にこのタグが付いていない場合、コンテンツは「[互換モード](#compatibility-mode)」で読み込まれます。

既存の外部コンテンツをEメールデザイナー内で完全に編集可能にするには、[既存のコンテンツを使用したEメールのデザイン](../../designing/using/using-existing-content.md)の節を参照してください。

## 既存のEメールコンテンツのインポート {#importing}

### ファイルからのコンテンツの読み込み {#importing-content-from-a-file}

Eメールデザイナーのホームページで、「**[!UICONTROL Upload]**」ボタンをクリックして、お使いのコンピューターからファイルをアップロードし、確認します。

zipファイル構造に制約はありません。 ただし、HTMLファイルの参照は、zipフォルダーのツリー構造に従って相対パスでおこなう必要があります。

読み込みでは、次の形式がサポートされます。

* スタイルシートが組み込まれたHTMLファイル
* HTMLファイル、スタイルシート(.CSS)および画像を含む.zipフォルダー

>[!NOTE]
>
>Eメールコンテンツの場合は、スタイルシートを組み込んだ単一のHTMLファイルを読み込むことをお勧めします。

#### URLからのコンテンツの読み込み {#importing-content-from-a-url}

URLからコンテンツを読み込む前に、次の要件に従っていることを確認してください。

* コンテンツは、このURLを通じて公開されている必要があります。
* セキュリティ上の理由から、**[!UICONTROL https]**&#x200B;で始まるURLのみを使用できます。
* すべてのリソース（画像、CSS）が絶対リンクとHTTPSで設定されていることを確認します。 そうしないと、Eメールを送信した後、ミラーページにリソースが表示されなくなります。 絶対リンク定義の例を次に示します。

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>URLからのコンテンツの読み込みは、Eメールチャネルでのみ使用できます。

URLから既存のコンテンツを取得するには、次の手順に従います。

1. Eメールデザイナーのホームページで、「**[!UICONTROL Import from URL]**」ボタンを選択します。

   ![](assets/email_designer_importfromurl.png)

1. コンテンツの取得元となるURLを定義します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

この機能をビデオで確認.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)からご覧いただけます。

### 準備時にURLからコンテンツを自動的に取得する {#retrieving-content-from-a-url-automatically-at-preparation-time}

メッセージの準備中にURLからコンテンツを読み込むと、Eメールが準備されるたびに最新のHTMLコンテンツを取得できます。 これにより、繰り返しEメールのコンテンツは、送信時に常に最新の状態に保たれます。 また、この機能を使用すると、コンテンツの準備ができていなくても、特定の日付にスケジュールされたメッセージを作成できます。

準備時にコンテンツを取得するには、次の手順に従います。

1. **[!UICONTROL Content imported during preparation]**&#x200B;オプションを選択します。

   ![](assets/email_designer_importfromurl2.png)

1. URLコンテンツは、読み取り専用としてエディターに表示されます。

   >[!CAUTION]
   >
   >この手順では、コンテンツエディターでのHTML表示を考慮しないでください。 準備段階で取得されます。

1. 取得されたURLコンテンツをプレビューするには、メッセージの作成後にメッセージを開き、「**[!UICONTROL Preview]**」ボタンをクリックします。

コンテンツの取得元となるリモートURLをパーソナライズできます。 これは、次の手順に従って行います。

1. 画面上部のEメールラベルをクリックして、「 Eメールデザイナー」の「 **[!UICONTROL Properties]** 」タブにアクセスします。
1. **[!UICONTROL Remote URL]**&#x200B;フィールドを探します。

   ![](assets/email_designer_importfromurl4.png)

1. 目的のパーソナライゼーションフィールド、コンテンツブロックまたは動的テキストを挿入します。

   例えば、**[!UICONTROL Current date - YYYYMMDD]**&#x200B;コンテンツブロックを使用して、日付を挿入できます。

   >[!NOTE]
   >
   >使用可能なパーソナライゼーションフィールドは、**配信**&#x200B;属性（Eメール作成日、ステータス、キャンペーンラベルなど）にのみリンクされます。

### 互換性モード {#compatibility-mode}

コンテンツをアップロードする際には、EメールデザイナーのWYSIWYGエディターに完全に準拠し、編集可能な特定のタグがそのコンテンツに含まれている必要があります。

アップロードされたHTMLのすべてまたは一部が想定されるタグ付けに準拠していない場合、コンテンツは「互換モード」で読み込まれ、UIを使用した編集の可能性が制限されます。

コンテンツが互換モードで読み込まれても、インターフェイスを通じて次の変更を実行できます（使用できないアクションは非表示になります）。

* テキストの変更または画像の変更
* リンクとパーソナライゼーションフィールドの挿入
* 選択したHTMLブロックのスタイル設定オプションの一部を編集します。
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

Eメールに新しいセクションを追加したり、高度なスタイル設定をおこなうなど、その他の変更は、HTMLモードでEメールのソースコードで直接おこなう必要があります。

既存のEメールをEメールデザイナー互換のEメールに変換する方法について詳しくは、[この節](../../designing/using/using-existing-content.md)を参照してください。

**関連トピック**：

* [E メールの作成](../../channels/using/creating-an-email.md)
* [Eメールデザイナーの紹介ビデオ](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Eメールコンテンツをゼロからデザインする](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## HTMLコンテンツの変換 {#converting-an-html-content}

複数のEメールで再利用するために組み合わせ可能な、モジュール化されたテンプレートとフラグメントのフレームワークを構築する場合は、EメールのHTMLをEメールデザイナーテンプレートに変換することを検討してください。

この使用例では、HTML電子メールをEメールデザイナーコンポーネントにすばやく変換できます。

>[!CAUTION]
>
>この節は、HTMLコードに詳しい上級ユーザー向けです。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントは制限付きオプションで編集できます。インプレース編集のみ実行できます。

Eメールデザイナー以外では、元のHTMLが再利用可能なセクションに分割されていることを確認してください。

そうでない場合は、HTMLの様々なブロックを切り抜きます。 例：

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

すべてのブロックを特定したら、Eメールデザイナーで、既存のEメールの各セクションに対して次の手順を繰り返します。

1. Eメールデザイナーを開いて、空のEメールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。
1. 構造コンポーネントを追加します。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. HTMLコンポーネントを追加します。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. HTMLをそのコンポーネントにコピー&amp;ペーストします。
1. モバイル表示に切り替え. 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

   CSSが見つからないので、レスポンシブビューが壊れます。

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
