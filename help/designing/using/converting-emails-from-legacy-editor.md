---
title: 従来のエディターの E メールから E メールデザイナーへの変換
description: 従来のエディターの E メールで作成した E メールを E メールデザイナーに使用する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 8%

---

# レガシーエディターの E メールコンテンツの変換 {#converting-an-html-content}

E メールデザイナーの使用を開始し、レガシーエディターで作成した E メールHTMLから、再利用可能なテンプレートとフラグメントを構築します。

この使用例では、HTMLE メールを使用し、E メールデザイナーでHTMLコンポーネントに分割することで、E メールデザイナーテンプレートを作成できます。

>[!NOTE]
>
>互換性モードと同様に、HTMLコンポーネントは、次の制限付きオプションで編集できます。インプレース編集のみ実行できます。

>[!IMPORTANT]
>
>この節は、HTMLコードに詳しい上級ユーザー向けです。

## E メールコンテンツの準備

1. HTMLE メールを選択
1. HTMLE メールを分割するセクションを特定します。
1. HTMLから異なるブロックを切り出します。

## 電子メール構造を作成する

1. を開きます。 **[!UICONTROL Email Designer]**  空の e メールコンテンツを作成します。
1. ボディレベルの属性を設定します。背景色、幅など 詳しくは、[メールスタイルの編集](../../designing/using/styles.md)を参照してください。
1. 構造コンポーネントをセクションと同じ数だけ追加します。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。

## HTMLコンテンツを追加

1. 各構造コンポーネントにHTMLコンポーネントを追加します。 詳しくは、[フラグメントとコンポーネントの追加](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. すべてのコンポーネントにHTMLをコピー&amp;ペーストします。

## E メールのスタイルを管理 {#manage-the-style-of-your-email}

1. 切り替え先 **[!UICONTROL Mobile view]**. 詳しくは、[この節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)を参照してください。

1. これを修正するには、ソースコードモードに切り替えて、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。 例：

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
   >別のカスタムスタイルタグで、この後にスタイルを必ず追加してください。
   >
   >E メールデザイナーで生成された CSS を変更しないでください。
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. モバイル表示に戻って、コンテンツが正しく表示されていることを確認し、変更を保存します。

## 使用例

レガシーエディターで作成したこのメールを、 **[!UICONTROL Email Designer]** テンプレート。

### 電子メールのセクションを特定する

この電子メールで 11 のセクションを特定できます。

![](assets/html-dce-view-mail.png)

要素のどのセクションかを識別するには、HTMLを選択します。

![](assets/breadcrumbs.png)

E メールのHTMLバージョンを確認するには、 **[!UICONTROL Show source]**.

### E メールテンプレートとその構造を作成します。

1. ドラッグ&amp;ドロップ **[!UICONTROL Structure components]**  メールのレイアウトを反映します。

1. 必要な回数だけ繰り返します。 11 個の構造コンポーネントを作成する必要があります。

   ![](assets/structure-components-migration.png)

### HTMLコンテンツコンポーネントの挿入

1. 挿入 **[!UICONTROL HTML component]**  各 **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. 各セクションで、 **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. 「HTML」セクションを挿入します。

1. 「**[!UICONTROL Save]**」をクリックします。

これで、E メールのレンダリングを確認できます。

![](assets/migrated-email-result.png)

### モバイルビューに合わせたスタイルの管理

1. CSS 要素を挿入して、電子メールがモバイル表示に適していることを確認します。

1. ソースコードに切り替え、スタイルセクションを新しいスタイルセクションにコピー&amp;ペーストします。

詳しくは、 [E メールのスタイルを管理](#manage-the-style-of-your-email).

従来の E メールを E メールデザイナーで使用できるようになりました。
