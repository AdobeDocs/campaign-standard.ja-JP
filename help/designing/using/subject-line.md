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
content-type: 参照
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0cf4807fc3d617b0c5ca33705b6344d1f3994ab3

---


# Defining the subject line and the sender of an email{#defining-the-subject-line-of-an-email}

The message subject is mandatory to prepare and send the message.

>[!NOTE]
>
>件名行が空の場合は、メッセージダッシュボードと電子メールデザイナーに警告が表示されます。

電子メールの件名を設定するには、電子メールデザ **[!UICONTROL Properties]** イナーのホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。

**To define the subject line of an email:**

1. 電子メールを作成します。
1. ホームページを閉じます。
1. 電子メールデ **[!UICONTROL Properties]** ザイナのホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。

![](assets/email_designer_subject.png)

また、対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを件名行に追加することもできます。

**関連トピック：**

* [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

When editing an email, you can try out different subject lines and get an estimation of its open rate before you send it.

This feature is disabled by default. It is enabled when the first model is imported. A model is the result of training data sets specific to a given industry. Models allow the system to predict the open rate of the email when a new subject line is submitted.

>[!NOTE]
>
>This feature is available for email messages and for databases that contain English contents only. トレーニングを受けたモデルは一貫性がなく、インスタンスに他の言語の電子メールが含まれている場合は、誤った結果を招きます。 サブジェクトをテストするオプションは、モデルが既にインスタンスで使用可能な場合にのみ表示されます。

**関連トピック**

* [件名行のテスト](../../sending/using/testing-subject-line-email.md)

## 電子メールの送信者 {#email-sender}

送信するメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナーのホームページのタブに移動します( **[!UICONTROL Properties]** ホームアイコンからアクセスできます)。

![](assets/delivery_content_edition16.png)

* このフ **[!UICONTROL From: name]** ィールドには、送信者名を入力できます。 デフォルトでは、デフォルトの **Sender name** blockが自動的にフィールドに入力されます。 Adobe Campaignは、（Adobe Campaignロゴを介して）電子メールチャネルの設定 **[!UICONTROL Administration > Channels > Email > Email accounts]** を参照し、この送信者を指定します。

   送信者名は、[送信者名]ブロックをクリックして **変更できます** 。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

* このセ **[!UICONTROL From: email address]** クションではフィールドを編集できません。 電子メールのプロパティをダッシュボードから編集することで変更できます。 詳しくは、電子メールの詳細パラ [メーターのリストを参照してください](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>ヘッダーパラメーターは空にできません。 送信者のアドレスは、電子メールの送信を許可するために必須です（RFC標準）。 Adobe Campaignは、入力された電子メールアドレスの構文を確認します。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)