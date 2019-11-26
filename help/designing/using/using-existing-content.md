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
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---

# Designing using existing content {#designing-using-existing-content}

## 既存のコンテンツの選択{#selecting-an-existing-content}

Adobe Campaignには、作業を開始する際に役立つ事前定義済みコンテンツのセットが用意されています。 これらのいずれかを使用するか、送信する必要があるメッセージの内容がAdobe Campaignの外部で準備されている場合は、コンピューターまたはURLからインポートできます。

電子メールまたはランディングページを作成する場合、別のソースから既存のコンテンツを読み込むよう選択できます。

>[!NOTE]
>
>次の画像は、電子メールデザイナーを使用して既存のコンテンツを読み込む方法 [を示していま](../../designing/using/overview.md)す。

1. 電子メールまたはランディングページを作成したら、そのコンテンツを開きます。
1. ホームアイコンをクリックして、ホームページに **[!UICONTROL Email Designer]** アクセスします。

   ![](assets/des_loading_1.png)

1. 読み込むコンテンツのソースを選択します。

   * [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates):タブをクリック **[!UICONTROL Templates]** します。
   * [最初から](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)、最初からボタンをクリッ **[!UICONTROL Create]** クします。
   * [ZIPまたはHTMLファイル形式のコンテンツ](#importing-content-from-a-file):ボタンをクリッ **[!UICONTROL Upload]** クします。
   * [既存のURLからのコンテンツ](#importing-content-from-a-url) （電子メールのみ）:ボタンをクリッ **[!UICONTROL Import from URL]** クします。
   ![](assets/des_loading_2.png)

1. コンテンツを読み込みます。 選択したコンテンツが現在のコンテンツを置き換えます。

   読み込んだコンテンツは、編集してパーソナライズすることができます。

   >[!NOTE]
   >
   >電子メー [ルデザイナーは](../../designing/using/overview.md) 、特定のタグ付けを使用します。 キャンペーンにアップロードされる標準HTMLコンテンツは、電子メールデザイナーで完全な互換性と編集が可能なタグと一致する必要があります。 一致しない場合、コンテンツは互換モードでアップ [ロードされます](#compatibility-mode)。 既存のコンテンツを互換性を持たせるには、この節を [参照してくださ](#editing-existing-contents-with-the-email-designer)い。

**関連トピック：**

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [ランディングページの管理](../../channels/using/getting-started-with-landing-pages.md)

## 電子メールデザイナーによる既存のコンテンツの編集{#editing-existing-contents-with-the-email-designer}

電子メールデザイナーの編集機能を最大限に活用するには [](../../designing/using/overview.md)、アップロードしたHTMLに、WYSIWYGエディターに準拠する特定のタグが含まれている必要があります。

HTMLの全部または一部にこのタグが付いていない場合、コンテンツは「互換性モード [](#compatibility-mode)」に読み込まれます。

既存の外部コンテンツを電子メールデザイナー内で完全に編集できるようにするには、「既存のコンテンツを使用し [た電子メールのデザイン](../../designing/using/using-existing-content.md) 」を参照してください。

## 読み込み {#importing}

### ファイルからのコンテンツの読み込み {#importing-content-from-a-file}

電子メールデザイナのホームページで、ボタンをクリックし **[!UICONTROL Upload]** てコンピューターからファイルをアップロードし、確認します。

zipファイル構造には制約はありません。 ただし、HTMLファイルの参照はzipフォルダーのツリー構造を基準とした相対パスで行う必要があります。

読み込みでは、次の形式がサポートされています。

* スタイルシートが組み込まれたHTMLファイル
* HTMLファイル、スタイルシート(.CSS)、画像を含む.zipフォルダー

>[!NOTE]
>
>電子メールコンテンツの場合は、スタイルシートを組み込んだ単一のHTMLファイルを読み込むことをお勧めします。

#### URLからのコンテンツの読み込み {#importing-content-from-a-url}

URLからコンテンツを読み込む前に、次の要件に従っていることを確認します。

* コンテンツは、このURLで公開されている必要があります。
* セキュリティ上の理由から、で始まるURLのみを使 **[!UICONTROL https]** 用できます。
* すべてのリソース（画像、CSS）が絶対リンクとHTTPSで設定されていることを確認します。 そうしないと、電子メールを送信した後で、ミラーページがリソースなしで表示されます。 次に、絶対リンク定義の例を示します。

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>URLからのコンテンツの読み込みは、電子メールチャネルでのみ使用できます。

URLから既存のコンテンツを取得するには、次の手順に従います。

1. 電子メールデザイナのホームページで、ボタンを選択 **[!UICONTROL Import from URL]** します。

   ![](assets/email_designer_importfromurl.png)

1. コンテンツの取得元となるURLを定義します。
1. Click **[!UICONTROL Confirm]**.

**関連トピック：**

[URLビデオからのコンテンツの読み込み](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent) 、

### 準備時にURLからコンテンツを自動的に取得する {#retrieving-content-from-a-url-automatically-at-preparation-time}

メッセージの準備中にURLからコンテンツを読み込むと、電子メールの準備が完了するたびに最新のHTMLコンテンツを取得できます。 これにより、定期的な電子メールのコンテンツは、送信時に常に最新の状態になります。 また、この機能を使用すると、コンテンツの準備ができていなくても、特定の日にスケジュールされたメッセージを作成できます。

準備時にコンテンツを取得するには、次の手順に従います。

1. オプションを選 **[!UICONTROL Content imported during preparation]** 択します。

   ![](assets/email_designer_importfromurl2.png)

1. URLコンテンツは読み取り専用としてエディターに表示されます。

   >[!CAUTION]
   >
   >この手順では、コンテンツエディターでのHTML表示を考慮しないでください。 準備段階で取得されます。

1. 取得したURLコンテンツをプレビューするには、メッセージの作成後にメッセージを開き、ボタンをクリック **[!UICONTROL Preview]** します。

コンテンツの取得元のリモートURLをパーソナライズすることができます。 これをおこなうには、以下の手順に従います。

1. 画面の上部にある電子メールラベルをクリックして、「電子メールデザイナー」タブにアクセ **[!UICONTROL Properties]** スします。
1. フィールドを探 **[!UICONTROL Remote URL]** します。

   ![](assets/email_designer_importfromurl4.png)

1. 目的のパーソナライゼーションフィールド、コンテンツブロックまたは動的テキストを挿入します。

   例え **[!UICONTROL Current date - YYYYMMDD]** ば、コンテンツブロックを使用して日付を挿入できます。

   >[!NOTE]
   >
   >利用可能なパーソナライゼーションフィールドは **配信** 属性（電子メール作成日、ステータス、キャンペーンラベルなど）にのみリンクされます。

### 互換性モード {#compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナーのWYSIWYGエディターに完全に準拠し、編集可能な特定のタグがコンテンツに含まれている必要があります。

アップロードされたHTMLのすべてまたは一部が期待されたタグ付けに準拠していない場合、コンテンツは「互換性モード」で読み込まれ、UIを使用した編集の可能性が制限されます。

コンテンツが互換モードで読み込まれても、インターフェイスを通じて次の変更を行うことができます（使用できないアクションは非表示になります）。

* テキストの変更または画像の変更
* リンクとパーソナライゼーションフィールドの挿入
* 選択したHTMLブロックのスタイル設定オプションの一部を編集
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

電子メールに新しいセクションを追加したり、高度なスタイル設定を行ったりするなど、その他の変更は、電子メールのソースコードでHTMLモードを使用して直接行う必要があります。

既存の電子メールを電子メールデザイナー互換の電子メールに変換する方法について詳しくは、この節を参 [照してくださ](../../designing/using/using-existing-content.md)い。

**関連トピック**:

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [電子メールデザイナーの紹介ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)
* [電子メールコンテンツの新規デザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## HTMLコンテンツの変換 {#converting-an-html-content}

複数の電子メールで再利用できるモジュラー型テンプレートとフラグメントのフレームワークを構築する場合は、電子メールHTMLを電子メールデザイナーテンプレートに変換することを検討してください。

この使用例では、HTML電子メールを電子メールデザイナーコンポーネントにすばやく変換できます。

>[!CAUTION]
>
>この節は、HTMLコードに詳しい上級ユーザーを対象としています。

>[!NOTE]
>
>互換性モードと同様に、HTMLコンポーネントは次の制限付きオプションで編集できます。インプレースエディションのみを実行できます。

電子メールデザイナーの外部で、元のHTMLが再利用可能なセクションに分割されていることを確認します。

そうでない場合は、HTMLの異なるブロックを切り取ってください。 次に例を示します。

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
1. 構造コンポーネントを追加します。 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. HTMLコンポーネントを追加します。 詳しくは、フラグメントとコンポーネ [ントの追加を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. HTMLをそのコンポーネントにコピー&amp;ペーストします。
1. モバイルビューに切り替えます。 For more on this, see [this section](../../designing/using/styles.md#switching-to-mobile-view).

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
   >電子メールデザイナーが生成したCSSは変更しないでください。 `<style acrite-template-css="true">` と `<style acrite-custom-styles="" type="text/css">`。 この後にスタイルを追加してください。

1. モバイルビューに戻って、コンテンツが正しく表示されていることを確認し、変更を保存します。
