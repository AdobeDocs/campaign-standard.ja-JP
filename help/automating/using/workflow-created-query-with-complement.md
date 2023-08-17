---
title: 補完を含んだ配信の作成
description: この使用例は、補集合を含む配信の作成方法を示しています。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5cd71e07-f955-4c15-bdfb-14b0daccec1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---

# 補完を含んだ配信の作成 {#deliveries-with-complement}

顧客に E メールを送信できます。1 年未満に作成されたクライアント向けと 1 年以上前に作成されたクライアント向けです。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## クエリアクティビティの作成 {#create-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. In **[!UICONTROL Shortcuts]**、ドラッグ&amp;ドロップ **[!UICONTROL Profiles]** を選択し、 **[!UICONTROL email]** 演算子を使用 **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**、ドラッグ&amp;ドロップ **[!UICONTROL Profiles]** を選択し、 **[!UICONTROL no longer contact by email]** と値 **[!UICONTROL no]**.
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## Segmentation アクティビティの作成 {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**、ドラッグ&amp;ドロップ [セグメント化](../../automating/using/segmentation.md) 「 」アクティビティをクリックし、ダブルクリックします。
1. セグメントの上にマウスポインターを置いて、「 ![](assets/edit_darkgrey-24px.png) を使用して、今年データベースに追加された顧客をターゲット化できます。
1. ドラッグ&amp;ドロップ **[!UICONTROL Profiles]** を選択し、 **[!UICONTROL Created]** フィルタータイプ **[!UICONTROL Relative]**.
1. 次を変更： **[!UICONTROL Level of precision]** から **[!UICONTROL Year]** を選択し、 **[!UICONTROL This year]**.
1. 「**[!UICONTROL Confirm]**」を 2 回クリックします。
1. In **[!UICONTROL Advanced Options]**, check **[!UICONTROL Generate complement]** をクリックして、残りの受信者をターゲティングするセグメントを作成します。
1. 「**[!UICONTROL Confirm]**」をクリックします。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>ルールの構造を観察するには、 **[!UICONTROL Advanced Mode]**.

## E メール配信の作成 {#create-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**、ドラッグ&amp;ドロップ [E メール配信](../../automating/using/email-delivery.md) 」アクティビティが表示されます。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Single send email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各配信に固有のオファーを使用して、E メールをパーソナライズします。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

詳しくは、[E メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。

![](assets/wf-deliveries-with-a-complement.png)
