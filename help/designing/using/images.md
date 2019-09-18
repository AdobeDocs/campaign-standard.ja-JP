---
title: 電子メールのイメージを管理する
seo-title: 電子メールのイメージを管理する
description: 電子メールのイメージを管理する
seo-description: 電子メールデザイナを使用して電子メール内のイメージを管理する方法を説明します。
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
source-git-commit: a7de545e9eec675444245576cddc6eaf8dce05f4

---


# イメージ {#images}

## イメージの挿入{#inserting-images}

電子メールやランディング·ページにイメージを挿入できます。

構成に応じて、次の種類のイメージを使用できます。

* ローカルイメージ
* Adobe Experience Cloudで共有された画像- 「キャンペーンとアセット [のコアサービス](../../integrating/using/working-with-campaign-and-assets-core-service.md) /アセットのオンデマンド操作」を参照
* Adobe Targetのダイナミックイメージ- 「キャンペーンとターゲ [ットの操作」を参照](../../integrating/using/about-campaign-target-integration.md)

有効にした場合、Adobe Creative SDKを使用してイメージを変更できます。 Adobe Creative SDK [を使用した画像の変更を参照してください](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)。

>[!CAUTION]
>
>電子メールのHTMLバージョンを編集してイメージを直接追加する場合は、HTMLページの&lt;script&gt;タグに外部フ **ァイルを呼び出してはいけません** 。 これらのファイルは、Adobe Campaignサーバーにインポートされません。

### 電子メールへのイメージの挿入 {#inserting-images-in-an-email}

1. 構造コンポーネントを追加します。 詳細については、「電子メール構 [造の編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. この構造コンポーネント内に、コンテンツコンポーネ **[!UICONTROL Image]** ントを追加します。

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. イメージをドラッグアンドドロップするか、コンピュータからファイルを選択します。

   ![](assets/des_insert_images_2.png)

1. 追加したコンテンツコンポーネントを選択します。
1. イメージのプロパティを確認し、必要に応じて調整します。

   ![](assets/des_insert_images_3.png)

## イメージのプロパティの設定{#setting-up-image-properties}

イメージを含むブロックを選択すると、次のプロパティがパレットに表示されます。

* **[個人用設定を有効にする** ]では、イメージソースをカスタマイズできます。 詳しくは、 [イメージソースの個人用設定を参照してくださ](../../designing/using/personalization.md#personalizing-an-image-source)い。
* **[イメージタイトル** ]では、イメージのタイトルを定義できます。
* **Altテキスト** (email)または **Caption** （ランディング·ページ）を使用して、イメージにリンクされたキャプションを定義できます( **alt** HTML属性に対応)。
* 電子メールを編集する場合は、 **Style** （スタイル）を使用して、イメージのサイズ、背景、および枠線を指定できます。
* ランディング·ページを編集する場合は、 **「Dimensions** 」でイメージ·サイズをピクセル単位で指定できます。

エディタを使用すると、ブラウザと互換性のあ **る形式のすべてのイメージ** ·タイプを操作できます。 エディタと互換性を持たせるに **は、「Flash」タイプのアニメーションを** HTMLページに次のように挿入する必要があります。

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

## Adobe Creative SDKを使用したイメージの変更{#modifying-images-with-the-adobe-creative-sdk}

Adobe Creative SDKを搭載した一連の機能を使用して、電子メールやランディングページを編集する際に、コンテンツエディタでイメージを直接拡張できます。

イメージエディタは、イメージの編集、エフェクトやフレームの適用、オリジナルの高品質なステッカー、美しいオーバーレイ、ティルトシフトやカラースプラッシュ、プロレベル調整などの楽しい機能を提供する、フル機能のイメージ編集UIコンポーネントです。

Adobe Creative SDKを使用してイメージを変更するには：

1. イメージを選択します。
1. ツールバーで、[クリエイティブクラウド]アイコンをクリックします。

   ![](assets/des_creative_sdk_icon.png)

1. イメージを修正するために、ウィンドウの上部にあるアイコンを使用して使用するツールを選択します。

   ![](assets/email_designer_ccsdktoolbar.png)

1. 変更が終 **[!UICONTROL Save]** 了したら、をクリックします。 更新されたイメージはAdobe Campaignサーバーに保存され、使用する準備が整います。

>[!NOTE]
イメージエディタで提供されるツールはカスタマイズできません。
