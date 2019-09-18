---
title: '"ワークフローの使用例：非開店者をリターゲット»'
seo-title: '"ワークフローの使用例：非開店者をリターゲット»'
description: '"ワークフローの使用例：非開店者をリターゲット»'
seo-description: '"ワークフローの使用例：非開店者をリターゲット»'
page-status-flag: 未活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'ワークフロー，ユースケース，クエリ，待機，配信 '
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# ワークフローの使用例：未開封者に新しい配送を送信するワークフローを再ターゲットする{#retargeting-delivery-to-non-openers}

お客様にメールを送信し、メールを開かなかった人にメールを送信できます。

1. で、をク **[!UICONTROL Marketing Activities]**&#x200B;リックして **[!UICONTROL Create]** を選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** の種類としてを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## クエリアクティビティの作成{#creating-a-query-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子を使用してドラ **[!UICONTROL Profiles]** ッグアン **[!UICONTROL email]** ドドロップし、選択します **[!UICONTROL is not empty]**。
1. で、値 **[!UICONTROL Shortcuts]**&#x200B;を使用してドラ **[!UICONTROL Profiles]** ッグアン **[!UICONTROL no longer contact by email]** ドドロップし、選択します **[!UICONTROL no ]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 電子メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後ろにをドラ **[!UICONTROL Email delivery]** ッグ&amp;ドロップします。
1. アクティビティをクリックし、編集するア ![](assets/edit_darkgrey-24px.png) クティビティを選択します。
1. を選択し、 **[!UICONTROL Simple email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. を選択し、 **[!UICONTROL Add an outbound transition without the population]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、をクリックしま **[!UICONTROL Using the Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のサービスを使用して、電子メールをパーソナライズします。詳細については、電子メールのデザ [インを参照してくださ](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)い。
1. レイアウトを **[!UICONTROL Preview]** 確認するには、をクリックします。
1. Click **[!UICONTROL Save]**.

## クエリアクティビティの非開始者をターゲットにする{#targeting-non-openers-in-a-query-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Execution]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Wait activity]**![](assets/wait.png)す。
1. で、を **[!UICONTROL Duration]**&#x200B;クリックし ![](assets/duration-icon.png) て1日を選択します。
1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Targeting]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Query activity]**![](assets/query.png)す。
1. アクティビティをダブルクリックします。
1. で、演 **[!UICONTROL Shortcuts]**&#x200B;算子と共にドラ **[!UICONTROL Tracking Logs]** ッグアンドドロップしま **[!UICONTROL exists]**&#x200B;す。
1. &gt;で、 **[!UICONTROL Shortcuts]**&#x200B;演算子と共にドラッ **[!UICONTROL Delivery]**&#x200B;グ·アンド·ドロ **[!UICONTROL delivery]****[!UICONTROL is equal to]** ップし、搬送を値として選択します。
1. &gt;で、ドラ **[!UICONTROL Shortcuts]**&#x200B;ッグアン **[!UICONTROL Delivery]**&#x200B;ドドロップし、値と **[!UICONTROL type]** してチェ **[!UICONTROL Open]** ックします。
1. ルール間の演算子をとして選択しま **[!UICONTROL except]**&#x200B;す。
1. Click **[!UICONTROL Confirm]**.

## SMS配信の作成{#creating-a-sms-delivery}

1. 各セグメントの後に、SMS配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、編集するア ![](assets/edit_darkgrey-24px.png) クティビティを選択します。
1. を選択し、 **[!UICONTROL Simple sms]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. SMSテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. smsプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 通知のレイアウトを作成するには、をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有のサービスを使用して、SMSをカスタマイズします。
詳細は、「 SMSの設計」を参 [照してください](../../channels/using/creating-an-sms-message.md)。
1. レイアウトを **[!UICONTROL Preview]** 確認するには、をクリックします。
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**関連トピック：**

* [クエリ](../../automating/using/query.md)
* [SMS配信](../../automating/using/sms-delivery.md)
* [電子メール配信](../../automating/using/email-delivery.md)
* [電子メールチャネル](../../channels/using/creating-an-email.md)
