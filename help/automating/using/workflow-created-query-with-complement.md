---
title: 補完を含む配信の作成
description: この使用例は、補数を持つ配信の作成方法を示します。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 5%

---


# 補完を含む配信の作成 {#deliveries-with-complement}

顧客に電子メールを送信できます。 1年前に作成されたクライアント用、1年前に作成されたクライアント用。

1. で、 **[!UICONTROL Marketing Activities]**&#x200B;をクリック **[!UICONTROL Create]** してを選択し **[!UICONTROL Workflow]**&#x200B;ます。
1. ワークフローのタイプ **[!UICONTROL New Workflow]** として選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. ワークフローのプロパティを入力し、をクリックし **[!UICONTROL Create]**&#x200B;ます。

## クエリアクティビティの作成 {#create-a-query-activity}

1. /で、 **[!UICONTROL Activities]** クエリ **[!UICONTROL Targeting]**[](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを重複クリックします。
1. で、演算子 **[!UICONTROL Shortcuts]**&#x200B;を使用 **[!UICONTROL Profiles]** してドラッグ&amp;ドロップ **[!UICONTROL email]** し、選択し **[!UICONTROL is not empty]**&#x200B;ます。
1. で、値 **[!UICONTROL Shortcuts]**&#x200B;をドラッグ&amp;ドロップ **[!UICONTROL Profiles]** し、値 **[!UICONTROL no longer contact by email]** で選択し **[!UICONTROL no]**&#x200B;ます。
1. クリック **[!UICONTROL Confirm]** .

![](assets/wf-complement-query.png)

## セグメントアクティビティの作成 {#create-a-segmentation-activity}

1. >で、 **[!UICONTROL Activities]** セグメント **[!UICONTROL Targeting]**[](../../automating/using/segmentation.md) アクティビティをドラッグ&amp;ドロップし、重複クリックします。
1. セグメントの上にマウスポインターを置き、「To Database」をクリックして、ターゲットに年内に追加した顧客 ![](assets/edit_darkgrey-24px.png) を選択します。
1. フィルタータイプ **[!UICONTROL Profiles]** でドラッグ&amp;ドロップ **[!UICONTROL Created]** して選択 **[!UICONTROL Relative]**&#x200B;します。
1. をに変更 **[!UICONTROL Level of precision]** し、を選択 **[!UICONTROL Year]** し **[!UICONTROL This year]**&#x200B;ます。
1. 2回クリック **[!UICONTROL Confirm]** します。
1. で、残り **[!UICONTROL Advanced Options]**&#x200B;の受信者 **[!UICONTROL Generate complement]** をターゲットにしたセグメントを作成する場合にオンにします。
1. クリック **[!UICONTROL Confirm]** .
1. クリック **[!UICONTROL Save]** .

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>ルールの構造を確認するには、をクリックし **[!UICONTROL Advanced Mode]**&#x200B;ます。

## Creating an Email delivery {#create-an-email-delivery}

1. / **[!UICONTROL Activities]** で、 **[!UICONTROL Channels]**&#x200B;各セグメントの後に [電子メール配信](../../automating/using/email-delivery.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、「編集」 ![](assets/edit_darkgrey-24px.png) を選択します。
1. を選択 **[!UICONTROL Single send email]** し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールテンプレートを選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのプロパティを入力し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのレイアウトを作成するには、[オン]をクリックし **[!UICONTROL Email Designer]**&#x200B;ます。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各配信に固有のオファーを使用して、電子メールをパーソナライズします。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. クリック **[!UICONTROL Save]** .

詳しくは、「電子メールの [設計](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)」を参照してください。

![](assets/wf-deliveries-with-a-complement.png)
