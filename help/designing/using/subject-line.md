---
title: 電子メールの件名行と送信者の定義
description: 電子メールデザイナーで電子メールの件名と送信者を定義する方法を確認します。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 10%

---


# 電子メールの件名行と送信者の定義{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

メッセージの件名は、メッセージの準備と送信を行うために必須です。

>[!NOTE]
>
>件名行が空の場合は、メッセージダッシュボードと電子メールデザイナーに警告が表示されます。

1. E メールの作成.
1. 電子メールデザイナホームページの **[!UICONTROL Properties]** タブに移動します（ホームアイコンからアクセスできます）。
1. Fill in the **[!UICONTROL Subject]** section.

   ![](assets/email_designer_subject.png)

1. 対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを件名行に追加することもできます。 For more on this, see [Personalization](../../designing/using/personalization.md).
1. 送信する前に、電子メールの開封率の見積もりを得るために、別の件名行を試すことができます。 詳しくは、「電子メールの件名行の [テスト](../../sending/using/testing-subject-line-email.md)」を参照してください。

## 電子メールの電子メール送信者の定義 {#email-sender}

送信されるメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナーホームページの **[!UICONTROL Properties]** タブに移動します（ホームアイコンからアクセスできます）。

![](assets/delivery_content_edition16.png)

* この **[!UICONTROL From: name]** フィールドには、送信者名を入力できます。 デフォルトでは、デフォルトの **送信者名** (Sender name)ブロックが自動的にフィールドに入力されます。 デフォルトの送信者の電子メールアドレスと送信者の名前は、詳細メニューの下にあるAdobe Campaignロゴから **[!UICONTROL Brands]** アクセスできるように定義され **[!UICONTROL Administration > Instance settings > Brand configuration]** ます。

   送信者の名前は、 **送信者の名前** ブロックをクリックして変更できます。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。 For more on this, see [Personalization](../../designing/using/personalization.md).

* このセクションでは **[!UICONTROL From: email address]** フィールドを編集できません。 ダッシュボードから電子メールのプロパティを編集することで、変更できます。 詳しくは、電子メールのアドバンスパラメーターの [リストを参照してください](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
