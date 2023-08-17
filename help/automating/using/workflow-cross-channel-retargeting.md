---
title: メールを開封していないユーザーのリターゲティング
description: この使用例では、メールを開封していないユーザーをリターゲティングする方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---

# メールを開封していないユーザーに新しい配信を送信する再ターゲティングワークフロー{#retargeting-delivery-to-non-openers}

顧客に E メールを送信し、メールを開封していないユーザーに Sms を送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## クエリアクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. In **[!UICONTROL Shortcuts]**、ドラッグ&amp;ドロップ **[!UICONTROL Profiles]** を選択し、 **[!UICONTROL email]** 演算子を使用 **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**、ドラッグ&amp;ドロップ **[!UICONTROL Profiles]** を選択し、 **[!UICONTROL no longer contact by email]** と値 **[!UICONTROL no]**.
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## メール配信の作成{#creating-an-email-delivery}

1. ドラッグ&amp;ドロップ [E メール配信](../../automating/using/email-delivery.md) 各セグメントの後。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. 「**[!UICONTROL Add an outbound transition without the population]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Using the Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、E メールをパーソナライズします。詳しくは、 [e メールの設計](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

## クエリアクティビティでのメールを開封していないユーザーのターゲティング{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**、ドラッグ&amp;ドロップ [待機](../../automating/using/wait.md) アクティビティ。
1. In **[!UICONTROL Duration]**&#x200B;をクリックし、 ![](assets/duration-icon.png) をクリックし、1 日を選択します。
1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、**[!UICONTROL Query activity]** をドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. In **[!UICONTROL Shortcuts]**、ドラッグ&amp;ドロップ **[!UICONTROL Tracking Logs]** および演算子 **[!UICONTROL exists]**.
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**、ドラッグ&amp;ドロップ **[!UICONTROL delivery]** 演算子を使用 **[!UICONTROL is equal to]** 配信を値として選択します。
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**、ドラッグ&amp;ドロップ **[!UICONTROL type]** およびチェック **[!UICONTROL Open]** 値として。
1. ルール間の演算子を次のように選択します。 **[!UICONTROL except]**.
1. 「**[!UICONTROL Confirm]**」をクリックします。

## SMS 配信の作成{#creating-a-sms-delivery}

1. 各セグメントの後に SMS 配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple sms]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. sms テンプレートを選択し、「 **[!UICONTROL Next]**.
1. sms のプロパティを入力し、「 **[!UICONTROL Next]**.
1. SMS のレイアウトを作成するには、 **[!UICONTROL Email Designer]**.
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、SMS をパーソナライズします。
詳しくは、 [SMS のデザイン](../../channels/using/creating-an-sms-message.md) 」セクションに入力します。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [メールチャネル](../../channels/using/creating-an-email.md)
