---
title: 「ワークフローのユースケース:補足を使用した搬送の作成
seo-title: 「ワークフローのユースケース:補足を使用した搬送の作成
description: 「ワークフローのユースケース:補足を使用した搬送の作成
seo-description: 「ワークフローのユースケース:補足を使用した搬送の作成
page-status-flag: 決して活性化されていない
uuid: 396a3de1-6fa-4385- ac9f-15fdee5a366
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc- a1ad-8a2f5d409
context-tags: ワークフロー、ユースケース、セグメンテーション
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 035726bbd3112058b9a89525a861521bc3b9867e

---


# ワークフローのユースケース:補足を使用した搬送の作成 {#deliveries-with-complement}

お客様に電子メールを送信できます。1年以上前に作成されたクライアントの場合、1年以上前に作成されたクライアント用のクライアント。

1. で **[!UICONTROL Marketing Activities]**、をクリック **[!UICONTROL Create]** して選択 **[!UICONTROL Workflow]**&#x200B;します。
1. ワークフロータイプ **[!UICONTROL New Workflow]** として選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. ワークフローのプロパティを入力し、をクリック **[!UICONTROL Create]**&#x200B;します。

## クエリアクティビティの作成 {#create-a-query-activity}

1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Targeting]**、をドラッグアンドドロップ **[!UICONTROL Query activity]**![](assets/query.png)します。
1. アクティビティをダブルクリックします。
1. で **[!UICONTROL Shortcuts]**、ドラッグアンドドロップ **[!UICONTROL Profiles]** してオペレータ **[!UICONTROL email]** を選択 **[!UICONTROL is not empty]**&#x200B;します。
1. で **[!UICONTROL Shortcuts]**、ドラッグアンドドロップ **[!UICONTROL Profiles]** して値 **[!UICONTROL no longer contact by email]** を選択 **[!UICONTROL no]**&#x200B;します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

![](assets/wf-complement-query.png)

## セグメンテーションアクティビティを作成する {#create-a-segmentation-activity}

1. **[!UICONTROL Activities]** &gt;&gt; **[!UICONTROL Targeting]**&#x200B;で **[!UICONTROL Segmentation]** 、アクティビティをドラッグアンドドロップしてダブルクリックします。
1. セグメント上にマウスポインタを移動し、この年に追加されたターゲット顧客 ![](assets/edit_darkgrey-24px.png) をデータベースに追加します。
1. ドラッグアンドドロップ **[!UICONTROL Profiles]** し、フィルタタイプ **[!UICONTROL Created]** で選択 **[!UICONTROL Relative]**&#x200B;します。
1. to **[!UICONTROL Level of precision]** に **[!UICONTROL Year]** 変更して選択 **[!UICONTROL This year]**&#x200B;します。
1. 2 **[!UICONTROL Confirm]** 回クリックします。
1. で **[!UICONTROL Advanced Options]**、 **[!UICONTROL Generate complement]** 残りの受信者を対象とするセグメントを作成します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックします。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>規則の構造を確認するには、をクリック **[!UICONTROL Advanced Mode]**&#x200B;します。

## 電子メール配信の作成 {#create-an-email-delivery}

1. **[!UICONTROL Activities]** &gt;&gt; **[!UICONTROL Channels]**&#x200B;で、各セグメントの後に電子メール配信をドラッグアンドドロップします。
1. アクティビティをクリックし、編集 ![](assets/edit_darkgrey-24px.png) するように選択します。
1. を選択 **[!UICONTROL Single send email]** してをクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールテンプレートを選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのプロパティを入力し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのレイアウトを作成するには、をクリック **[!UICONTROL Email Designer]**&#x200B;します。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各配信に固有の特典でEメールをカスタマイズできます。
1. クリック **[!UICONTROL Preview]** すると、レイアウトが確認されます。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

詳細については、電子メール [の設計](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)を参照してください。

![](assets/wf-deliveries-with-a-complement.png)

**関連トピック:**

* [クエリー](../../automating/using/query.md)
* [セグメンテーション活動](../../automating/using/segmentation.md)
* [Eメール配信](../../automating/using/email-delivery.md)
