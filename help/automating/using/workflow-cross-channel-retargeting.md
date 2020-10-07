---
title: メールを開封していないユーザーのリターゲティング
description: この使用例では、非開封者の再ターゲティング方法を示します。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---


# Retargeting workflow sending a new delivery to non-openers{#retargeting-delivery-to-non-openers}

顧客に電子メールを送信し、そのメールを開封しなかったユーザーに電子メールを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## Creating a query activity{#creating-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no ]**.
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## E メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後に [電子メール配信](../../automating/using/email-delivery.md) をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. 「**[!UICONTROL Add an outbound transition without the population]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Using the Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、電子メールをパーソナライズします。詳細については、「電子メールの [デザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)」を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

## クエリアクティビティでの非開封ユーザーのターゲット設定{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Wait](../../automating/using/wait.md) activity.
1. にある「 」 **[!UICONTROL Duration]**&#x200B;をクリック ![](assets/duration-icon.png) し、1日を選択します。
1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、**[!UICONTROL Query activity]** をドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. で、演算子 **[!UICONTROL Shortcuts]**&#x200B;をドラッグ&amp;ドロップ **[!UICONTROL Tracking Logs]** して使用し **[!UICONTROL exists]**&#x200B;ます。
1. >で、演算子 **[!UICONTROL Shortcuts]**&#x200B;を使用してドラッグ&amp;ドロップし、配信 **[!UICONTROL Delivery]****[!UICONTROL delivery]****[!UICONTROL is equal to]** を値として選択します。
1. >で、ドラッグ&amp;ドロップ **[!UICONTROL Shortcuts]**&#x200B;して値 **[!UICONTROL Delivery]**&#x200B;としてチェック **[!UICONTROL type]****[!UICONTROL Open]** します。
1. ルール間の演算子を「」として選択し **[!UICONTROL except]**&#x200B;ます。
1. 「**[!UICONTROL Confirm]**」をクリックします。

## Creating a sms delivery{#creating-a-sms-delivery}

1. 各セグメントの後にsms配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple sms]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. Select an sms template and click **[!UICONTROL Next]**.
1. Enter the sms properties and click **[!UICONTROL Next]**.
1. To create the layout of your sms, click on **[!UICONTROL Email Designer]**.
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーでSMSをパーソナライズします。
詳細については、「smsの [設計](../../channels/using/creating-an-sms-message.md) 」を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [E メールチャネル](../../channels/using/creating-an-email.md)
