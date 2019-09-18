---
title: '既存のコンテンツを使用して電子メールをデザインする '
seo-title: '既存のコンテンツを使用して電子メールをデザインする '
description: '既存のコンテンツを使用して電子メールをデザインする '
seo-description: 電子メールデザイナで既存のコンテンツの電子メールコンテンツを使用して電子メールをデザインする方法を説明します。
page-status-flag: 未活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: 編集，電子メールの内容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: a7de545e9eec675444245576cddc6eaf8dce05f4

---

# 既存のコンテンツを使用して設計する {#designing-using-existing-content}

## 既存のコンテンツの選択{#selecting-an-existing-content}

Adobe Campaignには、作業を開始するのに役立つ定義済みのコンテンツのセットが用意されています。 これらのいずれかを使用するか、送信する必要のあるメッセージの内容がAdobe Campaignの外部で準備されている場合は、コンピュータまたはURLから読み込むことができます。

電子メールまたはランディング·ページを作成する場合は、別のソースから既存のコンテンツを読み込むことを選択できます。

>[!NOTE]
>
>次の図は、電子メールデザイナを使用して既存のコンテンツを読み込む方 [法を示しています](../../designing/using/overview.md)。

1. 電子メールまたはランディング·ページを作成した後、その内容を開きます。
1. ホーム·アイコンをクリックして、ホーム·ページに **[!UICONTROL Email Designer]** アクセスします。

   ![](assets/des_loading_1.png)

