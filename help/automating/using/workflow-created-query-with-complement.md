---
solution: Campaign Standard
product: campaign
title: 補完を含む配信の作成
description: この使用例は、補数を持つ配信の作成方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 補完を含む配信の作成 {#deliveries-with-complement}

顧客に電子メールを送信できます。1年前に作成されたクライアント用、1年前に作成されたクライアント用。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## クエリアクティビティの作成{#create-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、演算子&#x200B;**[!UICONTROL is not empty]**&#x200B;を使用して&#x200B;**[!UICONTROL email]**&#x200B;を選択します。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL no]**&#x200B;の値で&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;を選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## セグメントアクティビティの作成{#create-a-segmentation-activity}

1. **[!UICONTROL Activities]**/**[!UICONTROL Targeting]**&#x200B;に[セグメント化](../../automating/using/segmentation.md)アクティビティをドラッグ&amp;ドロップし、重複クリックします。
1. セグメントの上にマウスポインターを置き、「![](assets/edit_darkgrey-24px.png)」をクリックすると、顧客がデータベースに今年追加したターゲットが表示されます。
1. **[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、フィルタータイプ&#x200B;**[!UICONTROL Relative]**&#x200B;で&#x200B;**[!UICONTROL Created]**&#x200B;を選択します。
1. **[!UICONTROL Level of precision]**&#x200B;を&#x200B;**[!UICONTROL Year]**&#x200B;に変更し、**[!UICONTROL This year]**&#x200B;を選択します。
1. 「**[!UICONTROL Confirm]**」を 2 回クリックします。
1. **[!UICONTROL Advanced Options]**&#x200B;で、**[!UICONTROL Generate complement]**&#x200B;をチェックして、残りの受信者をターゲットにしたセグメントを作成します。
1. 「**[!UICONTROL Confirm]**」をクリックします。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>ルールの構造を確認するには、**[!UICONTROL Advanced Mode]**&#x200B;をクリックします。

## E メール配信の作成 {#create-an-email-delivery}

1. **[!UICONTROL Activities]**/**[!UICONTROL Channels]**&#x200B;で、[電子メール配信](../../automating/using/email-delivery.md)アクティビティを各セグメントの後にドラッグ&amp;ドロップします。
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
