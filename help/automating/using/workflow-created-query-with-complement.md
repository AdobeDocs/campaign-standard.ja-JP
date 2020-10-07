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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---


# 補完を含む配信の作成 {#deliveries-with-complement}

顧客に電子メールを送信できます。1年前に作成されたクライアント用、1年前に作成されたクライアント用。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## Create a Query activity {#create-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no]**.
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## Create a Segmentation activity {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. セグメントの上にマウスポインターを置き、「To Database」をクリックして、ターゲットに年内に追加した顧客 ![](assets/edit_darkgrey-24px.png) を選択します。
1. Drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL Created]** with the filter type **[!UICONTROL Relative]**.
1. Change the **[!UICONTROL Level of precision]** to **[!UICONTROL Year]** and select **[!UICONTROL This year]**.
1. 「**[!UICONTROL Confirm]**」を 2 回クリックします。
1. で、残り **[!UICONTROL Advanced Options]**&#x200B;の受信者 **[!UICONTROL Generate complement]** をターゲットにしたセグメントを作成する場合にオンにします。
1. 「**[!UICONTROL Confirm]**」をクリックします。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>ルールの構造を確認するには、をクリックし **[!UICONTROL Advanced Mode]**&#x200B;ます。

## E メール配信の作成 {#create-an-email-delivery}

1. / **[!UICONTROL Activities]** で、 **[!UICONTROL Channels]**&#x200B;各セグメントの後に [電子メール配信](../../automating/using/email-delivery.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Single send email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各配信に固有のオファーを使用して、電子メールをパーソナライズします。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

詳しくは、[E メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。

![](assets/wf-deliveries-with-a-complement.png)
