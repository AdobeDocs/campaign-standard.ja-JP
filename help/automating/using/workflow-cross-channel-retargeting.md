---
title: メールを開封していないユーザーのリターゲティング
description: この使用例では、メールを開封していないユーザーを再ターゲティングする方法を示します。
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

顧客にEメールを送信し、そのメールを開封していないユーザーにSmsを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## クエリアクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、演算子&#x200B;**[!UICONTROL is not empty]**&#x200B;を使用して&#x200B;**[!UICONTROL email]**&#x200B;を選択します。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、値&#x200B;**[!UICONTROL no ]**&#x200B;を使用して&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;を選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後に[Eメール配信](../../automating/using/email-delivery.md)をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. 「**[!UICONTROL Add an outbound transition without the population]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Using the Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、Eメールをパーソナライズします。詳しくは、[Eメールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

## クエリアクティビティで開封していないユーザーのターゲティング{#targeting-non-openers-in-a-query-activity}

1. **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;で、[待機](../../automating/using/wait.md)アクティビティをドラッグ&amp;ドロップします。
1. **[!UICONTROL Duration]**&#x200B;で![](assets/duration-icon.png)をクリックし、1日を選択します。
1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、**[!UICONTROL Query activity]** をドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Tracking Logs]**&#x200B;および演算子&#x200B;**[!UICONTROL exists]**&#x200B;をドラッグ&amp;ドロップします。
1. **[!UICONTROL Shortcuts]** **[!UICONTROL Delivery]**&#x200B;で、**[!UICONTROL delivery]**&#x200B;を演算子&#x200B;**[!UICONTROL is equal to]**&#x200B;でドラッグ&amp;ドロップし、配信を値として選択します。
1. **[!UICONTROL Shortcuts]** **[!UICONTROL Delivery]**&#x200B;で、**[!UICONTROL type]**&#x200B;をドラッグ&amp;ドロップし、値として&#x200B;**[!UICONTROL Open]**&#x200B;をチェックします。
1. ルール間の演算子を&#x200B;**[!UICONTROL except]**&#x200B;として選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

## SMS配信の作成{#creating-a-sms-delivery}

1. 各セグメントの後にsms配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple sms]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. smsテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. smsのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. smsのレイアウトを作成するには、「**[!UICONTROL Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、smsをパーソナライズします。
詳しくは、[sms](../../channels/using/creating-an-sms-message.md)のデザインの節を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [メールチャネル](../../channels/using/creating-an-email.md)
