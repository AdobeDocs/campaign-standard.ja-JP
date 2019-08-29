---
title: 電子メール構造の定義
seo-title: 電子メール構造の定義
description: 電子メール構造の定義
seo-description: Campaignで電子メールデザイナを使用して電子メールを整形し、コンテンツコンポーネントを設定する方法を見つけます。
page-status-flag: 決して活性化されていない
uuid: 6ec63f65-1425-4c28-84e8- b09574458db3
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: デザイン
content-type: 参照
topic-tags: 編集電子メールコンテンツ
discoiquuid: 207fdf6d-165a-41af- ad53- ba97d3403b62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2ac7fa8be4c408d75d77d3035af4cec25ac001c2

---


# 電子メール構造の定義{#defining-the-email-structure}

## 電子メール構造の編集 {#editing-the-email-structure}

電子メールデザイナを使用すると、電子メールの構造を簡単に定義できます。単純なドラッグアンドドロップアクションで構造要素を追加および移動することにより、電子メールの形状を秒単位でデザインできます。

電子メールの構造を編集するには:

1. 既存のコンテンツを開くか、新しい電子メールコンテンツを作成します。
1. 左側 **[!UICONTROL Structure components]** の+ **** アイコンを選択して、にアクセスします。

   ![](assets/email_designer_structure.png)

1. 電子メールの整形に必要な構造コンポーネントをドラッグアンドドロップします。

   ![](assets/email_designer_structure_components.png)

   青い線は、構造コンポーネントの正確な位置を削除してから削除します。上にドロップすることも、他のコンポーネントの下または下に置くこともできますが、内部にはドロップできません。

   >[!NOTE]
   >
   >電子メールに配置すると、コンテンツコンポーネントまたはフラグメントが内部に配置されていない限り、コンポーネントを移動または削除できません。

1. 1つまたは複数の列で構成される複数の構造コンポーネントを使用できます。

   選択した列の数（3~10）を定義する **[!UICONTROL n:n column]** コンポーネントを選択します。各列の下部にある矢印を移動することによって、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各柱のサイズは、構造コンポーネントの合計幅の10%未満にすることはできません。空でない列は削除できません。

構造を定義すると、コンテンツフラグメントとコンポーネントを電子メールに追加できます。

## フラグメントとコンテンツコンポーネントの追加 {#adding-fragments-and-content-components}

電子メールデザイナでは、構造コンポーネントを電子メールに追加した後で、そのコンテンツを定義できます。そのためには、各構造コンポーネント内に要素を追加する必要があります。

使用できるコンテンツ要素には2つのカテゴリがあります。 **フラグメント** と **コンテンツコンポーネント**。

### フラグメントについて {#about-fragments}

フラグメントは、1つ以上の電子メールで参照できる再利用可能なコンポーネントです。

電子メールデザイナでフラグメントを最適に使用するには、次の手順に従います。

