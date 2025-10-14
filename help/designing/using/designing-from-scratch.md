---
title: 新規でのメールのデザイン
description: メールDesignerでメールをゼロのメールコンテンツからデザインする方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: 0079a924db522de8afc628ef50aa2c861e5a12ee
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 27%

---

# 新規でのメールのデザイン {#designing-an-email-content-from-scratch}

メールコンテンツ編集をマスターする方法を説明します。 メールDesignerを使用すると、定義済みのコンテンツの有無に関わらず、メールとテンプレートを作成できます。

以下は、メールDesignerを使用してメールコンテンツをゼロから作成およびデザインする主な手順です。

1. メールを作成し、そのコンテンツを開きます。
1. 構造コンポーネントを追加して、メールを形作ります。 [&#x200B; メール構造の編集 &#x200B;](#defining-the-email-structure) を参照してください。
1. 構造コンポーネントにコンテンツコンポーネントとフラグメントを挿入します。 詳しくは、[&#x200B; フラグメントとコンテンツコンポーネントの追加 &#x200B;](#defining-the-email-structure) を参照してください。
1. 画像を追加し、メールのテキストを編集します。 [画像の挿入](../../designing/using/images.md#inserting-images)を参照してください。
1. パーソナライゼーションフィールド、リンクなどを追加して、メールをパーソナライズします。 [&#x200B; パーソナライゼーションフィールドの挿入 &#x200B;](../../designing/using/personalization.md#inserting-a-personalization-field)、[&#x200B; リンクの挿入 &#x200B;](../../designing/using/links.md#inserting-a-link) および [&#x200B; メールへの動的コンテンツの定義 &#x200B;](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) を参照してください。
1. メールの件名を定義します。 [&#x200B; メールの件名のパーソナライズ &#x200B;](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email) を参照してください。
1. メールのプレビュー。
1. コンテンツを保存し、オーディエンスを定義し、送信を適切にスケジュールしたことを確認した後、メッセージに進みます。

こちらの [&#x200B; 紹介ビデオ &#x200B;](https://video.tv.adobe.com/v/330102/?autoplay=true&hidetitle=true&captions=jpn) も確認できます。

>[!NOTE]
>
>メールコンテンツをゼロからデザインしないようにするには、標準提供のコンテンツテンプレートを使用できます。 詳しくは、[&#x200B; コンテンツテンプレート &#x200B;](../../designing/using/using-reusable-content.md#content-templates) を参照してください。

## メール構造の定義 {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントは、メールのレイアウトを定義します。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="メール列の定義"
>abstract="E メールデザイナーを使用すると、列構造を定義することで、メールのレイアウトを簡単に定義できます。"

E メールデザイナーを使用すると、メールの構造を簡単に定義できます。簡単なドラッグ＆ドロップ操作で構造要素を追加して移動することで、メールの形状を数秒でデザインできます。

メールの構造を編集するには：

1. 既存のコンテンツを開くか、新しいメールコンテンツを作成します。
1. **[!UICONTROL Structure components]** にアクセスするには、左側の「**+**」アイコンを選択します。

   ![](assets/email_designer_structure.png)

1. メールを形作るのに必要な構造コンポーネントをドラッグ&amp;ドロップします。

   ![](assets/email_designer_structure_components.png)

   青い線は、構造コンポーネントをドロップする前の、構造コンポーネントの正確な場所を具体化しています。 他のどのコンポーネントの上、間、下にドロップしても構いませんが、コンポーネント内にはドロップできません。

   >[!NOTE]
   >
   >列のスタックは、すべてのメールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、列はスタックされません。
   >
   >メールに配置した後は、既にコンテンツコンポーネントまたはフラグメントが内部に配置されていない限り、コンポーネントを移動または削除できません。

1. 1 つ以上の列で構成される、複数の構造コンポーネントを使用できます。

   **[!UICONTROL n:n column]** コンポーネントを選択して、列数（3～10）を任意に定義します。 また、各列の下部にある矢印を移動して、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各列のサイズは、構造コンポーネントの全幅の 10％未満にすることはできません。空でない列は削除できません。

構造を定義すると、コンテンツフラグメントやコンポーネントをメールに追加できます。

## プリヘッダーの使用 {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="プリヘッダーの使用"
>abstract="プリヘッダーを使用すると、メールの開封率を高める短い概要テキストを設定できます。"

プリヘッダーは、インボックスからメールを表示する際に件名の後に表示される短い概要テキストです。 プリヘッダーは、より高い開封率を提供します。

「**[!UICONTROL Preheader]**」編集ボックスを選択し、コンテンツを入力します。

![](assets/email_designer_preheader.png)

プリヘッダーコンテンツには、**[!UICONTROL Content block]**、**[!UICONTROL Dynamic content]** または **[!UICONTROL Personalization fields]** を追加できます。

>[!NOTE]
>
>プリヘッダーは、すべてのメールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、プリヘッダーは表示されません。

## コンテンツコンポーネントの使用 {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、メールの作成に編集できる空のコンテンツプレースホルダーです。"

コンテンツコンポーネントは、メールに配置して編集できる生の空コンポーネントです。

構造コンポーネントには、必要な数だけコンテンツコンポーネントを追加できます。 これらは、構造コンポーネント内または別の構造コンポーネントに移動することもできます。

以下は、メールDesignerで使用できるコンポーネントのリストです。

### **[!UICONTROL Button]**

複数のボタンを使用する必要がある場合は、各ボタンを最初から編集するのではなく、コンテキストツールバーを使用して **[!UICONTROL Button]** コンポーネントを複製できます。

再利用可能なフラグメントにボタンを保存することもできます。 詳しくは、[&#x200B; コンテンツフラグメントの作成 &#x200B;](../../designing/using/using-reusable-content.md#creating-a-content-fragment) および [&#x200B; コンテンツをフラグメントとして保存 &#x200B;](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment) を参照してください。

「**[!UICONTROL Fallback view]**」を選択すると、メールDesignerにフォールバック画像が表示されます。

### **[!UICONTROL Text]**

このコンポーネントを使用すると、メールにテキストを挿入できます。 テキストの色、スタイル、サイズは **[!UICONTROL Component Settings]** で調整できます。

### **[!UICONTROL Divider]**

このコンポーネントを使用すると、メールに分割線を挿入できます。 **[!UICONTROL Component Settings]** で区切り線の色、スタイル、およびサイズを選択できます。

### **[!UICONTROL HTML]**

このコンポーネントを使用して、既存のHTMLの別の部分をコピーして貼り付けることができます。 これにより、無料のモジュラーHTML コンポーネントを作成できます。

>[!NOTE]
>
>無料のHTML コンポーネントは、編集できますが、オプションは限られています。 すべてのスタイルがインライン化されていない場合は、HTML コードの **head** セクションに適切な CSS を必ず追加してください。そうしないと、メールは応答しません。 「**[!UICONTROL Preview]**」ボタンを使用して、コンテンツの応答性をテストします（[&#x200B; メッセージのプレビュー &#x200B;](../../sending/using/previewing-messages.md) を参照）。

外部コンテンツを簡単にメールDesignerAdobeに準拠させるには、ゼロからメッセージを作成し、既存のメールのコンテンツをフラグメントとコンポーネントにコピーすることをお勧めします。

再作成できないコンテンツがある場合は、**[!UICONTROL Html]** コンテンツコンポーネントを使用して、元のメールからHTML コードをコピー&amp;ペーストできます。 続行する前に、HTMLについて熟知していることを確認してください。

>[!NOTE]
>
>新しいコンテンツは、元のメールの正確なコピーではありませんが、以下の手順に従って、できるだけ近いメッセージを作成できます。

**コンテンツのコピー前**

1. 元のメールで、送信する各メールに固有のセクションから再利用可能なセクションを特定します。
1. 使用するすべての画像とアセットを保存します。
1. HTMLに精通している場合は、元のHTML コンテンツを様々な部分に分割します。

### ビデオ {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="ビデオ設定"
>abstract="このコンポーネントを使用して、メールにビデオを挿入します。ただし、ビデオはすべてのメールクライアントで機能するわけではありません。フォールバック画像を設定することをお勧めします。"

ビデオ コンポーネントをメールの構造コンポーネントに挿入し、**[!UICONTROL Component Settings]** ールバーにビデオリンクを入力します。

>[!NOTE]
>
>ビデオは、すべてのメールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、フォールバックが表示されます。

### 画像

このコンポーネントを使用して、メールに画像を挿入します。

画像コンポーネントを構造コンポーネントに挿入し、「参照」をクリックして、コンピューターから画像ファイルをアップロードします。

### **[!UICONTROL Social]**

このコンポーネントを使用すると、メールにソーシャルメディアページへのリンクを挿入できます。 表示するリンクと、**[!UICONTROL Component Settings]** に表示されるリンクのアイコンのサイズを選択できます。

### カルーセル {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="カルーセル設定"
>abstract="コンテンツにカルーセルを挿入して設定する方法を説明します。カルーセルは、一部のメールクライアントで機能せず、サポートされていない場合はフォールバック画像が表示されます。"

1. **[!UICONTROL Carousel]** コンポーネントを構造コンポーネントの中にドラッグ&amp;ドロップします。
1. コンピューターから画像を参照して選択します。

   ![](assets/des_carousel_browse.png)

1. **[!UICONTROL Settings]** パネルから、カルーセルに表示するサムネールの数を設定します。
1. コンピューターからフォールバック画像を選択します。

   ![](assets/des_carousel_fallback.png)

カルーセルコンポーネントは、すべてのメールプログラムと互換性があるわけではありません。メールにカルーセルがサポートされていない場合は、代わりに画像を表示するフォールバックをアップロードします。

>[!NOTE]
>
>カルーセルコンポーネントは、次のメールプラットフォームと互換性があります。Apple Mail 7、Apple Mail 8、Mac用の Outlook 2011、Mac用の Outlook 2016、Mozilla Thunderbird、iPadおよびiPad mini iOS、iPhone iOS、Android、AOL （Chrome、Firefox、Safari）。

**関連トピック**：

- [メールの作成](../../channels/using/creating-an-email.md)
- [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
- [メッセージのスケジュール設定](../../sending/using/about-scheduling-messages.md)
- [メッセージのプレビュー](../../sending/using/previewing-messages.md)
- [メールのレンダリング](../../sending/using/email-rendering.md)
