---
title: 「ワークフローの使用例：場所のセグメント化」
description: 「ワークフローの使用例：場所のセグメント化」
page-status-flag: 非活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'ワークフロー，ユースケース，クエリ，セグメント化，配信 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローの使用例：場所のセグメント化 {#segmentation-on-location}

地域の店舗でのオファーを含む顧客にターゲット設定用の電子メールを送信できます。

1. で、を **[!UICONTROL Marketing Activities]**&#x200B;クリックし **[!UICONTROL Create]** てを選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** タイプとして選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## 電子メールで連絡可能な受信者の選択{#selecting-recipients-contactable-via-email}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子を使用してフ **[!UICONTROL Profiles]** ィールドをドラッグ&amp;ド **[!UICONTROL email]** ロップして選択しま **[!UICONTROL is not empty]**&#x200B;す。
1. で、値 **[!UICONTROL Shortcuts]**&#x200B;を含むフィールドをド **[!UICONTROL Profiles]** ラッグ&amp;ドロッ **[!UICONTROL no longer contact by email]** プして選択しま **[!UICONTROL no]**&#x200B;す。
1. を2回クリ **[!UICONTROL Confirm]** ックします。

![](assets/wf-complement-query.png)

## セグメント化アクティビティの作成{#creating-a-segmentation-activity}

1. アクティビティをドラッグ&amp;ド **[!UICONTROL Segmentation]** ロップし、ダブルクリックします。
1. セグメントをクリックし、最初の都市の人々をターゲットにするトランジションを開きます。 ボストンです。
1. 演算子と値を使 **[!UICONTROL Location]** 用して、ド **[!UICONTROL City]** ラッグ&amp;ド **[!UICONTROL equals to]** ロップして選択しま **[!UICONTROL Boston]**す。
注意：ボストンに入ったすべての人々に連絡するには、大文字と小文字を区別せずに、[大文字と小文字を区別する]オプションをオフにします。
1. Click **[!UICONTROL Confirm]**.
1. で、をク **[!UICONTROL List of outbound segments]**&#x200B;リックし **[!UICONTROL Add an element]** て、をクリックし ![](assets/edit_darkgrey-24px.png) て、2番目の都市の人をターゲットにするセグメントを作成します。 シカゴだ。
1. 演算子を使用してド **[!UICONTROL Location]** ラッグ&amp;ド **[!UICONTROL City]** ロップし、値を **[!UICONTROL equals to]** 入力して **[!UICONTROL Chicago]** 選択します。
1. シカゴに入ったすべての人々に、大文字と小文字を無視して連絡を取るには、[大文字と小文字を区別する]オプションをオフにします。
1. Click **[!UICONTROL Confirm]**.

## E メール配信の作成{#creating-an-email-delivery}

1. &gt;で、各 **[!UICONTROL Activities]** セグメ **[!UICONTROL Channels]**&#x200B;ントの後にドラッグ&amp;ド **[!UICONTROL Email Delivery]** ロップします。
1. アクティビティをクリックし、編集する ![](assets/edit_darkgrey-24px.png) 対象を選択します。
1. を選択し、 **[!UICONTROL Simple email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、[オン]をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、電子メールをパーソナライズします。

詳しくは、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**関連トピック：**

* [クエリアクティビティ](../../automating/using/query.md)
* [分類アクティビティ](../../automating/using/segmentation.md)
* [E メール配信](../../automating/using/email-delivery.md)
