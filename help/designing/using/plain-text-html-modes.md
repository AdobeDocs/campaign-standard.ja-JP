---
title: プレーンテキスト、HTML、モバイルの E メールフォーマットの編集
description: プレーンテキストとHTMLモードの確認
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 760c3c30-c899-4cf4-ba59-fb2fade9fc5e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 1%

---

# プレーンテキスト、HTML、モバイルの E メールフォーマットの編集 {#plain-text-and-html-modes}

メールDesignerを使用すると、メールの複数のレンダリングを編集できます。 メールのテキストバージョンの生成、メールのHTMLソースの編集、モバイルビュー用のメールのデザインを行うことができます。

## メールのテキストバージョンの生成 {#generating-a-text-version-of-the-email}

デフォルトでは、メールの **[!UICONTROL Plain text]** バージョンが自動的に生成され、**[!UICONTROL Edit]** バージョンと同期されます。

HTMLバージョンに追加されたパーソナライゼーションフィールドとコンテンツブロックも、プレーンテキストバージョンと同期されます。

>[!NOTE]
>
>プレーンテキストバージョンでコンテンツブロックを使用するには、HTMLコードが含まれていないことを確認します。

プレーンテキストのバージョンをHTMLのバージョンと異なるバージョンにするには、メールの **[!UICONTROL Plain text]** 表示で **[!UICONTROL Sync with HTML]** スイッチをクリックして、この同期を無効にします。

![](assets/email_designer_textversion.png)

その後、必要に応じてプレーンテキストバージョンを編集できます。

>[!NOTE]
>
>同期が無効な状態で **[!UICONTROL Plain text]** のバージョンを編集すると、次に **[!UICONTROL Sync with HTML]** オプションを有効にしたときに、プレーンテキストのバージョンに加えたすべての変更がHTMLのバージョンに置き換えられます。 ビューで行った変更は **[!UICONTROL Plain text]** ビューに反映さ **[!UICONTROL HTML]** ません。

## HTMLでのメールコンテンツソースの編集 {#editing-an-email-content-source-in-html}

最も高度なユーザーとデバッグの場合は、メールコンテンツをHTMLで直接表示して編集できます。

メールのHTMLバージョンを編集するには、次の 2 つの方法があります。

* **[!UICONTROL Edit]**/**[!UICONTROL HTML]** を選択して、メール全体のHTMLバージョンを開きます。

  ![](assets/email_designer_html1.png)

* WYSIWYGのインターフェイスで、要素を選択し、「**[!UICONTROL Source code]**」アイコンをクリックします。

  選択した要素のソースのみが表示されます。 選択した要素が **[!UICONTROL HTML]** コンテンツコンポーネントの場合は、ソースコードを編集できます。 その他のコンポーネントは読み取り専用モードになっていますが、メールの完全なHTML版では引き続き編集できます。

  ![](assets/email_designer_html2.png)

このコードのHTMLを変更すると、メールの応答性が損なわれる可能性があります。 必ず「**[!UICONTROL Preview]**」ボタンを使用してテストしてください。 [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。

## モバイルレンダリング用の E メールのデザイン {#switching-to-mobile-view}

モバイル表示用にすべてのスタイルオプションを個別に編集することで、メールのレスポンシブデザインを微調整できます。 例えば、余白とパディングを調整したり、フォントサイズを小さくしたり大きくしたり、ボタンを変更したり、モバイル版のメールに固有の異なる背景色を適用したりできます。

モバイル表示では、すべてのスタイルオプションを使用できます。 メールDesignerのスタイル設定については、このページを参照してください。

1. メールを作成し、コンテンツの編集を開始します。 詳しくは、[ メールコンテンツをゼロからデザイン ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) を参照してください。
1. 専用のモバイル表示にアクセスするには、「**[!UICONTROL Switch to mobile view]**」ボタンを選択します。

   ![](assets/email_designer_mobile_view_switch.png)

   メールのモバイルバージョンが表示されます。 これには、デスクトップビューで定義されたすべてのコンポーネントとスタイルが含まれています。

1. 背景色、整列、パディング、余白、フォントファミリー、テキストの色など、すべてのスタイル設定を個別に編集できます。

   ![](assets/email_designer_mobile_view.png)

1. モバイル表示でスタイル設定を編集すると、変更はモバイル表示にのみ適用されます。

   例えば、画像のサイズを小さくし、背景を緑に変更して、モバイル表示でパディングを変更します。

   ![](assets/email_designer_mobile_view_change.png)

1. モバイルデバイスで表示したときにコンポーネントを非表示にすることができます。 これを行うには、**[!UICONTROL Display options]** ールバーから「**[!UICONTROL Show only on desktop devices]**」を選択します。

   また、このコンポーネントをデスクトップデバイスで非表示にすることもできます。つまり、モバイルデバイスでのみ表示されます。 それには、「**[!UICONTROL Show only on mobile devices]**」を選択します。

   例えば、このオプションを使用すると、モバイルデバイスに特定の画像を表示し、デスクトップデバイスで別の画像を表示できます。

   このオプションは、モバイルまたはデスクトップ表示から設定できます。

   ![](assets/email_designer_mobile_hide.png)

1. [**[!UICONTROL Switch to mobile view]**] ボタンをもう一度クリックすると、標準のデスクトップ表示に戻ります。 行ったスタイルの変更は反映されません。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一の例外は **[!UICONTROL Style inline]** 設定です。 スタイル インライン設定の変更は、標準のデスクトップ ビューにも適用されます。

1. テキストの編集、新しい画像のアップロード、新しいコンポーネントの追加など、メールの構造やコンテンツへのその他の変更。 標準ビューにも適用されます。

   例えば、モバイル表示に戻り、テキストを編集して画像を置き換えます。

   ![](assets/email_designer_mobile_view_change_content.png)

1. [**[!UICONTROL Switch to mobile view]**] ボタンをもう一度クリックすると、標準のデスクトップ表示に戻ります。 変更が反映されます。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. モバイル表示でスタイルを削除すると、デスクトップモードで適用されたスタイルに戻ります。

   例えば、モバイル表示で、ボタンに緑の背景色を適用します。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. デスクトップビューに切り替え、同じボタンにグレーの背景を適用します。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. モバイル表示に再度切り替えて、**[!UICONTROL Background color]** 設定を無効にします。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   デスクトップビューで定義した背景色が適用され、グレー（空白ではない）に変わります。

   唯一の例外は **[!UICONTROL Border color]** 設定です。 モバイルビューで無効にすると、境界線のカラーがデスクトップビューで定義されている場合でも、境界線は適用されなくなります。

>[!NOTE]
>
>モバイル表示は、[ フラグメント ](../../designing/using/using-reusable-content.md#about-fragments) では使用できません。
