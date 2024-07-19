---
title: メールを開封していないユーザーのリターゲティング
description: このユースケースは、オープナー以外のユーザーをリターゲティングする方法を示しています。
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

# リターゲティングワークフロー開いていないユーザーに新しい配信を送信{#retargeting-delivery-to-non-openers}

顧客にメールを送信した後、メールを開かなかった顧客に SMS を送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## クエリアクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]** で、**[!UICONTROL Profiles]** をドラッグ&amp;ドロップし、演算子 **[!UICONTROL is not empty]** を使用して **[!UICONTROL email]** を選択します。
1. **[!UICONTROL Shortcuts]** で、**[!UICONTROL Profiles]** をドラッグ&amp;ドロップし、値が **[!UICONTROL no]** の **[!UICONTROL no longer contact by email]** を選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後に [ メール配信 ](../../automating/using/email-delivery.md) をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. 「**[!UICONTROL Add an outbound transition without the population]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. メールのレイアウトを作成するには、「**[!UICONTROL Using the Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用してメールをパーソナライズします。詳しくは、[ メールのデザイン ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

## クエリアクティビティでの非オープナーのターゲティング{#targeting-non-openers-in-a-query-activity}

1. **[!UICONTROL Activities]**/**[!UICONTROL Execution]** で、「[ 待機 ](../../automating/using/wait.md)」アクティビティをドラッグ&amp;ドロップします。
1. **[!UICONTROL Duration]** で、「![](assets/duration-icon.png)」をクリックして 1 日を選択します。
1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、**[!UICONTROL Query activity]** をドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]** で、演算子 **[!UICONTROL exists]** を使用し **[!UICONTROL Tracking Logs]** とをドラッグ&amp;ドロップします。
1. **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** で、演算子 **[!UICONTROL is equal to]** を使用して **[!UICONTROL delivery]** をドラッグ&amp;ドロップし、値として配信を選択します。
1. **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** で、**[!UICONTROL type]** をドラッグ&amp;ドロップし、値として **[!UICONTROL Open]** をオンにします。
1. ルール間の演算子を **[!UICONTROL except]** のように選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

## SMS 配信の作成{#creating-a-sms-delivery}

1. 各セグメントの後に SMS 配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple sms]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. Sms テンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. SMS のプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. SMS のレイアウトを作成するには、「**[!UICONTROL Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して SMS をパーソナライズします。
詳しくは、[SMS のデザイン ](../../channels/using/creating-an-sms-message.md) の節を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [メールチャネル](../../channels/using/creating-an-email.md)
