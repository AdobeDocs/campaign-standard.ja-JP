---
solution: Campaign Standard
product: campaign
title: E メールスタイルの管理
description: 電子メールデザイナで電子メールのスタイルを管理する方法を見つけます。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: 電子メールデザイン
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 2%

---


# E メールスタイルの管理 {#managing-styles}


電子メールデザイナでは、要素を選択すると、選択したコンテンツの種類に固有のオプションが&#x200B;**[!UICONTROL Settings]**&#x200B;ペインに表示されます。 これらのオプションを使用すると、電子メールのスタイルを簡単に変更できます。

## 要素の選択{#selecting-an-element}

電子メールデザイナーインターフェイスで要素を選択するには、次のいずれかを実行します。

* 電子メール内で直接クリックし、
* または、左&#x200B;**パレット**&#x200B;にあるオプションから使用できる構造ツリーを参照します。

![](assets/des_tree_structure.png)

構造ツリーを参照すると、より正確な選択が可能になります。 次のいずれかを選択できます。

* 構造の全体
* 構造コンポーネントを構成する柱の1つ
* 列内にあるコンポーネントのみ。

![](assets/des_tree_structure_selection.png)

列を選択するには、次の操作も行えます。

1. 構造コンポーネントを選択します（電子メール内に直接、または左側の&#x200B;**パレット**&#x200B;から利用できる構造ツリーを使用）。
1. **コンテキストツールバー**&#x200B;で、**[!UICONTROL Select a column]**&#x200B;をクリックして目的の列を選択します。

