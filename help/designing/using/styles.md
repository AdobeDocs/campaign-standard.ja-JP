---
title: スタイルを管理する
seo-title: スタイルを管理する
description: スタイルを管理する
seo-description: 電子メールデザイナで電子メールスタイルを管理する方法を説明します。
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


# スタイルを管理する {#managing-styles}

## 電子メールのスタイルの編集{#editing-email-styles}

### 要素の編集 {#editing-an-element}

電子メールデザイナで、要素を選択すると、選択したコンテンツの種類に固有のオプションがペインに表示さ **[!UICONTROL Settings]** れます。 これらのオプションを使用して、電子メールのスタイルを簡単に変更できます。

### 要素の選択 {#selecting-an-element}

電子メール·デザイナ·インタフェースで要素を選択するには、次のいずれかを実行します。

* 電子メールを直接クリックし
* または、左側のパレットにあるオプションから使用できる構造ツリーを参照 **します**。

![](assets/des_tree_structure.png)

構造ツリーを参照すると、より正確な選択を行うことができます。 次のいずれかを選択できます。

* 全体の構造要素
* 構造コンポーネントを構成する列の1つ
* または、列内に配置されたコンポーネントのみ。

![](assets/des_tree_structure_selection.png)

列を選択するには、次の操作も実行できます。

1. 構造コンポーネントを選択します(電子メール内で直接選択するか、左側のパレットから使用可能な構造ツリーを使 **用します**)。
1. コンテキストツ **ールバーから**、をク **[!UICONTROL Select a column]** リックして目的の列を選択します。

