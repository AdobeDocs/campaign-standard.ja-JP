---
title: 場所でのセグメント化」
description: この使用例は、場所でセグメント化を実行する方法を示しています。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# 場所のセグメント化 {#segmentation-on-location}

地元の店舗のオファーを持つ顧客にターゲット設定の電子メールを送信できます。

1. で、 **[!UICONTROL Marketing Activities]**&#x200B;をクリック **[!UICONTROL Create]** してを選択し **[!UICONTROL Workflow]**&#x200B;ます。
1. ワークフローのタイプ **[!UICONTROL New Workflow]** として選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. ワークフローのプロパティを入力し、をクリックし **[!UICONTROL Create]**&#x200B;ます。

## 電子メールで連絡可能な受信者の選択{#selecting-recipients-contactable-via-email}

1. /で、 **[!UICONTROL Activities]** クエリ **[!UICONTROL Targeting]**&#x200B;アクティビティをドラッグ&amp;ドロップ [](../../automating/using/query.md)![](assets/query.png)します。
1. アクティビティを重複クリックします。
1. で、演算子 **[!UICONTROL Shortcuts]**&#x200B;を使用し **[!UICONTROL Profiles]** てフィールド **[!UICONTROL email]** をドラッグ&amp;ドロップして選択 **[!UICONTROL is not empty]**&#x200B;します。
1. で、値 **[!UICONTROL Shortcuts]**&#x200B;を含むフィールドをドラッグ&amp;ドロップ **[!UICONTROL Profiles]** して選択 **[!UICONTROL no longer contact by email]** し **[!UICONTROL no]**&#x200B;ます。
1. 2回クリック **[!UICONTROL Confirm]** します。

![](assets/wf-complement-query.png)

## セグメントアクティビティの作成{#creating-a-segmentation-activity}

1. セグメント [アクティビティをドラッグ&amp;ドロップし](../../automating/using/segmentation.md) 、重複を押しながらクリックします。
1. セグメントをクリックし、最初の都市のターゲットに対するトランジションを開きます。 ボストンです。
1. 演算子 **[!UICONTROL Location]** と値 **[!UICONTROL City]** を使用して、ドラッグ&amp;ドロップ **[!UICONTROL equals to]** して選択し **[!UICONTROL Boston]**ます。
注意： ボストンに入ったすべての人に連絡するには、大文字と小文字を区別しないで、[大文字と小文字を区別する]オプションをオフにします。
1. クリック **[!UICONTROL Confirm]** .
1. で、 **[!UICONTROL List of outbound segments]**&#x200B;をクリック **[!UICONTROL Add an element]**![](assets/edit_darkgrey-24px.png) し、をクリックして、2番目の都市の人をターゲットにしたセグメントを作成します。 シカゴだ。
1. ドラッグ&amp;ドロップ **[!UICONTROL Location]** し、演算子 **[!UICONTROL City]** を使用して選択し、値 **[!UICONTROL equals to]****[!UICONTROL Chicago]** を入力します。
1. シカゴに入ったすべての人々に、大文字と小文字の区別なしで連絡を取るには、[大文字と小文字の区別]オプションをオフにします。
1. クリック **[!UICONTROL Confirm]** .

## E メール配信の作成{#creating-an-email-delivery}

1. / **[!UICONTROL Activities]** で、 **[!UICONTROL Channels]**&#x200B;各セグメントの後に [電子メール配信](../../automating/using/email-delivery.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、「編集」 ![](assets/edit_darkgrey-24px.png) を選択します。
1. を選択 **[!UICONTROL Simple email]** し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールテンプレートを選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのプロパティを入力し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのレイアウトを作成するには、[オン]をクリックし **[!UICONTROL Email Designer]**&#x200B;ます。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、電子メールをパーソナライズします。

   詳しくは、「電子メールの [設計](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)」を参照してください。

1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. クリック **[!UICONTROL Save]** .

![](assets/wf-segmentation-location.png)

