---
solution: Campaign Standard
product: campaign
title: メールを開封していないユーザーのリターゲティング
description: この使用例では、非開封者の再ターゲティング方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 38%

---


# 非開封者に新しい配信を送信する再ターゲットワークフロー{#retargeting-delivery-to-non-openers}

顧客に電子メールを送信し、そのメールを開封しなかったユーザーに電子メールを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## クエリアクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、演算子&#x200B;**[!UICONTROL is not empty]**&#x200B;を使用して&#x200B;**[!UICONTROL email]**&#x200B;を選択します。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL no ]**&#x200B;の値で&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;を選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## E メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後に[電子メール配信](../../automating/using/email-delivery.md)をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. 「**[!UICONTROL Add an outbound transition without the population]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Using the Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、電子メールをパーソナライズします。詳細については、[電子メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

## クエリアクティビティの非開封ユーザーをターゲットに設定{#targeting-non-openers-in-a-query-activity}

1. **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;で、[Wait](../../automating/using/wait.md)アクティビティをドラッグ&amp;ドロップします。
1. **[!UICONTROL Duration]**&#x200B;で![](assets/duration-icon.png)をクリックし、1日を選択します。
1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、**[!UICONTROL Query activity]** をドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Tracking Logs]**&#x200B;をドラッグ&amp;ドロップし、演算子&#x200B;**[!UICONTROL exists]**&#x200B;を付けます。
1. **[!UICONTROL Shortcuts]** **[!UICONTROL Delivery]**&#x200B;で、**[!UICONTROL delivery]**&#x200B;を演算子&#x200B;**[!UICONTROL is equal to]**&#x200B;と共にドラッグ&amp;ドロップし、配信を値として選択します。
1. **[!UICONTROL Shortcuts]** **[!UICONTROL Delivery]**&#x200B;に&#x200B;**[!UICONTROL type]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL Open]**&#x200B;を値としてチェックします。
1. ルール間の演算子を&#x200B;**[!UICONTROL except]**&#x200B;として選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

## sms配信の作成{#creating-a-sms-delivery}

1. 各セグメントの後にsms配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple sms]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. smsテンプレートを選択し、**[!UICONTROL Next]**&#x200B;をクリックします。
1. smsプロパティを入力し、**[!UICONTROL Next]**&#x200B;をクリックします。
1. smsのレイアウトを作成するには、**[!UICONTROL Email Designer]**&#x200B;をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーでSMSをパーソナライズします。
詳細については、「[sms](../../channels/using/creating-an-sms-message.md)のデザイン」の節を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [E メールチャネル](../../channels/using/creating-an-email.md)