1. 読み込むコンテンツのソースを選択してください：

   * [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates):タブをクリック **[!UICONTROL Templates]** します。
   * [最初から](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)、最後に開始する内容：ボタンをクリック **[!UICONTROL Create]** します。
   * [ZIPまたはHTMLファイルとしてのコンテンツ](../../designing/using/using-existing-content.md#importing-content-from-a-file):ボタンをクリック **[!UICONTROL Upload]** します。
   * [既存のURLのコンテンツ](../../designing/using/using-existing-content.md#importing-content-from-a-url) （電子メールのみ）:ボタンをクリック **[!UICONTROL Import from URL]** します。
   ![](assets/des_loading_2.png)

1. コンテンツをロードします。 選択したコンテンツが現在のコンテンツに置き換えられます。

   インポート後は、コンテンツを編集してカスタマイズできます。

   >[!NOTE]
   >
   >電子メー [ルデザイナは](../../designing/using/overview.md) 、特定のタグを使用します。 キャンペーンにアップロードされる標準のHTMLコンテンツは、電子メールデザイナで完全に互換性を持ち、編集可能なタグ付けと一致する必要があります。 一致しない場合は、互換性モードでコンテンツがアップロ [ードされます](../../designing/using/using-existing-content.md#compatibility-mode)。 既存のコンテンツを互換性を持たせるには、このセクション [を参照してくださ](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer)い。

**関連トピック：**

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [ランディング·ページの管理](../../channels/using/about-landing-pages.md)

## 電子メールデザイナを使用した既存のコンテンツの編集{#editing-existing-contents-with-the-email-designer}

電子メールデザイナのエディション機能を完全に活用するには [](../../designing/using/overview.md)、アップロードしたHTMLに、WYSIWYGエディタに準拠する特定のタグ機能が含まれている必要があります。

HTMLの全部または一部にこのタグが付いていない場合は、コンテンツは「互換モード [](../../designing/using/using-existing-content.md#compatibility-mode)」で読み込まれます。

既存の外部コンテンツを電子メールデザイナ内で完全に編集可能にするには、「既存のコンテンツを使用し [た電子メールの設計」の項を参照してくだ](../../designing/using/using-existing-content.md) さい。

## インポート {#importing}

### ファイルからのコンテンツのインポート {#importing-content-from-a-file}

電子メールデザイナのホームページで、ボタンをクリックし **[!UICONTROL Upload]** てコンピュータからファイルをアップロードし、確認します。

zipファイル構造には制約はありません。 ただし、HTMLファイルを参照する場合は、相対的でzipフォルダのツリー構造を考慮する必要があります。

インポートでは、次の形式がサポートされています。

* スタイルシートを組み込んだHTMLファイル
* HTMLファイル、スタイルシート(.CSS)、イメージを含む。zipフォルダ

>[!NOTE]
>
>電子メールコンテンツの場合は、スタイルシートを組み込んだ単一のHTMLファイルを読み込むことをお勧めします。

#### URLからのコンテンツのインポート {#importing-content-from-a-url}

URLからコンテンツをインポートする前に、次の要件に従っていることを確認します。

* このURLを使用して、コンテンツを公開する必要があります。
* セキュリティ上の理由から、で始まるURLのみが許可 **[!UICONTROL https]** されています。
* すべてのリソース（イメージ、CSS）が絶対リンクとHTTPSに設定されていることを確認します。 それ以外の場合は、電子メールを送信した後、ミラーページがリソースなしで表示されます。 次に、絶対リンク定義の例を示します。

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>URLからのコンテンツの読み込みは、電子メールチャネルでのみ使用できます。

URLから既存のコンテンツを取得するには、次の手順に従います。

1. 電子メール·デザイナのホームページで、ボタンを選択 **[!UICONTROL Import from URL]** します。

   ![](assets/email_designer_importfromurl.png)

1. コンテンツの取得元のURLを定義します。
1. Click **[!UICONTROL Confirm]**.

**関連トピック：**

[URLビデオからのコンテンツの読み込み](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent) 。

### 準備時にURLからコンテンツを自動的に取得する {#retrieving-content-from-a-url-automatically-at-preparation-time}

メッセージの準備中にURLからコンテンツをインポートすると、電子メールの準備を行うたびに最新のHTMLコンテンツを取得できます。 このように、定期的な電子メールの内容は、送信時に常に最新の状態になります。 また、この機能を使用すると、コンテンツの準備が整っていない場合でも、特定の日付にスケジュールされたメッセージを作成できます。

準備時にコンテンツを取得するには、次の手順に従います。

1. オプションを選択 **[!UICONTROL Content imported during preparation]** します。

   ![](assets/email_designer_importfromurl2.png)

1. URLの内容が読み取り専用でエディタに表示されます。

   >[!CAUTION]
   >
   >この手順では、コンテンツエディタのHTML表示を考慮しないでください。 準備段階で検索します。

1. 取得したURLコンテンツをプレビューするには、メッセージを作成したら開き、ボタンをクリック **[!UICONTROL Preview]** します。

コンテンツの取得元となるリモートURLをパーソナライズできます。 これを行うには、次の手順に従います。

1. 画面の上部にある電子メールラベルをクリックして、「電子メールデザイナ」タブにアクセス **[!UICONTROL Properties]** します。
1. フィールドを検索 **[!UICONTROL Remote URL]** します。

   ![](assets/email_designer_importfromurl4.png)

1. 必要な個人用設定フィールド、コンテンツブロック、または動的テキストを挿入します。

   たと **[!UICONTROL Current date - YYYYMMDD]** えば、コンテンツブロックを使用して、日付を挿入できます。

   >[!NOTE]
   >
   >利用可能な個人用設定フィールドは、 **Delivery** 属性（電子メール作成日、ステータス、キャンペーンラベル……）にのみリンクされます。

### 互換モード {#compatibility-mode}

コンテンツをアップロードする場合、電子メールデザイナのWYSIWYGエディタで完全に準拠し、編集可能な特定のタグ付けを含める必要があります。

アップロードされたHTMLのすべてまたは一部が、必要なタグ付けに準拠していない場合、コンテンツは'互換モード'で読み込まれ、UIを通じての編集の可能性が制限されます。

互換モードでコンテンツをロードした場合でも、インタフェースを介して次の変更を実行できます（使用できないアクションは非表示になります）。

* テキストの変更、またはイメージの変更
* リンクと個人用設定フィールドの挿入
* 選択したHTMLブロックのスタイルオプションを編集します
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

新しいセクションを電子メールに追加したり、高度なスタイル設定を行ったりする他の変更は、HTMLモードを使用して電子メールのソースコードで直接行う必要があります。

既存の電子メールを電子メールデザイナー互換の電子メールに変換する方法の詳細については、この節を参照 [してください](../../designing/using/using-existing-content.md)。

**関連トピック**:

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [電子メールデザイナの概要ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)
* [Eメール·コンテンツをゼロから設計する](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## HTMLコンテンツの変換 {#converting-an-html-content}

複数の電子メールで再利用できるモジュラー型テンプレートとフラグメントのフレームワークを構築する場合は、電子メールHTMLを電子メールデザイナテンプレートに変換することを検討する必要があります。

この使用例では、HTML電子メールを電子メールデザイナのコンポーネントに変換する簡単な方法を提供します。

>[!CAUTION]
>
>このセクションは、HTMLコードに詳しい上級ユーザ向けです。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントは次の制限されたオプションで編集可能です。インプレイスエディションのみ実行できます。

電子メールデザイナの外部で、元のHTMLが再利用可能なセクションに分割されていることを確認します。

そうでない場合は、HTMLとは異なるブロックを切り離します。  例：

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

1. 電子メールデザイナを開いて、空の電子メールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など 詳細については、「電子メールのスタイルを編 [集する」を参照してくださ](../../designing/using/styles.md)い。
1. 構造コンポーネントを追加します。 詳細については、「電子メール構 [造の編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. HTMLコンポーネントを追加します。 詳細については、「フラグメントとコンポーネ [ントを追加する」を参照してくださ](../../designing/using/designing-from-scratch.md#defining-the-email-structure)い。
1. HTMLをそのコンポーネントにコピー&amp;ペーストします。
1. モバイルビューに切り替えます。 詳細は、この節を参照して [ください](../../designing/using/styles.md#switching-to-mobile-view)。

   CSSが見つからないため、応答ビューが壊れています。

1. これを修正するには、ソースコードモードに切り替え、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。 例：

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
   >電子メールデザイナで生成されたCSSを変更しないでください。 `<style acrite-template-css="true">` と `<style acrite-custom-styles="" type="text/css">`。 この後、必ずスタイルを追加してください。

1. モバイルビューに戻り、コンテンツが正しく表示されているか確認し、変更を保存します。
