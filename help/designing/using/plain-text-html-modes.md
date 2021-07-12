---
solution: Campaign Standard
product: campaign
title: プレーンテキスト、HTMLおよびモバイルEメール形式の編集
description: プレーンテキストとHTMLモードの確認
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Eメールデザイン
role: User
level: Intermediate
exl-id: 760c3c30-c899-4cf4-ba59-fb2fade9fc5e
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---

# プレーンテキスト、HTMLおよびモバイルEメール形式の編集 {#plain-text-and-html-modes}

Eメールデザイナーを使用すると、Eメールの複数のレンダリングを編集できます。 Eメールのテキストバージョンを生成し、EメールのHTMLソースを編集し、モバイル表示用にEメールをデザインできます。

## Eメールのテキストバージョンの生成 {#generating-a-text-version-of-the-email}

デフォルトでは、Eメールの&#x200B;**[!UICONTROL Plain text]**&#x200B;バージョンが自動的に生成され、**[!UICONTROL Edit]**&#x200B;バージョンと同期されます。

HTMLバージョンに追加されたパーソナライゼーションフィールドとコンテンツブロックも、プレーンテキストバージョンと同期されます。

>[!NOTE]
>
>プレーンテキストバージョンのコンテンツブロックを使用するには、HTMLコードが含まれていないことを確認します。

HTMLバージョンとは異なるプレーンテキストバージョンを使用するには、電子メールの&#x200B;**[!UICONTROL Plain text]**&#x200B;ビューの&#x200B;**[!UICONTROL Sync with HTML]**&#x200B;スイッチをクリックして、この同期を無効にします。

![](assets/email_designer_textversion.png)

その後、必要に応じてプレーンテキストバージョンを編集できます。

>[!NOTE]
>
>同期が無効な状態で&#x200B;**[!UICONTROL Plain text]**&#x200B;バージョンを編集する場合、次に&#x200B;**[!UICONTROL Sync with HTML]**&#x200B;オプションを有効にすると、プレーンテキストバージョンで行った変更がすべてHTMLバージョンに置き換えられます。 **[!UICONTROL Plain text]**&#x200B;ビューで行った変更は、**[!UICONTROL HTML]**&#x200B;ビューには反映されません。

## HTMLでのEメールコンテンツソースの編集 {#editing-an-email-content-source-in-html}

最も上級のユーザーおよびデバッグの場合は、EメールコンテンツをHTMLで直接表示および編集できます。

EメールのHTMLバージョンを編集する方法は2つあります。

* **[!UICONTROL Edit]** > **[!UICONTROL HTML]**&#x200B;を選択して、電子メール全体のHTMLバージョンを開きます。

   ![](assets/email_designer_html1.png)

* WYSIWYGインターフェイスで、要素を選択し、「**[!UICONTROL Source code]**」アイコンをクリックします。

   選択した要素のソースのみが表示されます。 選択した要素が&#x200B;**[!UICONTROL HTML]**&#x200B;コンテンツコンポーネントの場合は、ソースコードを編集できます。 その他のコンポーネントは読み取り専用モードですが、Eメールの完全なHTMLバージョンでは引き続き編集できます。

   ![](assets/email_designer_html2.png)

HTMLのコードを変更すると、Eメールの応答性が損なわれる可能性があります。 必ず&#x200B;**[!UICONTROL Preview]**&#x200B;ボタンを使用してテストしてください。 [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。

## モバイルレンダリング用のEメールのデザイン {#switching-to-mobile-view}

モバイル表示用のすべてのスタイルオプションを個別に編集することで、Eメールのレスポンシブデザインを微調整できます。 例えば、余白とパディングの調整、より小さいまたは大きいフォントサイズの使用、ボタンの変更、またはモバイルバージョンのEメールに固有の様々な背景色の適用を行うことができます。

すべてのスタイルオプションは、モバイル表示で使用できます。 Eメールデザイナーのスタイル設定については、このページで既に説明しています。

1. Eメールを作成し、コンテンツの編集を開始します。 詳しくは、[ゼロからのEメールコンテンツのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。
1. 専用のモバイルビューにアクセスするには、「**[!UICONTROL Switch to mobile view]**」ボタンを選択します。

   ![](assets/email_designer_mobile_view_switch.png)

   Eメールのモバイルバージョンが表示されます。 デスクトップビューで定義されたすべてのコンポーネントとスタイルが含まれます。

1. 背景色、整列、パディング、マージン、フォントファミリー、テキスト色など、すべてのスタイル設定を個別に編集します。

   ![](assets/email_designer_mobile_view.png)

1. モバイル表示でスタイル設定を編集すると、変更はモバイル表示にのみ適用されます。

   例えば、画像のサイズを小さくし、緑の背景を追加して、モバイルビューでのパディングを変更します。

   ![](assets/email_designer_mobile_view_change.png)

1. モバイルデバイスで表示する際に、コンポーネントを非表示にすることができます。 これをおこなうには、**[!UICONTROL Display options]**&#x200B;から&#x200B;**[!UICONTROL Show only on desktop devices]**&#x200B;を選択します。

   また、デスクトップデバイスでこのコンポーネントを非表示にすることもできます。つまり、このコンポーネントはモバイルデバイスでのみ表示されます。 これをおこなうには、**[!UICONTROL Show only on mobile devices]**&#x200B;を選択します。

   例えば、このオプションを使用すると、モバイルデバイスで特定の画像を表示し、デスクトップデバイスで別の画像を表示できます。

   このオプションは、モバイル表示またはデスクトップ表示から設定できます。

   ![](assets/email_designer_mobile_hide.png)

1. **[!UICONTROL Switch to mobile view]**&#x200B;ボタンをもう一度クリックして、標準のデスクトップビューに戻ります。 先ほど行ったスタイルの変更は反映されません。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一の例外は&#x200B;**[!UICONTROL Style inline]**&#x200B;設定です。 スタイルのインライン設定の変更は、標準のデスクトップビューにも適用されます。

1. テキスト編集、新しい画像のアップロード、新しいコンポーネントの追加など、Eメールの構造やコンテンツに対するその他の変更。 は標準ビューにも適用されます。

   例えば、モバイル表示に切り替え、テキストを編集して画像を置き換えます。

   ![](assets/email_designer_mobile_view_change_content.png)

1. **[!UICONTROL Switch to mobile view]**&#x200B;ボタンをもう一度クリックして、標準のデスクトップビューに戻ります。 変更が反映されます。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. モバイルビューでスタイルを削除すると、デスクトップモードで適用されたスタイルに戻ります。

   例えば、モバイル表示では、ボタンに緑の背景色を適用します。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. デスクトップビューに切り替え、同じボタンにグレーの背景を適用します。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. もう一度モバイル表示に切り替え、**[!UICONTROL Background color]**&#x200B;設定を無効にします。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   デスクトップビューで定義された背景色が適用されるようになりました。灰色に変わります（空白にはなりません）。

   唯一の例外は&#x200B;**[!UICONTROL Border color]**&#x200B;設定です。 モバイル表示で無効にした場合、デスクトップ表示で境界線の色が定義されていても、境界線は適用されなくなります。

>[!NOTE]
>
>モバイルビューは[フラグメント](../../designing/using/using-reusable-content.md#about-fragments)では使用できません。
