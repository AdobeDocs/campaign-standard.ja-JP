---
solution: Campaign Standard
product: campaign
title: '新規での E メールのデザイン '
description: 電子メールデザイナーでゼロから電子メールをデザインする方法を確認します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: 電子メールデザイン
role: 開業医
level: 初心者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 6%

---


# 新規での E メールのデザイン {#designing-an-email-content-from-scratch}

電子メールコンテンツのエディションをマスターする方法を説明します。 電子メールデザイナーを使用すると、独自の定義済みコンテンツの有無に関係なく、電子メールやテンプレートを作成できます。

電子メールデザイナーを使用して電子メールコンテンツを新規に作成しデザインする主な手順は次のとおりです。

1. 電子メールを作成し、その内容を開きます。
1. 電子メールを追加形成するためのコンポーネントを構造化します。 「[電子メール構造の編集](#defining-the-email-structure)」を参照してください。
1. 構造コンポーネントにコンテンツコンポーネントとフラグメントを挿入します。 [フラグメントとコンテンツコンポーネントの追加](#defining-the-email-structure)を参照してください。
1. 画像追加を作成し、電子メールのテキストを編集します。 [画像の挿入](../../designing/using/images.md#inserting-images)を参照してください。
1. パーソナライゼーションフィールドやリンクなどを追加して、電子メールをパーソナライズします。 「[パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)」、「[リンク](../../designing/using/links.md#inserting-a-link)の挿入」、「[電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)」を参照してください。
1. 電子メールの件名行を定義します。 [電子メールの件名行の個人設定](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email)を参照してください。
1. E メールのプレビュー.
1. コンテンツを保存し、オーディエンスを定義し、送信を正しくスケジュールした後、メッセージを続行します。

また、この[導入ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true)を見ることもできます。

>[!NOTE]
>
>電子メールコンテンツを一からデザインするのを避けるために、標準搭載されたコンテンツテンプレートを使用できます。 詳しくは、[コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates)を参照してください。

## 電子メール構造の定義{#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントは電子メールのレイアウトを定義します。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="電子メール列の定義"
>abstract="電子メールデザイナを使用すると、列構造を定義することで、電子メールのレイアウトを簡単に定義できます。"

電子メールデザイナーを使用すると、電子メールの構造を簡単に定義できます。 単純なドラッグ&amp;ドロップ操作で構造要素を追加したり移動したりすることで、電子メールの形状を数秒以内でデザインできます。

電子メールの構造を編集するには：

1. 既存のコンテンツを開くか、新しい電子メールコンテンツを作成します。
1. 左側の&#x200B;**+**&#x200B;アイコンを選択して、**[!UICONTROL Structure components]**&#x200B;にアクセスします。

   ![](assets/email_designer_structure.png)

1. 電子メールの形状を決めるために必要な構造コンポーネントをドラッグ&amp;ドロップします。

   ![](assets/email_designer_structure_components.png)

   青い線は、構造コンポーネントをドロップする前に、構造コンポーネントの正確な位置を具現化します。 上、他のコンポーネント間、または他のコンポーネントの下にドロップできますが、内部にはドロップできません。

   >[!NOTE]
   >
   >列のスタックはすべての E メールプログラムと互換性がないことに注意してください。サポートされていない場合、列はスタックされません。
   >
   >電子メールに配置したコンポーネントは、既にコンテンツコンポーネントまたはフラグメントが内部に配置されていない限り、移動または削除できません。

1. 1つ以上の列で構成される構造コンポーネントがいくつか使用できます。

   **[!UICONTROL n:n column]**&#x200B;コンポーネントを選択して、選択する列数を定義します(3 ～ 10)。 各列の下部にある矢印を動かして、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各列のサイズを構造コンポーネントの全幅の10%未満にすることはできません。 空以外の列は削除できません。

構造を定義すると、コンテンツのフラグメントやコンポーネントを電子メールに追加できます。

## プリヘッダーの使用{#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="プリヘッダーの使用"
>abstract="プリヘッダーを使用すると、電子メールの開封率を高める短い概要テキストを設定できます。"

プリヘッダーは、受信トレイから電子メールを表示する際に、件名の後に続く短い概要テキストです。 プリヘッダーは、より高いオープン率を提供します。

**[!UICONTROL Preheader]**&#x200B;編集ボックスを選択し、内容を入力します。

![](assets/email_designer_preheader.png)

プリヘッダーコンテンツには、**[!UICONTROL Content block]**、**[!UICONTROL Dynamic content]**、または&#x200B;**[!UICONTROL Personalization fields]**&#x200B;を追加できます。

>[!NOTE]
>
>プリヘッダーはすべての E メールプログラムと互換性がないことに注意してください。サポートされていない場合、プリヘッダーは表示されません。

## コンテンツコンポーネントの使用{#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは空のコンテンツプレースホルダーで、電子メールを作成するために編集できます。"

コンテンツコンポーネントは生の空のコンポーネントで、一度電子メールに配置すれば編集できます。

構造コンポーネントには、必要な数のコンテンツコンポーネントを追加できます。 構造コンポーネント内または別の構造コンポーネントに移動することもできます。

電子メールデザイナーで使用可能なコンポーネントのリストを次に示します。

### **[!UICONTROL Button]**

各ボタンを一から編集するのではなく、複数のボタンを使用する必要がある場合は、コンテキストツールバーを使用して&#x200B;**[!UICONTROL Button]**&#x200B;コンポーネントを重複できます。

また、再利用可能なボタンをフラグメントに保存することもできます。 詳しくは、[コンテンツフラグメントの作成](../../designing/using/using-reusable-content.md#creating-a-content-fragment)および[コンテンツをフラグメントとして保存](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)を参照してください。

**[!UICONTROL Fallback view]**&#x200B;を選択して、電子メールデザイナーにフォールバック画像を表示します。

### **[!UICONTROL Text]**

このコンポーネントを使用して、電子メールにテキストを挿入します。 **[!UICONTROL Component Settings]**&#x200B;では、テキストの色、スタイル、サイズを調整できます。

### **[!UICONTROL Divider]**

このコンポーネントを使用して、電子メールに分割線を挿入します。 **[!UICONTROL Component Settings]**&#x200B;では、改行線の色、スタイル、およびサイズを選択できます。

### **[!UICONTROL HTML]**

このコンポーネントを使用して、既存のHTMLの様々な部分をコピー&amp;ペーストします。 これにより、無料のモジュラー型HTMLコンポーネントを作成できます。

>[!NOTE]
>
>無料のHTMLコンポーネントは、制限されたオプションで編集できます。 すべてのスタイルがインラインでない場合は、HTMLコードの&#x200B;**head**&#x200B;セクションに適切なCSSを追加してください。追加しないと、電子メールはレスポンシブになりません。 **[!UICONTROL Preview]**&#x200B;ボタンを使用して、コンテンツの応答性をテストします（[メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照）。

外部コンテンツを単純に電子メールデザイナーに準拠させるために、Adobeでは、最初からメッセージを作成し、既存の電子メールの内容をフラグメントやコンポーネントにコピーすることをお勧めします。

再作成できないコンテンツがある場合は、**[!UICONTROL Html]**&#x200B;コンテンツコンポーネントを使用して、元の電子メールからHTMLコードをコピー&amp;ペーストできます。 先に進む前に、HTMLに関する十分な知識があることを確認してください。

>[!NOTE]
>
>新しいコンテンツは元の電子メールの正確なコピーではありませんが、次の手順に従って、できるだけ近いメッセージを作成します。

**コンテンツをコピーする前に**

1. 元の電子メールで、送信する各電子メールに固有のセクションから、再利用可能なセクションを特定します。
1. 使用するすべての画像とアセットを保存します。
1. HTMLに詳しい場合は、元のHTMLコンテンツを別々の部分に分割します。

### 動画 {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="ビデオ設定"
>abstract="このコンポーネントを使用して、ビデオを電子メールに挿入します。 ビデオは、すべての電子メールクライアントで機能するわけではありません。 フォールバックイメージを設定することをお勧めします。"
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="追加情報"

電子メールの構造コンポーネントにビデオコンポーネントを挿入し、**[!UICONTROL Component Settings]**&#x200B;にビデオリンクを入力します。

>[!NOTE]
>
>ビデオはすべての E メールプログラムと互換性がないことに注意してください。サポートされていない場合は、フォールバックが表示されます。

### 画像

このコンポーネントを使用して、電子メールに画像を挿入します。

画像コンポーネントを構造コンポーネントに挿入し、「参照」をクリックして、コンピューターから画像ファイルをアップロードします。

### **[!UICONTROL Social]**

このコンポーネントを使用して、ソーシャルメディアページへのリンクを電子メールに挿入します。 **[!UICONTROL Component Settings]**&#x200B;に表示するリンクとアイコンのサイズを選択できます。

### カルーセル {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="カルーセル設定"
>abstract="コンテンツにカルーセルを挿入および設定する方法を説明します。カルーセルはすべての電子メールクライアントで機能しません。サポートされていない場合は、フォールバック画像が表示されます。"

1. **[!UICONTROL Carousel]**&#x200B;コンポーネントを構造コンポーネント内にドラッグ&amp;ドロップします。
1. コンピューターから画像を参照して選択します。

   ![](assets/des_carousel_browse.png)

1. **[!UICONTROL Settings]**&#x200B;ペインで、カルーセルに含めるサムネールの数を設定します。
1. コンピューターからフォールバックイメージを選択します。

   ![](assets/des_carousel_fallback.png)

カルーセルコンポーネントは、すべての電子メールプログラムと互換性があるわけではありません。 電子メールでカルーセルがサポートされていない場合は、代わりに画像を表示するためのフォールバックをアップロードします。

>[!NOTE]
>
>カルーセルコンポーネントは、次の電子メールプラットフォームと互換性があります。Apple Mail 7、Apple Mail 8、Outlook 2011 for Mac、Outlook 2016 for Mac、Mozilla Thunderbird、iPadおよびiPad mini iOS、iPhone iOS、Android、AOL（Chrome、FirefoxおよびSafari）。

**関連トピック**：

- [E メールの作成](../../channels/using/creating-an-email.md)
- [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
- [メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)
- [メッセージのプレビュー](../../sending/using/previewing-messages.md)
- [E メールのレンダリング](../../sending/using/email-rendering.md)
