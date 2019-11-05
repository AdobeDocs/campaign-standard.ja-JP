---
title: プレーンテキストと HTML モード
description: プレーンテキストモードとHTMLモードの確認
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


# プレーンテキストと HTML モード {#plain-text-and-html-modes}

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
