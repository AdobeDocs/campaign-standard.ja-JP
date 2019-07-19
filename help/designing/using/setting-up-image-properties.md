---
title: 画像プロパティの設定
seo-title: 画像プロパティの設定
description: 画像プロパティの設定
seo-description: コンテンツに含まれる画像のプロパティを管理する方法を参照してください。
page-status-flag: 常にアクティブ化されていない
uuid: 1a439105- d9aa-4b30- a00d- bcf731a04e08
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: using- images
discoiquuid: 80c9c1a5-6050-443d-810a-6bb755d39dca
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Setting up image properties{#setting-up-image-properties}

画像を含むブロックを選択すると、パレットで次のプロパティが提供されます。

* **パーソナライゼーション** を有効にすると、画像ソースをカスタマイズできます。See [Personalizing an image source](../../designing/using/personalizing-an-image-source.md).
* **画像タイトル** を使用すると、画像のタイトルを定義できます。
* **Altテキスト** （電子メール）または **キャプション** （ランディングページ）では、画像にリンクされているキャプションを定義できます（ **alt** HTML属性に対応）。
* When editing an email, **Style** lets you specify the image size, background, and border.
* When editing a landing page, **Dimensions** lets you specify the image size in pixels.

The editor allows you to work with **all image types** whose formats are compatible with browsers. To be compatible with the editor, the **"Flash" type animations** have to be inserted in an HTML page as follows:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

