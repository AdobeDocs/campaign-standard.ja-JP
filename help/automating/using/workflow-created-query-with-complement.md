---
title: '"ワークフローの使用例：補数付き搬送の作成」'
seo-title: '"ワークフローの使用例：補数付き搬送の作成」'
description: '"ワークフローの使用例：補数付き搬送の作成」'
seo-description: '"ワークフローの使用例：補数付き搬送の作成」'
page-status-flag: 未活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: ワークフロー，ユースケース，セグメンテーション
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# ワークフローの使用例：補完を含む搬送の作成 {#deliveries-with-complement}

お客様にEメールを送信できます。1つは、1年前に作成されたクライアント用、1つは1年前に作成されたクライアント用です。

1. で、をク **[!UICONTROL Marketing Activities]**&#x200B;リックして **[!UICONTROL Create]** を選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** の種類としてを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## クエリアクティビティの作成 {#create-a-query-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子を使用してドラ **[!UICONTROL Profiles]** ッグアン **[!UICONTROL email]** ドドロップし、選択します **[!UICONTROL is not empty]**。
1. で、値 **[!UICONTROL Shortcuts]**&#x200B;を使用してドラ **[!UICONTROL Profiles]** ッグアン **[!UICONTROL no longer contact by email]** ドドロップし、選択します **[!UICONTROL no]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## セグメンテーションアクティビティの作成 {#create-a-segmentation-activity}

1. &gt;で、ア **[!UICONTROL Activities]** クティビティをドラ **[!UICONTROL Targeting]****[!UICONTROL Segmentation]** ッグ&amp;ドロップし、ダブルクリックします。
1. セグメントの上にカーソルを置き、次に、データベ ![](assets/edit_darkgrey-24px.png) ースに今年追加された顧客をターゲットにします。
1. フィルタ·タイプを使 **[!UICONTROL Profiles]** 用してドラ **[!UICONTROL Created]** ッグ·アンド·ドロップしま **[!UICONTROL Relative]**&#x200B;す。
1. をに変更し、 **[!UICONTROL Level of precision]** を選 **[!UICONTROL Year]** 択します **[!UICONTROL This year]**。
1. を2回クリ **[!UICONTROL Confirm]** ックします。
1. で、残り **[!UICONTROL Advanced Options]**&#x200B;の受信者を **[!UICONTROL Generate complement]** 対象とするセグメントを作成します。
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>規則の構造を確認するには、をクリックしま **[!UICONTROL Advanced Mode]**&#x200B;す。

## 電子メール配信の作成 {#create-an-email-delivery}

1. &gt;で、各セ **[!UICONTROL Activities]** グメ **[!UICONTROL Channels]**&#x200B;ントの後に電子メール配信をドラッグ·アンド·ドロップします。
1. アクティビティをクリックし、編集するア ![](assets/edit_darkgrey-24px.png) クティビティを選択します。
1. を選択し、 **[!UICONTROL Single send email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各配信に固有のサービスを使用して、電子メールをカスタマイズします。
1. レイアウトを **[!UICONTROL Preview]** 確認するには、をクリックします。
1. Click **[!UICONTROL Save]**.

詳細については、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)

**関連トピック：**

* [クエリ](../../automating/using/query.md)
* [セグメンテーション活動](../../automating/using/segmentation.md)
* [電子メール配信](../../automating/using/email-delivery.md)
