---
title: プレーンテキスト、HTMLおよびモバイルメール形式の編集
description: プレーンテキストとHTML モードについて説明します
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 760c3c30-c899-4cf4-ba59-fb2fade9fc5e
TQID: https://experienceleague.adobe.com/H-WFy-faNPufQFw5A-zN8c-G7rqwUuXTQ8iGN1CDk00
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: d5ef99fa-df0c-4153-bf94-105ad0724167
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 778
ht-degree: 1%

---

# プレーンテキスト、HTMLおよびモバイルメール形式の編集 {#plain-text-and-html-modes}

メールDesignerでは、メールの複数のレンダリングを編集できます。 メールのテキストバージョンを生成したり、メールのHTML ソースを編集したり、モバイルビュー用のメールをデザインしたりできます。

## メールのテキストバージョンの生成 {#generating-a-text-version-of-the-email}

デフォルトでは、メールの&#x200B;**[!UICONTROL Plain text]** バージョンが自動的に生成され、**[!UICONTROL Edit]** バージョンと同期されます。

HTML版に追加されたパーソナライゼーションフィールドとコンテンツブロックも、プレーンテキスト版と同期されます。

>[!NOTE]
>
>コンテンツブロックをプレーンテキスト版で使用するには、コンテンツブロックにHTML コードが含まれていないことを確認します。

プレーンテキスト版とHTML版を異なるバージョンにするには、メールの&#x200B;**[!UICONTROL Plain text]**&#x200B;表示から&#x200B;**[!UICONTROL Sync with HTML]** スイッチをクリックして、この同期を無効にできます。

![](assets/email_designer_textversion.png)

その後、必要に応じてプレーンテキストバージョンを編集できます。

>[!NOTE]
>
>同期が無効になっている間に&#x200B;**[!UICONTROL Plain text]** バージョンを編集すると、次回&#x200B;**[!UICONTROL Sync with HTML]** オプションを有効にすると、プレーンテキストバージョンで行ったすべての変更がHTML バージョンに置き換えられます。 **[!UICONTROL Plain text]** ビューで行われた変更は、**[!UICONTROL HTML]** ビューに反映できません。

## HTMLでのメールコンテンツソースの編集 {#editing-an-email-content-source-in-html}

最も高度なユーザーとデバッグの場合は、HTMLで電子メールコンテンツを直接表示および編集できます。

HTML版のメールを編集するには、次の2つの方法があります。

* **[!UICONTROL Edit]** > **[!UICONTROL HTML]**&#x200B;を選択して、メール全体のHTML バージョンを開きます。

  ![](assets/email_designer_html1.png)

* WYSIWYG インターフェイスから要素を選択し、**[!UICONTROL Source code]** アイコンをクリックします。

  選択した要素のソースのみが表示されます。 選択した要素が&#x200B;**[!UICONTROL HTML]** コンテンツコンポーネントの場合、ソースコードを編集できます。 その他のコンポーネントは読み取り専用モードですが、HTMLのフルバージョンのメールで編集できます。

  ![](assets/email_designer_html2.png)

HTMLのコードを変更すると、電子メールの応答性が低下する可能性があります。 必ず&#x200B;**[!UICONTROL Preview]** ボタンを使用してテストしてください。 [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。

## モバイルレンダリング用メールのデザイン {#switching-to-mobile-view}

モバイルディスプレイのすべてのスタイルオプションを個別に編集することで、メールのレスポンシブデザインを微調整できます。 例えば、余白やパディングを調整したり、フォントサイズを小さくしたり大きくしたり、ボタンを変更したり、モバイル版の電子メールに適した背景色を適用したりできます。

すべてのスタイルオプションは、モバイルビューで使用できます。 メールDesignerのスタイル設定は、このページで以前に示されています。

1. メールを作成し、コンテンツの編集を開始します。 詳しくは、[電子メールコンテンツをゼロからデザイン ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)するを参照してください。
1. 専用のモバイルビューにアクセスするには、**[!UICONTROL Switch to mobile view]** ボタンを選択します。

   ![](assets/email_designer_mobile_view_switch.png)

   メールのモバイル版が表示されます。 デスクトップビューで定義されたすべてのコンポーネントとスタイルが含まれます。

1. 背景色、整列、パディング、余白、フォントファミリー、テキストカラーなど、すべてのスタイル設定を個別に編集できます。

   ![](assets/email_designer_mobile_view.png)

1. モバイルビューでスタイル設定を編集する場合、変更はモバイルディスプレイにのみ適用されます。

   例えば、画像のサイズを小さくしたり、緑色の背景を追加したり、モバイルビューでパディングを変更したりします。

   ![](assets/email_designer_mobile_view_change.png)

1. モバイルデバイスで表示する場合は、コンポーネントを非表示にできます。 これをおこなうには、**[!UICONTROL Display options]**&#x200B;から&#x200B;**[!UICONTROL Show only on desktop devices]**&#x200B;を選択します。

   また、このコンポーネントをデスクトップデバイスで非表示にすることもできます。つまり、モバイルデバイスでのみ表示されます。 これを行うには、**[!UICONTROL Show only on mobile devices]**&#x200B;を選択します。

   例えば、このオプションを使用すると、モバイルデバイスに特定の画像を表示したり、デスクトップデバイスに別の画像を表示したりできます。

   このオプションは、モバイルビューまたはデスクトップビューから設定できます。

   ![](assets/email_designer_mobile_hide.png)

1. もう一度&#x200B;**[!UICONTROL Switch to mobile view]** ボタンをクリックして、標準のデスクトップビューに戻ります。 先ほど行ったスタイルの変更は反映されません。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一の例外は&#x200B;**[!UICONTROL Style inline]**&#x200B;設定です。 スタイルのインライン設定の変更は、標準のデスクトップビューにも適用されます。

1. テキスト編集、新しい画像のアップロード、新しいコンポーネントの追加など、メールの構造やコンテンツに対するその他の変更も、標準ビューに適用されます。

   例えば、モバイル表示に切り替え、テキストを編集して画像を置き換えます。

   ![](assets/email_designer_mobile_view_change_content.png)

1. もう一度&#x200B;**[!UICONTROL Switch to mobile view]** ボタンをクリックして、標準のデスクトップビューに戻ります。 変更が反映されます。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. モバイルビューでスタイルを削除すると、デスクトップモードで適用されたスタイルに戻ります。

   例えば、モバイルビューでは、ボタンに緑色の背景色を適用します。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. デスクトップビューに切り替え、同じボタンにグレーの背景を適用します。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. もう一度モバイルビューに切り替え、**[!UICONTROL Background color]**&#x200B;設定を無効にします。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   デスクトップビューで定義された背景色が適用されるようになりました。グレーになります（空白ではありません）。

   唯一の例外は&#x200B;**[!UICONTROL Border color]**&#x200B;設定です。 モバイルビューで無効にすると、境界線の色がデスクトップビューで定義されていても、境界線は適用されなくなります。

>[!NOTE]
>
>モバイルビューは、[ フラグメント ](../../designing/using/using-reusable-content.md#about-fragments)では利用できません。
