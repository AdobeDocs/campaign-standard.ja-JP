---
title: メールスタイルの管理
description: メールDesignerでメールスタイルを管理する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 8daeb12d-4170-464f-ba33-afb681f72a91
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 27%

---

# メールスタイルの管理 {#managing-styles}


電子メールDesignerでは、要素を選択すると、選択したコンテンツのタイプに固有のいくつかのオプションが **[!UICONTROL Settings]** ペインに表示されます。 これらのオプションを使用すると、メールのスタイルを簡単に変更できます。

## 要素の選択 {#selecting-an-element}

メールDesignerインターフェイスで要素を選択するには、次のいずれかを実行します。

* メール内で直接クリックする。
* または、左側の **パレット** にあるオプションから使用できる構造ツリーを参照します。

![](assets/des_tree_structure.png)

構造ツリーを参照することで、より正確な選択を行うことができます。 次のいずれかを選択できます。

* 構造コンポーネント全体、
* 構造コンポーネントを構成する列の 1 つ
* または、列の内側にあるコンポーネントのみ。

![](assets/des_tree_structure_selection.png)

列を選択するには、次の操作も実行します。

1. 構造コンポーネントを（メール内で直接選択するか、左側の **パレット** から使用可能な構造ツリーを使用して）選択します。
1. **コンテキストツールバー** から、「**[!UICONTROL Select a column]**」をクリックして目的の列を選択します。

