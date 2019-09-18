---
title: ランディング·ページでの動的コンテンツの定義
seo-title: ランディング·ページでの動的コンテンツの定義
description: ランディング·ページでの動的コンテンツの定義
seo-description: 次の手順に従って、Adobe Campaign式エディタで定義された条件に従って、ランディング·ページに異なるコンテンツを動的に表示します。
page-status-flag: 未活性化の
uuid: 64a8dd2-8bb0-44ef-bae9-b6b77a84ca8b
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: 定義条件付きコンテンツ
discoiquuid: 00e5ed81-d3d1-4211-8352-71805a7042c9
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# ランディング·ページでの動的コンテンツの定義{#defining-dynamic-content-in-a-landing-page}

ランディング·ページで動的コンテンツを定義するには、ブレッドクラムを使用するか、要素を直接クリックしてブロックを選択します。

![](assets/dynamic_content_lp_1.png)

イメージなどの特定のブロックは、直接選択できません。 この場合は、ブレッドクラムを使用して親ブロックを選択します。 次に、イメージを含め、この親要素に含まれるすべての要素を修正できます。 この条件は、親ブロック内のすべての子要素に適用されます。

ブレッドクラムは、「≪ブロックの管理| [Managing blocks](../../channels/using/managing-landing-page-structure-and-style.md) |emdw≫」セクションに表示されます。

ランディング·ページで動的コンテンツを定義する次の手順は、Eメールの手順と同じです。 本項 [を参照](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

>[!NOTE]
>
>バリアント要素の輪郭が赤の場合、式がまだ定義されていないことを意味します。

## ランディング·ページでの動的コンテンツのプレビュー {#previewing-dynamic-content-in-a-landing-page}

ブロックの異なるダイナミックコンテンツ間を移動できます。 これを行うには、次の手順に従います。

1. ブロックを選択します。

   イメージの右側と左側に矢印が表示されます。

1. 右矢印をクリックして、使用可能な動的コンテンツを参照します。

   ![](assets/dynamic_content_lp_2.png)

   最後に使用可能なダイナミックコンテンツに到達したか、最初に使用可能なダイナミックコンテンツに到達したかに応じて、両側の矢印が暗くなります。

   ![](assets/dynamic_content_lp_3.png)

1. ブロックに適用されているすべての条件を削除するには、そのブロックを選択し、アイコンをクリック **[!UICONTROL Disable dynamic content]** します。
1. 保持するダイナミックコンテンツを選択します。

   ![](assets/dynamic_content_lp_5.png)

パレットで、次の操作を行います。

* 式を入力した内容は、赤で表示されなくなり、灰色で表示されます。
* 現在選択されているコンテンツは青で表示されます。

![](assets/dynamic_content_lp_4.png)

