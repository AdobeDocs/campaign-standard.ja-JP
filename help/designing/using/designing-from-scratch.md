---
title: '最初から電子メールをデザインする '
seo-title: '最初から電子メールをデザインする '
description: '最初から電子メールをデザインする '
seo-description: 電子メールデザイナで、ゼロからの電子メールコンテンツから電子メールをデザインする方法を説明します。
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
source-git-commit: 78bb4189dea522bbdf3bf8248f405bb4ab381bae

---


# 最初から電子メールをデザインする {#designing-an-email-content-from-scratch}

電子メールコンテンツエディションをマスターする方法を説明します。 電子メールデザイナを使用すると、独自の定義済みコンテンツの有無に関係なく、電子メールやテンプレートを作成できます。

## Eメールを作成するための主な手順 {#key-steps-to-create-your-email}

電子メールデザイナを使用して、電子メールコンテンツを最初から作成し、設計する主な手順を次に示します。

1. 電子メールを作成し、その内容を開きます。
1. 電子メールの形状を作成する構造コンポーネントを追加します。 電子メ [ール構造の編集を参照](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 構造コンポーネントにコンテンツコンポーネントとフラグメントを挿入します。 フラグメン [トとコンテンツコンポーネントの追加を参照](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 画像を追加し、電子メールのテキストを編集します。 イメージの挿 [入を参照してくださ](../../designing/using/images.md#inserting-images)い。
1. 個人用設定フィールドやリンクなどを追加して、電子メールを個人用に設定します。 詳細は、「個 [人用設定フィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)」、「リ [ンクの挿入](../../designing/using/links.md#inserting-a-link) 」、「電子メー [ルでの動的コンテンツの定義」を参照してください](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。
1. 電子メールの件名を定義します。 詳しくは、 [電子メールの件名行のパーソナライズを参照してください](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email)。
1. 電子メールをプレビューします。
1. コンテンツを保存し、対象ユーザーが定義され、送信が適切にスケジュールされていることを確認した後で、メッセージを続行します。

この入門ビデオもご覧いただ [けます](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)。

>[!NOTE]
>
>Eメール·コンテンツを最初から設計しないように、標準のコンテンツ·テンプレートを使用できます。 詳細については、「コンテンツテンプレート」を [参照してください](../../designing/using/using-reusable-content.md#content-templates)。

### 電子メール構造の定義 {#defining-the-email-structure}

電子メールデザイナを使用すると、電子メールの構造を簡単に定義できます。 簡単なドラッグアンドドロップ操作で構造要素を追加および移動することで、数秒で電子メールの形状をデザインできます。

電子メールの構造を編集するには、次の手順に従います。

1. 既存のコンテンツを開くか、新しい電子メールコンテンツを作成します。
1. 左側の[+] **[!UICONTROL Structure components]** アイコンを **選択して** 、にアクセスします。

   ![](assets/email_designer_structure.png)

1. 電子メールの形状を作成する必要がある構造コンポーネントをドラッグ&amp;ドロップします。

   ![](assets/email_designer_structure_components.png)

   青い線は、構造コンポーネントをドロップする前の正確な位置を表します。 他のコンポーネントの上、下、間、または内側ではドロップできません。

   >[!NOTE]
   >
   >電子メールに配置した後は、コンテンツコンポーネントまたはフラグメントが既に内部に配置されていない限り、コンポーネントを移動または削除することはできません。

1. 1つまたは複数の柱で構成される複数の構造コンポーネントを使用できます。

   コンポーネン **[!UICONTROL n:n column]** トを選択して、選択する列の数(3 ~ 10)を定義します。 各列の下にある矢印を移動して、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各列のサイズは、構造コンポーネントの全幅の10%未満にすることはできません。 空でない列は削除できません。

構造が定義されると、コンテンツの断片やコンポーネントを電子メールに追加できます。

### コンテンツコンポーネントの使用 {#about-content-components}

コンテンツコンポーネントは、Eメールに配置した後で編集できる未加工の空のコンポーネントです。

構造コンポーネントには、必要な数のコンテンツコンポーネントを追加できます。 また、構造コンポーネント内や別の構造コンポーネントに移動することもできます。

電子メールデザイナで使用可能なコンポーネントのリストを次に示します。

- **[!UICONTROL Button]**

   各ボタンを最初から編集するのではなく、複数のボタンを使用する必要がある場合は、コンテキストツールバーを使用してコンポー **[!UICONTROL Button]** ネントを複製することができます。

   また、ボタンを再利用可能なフラグメントに保存することもできます。 詳細については、「コンテンツフラグメ [ントを作成する](../../designing/using/using-reusable-content.md#creating-a-content-fragment) 」および「フ [ラグメントとしてコンテンツを保存する」を参照してください](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)。

1. 電子メー **[!UICONTROL Fallback view]** ルデザイナにフォールバックイメージを表示する場合に選択します。

- **[!UICONTROL Text]**

   このコンポーネントを使用して、電子メールにテキストを挿入します。 では、テキストの色、スタイル、サイズを調整できます **[!UICONTROL Component Settings]**。

- **[!UICONTROL Divider]**

   このコンポーネントを使用して、電子メールに分割線を挿入します。 では、破断線の色、スタイル、サイズを選択できます **[!UICONTROL Component Settings]**。

- **[!UICONTROL Html]**

   このコンポーネントを使用して、既存のHTMLの異なる部分をコピー&amp;ペーストします。 これにより、無料のモジュラHTMLコンポーネントを作成できます。

   >[!NOTE]
   >
   >無料のHTMLコンポーネントは、制限されたオプションで編集できます。 すべてのスタイルがインライン化されていない場合は、HTMLコードの **head** セクションに適切なCSSを追加してください。追加しない場合は、電子メールが応答しません。 ボタンを使用 **[!UICONTROL Preview]** して、コンテンツの応答性をテストします(「メッセージのプ [レビュー](../../sending/using/previewing-messages.md)」を参照)。

   電子メールデザイナに準拠した外部コンテンツを作成する場合は、メッセージを最初から作成し、既存の電子メールからコンテンツを断片やコンポーネントにコピーすることをお勧めします。

   再作成できないコンテンツがある場合は、コンテンツコンポーネントを使用して、元の電子メールからHTMLコードをコピー&amp;ペースト **[!UICONTROL Html]** できます。 次に進む前に、HTMLに詳しいことを確認してください。

   <!-- A full example is presented below. -->

   >[!NOTE]
   >
   >新しいコンテンツは元のEメールの正確なコピーではありませんが、次の手順に従って、できるだけ近いメッセージを作成します。

   **コンテンツをコピーする前に**

   1. 元の電子メールで、送信する各電子メールに固有のセクションから再利用可能なセクションを特定します。
   1. 使用するイメージとアセットをすべて保存します。
   1. HTMLに詳しい場合は、元のHTMLコンテンツを別の部分に分割します。

- **[!UICONTROL Video]**

   このコンポーネントを使用して、電子メールにビデオを挿入します。

   電子メールの構造コンポーネントにビデオコンポーネントを挿入し、にビデオリンクを入力しま **[!UICONTROL Component Settings]**&#x200B;す。

- **[!UICONTROL Image]**

   このコンポーネントを使用して、電子メールにイメージを挿入します。

   イメージコンポーネントを構造コンポーネントに挿入し、[参照]をクリックして、コンピュータからイメージファイルをアップロードします。

- **[!UICONTROL Social]**

   このコンポーネントを使用して、電子メールにソーシャルメディアページへのリンクを挿入します。 表示するリンクと、のアイコンのサイズを選択できます **[!UICONTROL Component Settings]**。

- **[!UICONTROL Carousel]**

   1. 構造コンポーネント内でコンポー **[!UICONTROL Carousel]** ネントをドラッグ&amp;ドロップします。
   1. コンピュータからイメージを選択します。
   ![](assets/des_carousel_browse.png)

   1. ペインで **[!UICONTROL Settings]** 、カルーセル内で使用するサムネイルの数を設定します。
   1. コンピュータからフォールバックイメージを選択します。
   ![](assets/des_carousel_fallback.png)

   Caruoselコンポーネントは、一部のEメールプログラムと互換性がありません。 電子メールでカルーセルがサポートされていない場合に代わりに、フォールバックをアップロードしてイメージを表示します。

   >[!NOTE]
   >
   >caruoselコンポーネントは、次のEメールプラットフォームと互換性があります。Apple Mail 7、Apple Mail 8、Outlook 2011 for Mac、Outlook 2016 for Mac、Mozilla Thunderbird、iPadとiPad mini iOS、iPhone iOS、Android、AOL (Chrome、Firefox、 Sari)

**関連トピック**:

- [電子メールの作成](../../channels/using/creating-an-email.md)
- [メッセージ内の対象ユーザーの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
- [メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)
- [メッセージのプレビュー](../../sending/using/previewing-messages.md)
- [電子メールレンダリング](../../sending/using/email-rendering.md)
