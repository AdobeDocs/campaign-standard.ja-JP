---
title: 「ワークフローのユースケース:非公開者の再ターゲット」
seo-title: 「ワークフローのユースケース:非公開者の再ターゲット」
description: 「ワークフローのユースケース:非公開者の再ターゲット」
seo-description: 「ワークフローのユースケース:非公開者の再ターゲット」
page-status-flag: 決して活性化されていない
uuid: 396a3de1-6fa-4385- ac9f-15fdee5a366
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc- a1ad-8a2f5d409
context-tags: 'ワークフロー、ユースケース、クエリ、待機、配信 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# ワークフローのユースケース:新しい配送を非公開者に送信するワークフローの再ターゲット{#retargeting-delivery-to-non-openers}

お客様に電子メールを送信し、メールを開いていない人にはSMSを送信できます。

1. で **[!UICONTROL Marketing Activities]**、をクリック **[!UICONTROL Create]** して選択 **[!UICONTROL Workflow]**&#x200B;します。
1. ワークフロータイプ **[!UICONTROL New Workflow]** として選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. ワークフローのプロパティを入力し、をクリック **[!UICONTROL Create]**&#x200B;します。

## クエリアクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Targeting]**、をドラッグアンドドロップ **[!UICONTROL Query activity]**![](assets/query.png)します。
1. アクティビティをダブルクリックします。
1. で **[!UICONTROL Shortcuts]**、ドラッグアンドドロップ **[!UICONTROL Profiles]** してオペレータ **[!UICONTROL email]** を選択 **[!UICONTROL is not empty]**&#x200B;します。
1. で **[!UICONTROL Shortcuts]**、ドラッグアンドドロップ **[!UICONTROL Profiles]** して値 **[!UICONTROL no longer contact by email]** を選択 **[!UICONTROL no ]**&#x200B;します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

## 電子メール配信の作成{#creating-an-email-delivery}

1. 各セグメントの後に****[!UICONTROL Email delivery]電子メール配信をドラッグアンドドロップします。
1. アクティビティをクリックし、編集 ![](assets/edit_darkgrey-24px.png) するように選択します。
1. を選択 **[!UICONTROL Simple email]** してをクリック **[!UICONTROL Next]**&#x200B;します。
1. を選択 **[!UICONTROL Add an outbound transition without the population]** してをクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールテンプレートを選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのプロパティを入力し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メール **の電子メールオファーの名前を変更**&#x200B;します。
1. 電子メールのレイアウトを作成するには、をクリック **[!UICONTROL Using the Email Designer]**&#x200B;します。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有の特典を電子メールでカスタマイズします。詳細については、電子メール [のデザインを](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)参照してください。
1. クリック **[!UICONTROL Preview]** すると、レイアウトが確認されます。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

## クエリアクティビティで非公開者を対象にする{#targeting-non-openers-in-a-query-activity}

1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Execution]**、をドラッグアンドドロップ **[!UICONTROL Wait activity]**![](assets/wait.png)します。
1. で **[!UICONTROL Duration]**、をクリック ![](assets/duration-icon.png) して1日を選択します。
1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Targeting]**、をドラッグアンドドロップ **[!UICONTROL Query activity]**![](assets/query.png)します。
1. アクティビティをダブルクリックします。
1. で **[!UICONTROL Shortcuts]**、ドラッグアンドドロップ **[!UICONTROL Tracking Logs]** と操作を **[!UICONTROL exists]**&#x200B;行います。
1. **[!UICONTROL Shortcuts]**&gt;&gt; **[!UICONTROL Delivery]**&#x200B;で、オペレータ **[!UICONTROL delivery]****[!UICONTROL is equal to]** とともにドラッグアンドドロップして、配送を値として選択します。
1. **[!UICONTROL Shortcuts]**&gt;&gt; **[!UICONTROL Delivery]**&#x200B;で、ドラッグアンドドロップ **[!UICONTROL type]** して値としてチェック **[!UICONTROL Open]** します。
1. ルール間の演算子を選択 **[!UICONTROL except]**&#x200B;します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

## SMS配信の作成{#creating-a-sms-delivery}

1. 各セグメントの後に、SMS配信をドラッグアンドドロップします。
1. アクティビティをクリックし、編集 ![](assets/edit_darkgrey-24px.png) するように選択します。
1. を選択 **[!UICONTROL Simple sms]** してをクリック **[!UICONTROL Next]**&#x200B;します。
1. SMSテンプレートを選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. SMSプロパティを入力し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. SMSのレイアウトを作成するには、をクリック **[!UICONTROL Email Designer]**&#x200B;します。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. 各場所に固有の特典を使用して、SMSをカスタマイズします。
詳細については、"SMSの [設計](../../channels/using/creating-an-sms-message.md)」を参照してください。
1. クリック **[!UICONTROL Preview]** すると、レイアウトが確認されます。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

**関連トピック:**

* [クエリー](../../automating/using/query.md)
* [SMS配信](../../automating/using/sms-delivery.md)
* [Eメール配信](../../automating/using/email-delivery.md)
* [Eメールチャネル](../../channels/using/creating-an-email.md)
