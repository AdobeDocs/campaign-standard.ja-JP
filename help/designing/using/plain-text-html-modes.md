---
title: プレーンテキストモードとHTMLモード
seo-title: プレーンテキストモードとHTMLモード
description: プレーンテキストモードとHTMLモード
seo-description: プレーンテキストモードとHTMLモードの検出
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
source-git-commit: 2045c69398902a8e942e20c70287d7f3e9570837

---


# プレーンテキストモードとHTMLモード {#plain-text-and-html-modes}

## 電子メールのテキストバージョンの生成 {#generating-a-text-version-of-the-email}

既定では、電子メ **[!UICONTROL Plain text]** ールのバージョンは自動的に生成され、バージョンと同期さ **[!UICONTROL Edit]** れます。

また、HTMLバージョンに追加されたパーソナライズ·フィールドやコンテンツ·ブロックも、プレーン·テキスト·バージョンと同期されます。

>[!NOTE]
>
>プレーンテキストバージョンのコンテンツブロックを使用するには、HTMLコードが含まれていないことを確認します。

HTMLバージョンとは異なるプレーンテキストバージョンを使用する場合は、電子メールのビューから切り替えをクリッ **[!UICONTROL Sync with HTML]** クして、この同期を **[!UICONTROL Plain text]** 無効にすることができます。

![](assets/email_designer_textversion.png)

その後、必要に応じてプレーンテキストバージョンを編集できます。

>[!NOTE]
>
>同期が無効になっ **[!UICONTROL Plain text]****[!UICONTROL Sync with HTML]** ている間にバージョンを編集する場合、次にこのオプションを有効にしたときに、プレーンテキストバージョンで行った変更はすべてHTMLバージョンに置き換えられます。 ビューで行った変 **[!UICONTROL Plain text]** 更は、ビューには反映され **[!UICONTROL HTML]** ません。

## HTMLでの電子メールコンテンツソースの編集 {#editing-an-email-content-source-in-html}

最も高度なユーザーとデバッグを行う場合は、電子メールの内容をHTMLで直接表示および編集できます。

電子メールのHTMLバージョンを編集するには、次の2つの方法があります。

* 「&gt;」を選 **[!UICONTROL Edit]** 択し **[!UICONTROL HTML]** て、電子メール全体のHTMLバージョンを開きます。

   ![](assets/email_designer_html1.png)

* WYSIWYGインタフェースから要素を選択し、アイコンをクリック **[!UICONTROL Source code]** します。

   選択した要素のソースのみが表示されます。 選択した要素がコンテンツコンポーネントの場合は、ソースコードを編 **[!UICONTROL HTML]** 集できます。 その他のコンポーネントは読み取り専用モードですが、電子メールの完全なHTMLバージョンで編集できます。

   ![](assets/email_designer_html2.png)

コードをHTMLに変更すると、電子メールの応答性が失われる可能性があります。 ボタンを使って必ずテストしてく **[!UICONTROL Preview]** ださい。 メッセージのプ [レビューを参照してくださ](../../sending/using/previewing-messages.md)い。
