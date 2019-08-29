---
title: 「ワークフローのユースケース:場所のセグメンテーション」
seo-title: 「ワークフローのユースケース:場所のセグメンテーション」
description: 「ワークフローのユースケース:場所のセグメンテーション」
seo-description: 「ワークフローのユースケース:場所のセグメンテーション」
page-status-flag: 決して活性化されていない
uuid: 396a3de1-6fa-4385- ac9f-15fdee5a366
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc- a1ad-8a2f5d409
context-tags: 'ワークフロー、ユースケース、クエリ、セグメンテーション、配信 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# ワークフローのユースケース:場所におけるセグメンテーション {#segmentation-on-location}

ターゲットの電子メールをお客様に送信して、地元の店舗に提供することができます。

1. で **[!UICONTROL Marketing Activities]**、をクリック **[!UICONTROL Create]** して選択 **[!UICONTROL Workflow]**&#x200B;します。
1. ワークフロータイプ **[!UICONTROL New Workflow]** として選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. ワークフローのプロパティを入力し、をクリック **[!UICONTROL Create]**&#x200B;します。

## 電子メールでの受信者の選択{#selecting-recipients-contactable-via-email}

1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Targeting]**、をドラッグアンドドロップ **[!UICONTROL Query activity]**![](assets/query.png)します。
1. アクティビティをダブルクリックします。
1. で **[!UICONTROL Shortcuts]**、ドラッグアンドドロップ **[!UICONTROL Profiles]** して、演算子のあるフィールド **[!UICONTROL email]** を選択 **[!UICONTROL is not empty]**&#x200B;します。
1. で **[!UICONTROL Shortcuts]**、ドラッグアンドドロップ **[!UICONTROL Profiles]** して値を持つフィールド **[!UICONTROL no longer contact by email]** を選択 **[!UICONTROL no]**&#x200B;します。
1. 2 **[!UICONTROL Confirm]** 回クリックします。

## セグメンテーションアクティビティの作成{#creating-a-segmentation-activity}

1. **[!UICONTROL Segmentation]** アクティビティをドラッグアンドドロップし、ダブルクリックします。
1. 「セグメント」をクリックして、最初の都市のターゲット人に移行します。ボストンだ
1. ドラッグアンドドロップ **[!UICONTROL Location]****[!UICONTROL City]** して、演算子 **[!UICONTROL equals to]** と値を選択 **[!UICONTROL Boston]**します。
注意:ボストンに入った全ての人に到達するには、大文字と小文字を区別しないオプションの選択を解除します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックします。
1. で **[!UICONTROL List of outbound segments]**&#x200B;は、をクリック **[!UICONTROL Add an element]** してクリック ![](assets/edit_darkgrey-24px.png) し、2番目の都市の人を対象とするセグメントを作成します。シカゴだ
1. ドラッグアンドドロップ **[!UICONTROL Location]** して、演算子 **[!UICONTROL City]** で選択 **[!UICONTROL equals to]** し、値を入力 **[!UICONTROL Chicago]** します。

>[!NOTE]
>
>シカゴに入った全ての人に到達するには、大文字と小文字を区別しないオプションの選択を解除する。

1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

## 電子メール配信の作成{#creating-an-email-delivery}

1. **[!UICONTROL Activities]** &gt;&gt; **[!UICONTROL Channels]**&#x200B;で、各セグメントの後にドラッグ **[!UICONTROL Email Delivery]** アンドドロップします。
1. アクティビティをクリックし、編集 ![](assets/edit_darkgrey-24px.png) するように選択します。
1. を選択 **[!UICONTROL Simple email]** してをクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールテンプレートを選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのプロパティを入力し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのレイアウトを作成するには、をクリック **[!UICONTROL Email Designer]**&#x200B;します。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有の特典を電子メールでカスタマイズします。

詳細については、電子メール [の設計](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)を参照してください。

1. クリック **[!UICONTROL Preview]** すると、レイアウトが確認されます。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

**関連トピック:**

* [クエリアクティビティ](../../automating/using/query.md)
* [セグメンテーション活動](../../automating/using/segmentation.md)
* [Eメール配信](../../automating/using/email-delivery.md)
