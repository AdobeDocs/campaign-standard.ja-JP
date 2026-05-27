---
title: メールを開封していないユーザーのリターゲティング
description: このユースケースでは、非オープナーをリターゲティングする方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
TQID: https://experienceleague.adobe.com/FmSP-ecHeXM-ozitQoL684ZAQC0tbuj3vprW06znCUw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 315
ht-degree: 43%

---

# 開封者以外のユーザーに新しい配信を送信するリターゲティングワークフロー{#retargeting-delivery-to-non-openers}

顧客にメールを送信してから、メールを開かなかった顧客にSMSを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## クエリアクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、「[クエリ](../../automating/using/query.md)」アクティビティをドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、演算子&#x200B;**[!UICONTROL is not empty]**&#x200B;で&#x200B;**[!UICONTROL email]**&#x200B;を選択します。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Profiles]**&#x200B;をドラッグ&amp;ドロップし、値&#x200B;**[!UICONTROL no]**&#x200B;を持つ&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;を選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後に[ メール配信](../../automating/using/email-delivery.md)をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. 「**[!UICONTROL Add an outbound transition without the population]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. メールのレイアウトを作成するには、「**[!UICONTROL Using the Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、メールをパーソナライズします。詳しくは、[メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

## クエリアクティビティ内の非開封者をターゲットにする{#targeting-non-openers-in-a-query-activity}

1. **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;で、[待機](../../automating/using/wait.md) アクティビティをドラッグ&amp;ドロップします。
1. **[!UICONTROL Duration]**&#x200B;で、![](assets/duration-icon.png)をクリックし、1日を選択します。
1. **[!UICONTROL Activities]**／**[!UICONTROL Targeting]** で、**[!UICONTROL Query activity]** をドラッグ＆ドロップします。
1. アクティビティをダブルクリックします。
1. **[!UICONTROL Shortcuts]**&#x200B;で、**[!UICONTROL Tracking Logs]**&#x200B;と演算子&#x200B;**[!UICONTROL exists]**&#x200B;をドラッグ&amp;ドロップします。
1. **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;で、演算子&#x200B;**[!UICONTROL is equal to]**&#x200B;を使用して&#x200B;**[!UICONTROL delivery]**&#x200B;をドラッグ&amp;ドロップし、配信を値として選択します。
1. **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;で、**[!UICONTROL type]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL Open]**&#x200B;を値としてチェックします。
1. ルール間の演算子を&#x200B;**[!UICONTROL except]**&#x200B;として選択します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

## sms配信の作成{#creating-a-sms-delivery}

1. 各セグメントの後にSMS配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Simple sms]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. sms テンプレートを選択し、**[!UICONTROL Next]**&#x200B;をクリックします。
1. sms プロパティを入力し、**[!UICONTROL Next]**&#x200B;をクリックします。
1. SMSのレイアウトを作成するには、**[!UICONTROL Email Designer]**&#x200B;をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各地域に特化したオファーでsmsをパーソナライズします。
詳細については、「[smsの設計](../../channels/using/creating-an-sms-message.md)」の節を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [メールチャネル](../../channels/using/creating-an-email.md)
