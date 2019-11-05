---
title: 「ワークフローの使用例：未開封者の再ターゲット設定」
description: 「ワークフローの使用例：未開封者の再ターゲット設定」
page-status-flag: 非活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'ワークフロー，ユースケース，クエリ，待機，配信 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローの使用例：未開封者に新しい配信を送信する再ターゲットワークフロー{#retargeting-delivery-to-non-openers}

顧客に電子メールを送り、そのメールを開封しなかった人に通知することができます。

1. で、を **[!UICONTROL Marketing Activities]**&#x200B;クリックし **[!UICONTROL Create]** てを選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** タイプとして選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## クエリーアクティビティの作成{#creating-a-query-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子を使用してドラッ **[!UICONTROL Profiles]** グ&amp;ドロ **[!UICONTROL email]** ップして選択しま **[!UICONTROL is not empty]**&#x200B;す。
1. で、 **[!UICONTROL Shortcuts]**&#x200B;値を使用してドラッグ&amp;ド **[!UICONTROL Profiles]** ロップ **[!UICONTROL no longer contact by email]** し、選択します **[!UICONTROL no ]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## E メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後ろに、をドラッ **[!UICONTROL Email delivery]** グ&amp;ドロップします。
1. アクティビティをクリックし、編集する ![](assets/edit_darkgrey-24px.png) 対象を選択します。
1. を選択し、 **[!UICONTROL Simple email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. を選択し、 **[!UICONTROL Add an outbound transition without the population]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、[オン]をクリックしま **[!UICONTROL Using the Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して電子メールをパーソナライズします。詳細については、「電子メールの [デザイン」を参照してくださ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)い。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. Click **[!UICONTROL Save]**.

## クエリアクティビティの非開封者をターゲットに設定する{#targeting-non-openers-in-a-query-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Execution]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Wait activity]**![](assets/wait.png)す。
1. で、 **[!UICONTROL Duration]**&#x200B;をクリックし ![](assets/duration-icon.png) て1日を選択します。
1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子を使用してドラッ **[!UICONTROL Tracking Logs]** グ&amp;ドロップしま **[!UICONTROL exists]**&#x200B;す。
1. &gt;で、演 **[!UICONTROL Shortcuts]**&#x200B;算子 **[!UICONTROL Delivery]**&#x200B;と共にドラッグ&amp;ド **[!UICONTROL delivery]** ロップし、配信を **[!UICONTROL is equal to]** 値として選択します。
1. &gt;で、ド **[!UICONTROL Shortcuts]**&#x200B;ラッグ&amp;ド **[!UICONTROL Delivery]**&#x200B;ロップし、値と **[!UICONTROL type]** してチェ **[!UICONTROL Open]** ックします。
1. ルール間の演算子を「」として選択しま **[!UICONTROL except]**&#x200B;す。
1. Click **[!UICONTROL Confirm]**.

## Creating a sms delivery{#creating-a-sms-delivery}

1. 各セグメントの後にSMS配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、編集する ![](assets/edit_darkgrey-24px.png) 対象を選択します。
1. を選択し、 **[!UICONTROL Simple sms]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. SMSテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. smsプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. SMSのレイアウトを作成するには、をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のオファーを使用して、SMSをパーソナライズします。
詳細については、「SMSのデザイン」 [を参照してください](../../channels/using/creating-an-sms-message.md)。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [クエリ](../../automating/using/query.md)
* [SMS 配信](../../automating/using/sms-delivery.md)
* [E メール配信](../../automating/using/email-delivery.md)
* [E メールチャネル](../../channels/using/creating-an-email.md)
