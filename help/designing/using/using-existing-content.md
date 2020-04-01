---
title: '既存のコンテンツを使用した電子メールのデザイン '
description: 電子メールデザイナーで既存のコンテンツの電子メールコンテンツを使用して電子メールをデザインする方法を確認します。
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
source-git-commit: d68dbc3e9579f044b7ac1f76ac729548057bb6ec

---

# Designing using existing content {#designing-using-existing-content}

## 既存のコンテンツの選択{#selecting-an-existing-content}

Adobe Campaignには、開始に役立つ事前定義済みのコンテンツのセットが含まれています。 これらのいずれかを使用するか、送信する必要があるメッセージの内容がAdobe Campaignの外部で準備されている場合は、コンピューターまたはURLからインポートできます。

電子メールまたはランディングページを作成する際に、別のソースから既存のコンテンツを読み込むように選択できます。

>[!NOTE]
>
>次の画像は、電子メールデザイナーを使用して既存のコンテンツを読み込む方法を [示していま](../../designing/using/designing-content-in-adobe-campaign.md)す。

1. 電子メールまたはランディングページを作成したら、内容を開きます。
1. ホームアイコンをクリックして、アイコンにアクセス **[!UICONTROL Email Designer]** します。

   ![](assets/des_loading_1.png)

1. 読み込むコンテンツのソースを選択します。

   * [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates):タブをクリッ **[!UICONTROL Templates]** クします。
   * [コンテンツを一から](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)、新規開始:ボタンをクリッ **[!UICONTROL Create]** クします。
   * [ZIPまたはHTMLファイルとしてのコンテンツ](#importing-content-from-a-file):ボタンをクリッ **[!UICONTROL Upload]** クします。
   * [既存のURLからのコンテンツ](#importing-content-from-a-url) （電子メールの場合のみ）:ボタンをクリッ **[!UICONTROL Import from URL]** クします。
   ![](assets/des_loading_2.png)

1. コンテンツを読み込みます。 選択したコンテンツが現在のコンテンツを置き換えます。

   読み込みが完了すると、コンテンツを編集してパーソナライズできます。

   >[!NOTE]
   >
   >電子メー [ルデザイナーは](../../designing/using/designing-content-in-adobe-campaign.md) 、特定のタグを使用します。 キャンペーンにアップロードされる標準のHTMLコンテンツは、電子メールデザイナーで完全に互換性を持ち、編集できるように、期待されるタグと一致する必要があります。 一致しない場合、コンテンツは互換モードでアップロ [ードされます](#compatibility-mode)。 既存のコンテンツを互換性を持たせるには、この節を [参照してくださ](#editing-existing-contents-with-the-email-designer)い。

**関連トピック：**

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [ランディングページ](../../channels/using/getting-started-with-landing-pages.md)

## 電子メールデザイナでの既存のコンテンツの編集{#editing-existing-contents-with-the-email-designer}

電子メールデザイナーの編集機能を最大限に活用するには [](../../designing/using/designing-content-in-adobe-campaign.md)、アップロードしたHTMLに、WYSIWYGエディターに準拠する特定のタグが含まれている必要があります。

HTMLのすべてまたは一部にこのタグが付いていない場合、コンテンツは「互換性モード」で読 [み込まれます](#compatibility-mode)。

既存の外部コンテンツを電子メールデザイナー内で完全に編集できるようにするには、「既存のコンテンツを使用し [た電子メールのデザイン」の節を参照し](../../designing/using/using-existing-content.md) 、

## 既存の電子メールコンテンツの読み込み {#importing}

### ファイルからのコンテンツの読み込み {#importing-content-from-a-file}

電子メールデザイナーのホームページで、ボタンをク **[!UICONTROL Upload]** リックしてコンピューターからファイルをアップロードし、確認します。

zipファイル構造には制約はありません。 ただし、HTMLファイルの参照は、zipフォルダーのツリー構造を基準とした相対パスで行う必要があります。

読み込みでは、次の形式がサポートされています。

* スタイルシートが組み込まれたHTMLファイル
* HTMLファイル、スタイルシート(.CSS)および画像を含む.zipフォルダー

>[!NOTE]
>
>電子メールコンテンツの場合は、スタイルシートを組み込んで単一のHTMLファイルを読み込むことをお勧めします。

#### URLからのコンテンツの読み込み {#importing-content-from-a-url}

URLからコンテンツを読み込む前に、次の要件を満たしていることを確認します。

* コンテンツは、このURLで公開されている必要があります。
* セキュリティ上の理由から、で始まるURLのみが許 **[!UICONTROL https]** 可されます。
* すべてのリソース（画像、CSS）が絶対リンクとHTTPSで設定されていることを確認します。 そうしないと、電子メールを送信した後、ミラーページはリソースなしで表示されます。 次に、絶対リンク定義の例を示します。

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>URLからのコンテンツの読み込みは、電子メールチャネルでのみ可能です。

URLから既存のコンテンツを取得するには、次の手順に従います。

1. 電子メールデザイナーホームページで、ボタンを選択 **[!UICONTROL Import from URL]** します。

   ![](assets/email_designer_importfromurl.png)

1. コンテンツの取得元のURLを定義します。
1. クリック **[!UICONTROL Confirm]** .

**関連トピック:**

[URLビデオからのコンテンツの読み込み](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#Workingwithexistingcontent) 、

### 準備時にURLからコンテンツを自動的に取得する {#retrieving-content-from-a-url-automatically-at-preparation-time}

メッセージの準備中にURLからコンテンツを読み込むと、電子メールの準備が完了するたびに最新のHTMLコンテンツを取得できます。 これにより、定期的な電子メールのコンテンツは、送信時に常に最新の状態になります。 また、この機能を使用すると、コンテンツの準備ができていない場合でも、特定の日付にスケジュールされたメッセージを作成できます。

準備時にコンテンツを取得するには、次の手順に従います。

1. オプションを選 **[!UICONTROL Content imported during preparation]** 択します。

   ![](assets/email_designer_importfromurl2.png)

1. URLコンテンツは読み取り専用としてエディターに表示されます。

   >[!CAUTION]
   >
   >この手順では、コンテンツエディターでのHTML表示を考慮しないでください。 準備段階で取得されます。

1. 取得したURLコンテンツをプレビューするには、作成後にメッセージを開き、ボタンをクリック **[!UICONTROL Preview]** します。

コンテンツの取得元のリモートURLをパーソナライズできます。 これをおこなうには、以下の手順に従います。

1. 画面上部の電子メールラベルをクリックして、「電子メールデザイナ」タブにアクセ **[!UICONTROL Properties]** スします。
1. フィールドを探 **[!UICONTROL Remote URL]** します。

   ![](assets/email_designer_importfromurl4.png)

1. 目的のパーソナライゼーションフィールド、コンテンツブロックまたは動的テキストを挿入します。

   例え **[!UICONTROL Current date - YYYYMMDD]** ば、コンテンツブロックを使用して日付を挿入できます。

   >[!NOTE]
   >
   >使用可能なパーソナライゼーションフィールドは **配信** 属性(電子メール作成日、ステータス、キャンペーンラベルなど)にのみリンクされます。

### 互換性モード {#compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナーのWYSIWYGエディターで完全に準拠し、編集できるように、特定のタグが含まれている必要があります。

アップロードされたHTMLのすべてまたは一部が期待されたタグ付けに準拠していない場合、コンテンツは「互換性モード」で読み込まれ、UIを使用した編集の可能性が制限されます。

コンテンツが互換モードで読み込まれた場合でも、インターフェイスを通じて次の変更を実行できます（使用できないアクションは非表示になります）。

* テキストの変更または画像の変更
* リンクとパーソナライゼーションフィールド
* 選択したHTMLブロックの一部のスタイル設定オプションの編集
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

電子メールに新しいセクションを追加したり、高度なスタイルを設定したりするなど、その他の変更は、電子メールのソースコードでHTMLモードを使用して直接行う必要があります。

既存の電子メールを電子メールデザイナー互換の電子メールに変換する方法について詳しくは、この節を参 [照してくださ](../../designing/using/using-existing-content.md)い。

**関連トピック**:

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [電子メールデザイナの紹介ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)
* [電子メールコンテンツをゼロからデザインする](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## HTMLコンテンツの変換 {#converting-an-html-content}

複数の電子メールで再利用するために組み合わせることができるモジュール式のテンプレートとフラグメントのフレームワークを構築する場合は、電子メールのHTMLを電子メールデザイナーのテンプレートに変換することを検討してください。

この使用例では、オファーがHTML電子メールを電子メールデザイナーのコンポーネントに変換する簡単な方法を使用します。

>[!CAUTION]
>
>この節は、HTMLコードに詳しい上級ユーザーを対象としています。

>[!NOTE]
>
>互換性モードと同様に、HTMLコンポーネントは、次の制限付きオプションで編集できます。インプレースエディションのみ実行できます。

電子メールデザイナーの外部で、元のHTMLが再利用可能なセクションに分割されていることを確認します。

そうでない場合は、HTMLの異なるブロックを切り取ります。 次に例を示します。

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

1. 電子メールデザイナーを開いて、空の電子メールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など For more on this, see [Editing email styles](../../designing/using/styles.md).
1. 構追加造コンポーネント。 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 追加HTMLコンポーネント。 詳しくは、フラグメントとコンポーネ [ントの追加を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. HTMLをそのコンポーネントにコピー&amp;ペーストします。
1. モバイル表示 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

   レスポンシブ表示は、CSSが見つからないので壊れています。

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
