---
title: スタイルの管理
description: 電子メールデザイナーでの電子メールスタイルの管理方法を確認します。
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# スタイルの管理 {#managing-styles}

## 電子メールスタイルの編集{#editing-email-styles}

### 要素の編集 {#editing-an-element}

電子メールデザイナーでは、要素を選択する際に、選択したコンテンツの種類に固有のオプションがペインに表示さ **[!UICONTROL Settings]** れます。 これらのオプションを使用すると、電子メールのスタイルを簡単に変更できます。

### 要素の選択 {#selecting-an-element}

電子メールデザイナーインターフェイスで要素を選択するには、次のいずれかを実行します。

* 電子メール内で直接クリックし、
* または、左側のパレットにあるオプションから使用できる構造ツリーを参照 **します**。

![](assets/des_tree_structure.png)

構造ツリーを参照すると、より正確な選択を行うことができます。 次のいずれかを選択できます。

* 構造の全部
* 構造コンポーネントを構成する列の1つ
* または列内に配置されたコンポーネントのみ。

![](assets/des_tree_structure_selection.png)

列を選択するには、次の操作も実行できます。

1. 構造コンポーネントを選択します(電子メール内に直接、または左側のパレットにある構造ツリーを使 **用します**)。
1. コンテキストツ **ールバーで**、をク **[!UICONTROL Select a column]** リックして目的の列を選択します。

