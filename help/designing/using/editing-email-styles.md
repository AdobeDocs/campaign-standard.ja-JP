---
title: 電子メールスタイルの編集
seo-title: 電子メールスタイルの編集
description: 電子メールスタイルの編集
seo-description: 電子メールDesignerを使用して、容易にアクセスできるようにすることで、コンテンツのスタイルをすばやく編集できます。
page-status-flag: 常にアクティブ化されていない
uuid: 1ac228d- c02c-410a- a4bd-0c3b163ab5f9
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: edit- email- content
discoiquuid: 09c66cd5-2bbf-4846- ac8a-312ab5c18473
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Editing email styles{#editing-email-styles}

## Editing an element {#editing-an-element}

In the Email Designer, when selecting an element, several options specific to the type of content selected are displayed in the **[!UICONTROL Settings]** pane. これらのオプションを使用すると、電子メールのスタイルを簡単に変更できます。

### Selecting an element {#selecting-an-element}

電子メールデザイナーインターフェイスで要素を選択するには、次のいずれかを実行します。

* 電子メールを直接クリックして、
* or browse the structure tree available from the options located in the left **Palette**.

![](assets/des_tree_structure.png)

構造ツリーを参照すると、より正確な選択を行うことができます。次のいずれかを選択できます。

* 構成要素全体、
* 構造コンポーネントを構成する列の1つ、
* または、列内にあるコンポーネントのみを指定します。

![](assets/des_tree_structure_selection.png)

列を選択するには、次の手順を実行します。

1. Select a structure component (directly in the email or using the structure tree available from the left **Palette**).
1. **コンテキストツールバー**&#x200B;で、をクリック **[!UICONTROL Select a column]** して目的の列を選択します。

See an example in [this section](../../designing/using/editing-email-styles.md#example--adjusting-vertical-alignment-and-padding).

### Adjusting style settings {#adjusting-style-settings}

1. 電子メール内の要素を選択します。For more on this, see [Selecting an element](../../designing/using/editing-email-styles.md#selecting-an-element).
1. 必要に応じて設定を調整します。選択した各要素には、異なる設定セットがあります。

   You can insert backgrounds, change sizes, modify horizontal or vertical alignment, manage colors, add [padding or margin](../../designing/using/editing-email-styles.md#about-padding-and-margin), and so on.

   To do this, use the options displayed in the **[!UICONTROL Settings]** pane or [add inline styling attributes](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. コンテンツを保存します。

### About padding and margin {#about-padding-and-margin}

電子メールデザイナーインターフェイスを使用すると、パディングとマージンの設定をすばやく調整できます。

**[!UICONTROL Padding]**:この設定により、要素の境界線内にあるスペースを管理できます。

![](assets/des_padding.png)

次に例を示します。

* パディングを使用して、画像の左右の辺に余白を設定します。
* Use top and bottom padding to add more spacing to a **[!UICONTROL Text]** or a **[!UICONTROL Divider]** component.
* 構造要素内の列間に境界線を設定するには、各列のパディングを定義します。

**[!UICONTROL Margin]**:この設定により、要素の境界線と次の要素の間のスペースを管理できます。

![](assets/des_margin.png)

>[!NOTE]
>
>選択内容（構造コンポーネント、列またはコンテンツコンポーネント）に応じて、結果は同じになりません。Adobe recommends setting the **[!UICONTROL Padding]** and **[!UICONTROL Margin]** parameters at the column level.

For both **[!UICONTROL Padding]** and **[!UICONTROL Margin]**, click the lock icon to break synchronization between top and bottom or right and left parameters. これにより、各パラメーターを個別に調整できます。

![](assets/des_padding_lock_icon.png)

### About alignment {#about-alignment}

* **テキストの整列**:マウスのカーソルをテキストに配置し、コンテキストツールバーを使用して整列します。

   ![](assets/des_text_alignment.png)

* **水平方向の配置** は、テキスト、画像およびボタンに適用できます（現在 **[!UICONTROL Divider]****[!UICONTROL Social]** 、コンポーネントには適用されません）。

   ![](assets/des_horizontal_alignment.png)

* **垂直方向の整列**&#x200B;を設定するには、構造コンポーネント内の列を選択し、設定パネルからオプションを選択します。

   ![](assets/des_set_vertical_alignment.png)

### About backgrounds {#about-backgrounds}

背景を電子メールデザイナーと設定する際には、次のことを推奨します。

1. デザインに必要な場合は、電子メールの本文に背景色を適用します。
1. ほとんどの場合、列レベルで背景色を設定します。
1. 管理が困難なときに、画像またはテキストコンポーネントで背景色を使用しないようにしてください。

以下に、使用可能な背景設定を示します。

* Set a **[!UICONTROL Background color]** for the whole email. 左側のパレットからアクセス可能なナビゲーションツリーで、ボディ設定を選択してください。

   ![](assets/des_background_body.png)

* Set the same background color for all structure components by selecting **[!UICONTROL Viewport background color]**. このオプションを使用すると、背景色から別の設定を選択できます。

   ![](assets/des_background_viewport.png)

* 構造コンポーネントごとに異なる背景色を設定します。左側のパレットからアクセスできるナビゲーションツリーの構造を選択して、特定の背景色のみをその構造に適用します。

   ![](assets/des_background_structure.png)

   ビューポートの背景色が設定されていないことを確認してください。

* Set a **[!UICONTROL Background image]** for the content of a structure component.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >一部の電子メールプログラムでは、背景画像はサポートされていません。画像を表示できない場合は、適切なフォールバック背景色を選択してください。

* 列レベルで背景色を設定します。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >これは最も一般的な使用例です。電子メールコンテンツ全体を編集する際には、列レベルで背景色を設定することをお勧めします。

   列レベルで背景画像を設定することもできますが、これはほとんど使用されません。

### Example: adjusting vertical alignment and padding {#example--adjusting-vertical-alignment-and-padding}

3つの列から構成される構造コンポーネント内のパディングと垂直方向の位置を調整します。これを行うには、次の手順に従います。

1. Select the structure component directly in the email or using the structure tree available from the left **Palette**.
1. **コンテキストツールバー**&#x200B;で、をクリック **[!UICONTROL Select a column]** し、編集する対象のツールバーを選択します。構造ツリーからも選択できます。

   ![](assets/des_selecting_column.png)

   The editable parameters for that column are displayed in the **[!UICONTROL Settings]** pane on the right.

1. Under **[!UICONTROL Vertical alignment]**, select **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   コンテンツコンポーネントが列の上に表示されます。

1. Under **[!UICONTROL Padding]**, define the top padding inside the column. ロックアイコンをクリックして、下部のパディングと同期します。

   その列の左右のパディングを定義します。

   ![](assets/des_adjusting_padding.png)

1. 同様に、他の列の整列とパディングを調整します。

   ![](assets/des_adjusting_columns.png)

1. 変更内容を保存します。

## Adding inline styling attributes {#adding-inline-styling-attributes}

電子メールデザイナーインターフェイスでは、要素を選択し、サイドパネルにその設定を表示すると、インライン属性とその特定の要素の値をカスタマイズできます。

1. コンテンツ内の要素を選択します。
1. On the side panel, look for the **[!UICONTROL Styles Inline]** settings.

   ![](assets/email_designer_inlineattributes.png)

1. Modify the values of the existing attributes, or add new ones using the **+** button. CSSに準拠した属性や値を追加できます。

スタイル設定は、選択した要素に適用されます。子要素に特定のスタイル属性が定義されていない場合、親要素のスタイル設定が継承されます。
