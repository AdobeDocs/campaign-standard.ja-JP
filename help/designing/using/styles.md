---
title: E メールスタイルの管理
description: EメールデザイナーでEメールスタイルを管理する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 8daeb12d-4170-464f-ba33-afb681f72a91
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 2%

---

# E メールスタイルの管理 {#managing-styles}


Eメールデザイナーでは、要素を選択する際に、選択したコンテンツのタイプに固有のオプションが&#x200B;**[!UICONTROL Settings]**&#x200B;ウィンドウに表示されます。 これらのオプションを使用すると、Eメールのスタイルを簡単に変更できます。

## 要素の選択 {#selecting-an-element}

Eメールデザイナーインターフェイスで要素を選択するには、次のいずれかを実行します。

* 電子メールを直接クリックします。
* または、左側の&#x200B;**パレット**&#x200B;にあるオプションから使用できる構造ツリーを参照します。

![](assets/des_tree_structure.png)

構造ツリーを参照すると、より正確な選択が可能になります。 次のいずれかを選択できます。

* 構造の構成要素全体
* 構造コンポーネントを構成する列の1つ
* または、列内に配置されているコンポーネントのみ。

![](assets/des_tree_structure_selection.png)

列を選択するには、次の操作も実行できます。

1. 構造コンポーネントを選択します（Eメール内で直接選択するか、左側の&#x200B;**パレット**&#x200B;から使用できる構造ツリーを使用します）。
1. **コンテキストツールバー**&#x200B;から、**[!UICONTROL Select a column]**&#x200B;をクリックして目的の列を選択します。