この節の例を参 [照します](#example--adjusting-vertical-alignment-and-padding)。

### スタイル設定の調整 {#adjusting-style-settings}

1. 電子メール内の要素を選択します。 詳しくは、要素の選択を参 [照してください](#selecting-an-element)。
1. 必要に応じて設定を調整します。 選択した各要素には、異なる設定のセットがあります。

   背景の挿入、サイズの変更、水平方向または垂直方向の位置揃えの変更、色の管理、パディング [やマージンの追加](#selecting-an-element)などができます。

   これを行うには、パネルに表示されるオプションを使用するか、インラ **[!UICONTROL Settings]** インスタ [イル属性を追加します](#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. コンテンツを保存します。

### パディングとマージンについて {#about-padding-and-margin}

電子メールデザイナーインターフェイスを使用すると、パディングとマージンの設定をすばやく調整できます。

**[!UICONTROL Padding]**:この設定を使用すると、要素の境界線の内側にあるスペースを管理できます。

![](assets/des_padding.png)

次に例を示します。

* パディングを使用して、画像の左右の余白を設定します。
* 上下のパディングを使用して、またはコンポーネントにさらに間隔 **[!UICONTROL Text]** を追加 **[!UICONTROL Divider]** します。
* 構造要素内の列間に境界線を設定するには、各列のパディングを定義します。

**[!UICONTROL Margin]**:この設定により、要素の境界線と次の要素の間のスペースを管理できます。

![](assets/des_margin.png)

>[!NOTE]
>
>選択内容（構造コンポーネント、列またはコンテンツコンポーネント）によっては、結果は同じではありません。 列レベルでパラメー **[!UICONTROL Padding]** ターとパ **[!UICONTROL Margin]** ラメーターを設定することをお勧めします。

との両方につ **[!UICONTROL Padding]** いて、ロ **[!UICONTROL Margin]**&#x200B;ックアイコンをクリックして、上、下、右、左の各パラメータの同期を解除します。 これにより、各パラメータを個別に調整できます。

![](assets/des_padding_lock_icon.png)

### 整列について {#about-alignment}

* **テキスト揃え**:マウスのカーソルをテキスト上に置き、コンテキストツールバーを使用して整列します。

   ![](assets/des_text_alignment.png)

* **水平方向の配置は** 、テキスト、画像、ボタンに適用できます。現在のとコンポーネントには適用 **[!UICONTROL Divider]** でき **[!UICONTROL Social]** ません。

   ![](assets/des_horizontal_alignment.png)

* 垂直方向の位 **置揃えを設定するには**、構造コンポーネント内の列を選択し、設定ペインからオプションを選択します。

   ![](assets/des_set_vertical_alignment.png)

### 背景について {#about-backgrounds}

電子メールデザイナーで背景を設定する場合は、次の設定をお勧めします。

1. デザインで必要な場合は、電子メールの本文に背景色を適用します。
1. ほとんどの場合、背景色は列レベルで設定します。
1. 管理が困難な画像やテキストコンポーネントでは、背景色を使用しないようにしてください。

使用できる背景設定は次のとおりです。

* 電子メール全 **[!UICONTROL Background color]** 体に対してを設定します。 左側のパレットからアクセス可能なナビゲーションツリーでボディ設定を選択していることを確認します。

   ![](assets/des_background_body.png)

* を選択して、すべての構造コンポーネントに同じ背景色を設定しま **[!UICONTROL Viewport background color]**&#x200B;す。 このオプションを使用すると、背景色とは異なる設定を選択できます。

   ![](assets/des_background_viewport.png)

* 構造コンポーネントごとに異なる背景色を設定します。 左側のパレットからアクセス可能なナビゲーションツリーで構造を選択し、その構造にのみ特定の背景色を適用します。

   ![](assets/des_background_structure.png)

   ビューポートの背景色は、構造の背景色を隠す場合があるので、設定しないでください。

* 構造コンポ **[!UICONTROL Background image]** ーネントのコンテンツに対してを設定します。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >一部の電子メールプログラムは背景画像をサポートしません。 画像を表示できない場合に備えて、適切なフォールバック背景色を選択してください。

* 列レベルで背景色を設定します。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >これが最も一般的な使用例です。 アドビでは、電子メールコンテンツ全体を編集する際の柔軟性を高めるため、背景色を列レベルで設定することをお勧めします。

   また、列レベルで背景画像を設定することもできますが、ほとんど使用されません。

#### 例：垂直方向の配置とパディングの調整 {#example--adjusting-vertical-alignment-and-padding}

3つの列で構成される構造コンポーネント内で、パディングと垂直方向の配置を調整する場合。 これをおこなうには、以下の手順に従います。

1. 電子メール内で直接構造コンポーネントを選択するか、左のパレットで使用可能な構造ツリーを使用 **します**。
1. コンテキ **ストツールバー**&#x200B;で **[!UICONTROL Select a column]** 、をクリックし、編集するツールを選択します。 構造ツリーから選択することもできます。

   ![](assets/des_selecting_column.png)

   その列の編集可能なパラメータが右側のパネル **[!UICONTROL Settings]** に表示されます。

1. の下で、 **[!UICONTROL Vertical alignment]**&#x200B;を選択しま **[!UICONTROL Up]**&#x200B;す。

   ![](assets/des_vertical_alignment.png)

   コンテンツコンポーネントが列の上部に表示されます。

1. 下で、 **[!UICONTROL Padding]**&#x200B;列内の上パディングを定義します。 下のパディングとの同期を解除するには、ロックアイコンをクリックします。

   その列の左右のパディングを定義します。

   ![](assets/des_adjusting_padding.png)

1. 同様に、他の列の整列とパディングを調整します。

   ![](assets/des_adjusting_columns.png)

1. 変更を保存します。

### リンクのスタイル設定について {#about-styling-links}

>[!NOTE]
>
>この機能は、Campaign Standard 19.4リリースから利用可能になります。

電子メールデザイナーで、リンクに下線を引き、その色とターゲットを選択できます。

1. リンクが挿入されるコンポーネントで、リンクのラベルテキストを選択します。

1. コンポーネント設定で、リンクのラ **[!UICONTROL Underline link]** ベルテキストに下線を引く場合にオンにします。

   ![](assets/stylelinks-selecttext.png)

1. リンクを開く参照コンテキストを選択するには、を選択しま **[!UICONTROL Target]**&#x200B;す。

   ![](assets/stylelinks-target.png)

1. リンクの色を変更するには、をクリックしま **[!UICONTROL Link color]**&#x200B;す。

   ![](assets/stylelinks-colorpicker.png)

1. 必要な色を選択します。

   ![](assets/stylelinks-colorchanged.png)

1. 変更を保存します。

### インラインスタイル属性の追加 {#adding-inline-styling-attributes}

電子メールデザイナーインターフェイスで、要素を選択し、サイドパネルにその設定を表示する場合、特定の要素のインライン属性とその値をカスタマイズできます。

1. コンテンツ内の要素を選択します。
1. サイドパネルで、設定を探し **[!UICONTROL Styles Inline]** ます。

   ![](assets/email_designer_inlineattributes.png)

1. 既存の属性の値を変更するか、[ **+]ボタンを使用して新しい属性を追加** します。 CSSに準拠している任意の属性と値を追加できます。

次に、選択した要素にスタイル設定が適用されます。 子要素に特定のスタイル属性が定義されていない場合、親要素のスタイル設定が継承されます。

## モバイルビューへの切り替え {#switching-to-mobile-view}

モバイルディスプレイ用のすべてのスタイルオプションを個別に編集することで、電子メールのレスポンシブデザインを微調整できます。 例えば、余白とパディングを調整したり、小さいフォントサイズまたは大きいフォントサイズを使用したり、ボタンを変更したり、電子メールのモバイルバージョンに固有の異なる背景色を適用したりできます。

モバイルビューでは、すべてのスタイルオプションを使用できます。 電子メールデザイナーのスタイル設定は、「電子メールスタイルの編 [集」セクションに表示され](#editing-email-styles) ます。

1. 電子メールを作成し、コンテンツの編集を開始します。 詳しくは、「新規での電子メール [コンテンツのデザイン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 専用のモバイルビューにアクセスするには、ボタンを選択 **[!UICONTROL Switch to mobile view]** します。

   ![](assets/email_designer_mobile_view_switch.png)

   電子メールのモバイルバージョンが表示されます。 デスクトップビューで定義されたすべてのコンポーネントとスタイルが含まれます。

1. 背景色、配置、パディング、マージン、フォントファミリー、テキストカラーなど、すべてのスタイル設定を個別に編集します。

   ![](assets/email_designer_mobile_view.png)

1. モバイルビューでスタイル設定を編集する場合、変更はモバイルディスプレイにのみ適用されます。

   例えば、画像のサイズを小さくし、緑の背景を追加して、モバイルビューでパディングを変更します。

   ![](assets/email_designer_mobile_view_change.png)

1. モバイルデバイスで表示する際にコンポーネントを非表示にすることができます。 これを行うには、からを **[!UICONTROL Show only on desktop devices]** 選択しま **[!UICONTROL Display options]**す。
また、デスクトップデバイスでこのコンポーネントを非表示にすることもできます。つまり、このコンポーネントはモバイルデバイスでのみ表示されます。 これを行うには、を選択しま **[!UICONTROL Show only on mobile devices]**す。
例えば、このオプションを使用すると、モバイルデバイスに特定の画像を表示し、デスクトップデバイスに別の画像を表示できます。
このオプションは、モバイルビューまたはデスクトップビューから設定できます。

   ![](assets/email_designer_mobile_hide.png)

1. 標準のデスクトップ **[!UICONTROL Switch to mobile view]** ビューに戻るには、ボタンをもう一度クリックします。 先ほど行ったスタイルの変更は反映されません。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一の例外は設定 **[!UICONTROL Style inline]** です。 スタイルのインライン設定の変更は、標準のデスクトップビューにも適用されます。

1. テキスト編集、新しい画像のアップロード、新しいコンポーネントの追加など、電子メールの構造またはコンテンツに対するその他の変更。 は標準ビューにも適用されます。

   例えば、モバイルビューに切り替え、テキストを編集して画像を置き換えます。

   ![](assets/email_designer_mobile_view_change_content.png)

   標準のデスクトップ **[!UICONTROL Switch to mobile view]** ビューに戻るには、ボタンをもう一度クリックします。 変更が反映されます。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. モバイルビューでスタイルを削除すると、デスクトップモードで適用されたスタイルに戻ります。

   例えば、モバイルビューでは、ボタンに緑の背景色を適用します。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. デスクトップビューに切り替えて、同じボタンにグレーの背景を適用します。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. もう一度モバイルビューに切り替え、設定を無効に **[!UICONTROL Background color]** します。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   デスクトップビューで定義された背景色が適用されるようになりました。灰色に変わります（空白ではありません）。

   唯一の例外は設定 **[!UICONTROL Border color]** です。 モバイルビューで無効にした場合、デスクトップビューで境界線の色が定義されていても、境界線が適用されなくなりました。

>[!NOTE]
>
>モバイルビューはフラグメントでは使用でき [ません](../../designing/using/using-reusable-content.md#about-fragments)。
