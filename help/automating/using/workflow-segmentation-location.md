---
title: 場所でのセグメント化»
description: この使用例では、場所でセグメント化を実行する方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,segmentation,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: feedc2f5-63da-44a5-b8f0-15afdfd47daa
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 80%

---

# 場所でのセグメント化 {#segmentation-on-location}

地元の店舗でのオファーで顧客にターゲティングメールを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## E メールで連絡可能な受信者の選択{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**、ドラッグ&amp;ドロップ [クエリ](../../automating/using/query.md) アクティビティ ![](assets/query.png).
1. アクティビティをダブルクリックします。
1. 「**[!UICONTROL Shortcuts]**」で、「**[!UICONTROL Profiles]**」をドラッグ＆ドロップし、演算子「**[!UICONTROL email]**」を使用してフィールド「**[!UICONTROL is not empty]**」を選択します。
1. 「**[!UICONTROL Shortcuts]**」で、「**[!UICONTROL Profiles]**」をドラッグ＆ドロップして、値「**[!UICONTROL no longer contact by email]**」を含むフィールド「**[!UICONTROL no]**」を選択します。
1. 「**[!UICONTROL Confirm]**」を 2 回クリックします。

![](assets/wf-complement-query.png)

## Segmentation アクティビティの作成{#creating-a-segmentation-activity}

1. 次をドラッグ&amp;ドロップ： [セグメント化](../../automating/using/segmentation.md) 「 」アクティビティをクリックし、ダブルクリックします。
1. セグメントをクリックし、トランジションを開いて、最初の都市の人をターゲットにします。ボストンです。
1. 「**[!UICONTROL Location]**」をドラッグ＆ドロップし、演算子「**[!UICONTROL equals to]**」と値「**[!UICONTROL Boston]**」を使用して、「**[!UICONTROL City]**」を選択します。
注意：ボストンに入ったすべての人に連絡するには、大文字と小文字を区別しないで、「大文字と小文字を区別する」オプションをオフにします。
1. 「**[!UICONTROL Confirm]**」をクリックします。
1. 「**[!UICONTROL List of outbound segments]**」で、「**[!UICONTROL Add an element]**」をクリックし、「![](assets/edit_darkgrey-24px.png)」をクリックして、2 番目の都市の人をターゲットにしたセグメントを作成します。シカゴです。
1. 「**[!UICONTROL Location]**」をドラッグ＆ドロップし、演算子「**[!UICONTROL City]**」を使用して「**[!UICONTROL equals to]**」を選択し、値に「**[!UICONTROL Chicago]**」を入力します。
1. シカゴに入ったすべての人に連絡するには、大文字と小文字を区別しないで、「大文字と小文字を区別する」オプションをオフにします。
1. 「**[!UICONTROL Confirm]**」をクリックします。

## メール配信の作成{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**、ドラッグ&amp;ドロップ [E メール配信](../../automating/using/email-delivery.md) 」アクティビティが表示されます。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. メールのレイアウトを作成するには、「**[!UICONTROL Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、メールをパーソナライズします。

   詳しくは、[メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。

1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-segmentation-location.png)
