---
title: 電子メールの件名と送信者の定義
seo-title: 電子メールの件名と送信者の定義
description: 電子メールの件名と送信者の定義
seo-description: 電子メールデザイナーで電子メールの件名と送信者を定義する方法を確認します。
page-status-flag: 非活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5847c89b97ede8b03e75d1d90f31c88ed5c8a84e

---


# 電子メールの件名と送信者の定義{#defining-the-subject-line-of-an-email}

The message subject is mandatory to prepare and send the message.

>[!NOTE]
>
>If the subject line is empty, a warning is displayed in the message dashboard and in the Email Designer.

To configure the email subject, go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

**To define the subject line of an email:**

1. Create an email.
1. Close homepage.
1. Go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

![](assets/email_designer_subject.png)

You can also add personalization fields, content blocks and dynamic content to the subject line by clicking the corresponding icons.

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

電子メールを編集する場合は、送信する前に別の件名を試して、開封率の見積もりを受け取ることができます。

This feature is disabled by default. It is enabled when the first model is imported. モデルは、特定の業界に固有のトレーニングデータセットの結果です。 Models allow the system to predict the open rate of the email when a new subject line is submitted.

>[!NOTE]
>
>This feature is available for email messages and for databases that contain English contents only. The trained model will be inconsistent and will lead to erroneous results if your instance contains emails in other languages. サブジェクトをテストするオプションは、モデルが既にインスタンスで使用可能な場合にのみ表示されます。

**関連トピック**

* [電子メールの件名行のテスト](../../sending/using/testing-subject-line-email.md)

## 電子メールの送信者 {#email-sender}

送信するメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナーのホームページのタブに移動します( **[!UICONTROL Properties]** ホームアイコンからアクセスできます)。

![](assets/delivery_content_edition16.png)

* このフ **[!UICONTROL From: name]** ィールドには、送信者名を入力できます。 デフォルトでは、デフォルトの **Sender name** blockが自動的にフィールドに入力されます。 Adobe Campaignは、（Adobe Campaignロゴを介して）電子メールチャネルの設定 **[!UICONTROL Administration > Channels > Email > Email accounts]** を参照し、この送信者を指定します。

   送信者名は、[送信者名]ブロックをクリックして **変更できます** 。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

* このセ **[!UICONTROL From: email address]** クションではフィールドを編集できません。 電子メールのプロパティをダッシュボードから編集することで変更できます。 詳しくは、電子メールの詳細パラ [メーターのリストを参照してください](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
