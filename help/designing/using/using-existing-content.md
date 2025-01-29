---
title: 既存のコンテンツを使用したメールのデザイン
description: メールDesignerで既存のコンテンツのメールコンテンツを使用してメールをデザインする方法について説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 4%

---

# 既存のコンテンツを使用したデザイン {#designing-using-existing-content}

## 既存のコンテンツの選択{#selecting-an-existing-content}

Adobe Campaignには、利用を開始するのに役立つ、事前定義済みの一連のコンテンツが付属しています。 これらのいずれかを使用できます。または、送信する必要があるメッセージのコンテンツがAdobe Campaign以外で準備されている場合は、コンピューターまたは URL から読み込むことができます。

メールまたはランディングページの作成時に、別のソースから既存のコンテンツを読み込むように選択できます。

>[!NOTE]
>
>以下の画像は、[ メールDesigner](../../designing/using/designing-content-in-adobe-campaign.md) を使用して既存のコンテンツを読み込む方法を示しています。

1. メールまたはランディングページを作成したら、そのコンテンツを開きます。
1. ホームアイコンをクリックして、**[!UICONTROL Email Designer]** のホームページにアクセスします。

   ![](assets/des_loading_1.png)

1. 読み込むコンテンツのソースを選択します。

   * [ コンテンツテンプレート ](../../designing/using/using-reusable-content.md#content-templates):「コンテン **[!UICONTROL Templates]**」タブをクリックします。
   * [ コンテンツをゼロから ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)、新規に開始するには、「**[!UICONTROL Create]** 開」ボタンをクリックします。
   * [ZIP ファイルまたはHTMLファイルとしてコンピューターからコンテンツを取得 ](#importing-content-from-a-file):「**[!UICONTROL Upload]**」ボタンをクリックします。
   * [ 既存の URL のコンテンツ ](#importing-content-from-a-url) （メールの場合のみ）:「**[!UICONTROL Import from URL]** 信」ボタンをクリックします。

   ![](assets/des_loading_2.png)

1. コンテンツを読み込みます。 選択したコンテンツが現在のコンテンツを置き換えます。

   インポートすると、コンテンツを編集してパーソナライズできます。

   >[!NOTE]
   >
   >[ 電子メールDesigner](../../designing/using/designing-content-in-adobe-campaign.md) では、特定のタグ付けを使用します。 Campaign にアップロードされる標準HTMLコンテンツは、電子メールDesignerから完全に互換性を持ち編集可能にするために、期待されるタグと一致する必要があります。 一致しない場合、コンテンツは [ 互換性モード ](#compatibility-mode) でアップロードされます。 既存のコンテンツに互換性を持たせるには、[ この節 ](#editing-existing-contents-with-the-email-designer) を参照してください。

**関連トピック：**

* [メールの作成](../../channels/using/creating-an-email.md)
* [ランディングページの管理](../../channels/using/getting-started-with-landing-pages.md)

## メールDesignerを使用した既存のコンテンツの編集{#editing-existing-contents-with-the-email-designer}

[ メールDesigner](../../designing/using/designing-content-in-adobe-campaign.md) の編集機能を最大限に活用するには、アップロードするHTMLに、WYSIWYG エディターに準拠するための特定のタグが含まれている必要があります。

HTMLのすべてまたは一部にこのタグ付けがない場合、コンテンツは「[ 互換モード ](#compatibility-mode)」で読み込まれます。

既存の外部コンテンツをメールDesigner内で完全に編集可能にするには、[ 既存のコンテンツを使用したメールのデザイン ](../../designing/using/using-existing-content.md) の節を参照してください。

## 既存のメールコンテンツの読み込み {#importing}

### ファイルからのコンテンツの読み込み {#importing-content-from-a-file}

メールDesignerのホームページで、「**[!UICONTROL Upload]**」ボタンをクリックしてコンピューターからファイルをアップロードし、確認します。

zip ファイル構造に制約はありません。 ただし、HTMLファイルの参照は相対パスにする必要があり、zip フォルダーのツリー構造に従う必要があります。

読み込みでは、次の形式がサポートされています。

* スタイルシートが組み込まれたHTMLファイル
* HTMLファイル、スタイルシート（.CSS）、画像を含んだ.zip フォルダー

>[!NOTE]
>
>メールコンテンツの場合は、スタイルシートが組み込まれたシングルHTMLファイルを読み込むことをお勧めします。

#### URL からのコンテンツの読み込み {#importing-content-from-a-url}

URL からコンテンツを読み込む前に、以下の要件に従っていることを確認してください。

* コンテンツは、この URL を通じて公開する必要があります。
* セキュリティ上の理由から、**[!UICONTROL https]** で始まる URL のみを使用できます。
* すべてのリソース（画像、CSS）が絶対リンクと HTTPS で設定されていることを確認します。 そうでない場合は、メールを送信した後、リソースのないミラーページが表示されます。 絶対リンク定義の例を次に示します。

  ```
  <a href="https://www.mywebsite.com/images/myimage.png">
  ```

>[!NOTE]
>
>URL からのコンテンツの読み込みは、メールチャネルでのみ使用できます。

URL から既存のコンテンツを取得するには、次の手順に従います。

1. メールDesignerのホームページで、「**[!UICONTROL Import from URL]**」ボタンを選択します。

   ![](assets/email_designer_importfromurl.png)

1. コンテンツの取得元となる URL を定義します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

ビデオでこの機能を確認します。

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

その他のCampaign Standardチュートリアルビデオについては、[ こちら ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。

### 準備時に URL からコンテンツを自動的に取得 {#retrieving-content-from-a-url-automatically-at-preparation-time}

メッセージの準備中に URL からコンテンツを読み込むと、メールを準備するたびに最新のHTMLコンテンツを取得できます。 これにより、繰り返しメールのコンテンツは常に最新の送信時のコンテンツになります。 また、この機能を使用すると、コンテンツの準備がまだ整っていない場合でも、特定の日付にスケジュールされたメッセージを作成できます。

準備時にコンテンツを取得するには、次の手順に従います。

1. **[!UICONTROL Content imported during preparation]** オプションを選択します。

   ![](assets/email_designer_importfromurl2.png)

1. URL コンテンツは、エディターに読み取り専用として表示されます。

   >[!CAUTION]
   >
   >この段階では、コンテンツエディターでのHTML表示は考慮しないでください。 準備段階で取得されます。

1. 取得した URL コンテンツをプレビューするには、メッセージの作成後にメッセージを開き、「**[!UICONTROL Preview]**」ボタンをクリックします。

コンテンツの取得元となるリモート URL をパーソナライズできます。 これを行うには、次の手順に従います。

1. 画面上部のメールラベルをクリックして、「メールDesigner **[!UICONTROL Properties]**」タブにアクセスします。
1. 「**[!UICONTROL Remote URL]**」フィールドを検索します。

   ![](assets/email_designer_importfromurl4.png)

1. 目的のパーソナライゼーションフィールド、コンテンツブロック、動的テキストを挿入します。

   例えば、**[!UICONTROL Current date - YYYYMMDD]** コンテンツブロックを使用すると、日付を挿入できます。

   >[!NOTE]
   >
   >使用可能なパーソナライゼーションフィールドは、**配信** 属性（メール作成日、ステータス、キャンペーンラベルなど）にのみリンクされています。

1 回目にコンテンツのダウンロードに失敗した場合は、2 回再試行できます。

1. 2 回目の試行は、1 回目の試行から 50 ミリ秒後に開始されます。
1. 3 回目のトライは、2 回目のトライから 100 ミリ秒後に開始されます。

これらの再試行は、次の場合に役立ちます。

* 遠隔サーバーでの短時間のサービス障害
* クラスターでのサーバー障害。この場合、動作中のサーバーへのロードバランシングによって再試行が成功する可能性が高くなります。

### 互換モード {#compatibility-mode}

コンテンツをアップロードする場合、電子メールDesignerのWYSIWYG エディターに完全に準拠し編集可能にするには、特定のタグが含まれている必要があります。

アップロードされたHTMLの全部または一部が期待されるタグ付けに準拠していない場合、コンテンツは「互換モード」で読み込まれ、UI を使用した編集の可能性が制限されます。

コンテンツが互換性モードで読み込まれた場合でも、インターフェイスを通じて次の変更を実行できます（使用できないアクションは非表示になります）。

* テキストの変更または画像の変更
* リンクとパーソナライゼーションフィールドの挿入
* 選択したHTMLブロックのスタイルオプションを編集します
* 条件付きコンテンツの定義

![](assets/email_designer_compatibility.png)

メールに新しいセクションを追加したり、高度なスタイルを設定したりするなどの他の変更は、HTMLモードを使用して、メールのソースコードで直接行う必要があります。

既存のメールをメールDesigner互換のメールに変換する方法については、[ この節 ](../../designing/using/using-existing-content.md) を参照してください。

**関連トピック**：

* [メールの作成](../../channels/using/creating-an-email.md)
* [メールDesignerの概要ビデオ](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [メールコンテンツのゼロからのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## HTMLコンテンツの変換 {#converting-an-html-content}

複数のメールで再利用できるように組み合わせることができるモジュール型テンプレートおよびフラグメントのフレームワークを構築する場合は、メールテンプレートをメールDesignerHTMLに変換することを検討する必要があります。

このユースケースは、HTMLメールをメールDesignerコンポーネントに簡単に変換する方法を提供します。

>[!CAUTION]
>
>この節は、HTMLコードに精通した上級ユーザーを対象としています。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントも編集可能で、オプションは限られています。つまり、インプレース編集のみを実行できます。

メールDesignerの外部で、元のHTMLが再利用可能なセクションに分割されていることを確認します。

そうでない場合は、HTMLから別のブロックを切り取ります。 例：

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

メールDesignerで、すべてのブロックを識別したら、既存のメールの各セクションに対して次の手順を繰り返します。

1. メールDesignerを開いて、空のメールコンテンツを作成します。
1. 背景色や幅など、本文レベルの属性を設定します。 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。
1. 構造コンポーネントを追加します。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. HTMLコンポーネントを追加します。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. HTMLした内容を、そのコンポーネントにコピー&amp;ペーストします。
1. モバイル表示に切り替えます。 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

   CSS がないので、レスポンシブビューが壊れます。

1. これを修正するには、ソースコードモードに切り替えて、「スタイル」セクションをコピーして新しい「スタイル」セクションに貼り付けます。 例：

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
   >この後に、必ず別のカスタムスタイルタグでスタイルを追加してください。
   >
   >メールDesignerで生成された CSS を変更しないでください。
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. モバイルビューに戻ってコンテンツが正しく表示されていることを確認し、変更を保存します。