[ この節 ](#example--adjusting-vertical-alignment-and-padding) の例を参照してください。

## スタイル設定の調整 {#adjusting-style-settings}

1. メールの要素を選択します。 詳しくは、[ 要素の選択 ](#selecting-an-element) を参照してください。
1. 必要に応じて設定を調整します。 選択した要素ごとに異なる設定セットが用意されています。

   背景の挿入、サイズの変更、水平方向または垂直方向の整列の変更、色の管理、[ パディングまたは余白 ](#selecting-an-element) の追加などを行うことができます。

   それには、**[!UICONTROL Settings]** ペインに表示されるオプションを使用するか、[ インラインスタイル属性を追加 ](#adding-inline-styling-attributes) します。

   ![](assets/des_settings_pane.png)

1. コンテンツを保存します。

## パディングと余白の調整 {#about-padding-and-margin}

メールDesigner インターフェイスを使用すると、パディングと余白をすばやく調整できます。

**[!UICONTROL Padding]**：この設定を使用すると、要素の境界線の内側にあるスペースを管理できます。

![](assets/des_padding.png)

例：

* パディングを使用して、画像の左右に余白を設定します。
* 上と下のパディングを使用して、**[!UICONTROL Text]** または **[!UICONTROL Divider]** コンポーネントに間隔を追加します。
* 構造体要素内の列間に境界線を設定するには、各列のパディングを定義します。

**[!UICONTROL Margin]**：この設定を使用すると、要素の境界線と次の要素の間のスペースを管理できます。

![](assets/des_margin.png)

>[!NOTE]
>
>選択（構造コンポーネント、列コンポーネント、コンテンツコンポーネント）によっては、結果が同じにならない場合があります。 Adobeでは、列レベルで **[!UICONTROL Padding]** パラメーターと **[!UICONTROL Margin]** パラメーターを設定することをお勧めします。

**[!UICONTROL Padding]** と **[!UICONTROL Margin]** の両方について、ロックアイコンをクリックして、上下または左右のパラメーターの同期を解除します。 これにより、各パラメーターを個別に調整できます。

![](assets/des_padding_lock_icon.png)

## スタイルの関連付け {#about-alignment}

* **テキストの位置揃え**：テキストの上にマウスのカーソルを置き、コンテキストツールバーを使用してテキストを位置揃えします。

  ![](assets/des_text_alignment.png)

* **水平方向の位置揃え** は、テキスト、画像、ボタンに適用できます。現時点では、**[!UICONTROL Divider]** コンポーネントと **[!UICONTROL Social]** コンポーネントには適用されません。

  ![](assets/des_horizontal_alignment.png)

* **垂直方向の整列** を設定するには、構造コンポーネント内の列を選択し、設定ペインからオプションを選択します。

  ![](assets/des_set_vertical_alignment.png)

## 背景の設定 {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景設定"
>abstract="E メールデザイナーでは、コンテンツの背景色や背景画像をパーソナライズできます。なお、背景画像は、一部のメールクライアントではサポートされていません。"

E メールデザイナーで背景を設定する際の推奨事項は次のとおりです。

1. デザインで必要な場合は、メールの本文に背景色を適用します。
1. ほとんどの場合、列レベルで背景色を設定します。
1. 画像やテキストコンポーネントは管理が困難であるため、背景色を使用しないようにしてください。

使用可能な背景設定を次に示します。

* メール全体の **[!UICONTROL Background color]** を設定します。 左側のパレットからアクセスできるナビゲーションツリーで、本文設定を選択していることを確認してください。

  ![](assets/des_background_body.png)

* **[!UICONTROL Viewport background color]** を選択して、すべての構造コンポーネントに同じ背景色を設定する。 このオプションを使用すると、背景色から別の設定を選択できます。

  ![](assets/des_background_viewport.png)

* 構造コンポーネントごとに異なる背景色を設定します。左側のパレットからアクセス可能なナビゲーションツリーで構造を選択し、特定の背景色をその構造にのみ適用します。

  ![](assets/des_background_structure.png)

  構造の背景色が隠れてしまう場合があるので、ビューポートの背景色を設定しないでください。

* 構造コンポーネントのコンテンツの **[!UICONTROL Background image]** を設定します。

  ![](assets/des_background_image.png)

  >[!NOTE]
  >
  >一部のメールプログラムでは、背景画像はサポートされていません。サポートされていない場合は、代わりに行の背景色が使用されます。画像を表示できない場合は、必ず適切なフォールバックの背景色を選択してください。

* 列レベルで背景色を設定します。

  ![](assets/des_background_column.png)

  >[!NOTE]
  >
  >これは最も一般的な使用例です。アドビでは、メールコンテンツ全体を柔軟に編集できるように、背景色を列レベルで設定することをお勧めします。

  また、列レベルで背景画像を設定することもできますが、ほとんど使用されません。

### 例：垂直方向の整列とパディングを調整する {#example--adjusting-vertical-alignment-and-padding}

3 列で構成される構造コンポーネント内で、パディングと垂直方向の整列を調整する場合。 これを行うには、次の手順に従います。

1. メール内で直接構造コンポーネントを選択するか、左側の **パレット** から使用可能な構造ツリーを使用します。
1. **コンテキストツールバー** から、「**[!UICONTROL Select a column]**」をクリックし、編集するツールバーを選択します。 構造ツリーから選択することもできます。

   ![](assets/des_selecting_column.png)

   その列の編集可能なパラメーターは、右側の **[!UICONTROL Settings]** ペインに表示されます。

1. 「**[!UICONTROL Vertical alignment]**」で、「**[!UICONTROL Up]**」を選択します。

   ![](assets/des_vertical_alignment.png)

   コンテンツコンポーネントは、列の一番上に表示されます。

1. 「**[!UICONTROL Padding]**」で、列の上のパディングを定義します。 鍵アイコンをクリックして、下のパディングとの同期を解除します。

   その列の左右のパディングを定義します。

   ![](assets/des_adjusting_padding.png)

1. 他の列の整列とパディングを調整する場合と同様に行います。

   ![](assets/des_adjusting_columns.png)

1. 変更内容を保存します。

## リンクのスタイル設定 {#about-styling-links}

E メールデザイナーでは、リンクに下線を引き、その色とターゲットを選択できます。

1. リンクを挿入するコンポーネントで、リンクのラベルテキストを選択します。

1. コンポーネント設定で、「」にチェックを入 **[!UICONTROL Underline link]** て、リンクのラベルテキストに下線を引きます。

   ![](assets/stylelinks-selecttext.png)

1. リンクを開く閲覧コンテキストを選択するには、**[!UICONTROL Target]** を選択します。

   ![](assets/stylelinks-target.png)

1. リンクの色を変更するには、「**[!UICONTROL Link color]**」をクリックします。

   ![](assets/stylelinks-colorpicker.png)

1. 必要な色を選択します。

   ![](assets/stylelinks-colorchanged.png)

1. 変更内容を保存します。

## インラインスタイル属性の追加 {#adding-inline-styling-attributes}

メールDesigner インターフェイスで要素を選択し、サイドパネルで設定を表示すると、その要素のインライン属性と値をカスタマイズできます。

1. コンテンツの要素を選択します。
1. サイドパネルで、**[!UICONTROL Styles Inline]** 設定を探します。

   ![](assets/email_designer_inlineattributes.png)

1. 既存の属性の値を変更するか、「**+**」ボタンを使用して新しい属性を追加します。 CSS に準拠している任意の属性と値を追加できます。

スタイルが選択した要素に適用されます。 子要素に特定のスタイル属性が定義されていない場合、親要素のスタイル設定が継承されます。