* 自分のフラグメントを作成します。コンテンツ [フラグメントの作成](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) とフラグメントとしてのコンテンツ [の保存を参照](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)してください。
* メールで必要な回数だけ使用します。「電子メールへの要素 [の挿入」を](../../designing/using/defining-the-email-structure.md#inserting-elements-into-an-email)参照してください。
* フラグメントを編集すると、変更は同期されます。これらは、そのフラグメントを含むすべての電子メール（準備または送信されていない）に自動的に伝播されます。

電子メールに追加すると、フラグメントは既定でロックされます。特定の電子メールのフラグメントを変更する場合は、そのフラグメントを使用する電子メールでロック解除することによって、元のフラグメントとの同期を解除できます。変更はもう同期されません。

電子メール内のフラグメントをロック解除するには、そのフラグメントを選択し、コンテキストツールバーからロックアイコンをクリックします。

![](assets/des_unlocking_fragment.png)

このフラグメントは、元のフラグメントにリンクされていないスタンドアロンコンポーネントになります。その後、その他のコンテンツコンポーネントとして編集できます。コンテンツコンポーネント [についてを参照](../../designing/using/defining-the-email-structure.md#about-content-components)してください。

### コンテンツコンポーネントについて {#about-content-components}

コンテンツコンポーネントは、電子メールに配置した後に編集できる未処理の空のコンポーネントです。

構造コンポーネントには、必要な数のコンテンツコンポーネントを追加できます。構造コンポーネントまたは別の構造コンポーネントの内部に移動することもできます。

電子メールデザイナで使用可能なコンポーネントの一覧を次に示します。

* **[!UICONTROL Button]**

   各ボタンを最初から編集するのではなく、複数のボタンを使用する必要がある場合は、コンテキストツールバーを使用して **[!UICONTROL Button]** コンポーネントを複製できます。

   また、再利用可能なフラグメントにボタンを保存することもできます。詳細については、「 [コンテンツフラグメントの作成](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) とフラグメントとしてのコンテンツ [の保存」を](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)参照してください。

* **[!UICONTROL Carousel]**

   詳細については、「カルーセルコンポーネント [を使用する」を](../../designing/using/defining-the-email-structure.md#using-the-carousel-component)参照してください。

* **[!UICONTROL Divider]**
* **[!UICONTROL Html]**

   このコンポーネントを使用して、既存のHTMLの異なる部分をコピーします。これにより、フリーモジュールHTMLコンポーネントを作成できます。

   >[!NOTE]
   >
   >自由なHTMLコンポーネントは、制限付きのオプションで編集できます。すべてのスタイルがインラインでない場合は、HTMLコードのhead **** セクションに適切なCSSを追加してください。それ以外の場合は、電子メールは応答しません。ボタン **[!UICONTROL Preview]** を使用して、コンテンツの応答性をテストします（メッセージ [](../../sending/using/previewing-messages.md)のプレビューを参照）。

* **[!UICONTROL Image]**
* **[!UICONTROL Social]**
* **[!UICONTROL Text]**

#### カルセルコンポーネントの使用 {#using-the-carousel-component}

1. コンポーネントコンポーネント内に **[!UICONTROL Carousel]** コンポーネントをドラッグアンドドロップします。
1. コンピュータからイメージを選択します。

   ![](assets/des_carousel_browse.png)

1. ペイン **[!UICONTROL Settings]** から、カルセルに必要なサムネイルの数を設定します。
1. コンピュータからフォールバックイメージを選択します。

   ![](assets/des_carousel_fallback.png)

   カルーセルコンポーネントはすべての電子メールプログラムと互換性がありません。電子メールでカルーセルがサポートされていない場合は、フォールバックをアップロードしてイメージを表示します。

   >[!NOTE]
   >
   >カルーセルコンポーネントは、次の電子メールプラットフォームと互換性があります。Apple Mail7、Apple Mail8、Outlook2011for Mac、Outlook2016for Mac、Mozilla Thunderbird、iPadおよびiPad Mini iOS、iPhone iOS、Android、AOL（Chrome、Firefox、Safari）。

1. オン **[!UICONTROL Fallback view]** にすると、電子メールデザイナにフォールバックイメージが表示されます。

### 電子メールへの要素の挿入 {#inserting-elements-into-an-email}

電子メールのコンテンツを定義するには、あらかじめ配置した構造コンポーネントにコンテンツ要素を追加します。電子 [メール構造の編集を参照](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)してください。

1. 左側の+ **** アイコンを選択して、コンテンツ要素にアクセスします。[フラグメントまた](../../designing/using/defining-the-email-structure.md#about-fragments) は [コンテンツコンポーネント](../../designing/using/defining-the-email-structure.md#about-content-components)を選択します。
1. 追加するフラグメントのラベルまたはラベルの一部が既にわかっている場合は、そのラベルを検索できます。

   ![](assets/email_designer_fragmentsearch.png)

1. パレットから電子メールの構造コンポーネントにフラグメントまたはコンテンツコンポーネントをドラッグアンドドロップします。

   ![](assets/email_designer_addfragment.png)

   電子メールに要素を追加すると、構造コンポーネント内または電子メールの別の構造コンポーネントに移動できます。

   ![](assets/email_designer_movefragment.png)

1. この電子メールの正確なニーズに合わせて要素を編集します。テキスト、リンク、イメージなどを追加できます。

   >[!NOTE]
   >
   >フラグメントは、電子メールに追加するときに既定でロックされます。特定の電子メールのフラグメントを変更する場合や、フラグメント内で変更を直接行う場合は、元のフラグメントとの同期を解除できます。「フラグメント [について」を参照](../../designing/using/defining-the-email-structure.md#about-fragments)してください。

1. 電子メールに追加する必要があるすべての要素について、この手順を繰り返します。
1. 電子メールを保存します。

電子メールの構造が設定されたので、各コンテンツ要素のスタイルを編集できます。要素 [の編集を参照](../../designing/using/editing-email-styles.md#editing-an-element)してください。

>[!NOTE]
>
>フラグメントが変更されると、変更は使用されている電子メールに自動的に反映されます。詳細については、「フラグメントについて」を参照 [](../../designing/using/defining-the-email-structure.md#about-fragments)してください。

### コンテンツフラグメントの作成 {#creating-a-content-fragment}

自分自身のコンテンツフラグメントを作成して、必要に応じて1つ以上の電子メールで使用できます。

1. **[!UICONTROL Resources]** &gt;に **[!UICONTROL Content templates & fragments]** 移動し、をクリック **[!UICONTROL Create]**&#x200B;します。
1. 電子メール・ラベルをクリックして、電子メール・デザイナの **[!UICONTROL Properties]** タブにアクセスします。
1. 電子メールの内容を編集するときにフラグメントを検索するには、認識可能なラベルを指定し、次のパラメータを選択します。

   * フラグメントは電子メールとのみ互換性があるため、ドロップダウンリスト **[!UICONTROL Delivery]****[!UICONTROL Content type]** から選択します。
   * この **[!UICONTROL Fragment]** コンテンツをフラグメントとして使用できる **[!UICONTROL HTML type]** ようにするには、ドロップダウンリストから選択します。
   ![](assets/email_designer_createfragment.png)

1. 必要に応じて、フラグメントのサムネイルとして使用するイメージを設定できます。テンプレートプロパティの **[!UICONTROL Thumbnail]** タブから選択します。

   ![](assets/email_designer_createfragment_thumbnail.png)

   このサムネイルは、電子メールの編集時にフラグメントのラベルの横に表示されます。

1. **[!UICONTROL Properties]** タブを閉じて、メインワークスペースに戻ります。
1. 必要に応じてカスタマイズできる構造コンポーネントおよびコンテンツコンポーネントを追加します。

   >[!NOTE]
   >
   >フラグメントには、パーソナル化フィールド、動的コンテンツ、または別のフラグメントを含めることはできません。
   >モバイル [ビュー](../../designing/using/about-email-content-design.md#switching-to-mobile-view) はフラグメントでは使用できません。

1. 編集したら、フラグメントを保存します。

このフラグメントは、電子メールデザイナで構築された電子メールで使用できるようになりました。パレットの **[!UICONTROL Fragments]** セクションの下に表示されます。

>[!NOTE]
>
>電子メールで使用したりロック解除したりしない限り、フラグメント化フィールドをフラグメント内に挿入することはできません。「フラグメント [について」を参照](../../designing/using/defining-the-email-structure.md#about-fragments)してください。

### フラグメントとしてのコンテンツの保存 {#saving-content-as-a-fragment}

電子メールデザイナで電子メールを編集する場合は、その電子メールの一部をフラグメントとして直接保存できます。

* パーソナル化フィールド、動的コンテンツ、または別のフラグメントを含む構造体をフラグメント化することはできません。
* 隣接する構造のみを選択できます。
<!--* You cannot select an empty structure.-->

1. 電子メールデザイナで電子メールを編集する場合は、メインツールバー **[!UICONTROL Save as fragment]** からを選択します。

   ![](assets/email_designer_save-as-fragment.png)

1. ワークスペースから、フラグメントを構成する構造を選択します。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >相互に隣接する構造を選択し、パーソナル化フィールド、動的コンテンツ、または別のフラグメントを含まない構造を選択してください。
   <!--You cannot select an empty structure.-->

1. **[!UICONTROL Create]**&#x200B;をクリックします。

1. 必要に応じてラベルと説明を追加し、をクリック **[!UICONTROL Save]**&#x200B;します。

   ![](assets/email_designer_save-as-fragment_popup.png)

1. 作成したフラグメントを見つけるには **[!UICONTROL Resources]** 、&gt; **[!UICONTROL Content templates & fragments]**&#x200B;に進みます。

   ![](assets/email_designer_save-as-fragment_list.png)

1. 新しいフラグメントを使用するには、任意の電子メールコンテンツを開き、フラグメントリストから選択します。

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>モバイル [ビュー](../../designing/using/about-email-content-design.md#switching-to-mobile-view) はフラグメントでは使用できません。電子メールモバイルビューを編集する場合は、コンテンツをフラグメントとして保存する前に、このビューを実行します。

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

