---
title: 再利用可能なコンテンツの作成と使用
description: メールDesignerを使用して、再利用可能なメールコンテンツの作成を開始します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 64c3d3dd-0c41-4dbc-abcd-9ddea23759f4
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1812'
ht-degree: 2%

---

# 再利用可能なコンテンツの作成と使用 {#using-reusable-content}

メールコンテンツ編集をマスターする方法を説明します。 メールDesignerを使用すると、事前に定義された独自のコンテンツでテンプレートやフラグメントを作成し、それらを後続の配信に再利用できます。

## テンプレートを使用した E メールのデザイン {#designing-templates}

>[!NOTE]
>
> Adobe Campaign Standardでは、**リソース**/**テンプレート** メニューからアクセスできる様々なタイプのテンプレートを作成できます。 メールDesignerで使用されるテンプレートは、コンテンツテンプレートです。 詳しくは、[ テンプレートについて ](../../start/using/marketing-activity-templates.md) を参照してください。

![](assets/do-not-localize/how-to-video.png) [ ビデオでテンプレートを作成する方法を確認する ](#video)

### コンテンツテンプレートについて {#content-templates}

[ メールHTML](../../designing/using/designing-content-in-adobe-campaign.md) ホームページの「**[!UICONTROL Templates]**」タブで提供されるDesignerコンテンツを管理できます。

標準のメールコンテンツテンプレートには、Behanceのアーティストによってデザインされた、モバイル向けに最適化された 18 のレイアウトと、クラス最高の 4 つのレスポンシブテンプレートが含まれています。 これらは、顧客歓迎メッセージ、ニュースレター、リエンゲージメントメールなど、最新の用途に対応しています。 ブランドのコンテンツに合わせて簡単にカスタマイズでき、メールをゼロから簡単に設計できます。

![](assets/template_content.png)

HTMLコンテンツテンプレートには、[ 詳細メニュー ](../../start/using/interface-description.md#advanced-menu) の **[!UICONTROL Resources]**/**[!UICONTROL Content templates & fragments]** 画面からアクセスできます。 ここから、ランディングページのコンテンツテンプレート、メールコンテンツテンプレートおよびフラグメントを管理できます。

![](assets/content_templates_list.png)

標準提供のコンテンツテンプレートは読み取り専用です。 このうちのいずれかを編集するには、まず目的のテンプレートを複製する必要があります。

