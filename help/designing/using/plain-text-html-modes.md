---
title: プレーンテキスト、HTMLおよびモバイル電子メール形式の編集
description: プレーンテキストモードとHTMLモードの確認
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e2ea8020c82f578b2cf8c00fa7b9f55b6ce2edd

---


# プレーンテキスト、HTMLおよびモバイル電子メール形式の編集 {#plain-text-and-html-modes}

電子メールデザイナーを使用すると、電子メールの複数のレンダリングを編集できます。 電子メールのテキストバージョンを生成し、電子メールのHTMLソースを編集し、モバイルビュー用の電子メールをデザインできます。

## 電子メールのテキストバージョンの生成 {#generating-a-text-version-of-the-email}

デフォルトでは、電子メ **[!UICONTROL Plain text]** ールのバージョンは自動的に生成され、バージョンと同期さ **[!UICONTROL Edit]** れます。

HTMLバージョンに追加されたパーソナライゼーションフィールドとコンテンツブロックもプレーンテキストバージョンと同期されます。

>[!NOTE]
>
>プレーンテキストバージョンでコンテンツブロックを使用する場合は、HTMLコードが含まれていないことを確認します。

HTMLバージョンとは異なるプレーンテキストバージョンを使用するには、電子メールの表示から切り替えボタンをクリックし **[!UICONTROL Sync with HTML]** て、この同期を無 **[!UICONTROL Plain text]** 効にすることができます。

![](assets/email_designer_textversion.png)

その後、必要に応じてプレーンテキストバージョンを編集できます。

>[!NOTE]
>
>同期が無効な間に **[!UICONTROL Plain text]** バージョンを編集する場合、次回このオプションを有効にすると、プレーンテキストバージョンで行ったすべての変更が **[!UICONTROL Sync with HTML]** HTMLバージョンに置き換えられます。 ビューで行った変 **[!UICONTROL Plain text]** 更をビューに反映でき **[!UICONTROL HTML]** ません。

## HTMLでの電子メールコンテンツソースの編集 {#editing-an-email-content-source-in-html}

最も上級のユーザーおよびデバッグの場合は、電子メールコンテンツをHTMLで直接表示および編集できます。

電子メールのHTMLバージョンを編集するには、次の2つの方法があります。

* /を選 **[!UICONTROL Edit]** 択し **[!UICONTROL HTML]** て、電子メール全体のHTMLバージョンを開きます。

   ![](assets/email_designer_html1.png)

* WYSIWYGインターフェイスで、要素を選択し、アイコンをクリック **[!UICONTROL Source code]** します。

   選択した要素のソースのみが表示されます。 選択した要素がコンテンツコンポーネントの場合は、ソースコードを編 **[!UICONTROL HTML]** 集できます。 その他のコンポーネントは読み取り専用モードですが、電子メールの完全なHTMLバージョンでは編集できます。

   ![](assets/email_designer_html2.png)

HTMLをコードに変更すると、電子メールの応答性が損なわれる可能性があります。 ボタンを使用してテストを行ってく **[!UICONTROL Preview]** ださい。 詳しくは、メッ [セージのプレビューを参照してくださ](../../sending/using/previewing-messages.md)い。

## モバイルレンダリング用の電子メールのデザイン {#switching-to-mobile-view}

モバイルディスプレイ用のすべてのスタイルオプションを個別に編集することで、電子メールのレスポンシブデザインを微調整できます。 例えば、余白とパディングを調整したり、小さいフォントサイズまたは大きいフォントサイズを使用したり、ボタンを変更したり、電子メールのモバイルバージョンに固有の異なる背景色を適用したりできます。

モバイルビューでは、すべてのスタイルオプションを使用できます。 電子メールデザイナーのスタイル設定は、このページで事前に表示されています。

1. 電子メールを作成し、コンテンツの編集を開始します。 詳しくは、「新規での電子メール [コンテンツのデザイン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 専用のモバイルビューにアクセスするには、ボタンを選択 **[!UICONTROL Switch to mobile view]** します。

   ![](assets/email_designer_mobile_view_switch.png)

   電子メールのモバイルバージョンが表示されます。 デスクトップビューで定義されたすべてのコンポーネントとスタイルが含まれます。

1. 背景色、配置、パディング、マージン、フォントファミリー、テキストカラーなど、すべてのスタイル設定を個別に編集します。

   ![](assets/email_designer_mobile_view.png)

1. モバイルビューでスタイル設定を編集する場合、変更はモバイルディスプレイにのみ適用されます。

   例えば、画像のサイズを小さくし、緑の背景を追加して、モバイルビューでパディングを変更します。

   ![](assets/email_designer_mobile_view_change.png)

1. モバイルデバイスで表示する際にコンポーネントを非表示にすることができます。 これを行うには、からを **[!UICONTROL Show only on desktop devices]** 選択しま **[!UICONTROL Display options]**&#x200B;す。

   また、デスクトップデバイスでこのコンポーネントを非表示にすることもできます。つまり、このコンポーネントはモバイルデバイスでのみ表示されます。 これを行うには、を選択しま **[!UICONTROL Show only on mobile devices]**&#x200B;す。

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
