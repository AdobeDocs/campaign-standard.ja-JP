---
title: 「ワークフローの使用例：補完的な配信の作成」
description: 「ワークフローの使用例：補完的な配信の作成」
page-status-flag: 非活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローの使用例：補完を含む配信の作成 {#deliveries-with-complement}

顧客に電子メールを送信できます。1年前に作成されたクライアント用、1年前に作成されたクライアント用。

1. で、を **[!UICONTROL Marketing Activities]**&#x200B;クリックし **[!UICONTROL Create]** てを選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** タイプとして選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## Queryアクティビティの作成 {#create-a-query-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子を使用してドラッ **[!UICONTROL Profiles]** グ&amp;ドロ **[!UICONTROL email]** ップして選択しま **[!UICONTROL is not empty]**&#x200B;す。
1. で、 **[!UICONTROL Shortcuts]**&#x200B;値を使用してドラッグ&amp;ド **[!UICONTROL Profiles]** ロップ **[!UICONTROL no longer contact by email]** し、選択します **[!UICONTROL no]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## セグメント化アクティビティの作成 {#create-a-segmentation-activity}

1. &gt;で、ア **[!UICONTROL Activities]** クティビティ **[!UICONTROL Targeting]**&#x200B;をドラッグ&amp;ドロ **[!UICONTROL Segmentation]** ップし、ダブルクリックします。
1. セグメントの上にマウスポインターを置き、をクリ ![](assets/edit_darkgrey-24px.png) ックして、データベースに今年追加された顧客をターゲットにします。
1. ドラッグ&amp;ドロッ **[!UICONTROL Profiles]** プし、フィ **[!UICONTROL Created]** ルタータイプで選択しま **[!UICONTROL Relative]**&#x200B;す。
1. をに変更し **[!UICONTROL Level of precision]** 、を **[!UICONTROL Year]** 選択しま **[!UICONTROL This year]**&#x200B;す。
1. を2回クリ **[!UICONTROL Confirm]** ックします。
1. で、残り **[!UICONTROL Advanced Options]**&#x200B;の受信者を **[!UICONTROL Generate complement]** ターゲットにしたセグメントを作成する場合に選択します。
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>ルールの構造を確認するには、をクリックしま **[!UICONTROL Advanced Mode]**&#x200B;す。

## Creating an Email delivery {#create-an-email-delivery}

1. &gt;で、各 **[!UICONTROL Activities]** セグメ **[!UICONTROL Channels]**&#x200B;ントの後に電子メール配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、編集する ![](assets/edit_darkgrey-24px.png) 対象を選択します。
1. を選択し、 **[!UICONTROL Single send email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、[オン]をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各配信に固有のオファーを使用して、電子メールをパーソナライズします。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. Click **[!UICONTROL Save]**.

詳しくは、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)

**関連トピック：**

* [クエリ](../../automating/using/query.md)
* [分類アクティビティ](../../automating/using/segmentation.md)
* [E メール配信](../../automating/using/email-delivery.md)
