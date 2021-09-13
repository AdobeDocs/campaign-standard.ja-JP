---
title: '新規での E メールのデザイン '
description: EメールデザイナーでゼロからEメールをデザインする方法を紹介します。
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
ht-degree: 7%

---

# 新規での E メールのデザイン {#designing-an-email-content-from-scratch}

Eメールコンテンツの編集をマスターする方法を説明します。 Eメールデザイナーを使用すると、独自の定義済みコンテンツを使用して、または使用せずに、Eメールやテンプレートを作成できます。

Eメールデザイナーを使用してEメールコンテンツを最初から作成およびデザインする主な手順は次のとおりです。

1. Eメールを作成し、その内容を開きます。
1. 構造コンポーネントを追加して、Eメールを形成します。 [Eメール構造の編集](#defining-the-email-structure)を参照してください。
1. 構造コンポーネントにコンテンツコンポーネントとフラグメントを挿入します。 [フラグメントとコンテンツコンポーネントの追加](#defining-the-email-structure)を参照してください。
1. 画像を追加し、Eメールのテキストを編集します。 [画像の挿入](../../designing/using/images.md#inserting-images)を参照してください。
1. パーソナライゼーションフィールドやリンクなどを追加して、Eメールをパーソナライズします。 [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)、[リンクの挿入](../../designing/using/links.md#inserting-a-link)および[Eメールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)を参照してください。
1. 電子メールの件名行を定義します。 [Eメールの件名行のパーソナライズ](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email)を参照してください。
1. E メールのプレビュー.
1. コンテンツを保存し、オーディエンスを定義し、送信を適切にスケジュールした後で、メッセージを続行します。

[紹介ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true)もご覧ください。

>[!NOTE]
>
>Eメールコンテンツをゼロからデザインするのを避けるために、標準のコンテンツテンプレートを使用できます。 詳しくは、[コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates)を参照してください。

## 電子メール構造の定義 {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントは、Eメールのレイアウトを定義します。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Eメール列の定義"
>abstract="Eメールデザイナーを使用すると、列構造を定義することで、Eメールのレイアウトを簡単に定義できます。"

Eメールデザイナーを使用すると、Eメールの構造を簡単に定義できます。 簡単なドラッグ&amp;ドロップ操作で構造要素を追加および移動することで、Eメールの形状を数秒でデザインできます。

Eメールの構造を編集するには：

1. 既存のコンテンツを開くか、新しいEメールコンテンツを作成します。
1. 左側の&#x200B;**+**&#x200B;アイコンを選択して、**[!UICONTROL Structure components]**&#x200B;にアクセスします。

   ![](assets/email_designer_structure.png)

1. Eメールの形状を設定する必要がある構造コンポーネントをドラッグ&amp;ドロップします。

   ![](assets/email_designer_structure_components.png)

   構造コンポーネントをドロップする前に、青い線が正確な位置を具現化します。 他のコンポーネントの間または下にドロップできますが、内部にドロップすることはできません。

   >[!NOTE]
   >
   >列のスタックは、すべての電子メールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、列はスタックされません。
   >
   >Eメールに配置した後は、既にコンテンツコンポーネントまたはフラグメントが配置されていない限り、コンポーネントを移動または削除できません。

1. 1つ以上の列で構成される複数の構造コンポーネントを使用できます。

   **[!UICONTROL n:n column]**&#x200B;コンポーネントを選択して、選択する列の数を定義します(3 ～ 10)。 また、各列の下部にある矢印を動かして、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各列のサイズは、構造コンポーネントの全幅の10%未満にすることはできません。 空でない列は削除できません。

構造を定義すると、コンテンツフラグメントとコンポーネントをEメールに追加できます。

## プリヘッダーの使用 {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="プリヘッダーの使用"
>abstract="プリヘッダーを使用すると、より高い開封率を電子メールに提供する短い概要テキストを設定できます。"

プリヘッダーは、インボックスからEメールを表示する際に件名行に続く短い概要テキストです。 プリヘッダーは、開封率を高めます。

**[!UICONTROL Preheader]**&#x200B;編集ボックスを選択し、内容を入力します。

![](assets/email_designer_preheader.png)

プリヘッダーコンテンツには、**[!UICONTROL Content block]**、**[!UICONTROL Dynamic content]**&#x200B;または&#x200B;**[!UICONTROL Personalization fields]**&#x200B;を追加できます。

>[!NOTE]
>
>プリヘッダーは、すべての電子メールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、プリヘッダーは表示されません。

## コンテンツコンポーネントの使用 {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、空のコンテンツプレースホルダーで、電子メールを作成するために編集できます。"

コンテンツコンポーネントは生の空コンポーネントで、Eメールに配置すると編集できます。

コンテンツコンポーネントは、構造コンポーネントに必要な数だけ追加できます。 また、構造コンポーネント内や別の構造コンポーネント内に移動することもできます。

Eメールデザイナーで使用可能なコンポーネントのリストを次に示します。

### **[!UICONTROL Button]**

複数のボタンを使用する必要がある場合は、各ボタンを一から編集するのではなく、コンテキストツールバーを使用して&#x200B;**[!UICONTROL Button]**&#x200B;コンポーネントを複製できます。

また、ボタンをフラグメントに保存して再利用することもできます。 詳しくは、[コンテンツフラグメントの作成](../../designing/using/using-reusable-content.md#creating-a-content-fragment)および[コンテンツをフラグメントとして保存](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)を参照してください。

「 **[!UICONTROL Fallback view]** 」を選択して、Eメールデザイナーにフォールバック画像を表示します。

### **[!UICONTROL Text]**

このコンポーネントを使用して、Eメールにテキストを挿入します。 **[!UICONTROL Component Settings]**&#x200B;内のテキストの色、スタイル、サイズを調整できます。

### **[!UICONTROL Divider]**

このコンポーネントを使用して、Eメールに分割線を挿入します。 **[!UICONTROL Component Settings]**&#x200B;では、改行の色、スタイルおよびサイズを選択できます。

### **[!UICONTROL HTML]**

このコンポーネントを使用して、既存のHTMLの様々な部分をコピー&amp;ペーストします。 これにより、無料のモジュラーHTMLコンポーネントを作成できます。

>[!NOTE]
>
>無料のHTMLコンポーネントは、制限されたオプションで編集できます。 すべてのスタイルがインライン化されていない場合は、HTMLコードの&#x200B;**head**&#x200B;セクションに適切なCSSを追加してください。そうしないと、Eメールが応答しなくなります。 **[!UICONTROL Preview]**&#x200B;ボタンを使用して、コンテンツの応答性をテストします（[メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照）。

外部コンテンツをEメールデザイナーに準拠させるだけで済むように、Adobeでは、メッセージを一から作成して、既存のEメールからフラグメントやコンポーネントにコピーすることをお勧めします。

再作成できないコンテンツがある場合は、**[!UICONTROL Html]**&#x200B;コンテンツコンポーネントを使用して、元のEメールからHTMLコードをコピー&amp;ペーストできます。 先に進む前に、HTMLについて理解しておく必要があります。

>[!NOTE]
>
>新しいコンテンツは元のEメールの正確なコピーではありませんが、以下の手順で、できるだけ近いメッセージを作成します。

**コンテンツをコピーする前に**

1. 元のEメールで、送信する各Eメールに固有のセクションから再利用可能なセクションを特定します。
1. 使用するすべての画像とアセットを保存します。
1. HTMLに詳しい場合は、元のHTMLコンテンツを別々の部分に分けます。

### ビデオ {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="ビデオ設定"
>abstract="このコンポーネントを使用して、ビデオをEメールに挿入します。 ビデオは、すべての電子メールクライアントで機能するわけではありません。 フォールバック画像を設定することをお勧めします。"
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="追加情報"

電子メールの構造コンポーネントにビデオコンポーネントを挿入し、**[!UICONTROL Component Settings]**&#x200B;にビデオリンクを入力します。

>[!NOTE]
>
>ビデオは、すべての電子メールプログラムと互換性があるわけではないことに注意してください。サポートされていない場合、フォールバックが表示されます。

### 画像

このコンポーネントを使用して、Eメールに画像を挿入します。

画像コンポーネントを構造コンポーネントに挿入し、「参照」をクリックして、コンピューターから画像ファイルをアップロードします。

### **[!UICONTROL Social]**

このコンポーネントを使用して、Eメールにソーシャルメディアページへのリンクを挿入します。 **[!UICONTROL Component Settings]**&#x200B;では、表示するリンクとそのアイコンのサイズを選択できます。

### カルーセル {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="カルーセル設定"
>abstract="コンテンツにカルーセルを挿入して設定する方法を説明します。カルーセルは、すべての電子メールクライアントで機能するわけではなく、サポートされていない場合はフォールバック画像が表示されます。"

1. **[!UICONTROL Carousel]**&#x200B;コンポーネントを構造コンポーネント内にドラッグ&amp;ドロップします。
1. コンピューターから画像を参照して選択します。

   ![](assets/des_carousel_browse.png)

1. **[!UICONTROL Settings]**&#x200B;ウィンドウで、カルーセルに表示するサムネールの数を設定します。
1. コンピューターからフォールバックイメージを選択します。

   ![](assets/des_carousel_fallback.png)

カルーセルコンポーネントは、すべての電子メールプログラムと互換性があるわけではありません。 電子メールでカルーセルがサポートされていない場合は、代わりに画像を表示するためのフォールバックをアップロードします。

>[!NOTE]
>
>カルーセルコンポーネントは、次のEメールプラットフォームと互換性があります。Apple Mail 7、Apple Mail 8、Outlook 2011 for Mac、Outlook 2016 for Mac、Mozilla Thunderbird、iPadおよびiPad mini iOS、iPhone iOS、Android、AOL（Chrome、FirefoxおよびSari）。

**関連トピック**：

- [E メールの作成](../../channels/using/creating-an-email.md)
- [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
- [メッセージのスケジュール設定](../../sending/using/about-scheduling-messages.md)
- [メッセージのプレビュー](../../sending/using/previewing-messages.md)
- [E メールのレンダリング](../../sending/using/email-rendering.md)
