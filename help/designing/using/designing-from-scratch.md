---
title: '新規での電子メールのデザイン '
seo-title: '新規での電子メールのデザイン '
description: '新規での電子メールのデザイン '
seo-description: 電子メールデザイナーでゼロから電子メールをデザインする方法を確認します。
page-status-flag: 非活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 新規での電子メールのデザイン {#designing-an-email-content-from-scratch}

電子メールコンテンツの編集をマスターする方法について説明します。 電子メールデザイナーを使用すると、独自の定義済みコンテンツで始まる電子メールやテンプレートを作成できます。

## 電子メールを作成するための主要な手順 {#key-steps-to-create-your-email}

電子メールデザイナーを使用して電子メールコンテンツを最初から作成し、デザインする主な手順は次のとおりです。

1. 電子メールを作成し、その内容を開きます。
1. 電子メールの形状を決める構造コンポーネントを追加します。 「電子メ [ール構造の編集」を参照してください](#defining-the-email-structure)。
1. 構造コンポーネントにコンテンツコンポーネントとフラグメントを挿入します。 詳しくは、フラ [グメントとコンテンツコンポーネントの追加を参照してくださ](#defining-the-email-structure)い。
1. 画像を追加し、電子メールのテキストを編集します。 詳しくは、イ [メージの挿入を参照してくださ](../../designing/using/images.md#inserting-images)い。
1. パーソナライゼーションフィールドやリンクなどを追加して、電子メールをパーソナライズします。 詳しくは、 [パーソナライゼーション](../../designing/using/personalization.md#inserting-a-personalization-field)フィールドの挿入 [、リンクの挿入](../../designing/using/links.md#inserting-a-link) 、電子 [メールでの動的コンテンツの定義を参照してください](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。
1. 電子メールの件名行を定義します。 詳しくは、 [電子メールの件名行のパーソナライズを参照してください](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email)。
1. 電子メールをプレビューします。
1. コンテンツを保存し、オーディエンスが定義され、送信が正しくスケジュールされていることを確認した後、メッセージを進めます。

この紹介ビデオもご覧 [ください](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)。

>[!NOTE]
>
>電子メールコンテンツをゼロからデザインするのを避けるために、そのまま使用できるコンテンツテンプレートを使用できます。 詳しくは、「コンテンツテンプレート」を参 [照してください](../../designing/using/using-reusable-content.md#content-templates)。

### 電子メール構造の定義 {#defining-the-email-structure}

電子メールデザイナーを使用すると、電子メールの構造を簡単に定義できます。 簡単なドラッグ&amp;ドロップ操作で構造要素を追加したり移動したりすることで、電子メールの形状を数秒でデザインできます。

電子メールの構造を編集するには：

1. 既存のコンテンツを開くか、新しい電子メールコンテンツを作成します。
1. 左側の+ア **[!UICONTROL Structure components]** イコンを選 **択して** 、を表示します。

   ![](assets/email_designer_structure.png)

1. 電子メールの形状を決める必要がある構造コンポーネントをドラッグ&amp;ドロップします。

   ![](assets/email_designer_structure_components.png)

   青い線は、構造コンポーネントをドロップする前に、その正確な位置を具現化します。 上または下に他のコンポーネントの間または内部以外のコンポーネントの間にドロップできます。

   >[!NOTE]
   >
   >電子メールに配置したコンポーネントは、既にコンテンツコンポーネントまたはフラグメントが内部に配置されていない限り、移動したり削除したりすることはできません。

1. 1つ以上の列で構成される構造コンポーネントがいくつか使用できます。

   コンポーネン **[!UICONTROL n:n column]** トを選択して、選択する列の数を定義します(3 ～ 10)。 各列の下部にある矢印を動かして、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各列のサイズは、構造コンポーネントの全幅の10%未満にすることはできません。 空でない列は削除できません。

構造を定義すると、電子メールにコンテンツフラグメントやコンポーネントを追加できます。

### コンテンツコンポーネントの使用 {#about-content-components}

コンテンツコンポーネントは、電子メールに配置した後に編集できる生の空のコンポーネントです。

構造コンポーネントには、必要な数だけコンテンツコンポーネントを追加できます。 構造コンポーネント内または別の構造コンポーネント内に移動することもできます。

電子メールデザイナーで使用可能なコンポーネントのリストを次に示します。

- **[!UICONTROL Button]**

   各ボタンを最初から編集するのではなく、複数のボタンを使用する必要がある場合は、コンテキストツールバーを使用してコ **[!UICONTROL Button]** ンポーネントを複製できます。

   また、再利用可能なボタンをフラグメントに保存することもできます。 詳しくは、「コンテンツフラグメントの作 [成」および「フラグメントとし](../../designing/using/using-reusable-content.md#creating-a-content-fragment) てのコンテンツの保存」を参照してくださ [](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)い。

1. 電子メー **[!UICONTROL Fallback view]** ルデザイナーにフォールバック画像を表示する場合に選択します。

- **[!UICONTROL Text]**

   このコンポーネントを使用して、電子メールにテキストを挿入します。 では、テキストの色、スタイル、サイズを調整できます **[!UICONTROL Component Settings]**。

- **[!UICONTROL Divider]**

   電子メールに分割線を挿入するには、このコンポーネントを使用します。 で区切り線の色、スタイル、サイズを選択できます **[!UICONTROL Component Settings]**。

- **[!UICONTROL Html]**

   このコンポーネントを使用して、既存のHTMLの様々な部分をコピー&amp;ペーストします。 これにより、無料のモジュラーHTMLコンポーネントを作成できます。

   >[!NOTE]
   >
   >無料のHTMLコンポーネントは、限られたオプションで編集できます。 すべてのスタイルがインライン化されていない場合は、HTMLコードの **head** セクションに適切なCSSを必ず追加してください。追加しないと、電子メールがレスポンシブになりません。 ボタンを使用 **[!UICONTROL Preview]** して、コンテンツの応答性をテストします(メッセージのプレビ [ューを参照](../../sending/using/previewing-messages.md))。

   外部コンテンツを電子メールデザイナーに簡単に準拠させるために、最初からメッセージを作成し、既存の電子メールの内容をフラグメントやコンポーネントにコピーすることをお勧めします。

   再作成できないコンテンツがある場合は、コンテンツコンポーネントを使用して元の電子メールからHTMLコードをコピー&amp;ペースト **[!UICONTROL Html]** できます。 先に進む前に、HTMLに詳しくあることを確認してください。

   <!-- A full example is presented below. -->

   >[!NOTE]
   >
   >新しいコンテンツは元の電子メールの正確なコピーではありませんが、以下の手順に従って、できるだけ近いメッセージを作成します。

   **コンテンツをコピーする前に**

   1. 元の電子メールで、送信する各電子メールに固有のセクションから、再利用可能なセクションを特定します。
   1. 使用するすべての画像とアセットを保存します。
   1. HTMLに詳しい場合は、元のHTMLコンテンツを別々の部分に分割します。

- **[!UICONTROL Video]**

   このコンポーネントを使用して、電子メールにビデオを挿入します。

   電子メールの構造コンポーネントにビデオコンポーネントを挿入し、にビデオリンクを入力しま **[!UICONTROL Component Settings]**&#x200B;す。

- **[!UICONTROL Image]**

   このコンポーネントを使用して、電子メールに画像を挿入します。

   画像コンポーネントを構造コンポーネントに挿入し、「参照」をクリックして、コンピュータから画像ファイルをアップロードします。

- **[!UICONTROL Social]**

   このコンポーネントを使用して、電子メールにソーシャルメディアページへのリンクを挿入します。 表示するリンクと、そのアイコンのサイズを選択できます **[!UICONTROL Component Settings]**。

- **[!UICONTROL Carousel]**

   1. 構造コンポーネント内にコンポ **[!UICONTROL Carousel]** ーネントをドラッグ&amp;ドロップします。
   1. コンピューターから画像を参照して選択します。
   ![](assets/des_carousel_browse.png)

   1. パネル **[!UICONTROL Settings]** から、カルーセルに含めるサムネールの数を設定します。
   1. コンピューターからフォールバック画像を選択します。
   ![](assets/des_carousel_fallback.png)

   カルーセルコンポーネントは、すべての電子メールプログラムと互換性があるわけではありません。 電子メールでカルーセルがサポートされていない場合は、代わりに画像を表示するためのフォールバックをアップロードします。

   >[!NOTE]
   >
   >カルーセルコンポーネントは、次の電子メールプラットフォームと互換性があります。Apple Mail 7、Apple Mail 8、Outlook 2011 for Mac、Outlook 2016 for Mac、Mozilla Thunderbird、iPadおよびiPad mini iOS、iPhone iOS、Android、AOL（Chrome、FirefoxおよびAri）。

**関連トピック**：

- [電子メールの作成](../../channels/using/creating-an-email.md)
- [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
- [メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)
- [メッセージのプレビュー](../../sending/using/previewing-messages.md)
- [E メールのレンダリング](../../sending/using/email-rendering.md)
