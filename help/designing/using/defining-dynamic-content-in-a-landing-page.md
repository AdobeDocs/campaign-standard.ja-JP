---
title: ランディングページでの動的コンテンツの定義
seo-title: ランディングページでの動的コンテンツの定義
description: ランディングページでの動的コンテンツの定義
seo-description: Adobe Campaign式エディターで定義された条件に従ってランディングページに異なるコンテンツを動的に表示するには、次の手順に従います。
page-status-flag: 常にアクティブ化されていない
uuid: 64a8ddd2-8bb0-44ef- bae9- b6b77a84ca8b
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: 定義条件コンテンツ
discoiquuid: 00e5ed81- d3d1-4211-8352-71805a7042c9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining dynamic content in a landing page{#defining-dynamic-content-in-a-landing-page}

ランディングページで動的コンテンツを定義するには、パンくずリストを使用するか、要素を直接クリックしてブロックを選択します。

![](assets/dynamic_content_lp_1.png)

画像などの特定のブロックを直接選択することはできません。この場合、パンくずリストを使用して親ブロックを選択します。その後、この親要素に含まれるすべての要素（画像など）を変更できます。条件は、親ブロック内のすべての子要素に適用されます。

The breadcrumb is presented in the [Managing blocks](../../designing/using/managing-landing-page-structure-and-style.md) section.

ランディングページで動的なコンテンツを定義する次の手順は、電子メールに従う手順と似ています。See [this section](../../designing/using/defining-dynamic-content-in-an-email.md).

>[!NOTE]
>
>バリアント要素が赤で並んでいる場合、式がまだ定義されていないことを意味します。

## Previewing dynamic content in a landing page {#previewing-dynamic-content-in-a-landing-page}

ブロックの様々な動的コンテンツ間を移動できます。これを行うには、次の手順に従います。

1. ブロックを選択します。

   矢印は、画像の右側と左側に表示されます。

1. 使用可能な動的コンテンツを参照するには、右矢印をクリックします。

   ![](assets/dynamic_content_lp_2.png)

   最終的な使用可能な動的コンテンツに到達したかどうかに応じて、各辺の矢印が暗くなります。

   ![](assets/dynamic_content_lp_3.png)

1. To delete all the conditions applied to a block, select that block and click the **[!UICONTROL Disable dynamic content]** icon.
1. 保持する動的コンテンツを選択します。

   ![](assets/dynamic_content_lp_5.png)

パレット内:

* 入力された式の内容が赤で表示されなくなり、灰色で表示されます。
* 現在選択されているコンテンツは青色で表示されます。

![](assets/dynamic_content_lp_4.png)