この節の例を参照し [てください](../../designing/using/styles.md#example--adjusting-vertical-alignment-and-padding)。

### スタイル設定の調整 {#adjusting-style-settings}

1. 電子メール内の要素を選択します。 詳細は、要素の選択を参 [照してください](../../designing/using/styles.md#selecting-an-element)。
1. 必要に応じて設定を調整します。 選択した各要素には、異なる設定セットが用意されています。

   背景の挿入、サイズの変更、水平方向または垂直方向の配置の変更、色の管理、余白 [や余白の追加](../../designing/using/styles.md#selecting-an-element)などができます。

   これを行うには、ペインに表示されるオプションを使用するか、インラ **[!UICONTROL Settings]** インスタ [イル属性を追加します](../../designing/using/styles.md#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. コンテンツを保存します。

### 余白と余白について {#about-padding-and-margin}

電子メールデザイナのインタフェースを使用すると、パディングと余白の設定をすばやく調整できます。

**[!UICONTROL Padding]**:この設定を使用すると、要素の境界内にあるスペースを管理できます。

![](assets/des_padding.png)

例：

* 余白を使用して、画像の左右の余白を設定します。
* 上と下のパディングを使用して、またはコンポーネントに間隔を **[!UICONTROL Text]** 追加 **[!UICONTROL Divider]** します。
* 構造要素内の列間の境界を設定するには、各列のパディングを定義します。

**[!UICONTROL Margin]**:この設定を使用すると、要素の境界と次の要素の間のスペースを管理できます。

![](assets/des_margin.png)

>[!NOTE]
>
>選択内容（構造コンポーネント、列コンポーネント、またはコンテンツコンポーネント）に応じて、結果は同じになりません。 列レベルでとのパラ **[!UICONTROL Padding]** メータ **[!UICONTROL Margin]** を設定することをお勧めします。

との両方で、ロ **[!UICONTROL Padding]** ックア **[!UICONTROL Margin]**&#x200B;イコンをクリックして、上部と下部、または右部と左部のパラメータ間の同期を解除します。 これにより、各パラメータを個別に調整できます。

![](assets/des_padding_lock_icon.png)

### 線形について {#about-alignment}

* **文字の配置**:マウスのカーソルをテキストに置き、コンテキストツールバーを使用してテキストの位置を揃えます。

   ![](assets/des_text_alignment.png)

* **水平方向の配置は** 、現在のとコンポーネントには適用されない、テキスト、イメージ、およびボタンに **[!UICONTROL Divider]** 適用で **[!UICONTROL Social]** きます。

   ![](assets/des_horizontal_alignment.png)

* 垂直方向の位置合 **わせを設定するには**、構造コンポーネント内の列を選択し、[設定]ペインからオプションを選択します。

   ![](assets/des_set_vertical_alignment.png)

### 背景について {#about-backgrounds}

電子メールデザイナで背景を設定する場合は、次のことをお勧めします。

1. デザインで必要な場合は、電子メールの本文に背景色を適用します。
1. ほとんどの場合、列レベルで背景色を設定します。
1. イメージやテキストコンポーネントは管理が困難なため、背景色を使用しないようにしてください。

以下に、使用できる背景設定を示します。

* 電子メール全 **[!UICONTROL Background color]** 体のを設定します。 左側のパレットからアクセス可能なナビゲーションツリーで、ボディ設定を選択してください。

   ![](assets/des_background_body.png)

* を選択して、すべての構造コンポーネントに同じ背景色を設定しま **[!UICONTROL Viewport background color]**&#x200B;す。 このオプションを使用すると、背景色とは異なる設定を選択できます。

   ![](assets/des_background_viewport.png)

* 構造コンポーネントごとに異なる背景色を設定します。 左側のパレットからアクセス可能なナビゲーションツリーで構造を選択し、その構造にのみ特定の背景色を適用します。

   ![](assets/des_background_structure.png)

   ビューポートの背景色は、構造の背景色を非表示にする場合があるので、設定しないでください。

* 構造コンポー **[!UICONTROL Background image]** ネントの内容のを設定します。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >一部の電子メールプログラムは、背景画像をサポートしていません。 イメージが表示されない場合は、適切な予備の背景色を選択してください。

* 列レベルで背景色を設定します。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >これは最も一般的な使用例です。 Adobeでは、Eメールコンテンツ全体を編集する際の柔軟性を高めるため、列レベルで背景色を設定することをお勧めします。

   また、列レベルで背景イメージを設定することもできますが、ほとんど使用されません。

#### 例：垂直方向の配置とパディングの調整 {#example--adjusting-vertical-alignment-and-padding}

3つの柱で構成される構造コンポーネント内の余白と垂直方向の位置合わせを調整する場合。 これを行うには、次の手順に従います。

1. 電子メールで構造コンポーネントを直接選択するか、左側のパレットから使用可能な構造ツリーを使用 **します**。
1. コンテキスト **ツールバーで**、をク **[!UICONTROL Select a column]** リックして、編集するものを選択します。 構造ツリーから選択することもできます。

   ![](assets/des_selecting_column.png)

   その列の編集可能なパラメータが右側のペイン **[!UICONTROL Settings]** に表示されます。

1. で、を **[!UICONTROL Vertical alignment]**&#x200B;選択しま **[!UICONTROL Up]**&#x200B;す。

   ![](assets/des_vertical_alignment.png)

   列の上にコンテンツコンポーネントが表示されます。

1. の下で、 **[!UICONTROL Padding]**&#x200B;列の内側に上余白を定義します。 ロックアイコンをクリックして、下のパディングとの同期を解除します。

   その列の左右の余白を定義します。

   ![](assets/des_adjusting_padding.png)

1. 同様に、他の列の位置合わせとパディングを調整します。

   ![](assets/des_adjusting_columns.png)

1. 変更を保存します。

### インラインスタイル属性の追加 {#adding-inline-styling-attributes}

電子メールデザイナのインタフェースで、要素を選択し、その設定をサイド·パネルに表示すると、その特定の要素のインライン属性とその値をカスタマイズできます。

1. コンテンツ内の要素を選択します。
1. サイドパネルで、設定を探し **[!UICONTROL Styles Inline]** ます。

   ![](assets/email_designer_inlineattributes.png)

1. 既存の属性の値を変更するか、[ **+]ボタンを使用して新しい属性を追加** します。 CSS準拠の属性と値を追加できます。

次に、選択した要素にスタイルが適用されます。 子要素に特定のスタイル属性が定義されていない場合、親要素のスタイルが継承されます。

## モバイルビューに切り替え中 {#switching-to-mobile-view}

モバイルディスプレイのすべてのスタイルオプションを個別に編集することで、電子メールの応答性の高いデザインを微調整できます。 たとえば、余白やパディングを調整したり、フォントサイズを小さくしたり、ボタンを変更したり、メールのモバイルバージョンに固有の背景色を適用したりできます。

すべてのスタイルオプションは、モバイルビューで使用できます。 電子メールデザイナのスタイル設定は、「電子メールスタイルの編集」セ [クションに表示され](../../designing/using/styles.md) ます。

1. 電子メールを作成し、コンテンツの編集を開始します。 詳細については、「最初から電子メ [ールコンテンツをデザインする」を参照してくださ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)い。
1. 専用のモバイルビューにアクセスするには、ボタンを選択 **[!UICONTROL Switch to mobile view]** します。

   ![](assets/email_designer_mobile_view_switch.png)

   電子メールのモバイルバージョンが表示されます。 このビューには、デスクトップビューで定義されたすべてのコンポーネントとスタイルが含まれます。

1. 背景色、位置合わせ、余白、余白、フォントファミリ、文字色など、すべてのスタイル設定を個別に編集します。

   ![](assets/email_designer_mobile_view.png)

1. モバイルビューでスタイル設定を編集する場合、変更はモバイル表示にのみ適用されます。

   たとえば、画像のサイズを小さくし、緑の背景を追加し、モバイルビューでパディングを変更します。

   ![](assets/email_designer_mobile_view_change.png)

1. モバイルデバイスに表示されている場合は、コンポーネントを非表示にできます。 これを行うには、からを **[!UICONTROL Show only on desktop devices]** 選択しま **[!UICONTROL Display options]**す。
また、このコンポーネントをデスクトップデバイスで非表示にすることもできます。つまり、このコンポーネントはモバイルデバイスにのみ表示されます。 これを行うには、を選択しま **[!UICONTROL Show only on mobile devices]**す。
たとえば、このオプションを使用すると、モバイルデバイスに特定のイメージを表示し、デスクトップデバイスに別のイメージを表示できます。
このオプションは、モバイルビューまたはデスクトップビューから設定できます。

   ![](assets/email_designer_mobile_hide.png)

1. 標準のデスクトップ **[!UICONTROL Switch to mobile view]** ビューに戻るには、ボタンを再度クリックします。 変更したスタイルは反映されません。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一の例外は、設定で **[!UICONTROL Style inline]** す。 スタイルのインライン設定の変更は、標準のデスクトップビューにも適用されます。

1. テキストの編集、新しいイメージのアップロード、新しいコンポーネントの追加など、電子メールの構造や内容に対するその他の変更。 が標準ビューにも適用されます。

   たとえば、モバイルビューに切り替え、テキストを編集し、イメージを置き換えます。

   ![](assets/email_designer_mobile_view_change_content.png)

   標準のデスクトップ **[!UICONTROL Switch to mobile view]** ビューに戻るには、ボタンを再度クリックします。 変更が反映されます。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. モバイルビューでスタイルを削除すると、デスクトップモードで適用されたスタイルに戻ります。

   たとえば、モバイルビューでは、ボタンに緑の背景色を適用します。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. デスクトップ表示に切り替え、同じボタンにグレーの背景を適用します。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. もう一度モバイルビューに切り替え、設定を無効に **[!UICONTROL Background color]** します。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   デスクトップビューで定義された背景色が適用されました。灰色に変わる（空白ではない）。

   唯一の例外は設定で **[!UICONTROL Border color]** す。 モバイルビューで無効にすると、デスクトップビューで境界線の色が定義されていても、境界線は適用されなくなります。

>[!NOTE]
>
>モバイルビューはフラグメントでは使用で [きません](../../designing/using/using-reusable-content.md#about-fragments)。
