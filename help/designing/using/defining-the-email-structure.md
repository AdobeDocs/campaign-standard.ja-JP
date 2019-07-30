---
title: 電子メール構造の定義
seo-title: 電子メール構造の定義
description: 電子メール構造の定義
seo-description: Campaignで電子メールデザイナーを使用して電子メールを形成し、コンテンツコンポーネントを入力する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 6ec63f65-1425-4c28-84e8- b09574458db3
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: edit- email- content
discoiquuid: 207fdf6d-165a-41af- ad53- ba97d3403b62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7de6436bbd4f1cc5032e13414f7337f637bf608a

---


# Defining the email structure{#defining-the-email-structure}

## Editing the email structure {#editing-the-email-structure}

電子メールデザイナーを使用すると、電子メールの構造を簡単に定義できます。シンプルなドラッグ&amp;ドロップ操作で構造要素を追加および移動することで、電子メールの形を秒単位でデザインできます。

電子メールの構造を編集するには:

1. 既存のコンテンツを開くか、新しい電子メールコンテンツを作成します。
1. Access the **[!UICONTROL Structure components]** by selecting the **+** icon on the left.

   ![](assets/email_designer_structure.png)

1. 電子メールの形成に必要な構成コンポーネントをドラッグ&amp;ドロップします。

   ![](assets/email_designer_structure_components.png)

   青色の線は、ドロップする前にコンポーネントコンポーネントの正確な位置を物理化します。上ではなく、他のコンポーネントの間または下にドロップできます。

   >[!NOTE]
   >
   >電子メールに配置すると、コンテンツコンポーネントまたはフラグメントがすでに配置されていない限り、コンポーネントを移動または削除できません。

1. 1つ以上の列から構成される複数の構造コンポーネントを使用できます。

   **[!UICONTROL n:n column]** 選択する列数（3~10）を定義するコンポーネントを選択します。各列の下端にある矢印を移動して、各列の幅を定義することもできます。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >各列サイズは、構造コンポーネントの幅の10%未満にすることはできません。空以外の列は削除できません。

構造を定義すると、コンテンツフラグメントやコンポーネントを電子メールに追加できます。

## Adding fragments and content components {#adding-fragments-and-content-components}

電子メールデザイナーを使用して、電子メールに構造コンポーネントを追加すると、そのコンテンツを定義できます。そのためには、各構造コンポーネント内に要素を追加する必要があります。

There are two categories of content elements that you can use: **fragments** and **content components**.

### About fragments {#about-fragments}

フラグメントは、1つまたは複数の電子メールで参照できる再利用可能なコンポーネントです。

電子メールデザイナーのフラグメントを最高の形で使用するには:

