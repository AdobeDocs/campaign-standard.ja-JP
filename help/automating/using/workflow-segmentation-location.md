---
title: '"ワークフローの使用例：位置のセグメンテーション"'
seo-title: '"ワークフローの使用例：位置のセグメンテーション"'
description: '"ワークフローの使用例：位置のセグメンテーション"'
seo-description: '"ワークフローの使用例：位置のセグメンテーション"'
page-status-flag: 未活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'ワークフロー，ユースケース，クエリ，セグメンテーション，配信 '
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# ワークフローの使用例：場所でのセグメンテーション {#segmentation-on-location}

お店のお客様向けのEメールをお送りいただけます。

1. で、をク **[!UICONTROL Marketing Activities]**&#x200B;リックして **[!UICONTROL Create]** を選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** の種類としてを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## 電子メールで連絡可能な受信者を選択する{#selecting-recipients-contactable-via-email}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子を使用し **[!UICONTROL Profiles]** てフィールドをドラッ **[!UICONTROL email]** グ·アンド·ドロップしま **[!UICONTROL is not empty]**&#x200B;す。
1. で、値 **[!UICONTROL Shortcuts]**&#x200B;を含むフィー **[!UICONTROL Profiles]** ルドをドラッグアンドド **[!UICONTROL no longer contact by email]** ロップして選択しま **[!UICONTROL no]**&#x200B;す。
1. を2回クリ **[!UICONTROL Confirm]** ックします。

![](assets/wf-complement-query.png)

## セグメンテーション·アクティビティの作成{#creating-a-segmentation-activity}

1. アクティビティをドラッグ·ア **[!UICONTROL Segmentation]** ンド·ドロップしてダブルクリックします。
1. セグメントをクリックし、最初の都市の対象となる人々への移行を開きます。 ボストンです。
1. 演算子と値を使 **[!UICONTROL Location]** 用してド **[!UICONTROL City]** ラッグ·アンド· **[!UICONTROL equals to]** ドロップ選択しま **[!UICONTROL Boston]**す。
注：ボストンに入ったすべての人に、大文字と小文字を区別せずに連絡するには、大文字と小文字を区別するオプションをオフにします。
1. Click **[!UICONTROL Confirm]**.
1. で、をク **[!UICONTROL List of outbound segments]**&#x200B;リックし **[!UICONTROL Add an element]** て、をクリックし、 ![](assets/edit_darkgrey-24px.png) 2番目の都市の人を対象にしたセグメントを作成します。 シカゴだ。
1. 演算子を使用してドラ **[!UICONTROL Location]** ッグ·アンド· **[!UICONTROL City]** ドロップし、値 **[!UICONTROL equals to]** を入力し **[!UICONTROL Chicago]** て選択します。
1. シカゴに入ったすべての人に連絡するには、大文字と小文字を区別しないオプションをオフにします。
1. Click **[!UICONTROL Confirm]**.

## 電子メール配信の作成{#creating-an-email-delivery}

1. &gt;で、各セ **[!UICONTROL Activities]** グメン **[!UICONTROL Channels]**&#x200B;トの後ろをドラッグアン **[!UICONTROL Email Delivery]** ドドロップします。
1. アクティビティをクリックし、編集するア ![](assets/edit_darkgrey-24px.png) クティビティを選択します。
1. を選択し、 **[!UICONTROL Simple email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のサービスを使用して、電子メールをカスタマイズします。

詳細については、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. レイアウトを **[!UICONTROL Preview]** 確認するには、をクリックします。
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**関連トピック：**

* [クエリアクティビティ](../../automating/using/query.md)
* [セグメンテーション活動](../../automating/using/segmentation.md)
* [電子メール配信](../../automating/using/email-delivery.md)