新しいテンプレートやフラグメントを作成し、独自のコンテンツを定義できます。 詳しくは、[ コンテンツテンプレートの作成 ](#creating-a-content-template) および [ コンテンツフラグメントの作成 ](#creating-a-content-fragment) を参照してください。

メールDesignerでコンテンツを編集する際に、コンテンツをフラグメントまたはテンプレートとして保存して、コンテンツテンプレートを作成することもできます。 詳しくは、[ コンテンツをテンプレートとして保存 ](#saving-content-as-template) および [ コンテンツをフラグメントとして保存 ](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment) を参照してください。

**関連トピック：**

* コンテンツの編集について詳しくは、「[ メールコンテンツデザインについて ](../../designing/using/designing-content-in-adobe-campaign.md) を参照してください。

### コンテンツテンプレートの作成 {#creating-a-content-template}

独自のコンテンツテンプレートを作成して、必要な回数だけ使用できます。

次の例は、メールコンテンツテンプレートを作成する方法を示しています。

1. **[!UICONTROL Resources]**/**[!UICONTROL Content templates & fragments]** に移動し、「**[!UICONTROL Create]**」をクリックします。
1. メールのラベルをクリックして、メールDesignerの「**[!UICONTROL Properties]**」タブにアクセスします。
1. 認識可能なラベルを指定し、次のパラメーターを選択して、メールでこのテンプレートを使用できるようにします。

   * 「**[!UICONTROL Content type]**」ドロップダウンリストから「**[!UICONTROL Shared]**」または「**[!UICONTROL Delivery]**」を選択します。
   * 「**[!UICONTROL HTML type]**」ドロップダウンリストから「**[!UICONTROL Template]**」を選択します。

   ![](assets/email_designer_create-template.png)

1. 必要に応じて、テンプレートのサムネイルとして使用する画像を設定できます。 テンプレートのプロパティの「**[!UICONTROL Thumbnail]**」タブから選択します。

   ![](assets/email_designer_create-template_thumbnail.png)

   このサムネールは、[ メールDesigner](../../designing/using/designing-content-in-adobe-campaign.md) ホームページの「**[!UICONTROL Templates]**」タブに表示されます。

1. 「**[!UICONTROL Properties]**」タブを閉じて、メインワークスペースに戻ります。
1. 必要に応じてカスタマイズできる構造コンポーネントとコンテンツコンポーネントを追加します。
   >[!NOTE]
   >
   > コンテンツテンプレート内に、パーソナライゼーションフィールドや条件付きコンテンツを挿入することはできません。
1. 編集が完了したら、テンプレートを保存します。

このテンプレートは、メールDesignerで作成されたすべてのメールで使用できるようになりました。 [ メールDesigner](../../designing/using/designing-content-in-adobe-campaign.md) ホームページの「**[!UICONTROL Templates]**」タブから選択します。

![](assets/content_template_new.png)

### コンテンツをテンプレートとして保存 {#saving-content-as-template}

メールDesignerでメールを編集する際に、そのメールのコンテンツをテンプレートとして直接保存できます。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. メールDesignerのメインツールバーから「**[!UICONTROL Save as template]**」を選択します。

   ![](assets/email_designer_save-as-template.png)

1. 必要に応じてラベルと説明を追加し、「**[!UICONTROL Save]**」をクリックします。

   ![](assets/email_designer_save-as-template_creation.png)

1. 作成したテンプレートを見つけるには、**[!UICONTROL Resources]**/**[!UICONTROL Content templates & fragments]** に移動します。

1. 新しいテンプレートを使用するには、[ メールDesigner](../../designing/using/designing-content-in-adobe-campaign.md) ホームページの「**[!UICONTROL Templates]**」タブから選択します。

   ![](assets/content_template_new.png)

### フラグメントとコンポーネントを含むテンプレートの作成 {#template-fragments-components}

メールDesignerを使用して、メールテンプレートを作成できるようになりました。 コンテンツコンポーネントを使用してメールの様々なセクションを反映し、設定を調整して元のニュースレターにできるだけ近づけます。 最後に、作成したフラグメントを挿入します。

1. メールDesignerを使用して、テンプレートを作成します。 詳しくは、[ コンテンツテンプレート ](#content-templates) を参照してください。
1. メールのヘッダー、フッター、本文に対応する複数の構造コンポーネントをテンプレートに挿入します。 構造コンポーネントの追加について詳しくは、[ メールDesignerを使用したメール構造の編集 ](../../designing/using/designing-from-scratch.md#defining-the-email-structure) を参照してください。
1. ニュースレターの本文を作成するために必要な数のコンテンツコンポーネントを挿入します。 これは、毎月更新するメールの編集可能なコンテンツになります。

   ![](assets/des_loading_compatible_fragment_5.png)

   HTMLAdobe コードに精通している場合は、元のメールのより複雑な要素をコピーして貼り付けることができる **[!UICONTROL Html]** コンポーネントを利用することをお勧めします。 残りのコンテンツには、**[!UICONTROL Button]**、**[!UICONTROL Image]**、**[!UICONTROL Text]** などの他のコンポーネントを使用します。 詳しくは、[ コンテンツコンポーネントについて ](../../designing/using/designing-from-scratch.md#about-content-components) を参照してください。

   >[!NOTE]
   >
   >**[!UICONTROL Html]** コンポーネントを使用すると、編集可能なコンポーネントが作成されますが、作成されるオプションは限られています。 このコンポーネントを選択する前に、HTMLコードの処理方法を確認してください。

1. 元のメールに可能な限り一致するようにコンテンツコンポーネントを調整します。

   ![](assets/des_loading_compatible_fragment_6.png)

   スタイル設定とインライン属性の管理について詳しくは、[ メールスタイルの編集 ](../../designing/using/styles.md) を参照してください。

1. 前に作成した 2 つのフラグメント（ヘッダーとフッター）を、目的の構造コンポーネントに挿入します。

   ![](assets/des_loading_compatible_fragment_10.png)

1. テンプレートを保存します。

メールDesigner内でこのテンプレートを完全に管理して、毎月受信者に送信するニュースレターを作成および更新できるようになりました。

これを使用するには、メールを作成し、作成したばかりのコンテンツテンプレートを選択します。

**関連トピック**：

* [メールの作成](../../channels/using/creating-an-email.md)
* [メールDesignerの概要ビデオ](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [メールコンテンツのゼロからのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

### チュートリアルビデオ {#video}

このビデオでは、独自のテンプレートを作成する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23106?quality=12)

その他のCampaign Standardチュートリアルビデオについては、[ こちら ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。

## フラグメントについて {#about-fragments}

>[!CONTEXTUALHELP]
>id="ac_fragments"
>title="フラグメントについて"
>abstract="フラグメントは、1 つ以上のメールで参照できる再利用可能なコンテンツブロックです。"

フラグメントは、1 つ以上のメールで参照できる再利用可能なコンポーネントです。
これらのフラグメントは、インターフェイスの **リソース**/**コンテンツフラグメントとテンプレート** にあります。

メールDesignerでフラグメントを最大限に活用するには：

* 独自のフラグメントを作成します。 [ コンテンツフラグメントの作成 ](#creating-a-content-fragment) および [ コンテンツをフラグメントとして保存 ](#saving-content-as-a-fragment) を参照してください。
* 必要な回数だけメールで使用します。 [ メールへの要素の挿入 ](#inserting-elements-into-an-email) を参照してください。
* フラグメントを編集すると、変更内容が同期され、そのフラグメントを含むすべてのメール（準備や送信が済んでいない場合）に自動的に生成されます。

メールに追加すると、フラグメントはデフォルトでロックされます。 特定のメールのフラグメントを変更する場合は、元のフラグメントを使用しているメール内でフラグメントをロック解除することにより、フラグメントとの同期を解除できます。 変更内容は同期されなくなります。

メール内のフラグメントのロックを解除するには、フラグメントを選択し、コンテキストツールバーのロックアイコンをクリックします。

![](assets/des_unlocking_fragment.png)

そのフラグメントは、元のフラグメントにリンクされなくなったスタンドアロンのコンポーネントになります。 その後、他のコンテンツコンポーネントと同様に編集できます。 詳しくは [ コンテンツコンポーネントについて ](../../designing/using/designing-from-scratch.md#about-content-components) を参照してください。

### メールへのフラグメントの挿入 {#inserting-elements-into-an-email}

メールのコンテンツを定義するには、事前に配置した構造コンポーネントにコンテンツ要素を追加します。 [ メール構造の編集 ](../../designing/using/designing-from-scratch.md#defining-the-email-structure) を参照してください。

1. 左側の「**+**」アイコンを選択してコンテンツ要素にアクセスします。 [ フラグメント ](#about-fragments) または [ コンテンツコンポーネント ](../../designing/using/designing-from-scratch.md#about-content-components) を選択します。
1. 追加するフラグメントのラベルまたはラベルの一部が既にわかっている場合は、そのラベルを検索できます。

   ![](assets/email_designer_fragmentsearch.png)

1. フラグメントまたはコンテンツコンポーネントを、パレットからメールの構造コンポーネントにドラッグ&amp;ドロップします。

   ![](assets/email_designer_addfragment.png)

   要素をメールに追加したら、構造コンポーネント内またはメール内の別の構造コンポーネントに移動できます。

   ![](assets/email_designer_movefragment.png)

1. このメールの正確なニーズに一致するように要素を編集します。 テキスト、リンク、画像などを追加できます。

   >[!NOTE]
   >
   >メールに追加された場合、フラグメントはデフォルトでロックされます。 特定のメールのフラグメントを変更する場合や、フラグメント内で直接変更を行う場合は、元のフラグメントとの同期を解除できます。 [ フラグメントについて ](#about-fragments) を参照してください。

1. メールに追加する必要があるすべての要素に対して、この手順を繰り返します。
1. メールを保存します。

メール構造が入力されたので、各コンテンツ要素のスタイルを編集できます。 [ 要素の編集 ](../../designing/using/styles.md) を参照してください。

>[!NOTE]
>
>フラグメントが変更された場合、変更内容はフラグメントが使用されているメールに自動的に反映されます。 詳しくは、[ フラグメントについて ](#about-fragments) を参照してください。

### コンテンツフラグメントの作成 {#creating-a-content-fragment}

独自のコンテンツフラグメントを作成して、1 つ以上のメールで必要に応じて使用できます。

1. **[!UICONTROL Resources]**/**[!UICONTROL Content templates & fragments]** に移動し、「**[!UICONTROL Create]**」をクリックします。
1. メールのラベルをクリックして、メールDesignerの「**[!UICONTROL Properties]**」タブにアクセスします。
1. 認識可能なラベルを指定し、次のパラメーターを選択して、メールコンテンツの編集時にフラグメントを見つけます。

   * フラグメントはメールとのみ互換性があるので、「**[!UICONTROL Content type]**」ドロップダウンリストから「**[!UICONTROL Delivery]**」を選択します。
   * **[!UICONTROL HTML type]** ドロップダウンリストから「**[!UICONTROL Fragment]**」を選択して、このコンテンツをフラグメントとして使用できます。

   ![](assets/email_designer_createfragment.png)

1. 必要に応じて、フラグメントのサムネイルとして使用する画像を設定できます。 テンプレートのプロパティの「**[!UICONTROL Thumbnail]**」タブから選択します。

   ![](assets/email_designer_createfragment_thumbnail.png)

   このサムネールは、メールの編集時にフラグメントのラベルの横に表示されます。

1. 「**[!UICONTROL Properties]**」タブを閉じて、メインワークスペースに戻ります。
1. 必要に応じてカスタマイズできる構造コンポーネントとコンテンツコンポーネントを追加します。

   >[!CAUTION]
   >
   >フラグメントには、パーソナライゼーションフィールド、動的コンテンツ、別のフラグメントを含めることはできません。
   >
   >空の構造コンポーネントを含むフラグメントコンテンツとして保存しないでください。 > フラグメントを挿入した後は、編集できなくなります。
   >
   >[ モバイル表示 ](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view) は、フラグメントでは使用できません。

1. 編集が完了したら、フラグメントを保存します。

このフラグメントは、メールDesignerで作成されたすべてのメールで使用できるようになりました。 パレットの「**[!UICONTROL Fragments]**」セクションの下に表示されます。

>[!NOTE]
>
>メールで使用され、ロックが解除されていない場合は、フラグメント内にパーソナライゼーションフィールドを挿入できません。 [ フラグメントについて ](#about-fragments) を参照してください。

### コンテンツをフラグメントとして保存 {#saving-content-as-a-fragment}

メールDesignerでメールを編集する際に、そのメールの一部をフラグメントとして直接保存できます。

* パーソナライゼーションフィールド、動的コンテンツ、または別のフラグメントを含む構造をフラグメントとして保存することはできません。
* 互いに隣接する構造のみを選択できます。
  <!-- - You cannot select an empty structure.-->

1. メールDesignerでメールを編集する際に、メインツールバーから「**[!UICONTROL Save as fragment]**」を選択します。

   ![](assets/email_designer_save-as-fragment.png)

1. ワークスペースから、フラグメントを構成する構造を選択します。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >互いに隣接し、パーソナライゼーションフィールド、動的コンテンツ、別のフラグメントを含まない構造を選択してください。
   <!--You cannot select an empty structure.-->

1. 「**[!UICONTROL Create]**」をクリックします。

1. 必要に応じてラベルと説明を追加し、「**[!UICONTROL Save]**」をクリックします。

   ![](assets/email_designer_save-as-fragment_popup.png)

1. 作成したフラグメントを見つけるには、**[!UICONTROL Resources]**/**[!UICONTROL Content templates & fragments]** に移動します。

   ![](assets/email_designer_save-as-fragment_list.png)

1. 新しいフラグメントを使用するには、メールコンテンツを開き、フラグメントリストから選択します。

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>[ モバイル表示 ](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view) は、フラグメントでは使用できません。 メールモバイルビューを編集する場合は、コンテンツをフラグメントとして保存する前に編集します。

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

メールDesignerを使用して、再利用可能な各セクションにフラグメントを作成します。 この例では、2 つのフラグメントを作成します。1 つはヘッダー用、もう 1 つはフッター用です。 その後、関連する部分を既存のコンテンツからこれらのフラグメントにコピーできます。

これを行うには、次の手順に従います。

1. Adobe Campaignで、**[!UICONTROL Resources]** / **[!UICONTROL Content templates & fragments]** に移動し、ヘッダーのフラグメントを作成します。 詳しくは、[ コンテンツフラグメントの作成 ](#creating-a-content-fragment) を参照してください。
1. 必要な数の構造コンポーネントをフラグメントに追加します。

   ![](assets/des_loading_compatible_fragment_1.png)

1. 構造に画像コンポーネントとテキストコンポーネントを挿入します。

   ![](assets/des_loading_compatible_fragment_2.png)

1. 対応する画像をアップロードし、テキストを入力して、設定を調整します。

   ![](assets/des_loading_compatible_fragment_3.png)

1. フラグメントを保存します。
1. 同じようにしてフッターを作成し、保存します。

   ![](assets/des_loading_compatible_fragment_4.png)

これで、フラグメントをテンプレートで使用する準備が整いました。