[この節の例](#example--adjusting-vertical-alignment-and-padding)を参照してください。

## スタイル設定の調整 {#adjusting-style-settings}

1. Eメール内の要素を選択します。 詳しくは、[要素の選択](#selecting-an-element)を参照してください。
1. 必要に応じて設定を調整します。 選択した要素ごとに異なる設定が提供されます。

   背景の挿入、サイズの変更、水平方向または垂直方向の整列の変更、色の管理、[パディングまたはマージン](#selecting-an-element)の追加などを行うことができます。

   これをおこなうには、**[!UICONTROL Settings]**&#x200B;ウィンドウに表示されるオプションを使用するか、[インラインスタイル属性](#adding-inline-styling-attributes)を追加します。

   ![](assets/des_settings_pane.png)

1. コンテンツを保存します。

## パディングと余白の調整 {#about-padding-and-margin}

Eメールデザイナーインターフェイスを使用すると、パディングと余白の設定をすばやく調整できます。

**[!UICONTROL Padding]**:この設定を使用すると、要素の境界線内にあるスペースを管理できます。

![](assets/des_padding.png)

例：

* パディングを使用して、画像の左右に余白を設定します。
* **[!UICONTROL Text]**&#x200B;コンポーネントまたは&#x200B;**[!UICONTROL Divider]**&#x200B;コンポーネントにスペースを追加するには、上下のパディングを使用します。
* 構造要素内の列間に境界線を設定するには、各列のパディングを定義します。

**[!UICONTROL Margin]**:この設定を使用すると、要素の境界線と次の要素の間のスペースを管理できます。

![](assets/des_margin.png)

>[!NOTE]
>
>選択内容（構造コンポーネント、列コンポーネント、コンテンツコンポーネント）に応じて、結果は同じになりません。 Adobeでは、**[!UICONTROL Padding]**&#x200B;パラメーターと&#x200B;**[!UICONTROL Margin]**&#x200B;パラメーターを列レベルで設定することをお勧めします。

**[!UICONTROL Padding]**&#x200B;と&#x200B;**[!UICONTROL Margin]**&#x200B;の両方で、ロックアイコンをクリックして、上、下、または右、左のパラメーターの同期を解除します。 これにより、各パラメータを個別に調整できます。

![](assets/des_padding_lock_icon.png)

## スタイルの整列 {#about-alignment}

* **テキストの整列**:テキストにマウスのカーソルを置き、コンテキストツールバーを使用して整列します。

   ![](assets/des_text_alignment.png)

* **水平方** 向の整列は、テキスト、画像およびボタンに適用できます。現在、およびコンポーネントには適 **[!UICONTROL Divider]** 用で **[!UICONTROL Social]** きません。

   ![](assets/des_horizontal_alignment.png)

* **垂直方向の整列**&#x200B;を設定するには、構造コンポーネント内の列を選択し、設定ウィンドウからオプションを選択します。

   ![](assets/des_set_vertical_alignment.png)

## 背景の設定 {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景設定"
>abstract="Eメールデザイナーを使用すると、コンテンツの背景色や背景画像をパーソナライズできます。背景画像は、すべてのEメールクライアントでサポートされているわけではありません。"
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="追加情報"

Eメールデザイナーで背景を設定する場合、Adobeでは次の操作をお勧めします。

1. デザインで必要に応じて、Eメールの本文に背景色を適用します。
1. ほとんどの場合、列レベルで背景色を設定します。
1. 画像やテキストコンポーネントは管理が困難なので、背景色を使用しないようにしてください。

使用可能な背景設定は次のとおりです。

* 電子メール全体に&#x200B;**[!UICONTROL Background color]**&#x200B;を設定します。 左側のパレットからアクセス可能なナビゲーションツリーで、ボディ設定を選択していることを確認してください。

   ![](assets/des_background_body.png)

* **[!UICONTROL Viewport background color]**&#x200B;を選択して、すべての構造コンポーネントに同じ背景色を設定します。 このオプションを使用すると、背景色から別の設定を選択できます。

   ![](assets/des_background_viewport.png)

* 構造コンポーネントごとに異なる背景色を設定します。 左側のパレットからアクセス可能なナビゲーションツリーの構造を選択し、その構造にのみ特定の背景色を適用します。

   ![](assets/des_background_structure.png)

   ビューポートの背景色は、構造の背景色を隠すので、設定しないでください。

* 構造コンポーネントのコンテンツに&#x200B;**[!UICONTROL Background image]**&#x200B;を設定します。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >一部の電子メールプログラムは背景画像をサポートしていません。 サポートされていない場合は、代わりに行の背景色が使用されます。 画像を表示できない場合は、必ず適切なフォールバックの背景色を選択してください。

* 列レベルで背景色を設定します。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >これは最も一般的な使用例です。 Adobeでは、Eメールコンテンツ全体を編集する際の柔軟性を高めるため、背景色を列レベルで設定することをお勧めします。

   また、列レベルで背景画像を設定することもできますが、ほとんど使用されません。

### 例：垂直方向の整列とパディングの調整 {#example--adjusting-vertical-alignment-and-padding}

3つの列で構成される構造コンポーネント内で、パディングと垂直方向の整列を調整します。 これは、次の手順に従って行います。

1. Eメール内で直接構造コンポーネントを選択するか、左側の&#x200B;**パレット**&#x200B;から使用できる構造ツリーを使用します。
1. **コンテキストツールバー**&#x200B;から&#x200B;**[!UICONTROL Select a column]**&#x200B;をクリックし、編集するツールバーを選択します。 構造ツリーから選択することもできます。

   ![](assets/des_selecting_column.png)

   その列の編集可能なパラメータが、右側の&#x200B;**[!UICONTROL Settings]**&#x200B;ペインに表示されます。

1. **[!UICONTROL Vertical alignment]**&#x200B;の下で&#x200B;**[!UICONTROL Up]**&#x200B;を選択します。

   ![](assets/des_vertical_alignment.png)

   コンテンツコンポーネントが列の上に表示されます。

1. **[!UICONTROL Padding]**&#x200B;の下で、列内の上のパディングを定義します。 下パディングとの同期を解除するには、ロックアイコンをクリックします。

   その列の左右のパディングを定義します。

   ![](assets/des_adjusting_padding.png)

1. 同様に、他の列の整列とパディングを調整します。

   ![](assets/des_adjusting_columns.png)

1. 変更を保存します。

## リンクのスタイル設定 {#about-styling-links}

Eメールデザイナーで、リンクに下線を引き、その色とターゲットを選択できます。

1. リンクが挿入されるコンポーネントで、リンクのラベルテキストを選択します。

1. コンポーネント設定で、「**[!UICONTROL Underline link]**」をオンにして、リンクのラベルテキストに下線を引きます。

   ![](assets/stylelinks-selecttext.png)

1. リンクを開くブラウジングコンテキストを選択するには、**[!UICONTROL Target]**&#x200B;を選択します。

   ![](assets/stylelinks-target.png)

1. リンクの色を変更するには、**[!UICONTROL Link color]**&#x200B;をクリックします。

   ![](assets/stylelinks-colorpicker.png)

1. 必要な色を選択します。

   ![](assets/stylelinks-colorchanged.png)

1. 変更を保存します。

## インラインスタイル属性の追加 {#adding-inline-styling-attributes}

Eメールデザイナーインターフェイスで、要素を選択し、サイドパネルにその設定を表示する際に、その特定の要素のインライン属性と値をカスタマイズできます。

1. コンテンツ内の要素を選択します。
1. サイドパネルで、**[!UICONTROL Styles Inline]**&#x200B;設定を探します。

   ![](assets/email_designer_inlineattributes.png)

1. 既存の属性の値を変更するか、**+**&#x200B;ボタンを使用して新しい属性を追加します。 CSSに準拠している任意の属性と値を追加できます。

次に、選択した要素にスタイルが適用されます。 子要素に特定のスタイル設定属性が定義されていない場合、親要素のスタイル設定が継承されます。
