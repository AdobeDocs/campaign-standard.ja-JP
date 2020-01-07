---
title: 画像の操作
description: 電子メールデザイナーで電子メールの画像を管理する方法を確認します。
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
source-git-commit: 7e300de836a74372e411b5b1d584851fac77aafe

---


# 画像の操作 {#images}

## 画像の挿入{#inserting-images}

電子メールおよびランディングページに画像を挿入できます。

設定に応じて、次のタイプの画像を使用できます。

* ローカル画像
* Adobe Experience cloudから共有される画像 — キャンペーンとアセ [ットのコアサービス](../../integrating/using/working-with-campaign-and-assets-core-service.md) /アセットオンデマンドの操作を参照
* Adobe targetの動的な画像 — 「CampaignとTargetの [操作」を参照](../../integrating/using/about-campaign-target-integration.md)

有効にした場合、Adobe Creative SDKを使用して画像を変更できます。 詳しく [は、Adobe Creative SDKを使用した画像の変更を参照してください](#modifying-images-with-the-adobe-creative-sdk)。

>[!CAUTION]
>
>電子メールのHTMLバージョンを編集して画像を直接追加する場合は、HTMLページの&lt;script>タグで外部ファ **イルを呼び出しては** なりません。 これらのファイルは、Adobe Campaign サーバーにインポートされません。

### 電子メールへの画像の挿入 {#inserting-images-in-an-email}

1. 構造コンポーネントを追加します。 詳しくは、「電子メール構造の [編集」を参照してください](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. この構造コンポーネント内に、コンテンツコンポーネ **[!UICONTROL Image]**ントを追加します。

   ![](assets/des_insert_images_1.png)

1. クリック **[!UICONTROL Browse]**. 画像をドラッグ&amp;ドロップするか、クリックしてコンピューターからファイルを選択します。

   ![](assets/des_insert_images_2.png)

1. 先ほど追加したコンテンツコンポーネントを選択します。
1. 画像のプロパティを確認し、必要に応じて調整します。

   ![](assets/des_insert_images_3.png)

## 画像プロパティの設定{#setting-up-image-properties}

イメージを含むブロックを選択すると、パレットに次のプロパティが表示されます。

* **「パーソナライゼーション** 」を使用すると、画像ソースをカスタマイズできます。 詳しくは、 [画像ソースのパーソナライズを参照してくださ](../../designing/using/personalization.md#personalizing-an-image-source)い。
* **「画像のタイトル** 」では、画像のタイトルを定義できます。
* **代替テキスト** （電子メール）または **Caption** （ランディングページ）では、画像にリンクされたキャプションを定義できます( **alt** HTML属性に対応)。
* 電子メールの編集時に、 **Style** （スタイル）を使用して、画像のサイズ、背景および境界線を指定できます。
* ランディングページを編集する場合、「 **Dimensions** 」では画像サイズをピクセル単位で指定できます。

エディターでは、ブラウザーと互換性のある形 **式を持つすべての** 、画像タイプを操作できます。 エディターとの互換性を維持するには、次のよ **うに** 「Flash」タイプのアニメーションをHTMLページに挿入する必要があります。

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

## Adobe Creative SDKを使用した画像の変更{#modifying-images-with-the-adobe-creative-sdk}

電子メールやランディングページを編集する際に、Adobe Creative SDKを利用した画像編集や、すべての機能セットを使用して、コンテンツエディターで直接画像を拡張できます。

画像エディターには、画像の編集、効果やフレームの適用、オリジナルの高品質ステッカー、美しいオーバーレイ、チルトシフトやカラースプラッシュなどの楽しい機能、プロレベルの調整などを可能にする、強力なフル機能の画像編集UIコンポーネントが用意されています。

Adobe Creative SDKで画像を変更するには：

1. 画像を選択します。
1. ツールバーで、Creative cloudアイコンをクリックします。

   ![](assets/des_creative_sdk_icon.png)

1. ウィンドウ上部のアイコンを使用して、画像を変更するツールを選択します。

   ![](assets/email_designer_ccsdktoolbar.png)

1. 変更が **[!UICONTROL Save]**完了したら、をクリックします。 更新された画像がAdobe Campaignサーバーに保存され、使用できる状態になります。

>[!NOTE]
画像エディターで提供されるツールはカスタマイズできません。
