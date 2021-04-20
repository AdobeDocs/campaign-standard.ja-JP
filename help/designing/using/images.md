---
solution: Campaign Standard
product: campaign
title: 画像の操作
description: 電子メールデザイナーで電子メールの画像を管理する方法を確認します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 7%

---


# 画像の操作{#images}

## 画像の挿入{#inserting-images}

電子メールやランディングページに画像を挿入できます。

設定に応じて、次のタイプの画像を使用できます。

* ローカル画像
* Adobe Experience Cloudから共有された画像 — [キャンペーンとアセットのコアサービスの使用](../../integrating/using/working-with-campaign-and-assets-core-service.md) /アセットオンデマンドを参照
* Adobe Targetの動的画像 — [キャンペーンとターゲットの操作](../../integrating/using/about-campaign-target-integration.md)を参照

>[!CAUTION]
>
>電子メールのHTMLバージョンを編集して画像を直接追加する場合は、HTMLページの&lt;script>タグ&#x200B;**で**&#x200B;外部ファイルを呼び出してはいけません。 これらのファイルは、Adobe Campaign サーバーにインポートされません。

### 電子メールに画像を挿入{#inserting-images-in-an-email}

1. 構造追加コンポーネント。 詳しくは、[メール構造の編集](../../designing/using/designing-from-scratch.md#defining-the-email-structure)を参照してください。
1. この構造コンポーネント内に、**[!UICONTROL Image]**&#x200B;コンテンツコンポーネントを追加します。

   ![](assets/des_insert_images_1.png)

1. 「**[!UICONTROL Browse]**」をクリックします。画像をドラッグ&amp;ドロップするか、クリックしてコンピューターからファイルを選択します。

   ![](assets/des_insert_images_2.png)

1. 先ほど追加したコンテンツコンポーネントを選択します。
1. 画像のプロパティを確認し、必要に応じて調整します。

   ![](assets/des_insert_images_3.png)

## 画像プロパティの設定{#setting-up-image-properties}

イメージを含むブロックを選択すると、パレットに次のプロパティが表示されます。

* **「** パーソナライゼーションを有効にする」を選択すると、画像ソースをカスタマイズできます。[画像ソースの個人設定](../../designing/using/personalization.md#personalizing-an-image-source)を参照してください。
* **画像** タイトルは、画像のタイトルを定義します。
* **代替テキスト** （電子メール）または **キャプション** (ランディングページ)を使用すると、画像にリンクされたキャプションを定義できます( **** altHTML属性に対応)。
* 電子メールを編集する際に、**スタイル**&#x200B;を使用して、画像のサイズ、背景、境界線を指定できます。
* ランディングページの編集時に、**Dimension**&#x200B;で画像サイズをピクセル単位で指定できます。

エディタでは、ブラウザと互換性のある形式を持つ&#x200B;**すべてのイメージタイプ**&#x200B;を扱うことができます。 エディターと互換性を持たせるために、**&quot;Flash&quot;タイプのアニメーション**&#x200B;は、次のようにHTMLページに挿入する必要があります。

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->