[このセクション](#example--adjusting-vertical-alignment-and-padding)の例を参照してください。

## スタイル設定の調整{#adjusting-style-settings}

1. 電子メール内の要素を選択します。 詳しくは、[要素の選択](#selecting-an-element)を参照してください。
1. 必要に応じて設定を調整します。 選択した各オファーには、異なる設定のセットがあります。

   背景の挿入、サイズの変更、水平方向または垂直方向の位置の変更、色の管理、[パディングやマージン](#selecting-an-element)の追加などを行うことができます。

   これを行うには、**[!UICONTROL Settings]**&#x200B;ウィンドウに表示されるオプションを使用するか、[インラインスタイル属性を追加](#adding-inline-styling-attributes)します。

   ![](assets/des_settings_pane.png)

1. コンテンツを保存します。

## パディングとマージンの調整{#about-padding-and-margin}

電子メールデザイナーインターフェイスを使用すると、パディングとマージンの設定をすばやく調整できます。

**[!UICONTROL Padding]**:この設定を使用すると、要素の境界線の内側にあるスペースを管理できます。

![](assets/des_padding.png)

例：

* パディングを使用して、画像の左右に余白を設定します。
* 上下のパディングを使用して、**[!UICONTROL Text]**&#x200B;または&#x200B;**[!UICONTROL Divider]**&#x200B;コンポーネントにさらに間隔を追加します。
* 構造要素内の列間に境界線を設定するには、各列のパディングを定義します。

**[!UICONTROL Margin]**:この設定を使用すると、要素の境界線と次の要素の間のスペースを管理できます。

![](assets/des_margin.png)

>[!NOTE]
>
>選択内容（構造コンポーネント、列、またはコンテンツコンポーネント）に応じて、結果は同じになりません。 Adobeでは、**[!UICONTROL Padding]**&#x200B;パラメーターと&#x200B;**[!UICONTROL Margin]**&#x200B;パラメーターを列レベルで設定することをお勧めします。

**[!UICONTROL Padding]**&#x200B;と&#x200B;**[!UICONTROL Margin]**&#x200B;の両方で、ロックアイコンをクリックして、上下左右のパラメーターの同期を解除します。 これにより、各パラメーターを個別に調整できます。

![](assets/des_padding_lock_icon.png)

## 配置のスタイル設定{#about-alignment}

* **テキストの配置**:マウスのカーソルをテキストに合わせ、コンテキストツールバーを使用して整列します。

   ![](assets/des_text_alignment.png)

* **水平方向の** 整列は、テキスト、画像、ボタンに適用できます。現在のところ、 **[!UICONTROL Divider]** および **[!UICONTROL Social]** コンポーネントには適用できません。

   ![](assets/des_horizontal_alignment.png)

* **垂直方向の位置揃え**&#x200B;を設定するには、構造コンポーネント内の列を選択し、設定ペインからオプションを選択します。

   ![](assets/des_set_vertical_alignment.png)

## 背景の設定{#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景の設定"
>abstract="電子メールデザイナでは、コンテンツの背景色や背景画像をパーソナライズできます。背景画像は、すべての電子メールクライアントでサポートされているわけではありません。"
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="追加情報"

電子メールデザイナで背景を設定する場合は、次の操作をAdobeが推奨します。

1. デザインで必要な場合は、電子メールの本文に背景色を適用します。
1. ほとんどの場合、列レベルで背景色を設定します。
1. 管理が困難な画像やテキストコンポーネントでは、背景色を使用しないようにしてください。

使用可能な背景設定は次のとおりです。

* 電子メール全体の&#x200B;**[!UICONTROL Background color]**&#x200B;を設定します。 左側のパレットからアクセスできるナビゲーションツリーで、ボディの設定を選択していることを確認します。

   ![](assets/des_background_body.png)

* **[!UICONTROL Viewport background color]**&#x200B;を選択して、すべての構造コンポーネントに同じ背景色を設定します。 このオプションを使用すると、背景色とは異なる設定を選択できます。

   ![](assets/des_background_viewport.png)

* 構造コンポーネントごとに異なる背景色を設定します。 左側のパレットからアクセス可能なナビゲーションツリーで構造を選択し、その構造にのみ特定の背景色を適用します。

   ![](assets/des_background_structure.png)

   ビューポートの背景色は、構造の背景色が隠れる場合があるので、設定しないでください。

* 構造コンポーネントのコンテンツに対して&#x200B;**[!UICONTROL Background image]**&#x200B;を設定します。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >一部の電子メールプログラムは、背景画像をサポートしていません。 サポートされていない場合は、行の背景色が代わりに使用されます。 画像を表示できない場合に備えて、適切なフォールバックの背景色を選択してください。

* 列レベルで背景色を設定します。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >これが最も一般的な使用例です。 Adobeでは、電子メールコンテンツ全体を編集する際の柔軟性を高めるため、列レベルで背景色を設定することをお勧めします。

   また、列レベルで背景画像を設定することもできますが、ほとんど使用されません。

### 例：垂直方向の位置揃えとパディングの調整{#example--adjusting-vertical-alignment-and-padding}

3つの列で構成される構造コンポーネント内で、パディングと垂直方向の位置を調整する場合。 これをおこなうには、以下の手順に従います。

1. 電子メール内で直接構造コンポーネントを選択するか、左側の&#x200B;**パレット**&#x200B;から使用可能な構造ツリーを使用します。
1. **コンテキストツールバー**&#x200B;から&#x200B;**[!UICONTROL Select a column]**&#x200B;をクリックし、編集するツールバーを選択します。 構造ツリーから選択することもできます。

   ![](assets/des_selecting_column.png)

   その列の編集可能なパラメーターは、右側の&#x200B;**[!UICONTROL Settings]**&#x200B;ペインに表示されます。

1. **[!UICONTROL Vertical alignment]**&#x200B;の下で、**[!UICONTROL Up]**&#x200B;を選択します。

   ![](assets/des_vertical_alignment.png)

   コンテンツコンポーネントは、列の上部に表示されます。

1. **[!UICONTROL Padding]**&#x200B;の下で、列内の上パディングを定義します。 ロックアイコンをクリックして、下のパディングとの同期を解除します。

   その列の左右のパディングを定義します。

   ![](assets/des_adjusting_padding.png)

1. 同様に、他の列の位置揃えとパディングを調整します。

   ![](assets/des_adjusting_columns.png)

1. 変更を保存します。

## リンクのスタイル設定{#about-styling-links}

電子メールデザイナーでは、リンクに下線を引き、リンクの色とターゲットを選択できます。

1. リンクが挿入されるコンポーネントで、リンクのラベルテキストを選択します。

1. コンポーネント設定で、**[!UICONTROL Underline link]**&#x200B;をチェックして、リンクのラベルテキストに下線を付けます。

   ![](assets/stylelinks-selecttext.png)

1. リンクを開く参照コンテキストを選択するには、**[!UICONTROL Target]**&#x200B;を選択します。

   ![](assets/stylelinks-target.png)

1. リンクの色を変更するには、**[!UICONTROL Link color]**&#x200B;をクリックします。

   ![](assets/stylelinks-colorpicker.png)

1. 必要な色を選択します。

   ![](assets/stylelinks-colorchanged.png)

1. 変更を保存します。

## インラインスタイル属性の追加{#adding-inline-styling-attributes}

電子メールデザイナーインターフェイスで、要素を選択し、サイドパネルにその設定を表示する場合、インライン属性とその要素の値をカスタマイズできます。

1. コンテンツ内の要素を選択します。
1. サイドパネルで&#x200B;**[!UICONTROL Styles Inline]**&#x200B;設定を探します。

   ![](assets/email_designer_inlineattributes.png)

1. 既存の属性の値を変更するか、**+**&#x200B;ボタンを使用して新しい属性を追加します。 CSSに準拠している任意の属性と値を追加できます。

次に、選択した要素にスタイルが適用されます。 子要素に特定のスタイル設定属性が定義されていない場合、親要素のスタイル設定が継承されます。
