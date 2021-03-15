---
solution: Campaign Standard
product: campaign
title: プレーンテキスト、HTMLおよびモバイルE メールフォーマットの編集
description: プレーンテキストモードとHTMLモードの確認
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: 電子メールデザイン
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---


# プレーンテキスト、HTML、モバイルE メールフォーマットの編集{#plain-text-and-html-modes}

電子メールデザイナーでは、電子メールの複数のレンダリングを編集できます。 電子メールのテキスト版を生成したり、電子メールのHTMLソースを編集したり、モバイル表示用の電子メールをデザインしたりできます。

## 電子メールのテキスト版{#generating-a-text-version-of-the-email}の生成

デフォルトでは、電子メールの&#x200B;**[!UICONTROL Plain text]**&#x200B;バージョンが自動的に生成され、**[!UICONTROL Edit]**&#x200B;バージョンと同期されます。

また、HTMLバージョンに追加されたパーソナライゼーションフィールドやコンテンツブロックもプレーンテキストバージョンと同期されます。

>[!NOTE]
>
>プレーンテキストバージョンでコンテンツブロックを使用するには、HTMLコードが含まれていないことを確認します。

HTML表示とは異なるプレーンテキストバージョンを使用する場合は、電子メールの&#x200B;**[!UICONTROL Plain text]**&#x200B;バージョンの&#x200B;**[!UICONTROL Sync with HTML]**&#x200B;スイッチをクリックして、この同期を無効にできます。

![](assets/email_designer_textversion.png)

その後、必要に応じてプレーンテキストバージョンを編集できます。

>[!NOTE]
>
>同期が無効なときに&#x200B;**[!UICONTROL Plain text]**&#x200B;バージョンを編集する場合、次に&#x200B;**[!UICONTROL Sync with HTML]**&#x200B;オプションを有効にすると、プレーンテキストバージョンで行った変更がすべてHTMLバージョンに置き換えられます。 **[!UICONTROL Plain text]**&#x200B;表示で行われた変更は、**[!UICONTROL HTML]**&#x200B;表示に反映されません。

## HTML {#editing-an-email-content-source-in-html}での電子メールコンテンツソースの編集

最も上級のユーザーおよびデバッグ作業を行う場合は、電子メールコンテンツをHTMLで直接表示および編集できます。

電子メールのHTMLバージョンを編集するには、次の2つの方法があります。

* **[!UICONTROL Edit]**/**[!UICONTROL HTML]**&#x200B;を選択して、電子メール全体のHTMLバージョンを開きます。

   ![](assets/email_designer_html1.png)

* WYSIWYGインターフェイスで要素を選択し、**[!UICONTROL Source code]**&#x200B;アイコンをクリックします。

   選択した要素のソースのみが表示されます。 選択した要素が&#x200B;**[!UICONTROL HTML]**&#x200B;コンテンツコンポーネントの場合は、ソースコードを編集できます。 その他のコンポーネントは読み取り専用モードですが、電子メールの完全なHTMLバージョンでは編集できます。

   ![](assets/email_designer_html2.png)

HTMLコードを変更すると、電子メールの応答性が損なわれる可能性があります。 **[!UICONTROL Preview]**&#x200B;ボタンを使ってテストしてください。 [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。

## モバイルレンダリング用の電子メールのデザイン{#switching-to-mobile-view}

モバイル表示用のすべてのスタイルオプションを個別に編集することで、電子メールのレスポンシブデザインを微調整できます。 例えば、余白とパディングを調整したり、小さめまたは大きめのフォントサイズを使用したり、ボタンを変更したり、電子メールのモバイルバージョンに合わせて異なる背景色を適用したりできます。

モバイル表示では、すべてのスタイルオプションを使用できます。 電子メールデザイナーのスタイル設定は、このページで事前に表示されています。

1. コンテンツを編集する電子メールおよび開始を作成します。 詳しくは、[ゼロからの電子メールコンテンツのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。
1. 専用のモバイル表示にアクセスするには、「**[!UICONTROL Switch to mobile view]**」ボタンを選択します。

   ![](assets/email_designer_mobile_view_switch.png)

   電子メールのモバイルバージョンが表示されます。 デスクトップ表示で定義されたすべてのコンポーネントとスタイルが含まれます。

1. 背景色、配置、パディング、マージン、フォントファミリー、テキスト色など、すべてのスタイル設定を個別に編集する。

   ![](assets/email_designer_mobile_view.png)

1. モバイル表示でスタイル設定を編集する場合、変更はモバイルディスプレイにのみ適用されます。

   例えば、画像のサイズを小さくし、緑の背景を追加して、モバイル表示でパディングを変更します。

   ![](assets/email_designer_mobile_view_change.png)

1. コンポーネントをモバイルデバイスに表示するときに非表示にすることができます。 これを行うには、**[!UICONTROL Display options]**&#x200B;から&#x200B;**[!UICONTROL Show only on desktop devices]**&#x200B;を選択します。

   また、デスクトップデバイスでこのコンポーネントを非表示にすることもできます。これは、このコンポーネントがモバイルデバイスにのみ表示されることを意味します。 これを行うには、**[!UICONTROL Show only on mobile devices]**&#x200B;を選択します。

   例えば、このオプションを使用すると、モバイルデバイスに特定の画像を表示し、デスクトップデバイスに別の画像を表示できます。

   このオプションは、モバイル表示ーまたはデスクトップーから設定できます。

   ![](assets/email_designer_mobile_hide.png)

1. **[!UICONTROL Switch to mobile view]**&#x200B;ボタンをもう一度クリックして、標準のデスクトップ表示に戻ります。 先ほど変更したスタイルは反映されません。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一の例外は&#x200B;**[!UICONTROL Style inline]**&#x200B;設定です。 スタイルのインライン設定の変更は、標準のデスクトップ表示にも適用されます。

1. テキストの編集、新しい画像のアップロード、新しいコンポーネントの追加など、電子メールの構造またはコンテンツに対するその他の変更。 は、標準表示にも適用されます。

   例えば、モバイル表示に切り替え、テキストを編集して画像を置き換えます。

   ![](assets/email_designer_mobile_view_change_content.png)

1. **[!UICONTROL Switch to mobile view]**&#x200B;ボタンをもう一度クリックして、標準のデスクトップ表示に戻ります。 変更が反映されます。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. モバイル表示でスタイルを削除すると、デスクトップモードで適用されたスタイルに戻ります。

   例えば、モバイル表示では、ボタンに緑の背景色を適用します。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. デスクトップ表示に切り替え、同じボタンにグレーの背景を適用します。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. もう一度モバイル表示に切り替え、**[!UICONTROL Background color]**&#x200B;設定を無効にします。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   デスクトップ表示で定義されている背景色が適用されるようになりました。灰色に変わります（空白ではありません）。

   唯一の例外は&#x200B;**[!UICONTROL Border color]**&#x200B;設定です。 モバイル表示で無効にした場合、デスクトップ表示で境界線の色が定義されていても、境界線が適用されなくなりました。

>[!NOTE]
>
>モバイル表示は、[fragments](../../designing/using/using-reusable-content.md#about-fragments)では使用できません。
