---
title: 従来のエディターによる E メールから E メールDesignerへの変換
description: 従来のエディターのメールで作成されたメールを使用してメールDesignerに送信する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 8%

---

# 従来のエディターのメールコンテンツの変換 {#converting-an-html-content}

メールDesignerの使用を開始し、従来のエディターで作成したメールエディターから、再利用可能なテンプレートとフラグメントをHTMLします。

このユースケースを使用すると、HTMLのメールを使用し、メールDesignerでHTMLのコンポーネントに分割することで、メールDesignerテンプレートを作成できます。

>[!NOTE]
>
>互換モードと同様に、HTMLコンポーネントも編集できますが、編集できるオプションは限られています。つまり、インプレース編集のみを実行できます。

>[!IMPORTANT]
>
>この節は、HTMLコードに精通した上級ユーザーを対象としています。

## メールコンテンツの準備

1. HTMLメールを選択します。
1. HTMLメールを分割するセクションを特定します。
1. HTMLから様々なブロックを切り取ります。

## メール構造の作成

1. **[!UICONTROL Email Designer]** を開いて、空のメールコンテンツを作成します。
1. 背景色や幅など、本文レベルの属性を設定します。 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。
1. セクションと同じ数の構造コンポーネントを追加します。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。

## HTMLコンテンツを追加

1. 各構造コンポーネントにHTMLコンポーネントを追加します。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. HTMLした内容を、すべてのコンポーネントにコピー&amp;ペーストします。

## メールのスタイルの管理 {#manage-the-style-of-your-email}

1. **[!UICONTROL Mobile view]** に切り替えます。 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

1. これを修正するには、ソースコードモードに切り替えて、「スタイル」セクションをコピーして新しい「スタイル」セクションに貼り付けます。 例：

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >この後に、必ず別のカスタムスタイルタグでスタイルを追加してください。
   >
   >メールDesignerで生成された CSS を変更しないでください。
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. モバイルビューに戻ってコンテンツが正しく表示されていることを確認し、変更を保存します。

## ユースケース

従来のエディターで作成されたこのメールを、**[!UICONTROL Email Designer]** テンプレートに変換してみましょう。

### メールのセクションを識別

このメールでは、11 のセクションを特定できます。

![](assets/html-dce-view-mail.png)

HTMLのどのセクションかを特定するには、要素を選択します。

![](assets/breadcrumbs.png)

メールのHTMLバージョンを確認するには、「**[!UICONTROL Show source]**」をクリックします。

### メールテンプレートとその構造の作成

1. ドラッグ&amp;ドロップ **[!UICONTROL Structure components]**、メールのレイアウトを反映させます。

1. 必要なだけ繰り返します。 11 個の構造コンポーネントを作成する必要があります。

   ![](assets/structure-components-migration.png)

### HTMLコンテンツコンポーネントの挿入

1. 各 **[!UICONTROL Structure component]** に **[!UICONTROL HTML component]** を挿入します。

   ![](assets/html-components.png)

1. 各セクションで、「**[!UICONTROL Show source code]**」をクリックします。

   ![](assets/show-source-code.png)

1. HTMLセクションを挿入します。

1. 「**[!UICONTROL Save]**」をクリックします。

メールのレンダリングを確認できるようになりました。

![](assets/migrated-email-result.png)

### モバイルビューに合わせたスタイルの管理

1. CSS 要素を挿入して、メールがモバイルビューに適していることを確認します。

1. ソースコードに切り替え、スタイルセクションをコピーして新しいスタイルセクションに貼り付けます。

詳しくは、[ メールのスタイルの管理 ](#manage-the-style-of-your-email) を参照してください。

従来のメールが、メールDesignerで使用できるようになりました。
