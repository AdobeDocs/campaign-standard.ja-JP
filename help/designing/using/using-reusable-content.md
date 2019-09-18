---
title: '再利用可能なコンテンツの作成と使用 '
seo-title: 再利用可能なコンテンツの作成と使用
description: 再利用可能なコンテンツの作成と使用
seo-description: 電子メールデザイナを使用して、再利用可能な電子メールコンテンツの構築を開始します。
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

# 再利用可能なコンテンツの作成と使用 {#using-reusable-content}

電子メールコンテンツエディションをマスターする方法を説明します。 電子メールデザイナを使用すると、独自の定義済みコンテンツを含むテンプレートとフラグメントを作成し、後続の配信に再利用できます。

## テンプレートを使用して設計する {#designing-templates}

>[!NOTE]
>
> Adobe Campain Standardでは、 **Resources** &gt; **Templates** （リソース/テンプレート）メニューからアクセス可能なさまざまなタイプのテンプレートを作成できます。 電子メールデザイナで使用されるテンプレートは、コンテンツテンプレートです。 詳細については、「テンプレートにつ [いて](../../start/using/about-templates.md)」を参照。

### コンテンツテンプレート {#content-templates}

電子メールデザイナのホームページのタブで提供されるHTML **[!UICONTROL Templates]** コンテンツを管 [理できます](../../designing/using/overview.md) 。 異なるテンプレートは、複数のタイプの要素のさまざまな組み合わせを表します。 たとえば、「フェザー」テンプレートには余白があり、「アストロ」テンプレートには余白がありません。 詳細については、「コンテンツテンプレート」を [参照してください](../../designing/using/using-reusable-content.md#content-templates)。

![](assets/template_content.png)

標準のテンプレートから電子メールを作成する方法については、「電子メールデザイナ」を参照し [てください](../../designing/using/quick-start.md#building-content-from-an-out-of-the-box-template)。

### コンテンツテンプレートを作成する {#creating-a-content-template}

独自のコンテンツテンプレートを作成して、必要な回数だけ使用できます。

次の例は、電子メールコンテンツテンプレートを作成する方法を示しています。

1. &gt;に移動し、をク **[!UICONTROL Resources]** リッ **[!UICONTROL Content templates & fragments]** クしま **[!UICONTROL Create]**&#x200B;す。
1. 電子メール·ラベルをクリックして、電子メ **[!UICONTROL Properties]** ール·デザイナのタブにアクセスします。
1. 認識可能なラベルを指定し、次のパラメータを選択して、このテンプレートを電子メールで使用できます。

   * ドロップダウ **[!UICONTROL Shared]** ンリ **[!UICONTROL Delivery]** ストから、ま **[!UICONTROL Content type]** たはを選択します。
   * ドロップダウ **[!UICONTROL Template]** ンリストか **[!UICONTROL HTML type]** らを選択します。
   ![](assets/email_designer_create-template.png)

1. 必要に応じて、テンプレートのサムネイルとして使用するイメージを設定できます。 テンプレートのプロパティ **[!UICONTROL Thumbnail]** のタブから選択します。

   ![](assets/email_designer_create-template_thumbnail.png)

   このサムネイルは、電子メールデザイナのホ **[!UICONTROL Templates]** ームページのタ [ブに表示さ](../../designing/using/overview.md#about-the-email-designer) れます。

1. タブを閉じ **[!UICONTROL Properties]** て、メインワークスペースに戻ります。
1. 必要に応じてカスタマイズできる構造コンポーネントとコンテンツコンポーネントを追加します。
   >[!NOTE]
   >
   > 個人用設定フィールドや条件付きコンテンツをコンテンツテンプレート内に挿入することはできません。
1. 編集したら、テンプレートを保存します。

このテンプレートは、電子メールデザイナで作成された任意の電子メールで使用できます。 電子メールデザイナのホ **[!UICONTROL Templates]** ームページのタ [ブから](../../designing/using/overview.md#about-the-email-designer) 、選択します。

![](assets/content_template_new.png)

### テンプレートとしてのコンテンツの保存 {#saving-content-as-template}

電子メールデザイナで電子メールを編集する場合は、その電子メールの内容をテンプレートとして直接保存できます。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. 電子メー **[!UICONTROL Save as template]** ルデザイナのメインツールバーからを選択します。

   ![](assets/email_designer_save-as-template.png)

1. 必要に応じてラベルと説明を追加し、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   ![](assets/email_designer_save-as-template_creation.png)

1. 作成したテンプレートを検索するには、 **[!UICONTROL Resources]** &gt;に進みま **[!UICONTROL Content templates & fragments]**&#x200B;す。

1. 新しいテンプレートを使用するには、電子メールデザイナのホ **[!UICONTROL Templates]** ームページのタ [ブから](../../designing/using/overview.md#about-the-email-designer) 、テンプレートを選択します。

   ![](assets/content_template_new.png)

### フラグメントとコンポーネントを含むテンプレートの作成 {#template-fragments-components}

これで、電子メールデザイナを使用して電子メールテンプレートを作成できます。 コンテンツコンポーネントを使用して、電子メールの各セクションを反映し、設定を調整して、元のニュースレターにできる限り近づけます。 最後に、作成したフラグメントを挿入します。

1. 電子メールデザイナを使用して、テンプレートを作成します。 詳細については、「コンテンツテンプレート」を [参照してください](../../designing/using/using-reusable-content.md#content-templates)。
1. 電子メールのヘッダー、フッター、本文に対応する構造コンポーネントをテンプレートに挿入します。 構造コンポーネントの追加の詳細は、電子メールデザ [イナを使用した電子メール構造の編集を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. ニュースレターの本文を作成するために必要な数のコンテンツコンポーネントを挿入します。 これは、毎月更新する電子メールの編集可能なコンテンツです。

   ![](assets/des_loading_compatible_fragment_5.png)

   HTMLコードに慣れている場合は、元の電子メールのより複雑な要素をコ **[!UICONTROL Html]** ピー&amp;ペーストできるコンポーネントを活用することをお勧めします。 他のコンポーネント（、など） **[!UICONTROL Button]**&#x200B;を使 **[!UICONTROL Image]** 用して、 **[!UICONTROL Text]** 残りのコンテンツを作成します。 詳細については、「コンテンツコンポーネントにつ [いて」を参照してくださ](../../designing/using/designing-from-scratch.md#about-content-components)い。

   >[!NOTE]
   >
   >コンポーネントを使 **[!UICONTROL Html]** 用すると、制限されたオプションで編集可能なコンポーネントが作成されます。 このコンポーネントを選択する前に、HTMLコードの処理方法を確認してください。

1. コンテンツコンポーネントを、元のEメールにできる限り合わせて調整します。

   ![](assets/des_loading_compatible_fragment_6.png)

   スタイル設定とインライン属性の管理の詳細については、「電子メールスタイルを編 [集する」を参照してくださ](../../designing/using/styles.md)い。

1. 前に作成した2つのフラグメント（ヘッダーとフッター）を目的の構造コンポーネントに挿入します。

   ![](assets/des_loading_compatible_fragment_10.png)

1. テンプレートを保存します。

電子メールデザイナでこのテンプレートを完全に管理し、毎月受信者に送信するニュースレターを作成および更新できるようになりました。

これを使用するには、電子メールを作成し、作成したコンテンツテンプレートを選択します。

**関連トピック**:

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [電子メールデザイナの概要ビデオ](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=jpn)
* [Eメール·コンテンツをゼロから設計する](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## フラグメントについて {#about-fragments}

フラグメントは、1つ以上の電子メールで参照できる再利用可能なコンポーネントです。
これらは、「 **Resources** 」&gt;「 **Content fragments and templates」の下のインタフェースにあります**。

電子メールデザイナでフラグメントを最大限に活用するには、次の手順に従います。

* 独自のフラグメントを作成します。 詳細は、「 [コンテンツ·フラグメントの作成](../../designing/using/using-reusable-content.md#creating-a-content-fragment) 」および「フ [ラグメントとしてのコンテンツの保存」を参照してくださ](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)い。
* 必要な回数だけメールで使用します。 「電子メ [ールへの要素の挿入」を参照してください](../../designing/using/using-reusable-content.md#inserting-elements-into-an-email)。
* フラグメントを編集すると、変更は同期されます。そのフラグメントを含むすべての電子メールに自動的に伝達されます（準備が完了していないか、まだ送信されていない場合）。

電子メールに追加されると、フラグメントは既定でロックされます。 特定の電子メールのフラグメントを変更する場合は、使用先の電子メールのロックを解除して、元のフラグメントとの同期を解除できます。 変更は同期されなくなります。

電子メール内のフラグメントのロックを解除するには、そのフラグメントを選択し、コンテキストツールバーのロックアイコンをクリックします。

![](assets/des_unlocking_fragment.png)

そのフラグメントは、元のフラグメントにリンクされなくなったスタンドアロンコンポーネントになります。 その後、他のコンテンツコンポーネントとして編集できます。 「コンテンツコ [ンポーネントについて](../../designing/using/designing-from-scratch.md#about-content-components)」を参照。

### 電子メールへのフラグメントの挿入 {#inserting-elements-into-an-email}

電子メールの内容を定義するには、あらかじめ配置した構造コンポーネントにコンテンツ要素を追加します。 電子メ [ール構造の編集を参照](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 左側の+アイコンを選択して、コンテ **ンツ要素** にアクセスします。 「フラグメン [ト」または](../../designing/using/using-reusable-content.md#about-fragments) 「コンテ [ンツ」コンポーネントを選択します](../../designing/using/designing-from-scratch.md#about-content-components)。
1. 追加するフラグメントのラベルまたはラベルの一部が既にわかっている場合は、そのラベルを検索できます。

   ![](assets/email_designer_fragmentsearch.png)

1. フラグメントまたはコンテンツコンポーネントをパレットから電子メールの構造コンポーネントにドラッグ&amp;ドロップします。

   ![](assets/email_designer_addfragment.png)

   電子メールに要素を追加すると、電子メール内の構造コンポーネント内または別の構造コンポーネントに要素を移動できます。

   ![](assets/email_designer_movefragment.png)

1. この電子メールの正確なニーズに合わせて要素を編集します。 テキスト、リンク、イメージなどを追加できます。

   >[!NOTE]
   >
   >フラグメントは、電子メールに追加されると、既定でロックされます。 特定の電子メールのフラグメントを変更する場合、またはフラグメント内で直接変更する場合は、元のフラグメントとの同期を解除できます。 フラグメン [トについて](../../designing/using/using-reusable-content.md#about-fragments)。

1. 電子メールに追加する必要のあるすべての要素に対して、この手順を繰り返します。
1. メールを保存します。

電子メール構造が作成されたので、各コンテンツ要素のスタイルを編集できます。 要素の編 [集を参照してください](../../designing/using/styles.md#editing-an-element)。

>[!NOTE]
>
>フラグメントが変更されると、そのフラグメントが使用されている電子メールに変更が自動的に反映されます。 詳細については、「フラグメントについて」を参 [照してくださ](../../designing/using/using-reusable-content.md#about-fragments)い。

### コンテンツフラグメントの作成 {#creating-a-content-fragment}

1つ以上の電子メールで必要に応じて、独自のコンテンツフラグメントを作成して使用できます。

1. &gt;に移動し、をク **[!UICONTROL Resources]** リッ **[!UICONTROL Content templates & fragments]** クしま **[!UICONTROL Create]**&#x200B;す。
1. 電子メール·ラベルをクリックして、電子メ **[!UICONTROL Properties]** ール·デザイナのタブにアクセスします。
1. 電子メールコンテンツの編集時にフラグメントを検索するには、認識可能なラベルを指定し、次のパラメータを選択します。

   * フラグメントは電子メールとのみ互換性があるため、ドロッ **[!UICONTROL Delivery]** プダウンリスト **[!UICONTROL Content type]** から選択します。
   * このコ **[!UICONTROL Fragment]** ンテンツをフ **[!UICONTROL HTML type]** ラグメントとして使用できるようにするには、ドロップダウンリストから選択します。
   ![](assets/email_designer_createfragment.png)

1. 必要に応じて、フラグメントのサムネイルとして使用するイメージを設定できます。 テンプレートのプロパティ **[!UICONTROL Thumbnail]** のタブから選択します。

   ![](assets/email_designer_createfragment_thumbnail.png)

   このサムネイルは、電子メールの編集時にフラグメントのラベルの横に表示されます。

1. タブを閉じ **[!UICONTROL Properties]** て、メインワークスペースに戻ります。
1. 必要に応じてカスタマイズできる構造コンポーネントとコンテンツコンポーネントを追加します。

   >[!NOTE]
   >
   >フラグメントには、個人用設定フィールド、動的コンテンツ、または別のフラグメントを含めることはできません。
   >モバイル [ビューは](../../designing/using/styles.md#switching-to-mobile-view) 、フラグメントでは使用できません。

1. 編集したら、フラグメントを保存します。

このフラグメントは、電子メールデザイナーで作成された任意の電子メールで使用できます。 パレットのセクション **[!UICONTROL Fragments]** の下に表示されます。

>[!NOTE]
>
>個人用設定フィールドは、電子メールで使用され、ロックが解除されていない限り、フラグメント内に挿入できません。 フラグメン [トについて](../../designing/using/using-reusable-content.md#about-fragments)。

### コンテンツをフラグメントとして保存する {#saving-content-as-a-fragment}

電子メールデザイナで電子メールを編集する場合は、その電子メールの一部を断片として直接保存できます。

* 個人用設定フィールド、動的コンテンツ、または別のフラグメントを含む構造体をフラグメントとして保存することはできません。
* 互いに隣接する構造物のみを選択できます。
<!-- - You cannot select an empty structure.-->

1. 電子メールデザイナで電子メールを編集する場合は、メインツー **[!UICONTROL Save as fragment]** ルバーからを選択します。

   ![](assets/email_designer_save-as-fragment.png)

1. ワークスペースから、フラグメントを構成する構造を選択します。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >互いに隣接し、個人用設定フィールド、動的コンテンツ、または別のフラグメントを含まない構造を選択してください。
   <!--You cannot select an empty structure.-->

1. Click **[!UICONTROL Create]**.

1. 必要に応じてラベルと説明を追加し、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   ![](assets/email_designer_save-as-fragment_popup.png)

1. 作成したフラグメントを検索するには、 **[!UICONTROL Resources]** &gt;に進みます **[!UICONTROL Content templates & fragments]**。

   ![](assets/email_designer_save-as-fragment_list.png)

1. 新しいフラグメントを使用するには、任意の電子メールコンテンツを開き、フラグメントリストから選択します。

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>モバイル [ビューは](../../designing/using/styles.md#switching-to-mobile-view) 、フラグメントでは使用できません。 電子メールモバイルビューを編集する場合は、コンテンツをフラグメントとして保存する前に編集します。

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

## フラグメントを使用した再利用可能なヘッダーとフッターの作成 {#header-footer-fragments}

電子メールデザイナを使用して、再利用可能な各セクションのフラグメントを作成します。 この例では、次の2つのフラグメントを作成します。1つはヘッダー用、もう1つはフッター用です。 次に、既存のコンテンツから関連するパーツをこれらのフラグメントにコピーします。

これを行うには、次の手順に従います。

1. Adobe Campaignで、 &gt;に進み、ヘッ **[!UICONTROL Resources]** ダーのフ **[!UICONTROL Content templates & fragments]** ラグメントを作成します。 詳細については、「コンテンツフラグメ [ントを作成する」を参照してくださ](../../designing/using/using-reusable-content.md#creating-a-content-fragment)い。
1. 必要な数の構造コンポーネントをフラグメントに追加します。

![](assets/des_loading_compatible_fragment_1.png)

1. 構造にイメージとテキストのコンポーネントを挿入します。

![](assets/des_loading_compatible_fragment_2.png)

1. 対応するイメージをアップロードし、テキストを入力して設定を調整します。

![](assets/des_loading_compatible_fragment_3.png)

1. フラグメントを保存します。
1. 同様にフッターを作成し、保存します。

![](assets/des_loading_compatible_fragment_4.png)

これで、フラグメントをテンプレートで使用する準備が整いました。
