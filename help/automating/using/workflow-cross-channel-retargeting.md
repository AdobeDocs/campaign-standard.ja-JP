---
title: メールを開封していないユーザーの再ターゲティング
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 4%

---


# 非開封者に新しい配信を送信する再ターゲティングワークフロー{#retargeting-delivery-to-non-openers}

顧客に電子メールを送信し、そのメールを開封しなかったユーザーに電子メールを送信できます。

1. で、 **[!UICONTROL Marketing Activities]**&#x200B;をクリック **[!UICONTROL Create]** してを選択し **[!UICONTROL Workflow]**&#x200B;ます。
1. ワークフローのタイプ **[!UICONTROL New Workflow]** として選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. ワークフローのプロパティを入力し、をクリックし **[!UICONTROL Create]**&#x200B;ます。

## Creating a query activity{#creating-a-query-activity}

1. /で、 **[!UICONTROL Activities]** クエリ **[!UICONTROL Targeting]**[](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを重複クリックします。
1. で、演算子 **[!UICONTROL Shortcuts]**&#x200B;を使用 **[!UICONTROL Profiles]** してドラッグ&amp;ドロップ **[!UICONTROL email]** し、選択し **[!UICONTROL is not empty]**&#x200B;ます。
1. で、値 **[!UICONTROL Shortcuts]**&#x200B;をドラッグ&amp;ドロップ **[!UICONTROL Profiles]** し、値 **[!UICONTROL no longer contact by email]** で選択し **[!UICONTROL no ]**&#x200B;ます。
1. クリック **[!UICONTROL Confirm]** .

![](assets/wf-complement-query.png)

## E メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後に [電子メール配信](../../automating/using/email-delivery.md) をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、「編集」 ![](assets/edit_darkgrey-24px.png) を選択します。
1. を選択 **[!UICONTROL Simple email]** し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. を選択 **[!UICONTROL Add an outbound transition without the population]** し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールテンプレートを選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのプロパティを入力し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのレイアウトを作成するには、[オン]をクリックし **[!UICONTROL Using the Email Designer]**&#x200B;ます。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、電子メールをパーソナライズします。詳細については、「電子メールの [デザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)」を参照してください。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. クリック **[!UICONTROL Save]** .

## クエリアクティビティでの非開封ユーザーのターゲット設定{#targeting-non-openers-in-a-query-activity}

1. >で、 **[!UICONTROL Activities]** 待機 **[!UICONTROL Execution]**[](../../automating/using/wait.md) アクティビティをドラッグ&amp;ドロップします。
1. にある「 」 **[!UICONTROL Duration]**&#x200B;をクリック ![](assets/duration-icon.png) し、1日を選択します。
1. / **[!UICONTROL Activities]** に **[!UICONTROL Targeting]**&#x200B;あるをドラッグ&amp;ドロップし **[!UICONTROL Query activity]**&#x200B;ます。
1. アクティビティを重複クリックします。
1. で、演算子 **[!UICONTROL Shortcuts]**&#x200B;をドラッグ&amp;ドロップ **[!UICONTROL Tracking Logs]** して使用し **[!UICONTROL exists]**&#x200B;ます。
1. >で、演算子 **[!UICONTROL Shortcuts]**&#x200B;を使用してドラッグ&amp;ドロップし、配信 **[!UICONTROL Delivery]****[!UICONTROL delivery]****[!UICONTROL is equal to]** を値として選択します。
1. >で、ドラッグ&amp;ドロップ **[!UICONTROL Shortcuts]**&#x200B;して値 **[!UICONTROL Delivery]**&#x200B;としてチェック **[!UICONTROL type]****[!UICONTROL Open]** します。
1. ルール間の演算子を「」として選択し **[!UICONTROL except]**&#x200B;ます。
1. クリック **[!UICONTROL Confirm]** .

## Creating a sms delivery{#creating-a-sms-delivery}

1. 各セグメントの後にsms配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、「編集」 ![](assets/edit_darkgrey-24px.png) を選択します。
1. を選択 **[!UICONTROL Simple sms]** し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. smsテンプレートを選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. smsプロパティを入力し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. smsのレイアウトを作成するには、[オン]をクリックし **[!UICONTROL Email Designer]**&#x200B;ます。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーでSMSをパーソナライズします。
詳細については、「smsの [設計](../../channels/using/creating-an-sms-message.md) 」を参照してください。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. クリック **[!UICONTROL Save]** .

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [E メールチャネル](../../channels/using/creating-an-email.md)
