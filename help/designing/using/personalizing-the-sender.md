---
title: 送信者をパーソナライズする
seo-title: 送信者をパーソナライズする
description: 送信者をパーソナライズする
seo-description: メッセージの送信者の名前またはアドレスをパーソナライズする方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 7aa08d5d-9e6c-4c-4c- bff85368c2d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: personalizing- content
discoiquuid: 49532f6b-3cd0-4d03-932e- bcb7d05c74d4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Personalizing the sender{#personalizing-the-sender}

## Email sender {#email-sender}

To define the name of the sender which will appear in the header of messages sent, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon).

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]** このフィールドによって送信者名を入力できます。By default, the default **Sender name** block is automatically entered in the field. Adobe Campaign refers to the email channel configuration (from the advanced menu **[!UICONTROL Administration > Channels > Email > Email accounts]** via the Adobe Campaign logo) to designate this sender.

   You can change the sender name by clicking the **Sender name** block. このフィールドは編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

* **[!UICONTROL From: email address]** このセクションからはフィールドを編集できません。ダッシュボードから電子メールのプロパティを編集して変更できます。For more on this, see [List of email advanced parameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>ヘッダーパラメーターは空白にできません。電子メールの送信を許可するには、送信者のアドレスが必須です（RFC標準）。Adobe Campaignでは、入力した電子メールアドレスの構文をチェックします。

**関連トピック:**

* [パーソナライゼーションフィールドの挿入](../../designing/using/inserting-a-personalization-field.md)
* [コンテンツブロックの追加](../../designing/using/adding-a-content-block.md)
* [電子メールでの動的コンテンツの定義](../../designing/using/defining-dynamic-content-in-an-email.md)

## SMS sender {#sms-sender}

SMS送信者の名前をパーソナライズできます。For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
