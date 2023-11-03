---
title: 新規でのメールのデザイン
description: E メールデザイナーでゼロから E メールをデザインする方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 27%

---

# 新規でのメールのデザイン {#designing-an-email-content-from-scratch}

E メールコンテンツのマスター方法を説明します。 E メールデザイナーを使用すると、独自の定義済みコンテンツを使用して、または使用せずに E メールやテンプレートを作成できます。

E メールデザイナーを使用して E メールコンテンツを最初から作成および設計する主な手順は次のとおりです。

1. E メールを作成し、そのコンテンツを開きます。
1. 電子メールの形状を作成する構造コンポーネントを追加します。 詳しくは、 [メール構造の編集](#defining-the-email-structure).
1. 構造コンポーネントにコンテンツコンポーネントとフラグメントを挿入します。 詳しくは、 [フラグメントとコンテンツコンポーネントの追加](#defining-the-email-structure).
1. 画像を追加し、E メールのテキストを編集します。 [画像の挿入](../../designing/using/images.md#inserting-images)を参照してください。
1. パーソナライゼーションフィールドやリンクなどを追加して E メールをパーソナライズします。 詳しくは、 [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field), [リンクの挿入](../../designing/using/links.md#inserting-a-link) および [E メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. 電子メールの件名行を定義します。 詳しくは、 [E メールの件名行のパーソナライズ](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. メールのプレビュー.
1. コンテンツを保存し、オーディエンスを定義し、送信を適切にスケジュールしたことを確認したら、メッセージを続行します。

また、 [紹介ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true).

>[!NOTE]
>
>E メールコンテンツをゼロからデザインするのを避けるために、標準のコンテンツテンプレートを使用できます。 詳しくは、 [コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates).

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

E メールの構造を編集するには：

1. 既存のコンテンツを開くか、新しい E メールコンテンツを作成します。
1. 次にアクセス： **[!UICONTROL Structure components]** 選択して **+** アイコンをクリックします。

   ![](assets/email_designer_structure.png)

1. 電子メールの形成に必要な構造コンポーネントをドラッグ&amp;ドロップします。

   ![](assets/email_designer_structure_components.png)

   青い線は、ドロップする前に構造コンポーネントの正確な位置を具現化します。 上、他のコンポーネントの間または下にドロップできますが、内部にはドロップできません。

   >[!NOTE]
   >
   >列のスタックは、すべてのメールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、列はスタックされません。
   >
   >E メールに配置した後は、既にコンテンツコンポーネントまたはフラグメントが配置されていない限り、コンポーネントを移動または削除することはできません。

1. 1 つ以上の列で構成される構造コンポーネントを使用できます。

   を選択します。 **[!UICONTROL n:n column]** コンポーネントを使用して、選択する列の数を定義します (3 ～ 10)。 また、各列の下部にある矢印を移動して、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各列のサイズは、構造コンポーネントの全幅の 10％未満にすることはできません。空でない列は削除できません。

構造を定義したら、コンテンツフラグメントとコンポーネントを E メールに追加できます。

## プリヘッダーの使用 {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="プリヘッダーの使用"
>abstract="プリヘッダーを使用すると、メールの開封率を高める短い概要テキストを設定できます。"

プリヘッダーは、インボックスから E メールを表示する際に件名の後に続く短い概要テキストです。 プリヘッダーは、より高い開封率を提供します。

を選択します。 **[!UICONTROL Preheader]** 編集ボックスを開き、コンテンツを完成させます。

![](assets/email_designer_preheader.png)

次の項目を追加できます： **[!UICONTROL Content block]**, a **[!UICONTROL Dynamic content]** または **[!UICONTROL Personalization fields]** をプリヘッダーコンテンツに追加します。

>[!NOTE]
>
>プリヘッダーは、すべてのメールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、プリヘッダーは表示されません。

## コンテンツコンポーネントの使用 {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、メールの作成に編集できる空のコンテンツプレースホルダーです。"

コンテンツコンポーネントは生の空コンポーネントで、E メールに配置すると編集できます。

コンテンツコンポーネントは、必要な数だけ構造コンポーネントに追加できます。 また、構造コンポーネント内や別の構造コンポーネントに移動することもできます。

E メールデザイナーで使用可能なコンポーネントのリストを次に示します。

### **[!UICONTROL Button]**

複数のボタンを使用する必要がある場合は、各ボタンを一から編集するのではなく、 **[!UICONTROL Button]** コンポーネントを使用します。

また、ボタンをフラグメントに保存して再利用することもできます。 詳しくは、 [コンテンツフラグメントの作成](../../designing/using/using-reusable-content.md#creating-a-content-fragment) および [コンテンツをフラグメントとして保存](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

選択 **[!UICONTROL Fallback view]** をクリックして、E メールデザイナーにフォールバック画像を表示します。

### **[!UICONTROL Text]**

このコンポーネントを使用して、E メールにテキストを挿入します。 テキストの色、スタイル、サイズは、 **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

このコンポーネントを使用して、E メールに分割線を挿入します。 区切り線の色、スタイル、サイズは、 **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

このコンポーネントを使用して、既存のHTMLの異なる部分をコピー&amp;ペーストします。 これにより、無料のモジュラーHTMLコンポーネントを作成できます。

>[!NOTE]
>
>フリーHTMLコンポーネントは、制限付きオプションで編集できます。 すべてのスタイルがインライン化されていない場合は、 **head** HTMLコードのセクションに含めてください。そうしないと、E メールが応答しなくなります。 以下を使用します。 **[!UICONTROL Preview]** ボタンを使用して、コンテンツの応答性をテストします ( [メッセージのプレビュー](../../sending/using/previewing-messages.md)) をクリックします。

外部コンテンツを E メールデザイナーに準拠させる場合には、Adobeは最初からメッセージを作成し、既存の E メールのコンテンツをフラグメントやコンポーネントにコピーすることをお勧めします。

再作成できないコンテンツがある場合は、元の E メールから、 **[!UICONTROL Html]** コンテンツコンポーネント。 先に進む前に、HTMLに関する詳細を確認します。

>[!NOTE]
>
>新しいコンテンツは、元の E メールの正確なコピーではありませんが、以下の手順で、できるだけ近いメッセージを作成する手順を説明します。

**コンテンツをコピーする前に**

1. 元の E メールで、送信する各 E メールに固有のセクションから再利用可能なセクションを特定します。
1. 使用するすべての画像とアセットを保存します。
1. HTMLに詳しい場合は、元のHTMLコンテンツを別の部分に分割します。

### ビデオ {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="ビデオ設定"
>abstract="このコンポーネントを使用して、メールにビデオを挿入します。ただし、ビデオはすべてのメールクライアントで機能するわけではありません。フォールバック画像を設定することをお勧めします。"
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="追加情報"

ビデオコンポーネントを電子メールの構造コンポーネントに挿入し、 **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>ビデオは、すべてのメールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、フォールバックが表示されます。

### 画像

このコンポーネントを使用して、電子メールに画像を挿入します。

画像コンポーネントを構造コンポーネントに挿入し、「参照」をクリックして、コンピューターから画像ファイルをアップロードします。

### **[!UICONTROL Social]**

このコンポーネントを使用して、E メールにソーシャルメディアページへのリンクを挿入します。 表示するリンクと、そのアイコンのサイズを **[!UICONTROL Component Settings]**.

### カルーセル {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="カルーセル設定"
>abstract="コンテンツにカルーセルを挿入して設定する方法を説明します。カルーセルは、一部のメールクライアントで機能せず、サポートされていない場合はフォールバック画像が表示されます。"

1. 次をドラッグ&amp;ドロップ： **[!UICONTROL Carousel]** コンポーネントを構造コンポーネント内に配置します。
1. コンピューターから画像を参照して選択します。

   ![](assets/des_carousel_browse.png)

1. 次から： **[!UICONTROL Settings]** パネルで、カルーセルに表示するサムネールの数を設定します。
1. コンピューターからフォールバック画像を選択します。

   ![](assets/des_carousel_fallback.png)

カルーセルコンポーネントは、すべてのメールプログラムと互換性があるわけではありません。メールにカルーセルがサポートされていない場合は、代わりに画像を表示するフォールバックをアップロードします。

>[!NOTE]
>
>カルーセルコンポーネントは、次の E メールプラットフォームと互換性があります。 Apple Mail 7、Apple Mail 8、Outlook 2011 for Mac、Outlook 2016 for Mac、Mozilla Thunderbird、iPadとiPad mini iOS、iPhoneiOS、Android、AOL(Chrome、Firefox、Sari)。

**関連トピック**：

- [メールの作成](../../channels/using/creating-an-email.md)
- [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
- [メッセージのスケジュール設定](../../sending/using/about-scheduling-messages.md)
- [メッセージのプレビュー](../../sending/using/previewing-messages.md)
- [メールのレンダリング](../../sending/using/email-rendering.md)