* 独自のフラグメントを作成します。See [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) and [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).
* 電子メールで必要な回数だけ使用します。See [Inserting elements into an email](../../designing/using/defining-the-email-structure.md#inserting-elements-into-an-email).
* フラグメントを編集すると、変更が同期されます。そのフラグメントを含むすべての電子メール（準備または送信されていない）に自動的に反映されます。

電子メールに追加すると、フラグメントはデフォルトでロックされます。特定の電子メール用にフラグメントを変更する場合は、使用されている電子メールの中でそのフラグメントをロック解除して、元のフラグメントと同期を解除できます。変更は同期されません。

電子メール内のフラグメントをロック解除するには、そのフラグメントを選択し、コンテキストツールバーからロックアイコンをクリックします。

![](assets/des_unlocking_fragment.png)

このフラグメントは独立したコンポーネントになり、現在のフラグメントにリンクされません。その後、他のコンテンツコンポーネントとして編集できます。See [About content components](../../designing/using/defining-the-email-structure.md#about-content-components).

### About content components {#about-content-components}

コンテンツコンポーネントは生の空のコンポーネントで、一度電子メールに配置すると編集できます。

構造コンポーネントには、コンテンツコンポーネントをいくつでも追加できます。また、構造コンポーネントや別の構造コンポーネントにも移動できます。

Email Designerの利用可能なコンポーネントのリストを次に示します。

* **[!UICONTROL Button]**

   If you need to use multiple buttons, rather than editing each button from scratch, you can duplicate the **[!UICONTROL Button]** component using the contextual toolbar.

   また、ボタンをフラグメントに保存して、再利用することもできます。For more on this, see [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) and [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

* **[!UICONTROL Carousel]**

   For more on this, see [Using the carousel component](../../designing/using/defining-the-email-structure.md#using-the-carousel-component).

* **[!UICONTROL Divider]**
* **[!UICONTROL Html]**

   既存のHTMLの各部をコピーするには、このコンポーネントを使用します。これにより、無料のモジュール化HTMLコンポーネントを作成できます。

   >[!NOTE]
   >
   >無料のHTMLコンポーネントは、限られたオプションで編集できます。If all styles are not inlined, make sure to add the proper CSS in the **head** section of the HTML code, otherwise the email will not be responsive. Use the **[!UICONTROL Preview]** button to test the responsiveness of your content (see [Previewing messages](../../sending/using/previewing-messages.md)).

* **[!UICONTROL Image]**
* **[!UICONTROL Social]**
* **[!UICONTROL Text]**

#### Using the carousel component {#using-the-carousel-component}

1. Drag and drop the **[!UICONTROL Carousel]** component inside a structure component.
1. コンピューターから画像を選択します。

   ![](assets/des_carousel_browse.png)

1. From the **[!UICONTROL Settings]** pane, set the number of thumbnails that you want in the carousel.
1. コンピューターからフォールバック画像を選択します。

   ![](assets/des_carousel_fallback.png)

   カルーセルコンポーネントは、すべての電子メールプログラムと互換性がありません。カルーセルが電子メールでサポートされていない場合は、フォールバックをアップロードして画像を表示します。

   >[!NOTE]
   >
   >カルーセルコンポーネントは、次の電子メールプラットフォームと互換性があります。Apple Mail7、Apple Mail8、Outlook2011for Mac、Mozilla2016for Mac、Mozilla Thandber、iPadおよびiPad mini iOS、iPhone iOS、Android、AOL（Chrome、Firefox）。

1. Select **[!UICONTROL Fallback view]** to display the fallback image in the Email Designer.

### Inserting elements into an email {#inserting-elements-into-an-email}

電子メールのコンテンツを定義するには、事前に配置した構造コンポーネントにコンテンツ要素を追加します。See [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. Access the content elements by selecting the **+** icon on the left. [フラグメントまた](../../designing/using/defining-the-email-structure.md#about-fragments) は [コンテンツコンポーネントを選択](../../designing/using/defining-the-email-structure.md#about-content-components)します。
1. 追加するフラグメントのラベルまたはラベルの一部が既にわかっている場合は、そのラベルを検索できます。

   ![](assets/email_designer_fragmentsearch.png)

1. フラグメントまたはコンテンツコンポーネントをパレットから電子メールの構造コンポーネントにドラッグ&amp;ドロップします。

   ![](assets/email_designer_addfragment.png)

   要素を電子メールに追加すると、構造コンポーネント内または電子メール内の別の構造コンポーネントに移動できます。

   ![](assets/email_designer_movefragment.png)

1. この電子メールのニーズに合わせて要素を編集します。テキスト、リンク、画像などを追加できます。

   >[!NOTE]
   >
   >フラグメントは、電子メールに追加するときにデフォルトでロックされます。特定の電子メール用にフラグメントを変更したり、フラグメント内で変更を直接行ったりする場合は、元のフラグメントと同期を解除できます。See [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

1. 電子メールに追加する必要のあるすべての要素について、この手順を繰り返します。
1. 電子メールを保存します。

電子メール構造が設定されると、各コンテンツ要素のスタイルを編集できます。See [Editing an element](../../designing/using/editing-email-styles.md#editing-an-element).

>[!NOTE]
>
>フラグメントが変更されると、そのフラグメントが使用されている電子メールに変更が自動的に反映されます。For more on this, see [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

### Creating a content fragment {#creating-a-content-fragment}

独自のコンテンツフラグメントを作成して、必要に応じて1つ以上の電子メールで使用することができます。

1. **[!UICONTROL Resources]** に **[!UICONTROL Content templates & fragments]** 移動して、をクリック **[!UICONTROL Create]**&#x200B;します。
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer.
1. 認識できるラベルを指定し、次のパラメーターを選択して、後で新しい電子メールでフラグメントを探します。

   * Because fragments are only compatible with emails, select **[!UICONTROL Delivery]** from the **[!UICONTROL Content type]** drop-down list.
   * **[!UICONTROL Fragment]****[!UICONTROL HTML type]** このコンテンツを電子メールでフラグメントとして使用できるようにするには、ドロップダウンリストから選択します。
   ![](assets/email_designer_createfragment.png)

1. 必要に応じて、フラグメントのサムネールとして使用する画像を設定できます。Select it from the **[!UICONTROL Thumbnail]** tab of the template properties.

   ![](assets/email_designer_createfragment_thumbnail.png)

   このサムネールは、電子メールの編集時にフラグメントのラベルの横に表示されます。

1. 変更内容を保存してメインワークスペースに戻ります。
1. 必要に応じてカスタマイズできる構造コンポーネントとコンテンツコンポーネントを追加します。
1. 編集後、フラグメントを保存します。

このフラグメントは、電子メールデザイナーで作成された電子メールで使用できるようになりました。It appears under the **[!UICONTROL Fragments]** section of the Palette.

>[!NOTE]
>
>電子メールで使用しない限り、フラグメント内にパーソナライゼーションフィールドを挿入することはできません。これを行うには、このフラグメントのロックを解除する必要があります。See [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

### Saving content as a fragment {#saving-content-as-a-fragment}

電子メールを電子メールで編集する際に、その電子メールの一部をフラグメントとして直接保存できます。

>[!CAUTION]
>
>フラグメント化フィールド、動的コンテンツ、または他のフラグメントを含む構造をフラグメントとして保存することはできません。

1. When editing an email in the Email Designer, select **[!UICONTROL Save as fragment]** from the main toolbar.

   ![](assets/email_designer_save-as-fragment.png)

1. ワークスペースから、フラグメントを構成する構造を選択します。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >隣接する構造のみを選択できます。

1. **[!UICONTROL Create]**&#x200B;をクリックします。

1. Add a label and a description if needed, then click **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-fragment_popup.png)

1. To find the fragment that you just created, go to **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

   ![](assets/email_designer_save-as-fragment_list.png)

1. 新しいフラグメントを使用するには、任意の電子メールコンテンツを開き、フラグメントリストから選択します。

![](assets/email_designer_save-as-fragment_in-new-email.png)

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

