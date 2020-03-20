---
title: 電子メールの件名行と送信者の定義
description: 電子メールデザイナで電子メールの件名と送信者を定義する方法を確認します。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---


# 電子メールの件名行と送信者の定義{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

メッセージの件名は、メッセージの準備と送信を行うために必須です。

>[!NOTE]
>
>件名行が空の場合は、メッセージダッシュボードと電子メールデザイナーに警告が表示されます。

1. 電子メールを作成します。
1. 電子メールデザ **[!UICONTROL Properties]** イナのホームページのタブに移動します（ホームアイコンからアクセスできます）。
1. セクションに入力 **[!UICONTROL Subject]** します。

   ![](assets/email_designer_subject.png)

1. また、対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを件名行に追加することもできます。 For more on this, see [Personalization](../../designing/using/personalization.md).
1. 送信する前に、電子メールの開封率の見積もりを得るために、異なる件名を試すことができます。 詳しくは、「電子メールの件 [名行のテスト」を参照してください](../../sending/using/testing-subject-line-email.md)。

## 電子メールの電子メール送信者の定義 {#email-sender}

送信するメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナーのホームページのタブに移動します( **[!UICONTROL Properties]** ホームアイコンからアクセスできます)。

![](assets/delivery_content_edition16.png)

* このフ **[!UICONTROL From: name]** ィールドには、送信者名を入力できます。 デフォルトでは、デフォルトの **Sender name** blockが自動的にフィールドに入力されます。 デフォルトの送信者の電子メールアドレスと送信者の名前は、アドバンスメ **[!UICONTROL Brands]** ニューの下にあるAdobe Campaignロゴを使用してアクセス可能な形で定義されま **[!UICONTROL Administration > Instance settings > Brand configuration]** す。

   送信者名は、[送信者名]ブロックをクリックし **て変更できます** 。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。 For more on this, see [Personalization](../../designing/using/personalization.md).

* このセク **[!UICONTROL From: email address]** ションではフィールドを編集できません。 電子メールのプロパティをダッシュボードから編集することで変更できます。 詳しくは、電子メールの詳細パラメ [ーターのリストを参照してくださ](../../administration/using/configuring-email-channel.md#advanced-parameters)い。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
