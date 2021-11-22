---
title: E メールの件名行と送信者の定義
description: E メールデザイナーで E メールの件名行と送信者を定義する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 11%

---

# E メールの件名行と送信者の定義{#defining-the-subject-line-of-an-email}

## E メールの件名行の定義 {#subject-line}

メッセージの件名は、メッセージの準備と送信に必須です。

>[!NOTE]
>
>件名行が空の場合、警告がメッセージダッシュボードと E メールデザイナーに表示されます。

1. メールの作成.
1. 次に進みます。 **[!UICONTROL Properties]** Email Designer ホームページの「 」タブ（ホームアイコンからアクセス可能）
1. 次の項目に入力： **[!UICONTROL Subject]** 」セクションに入力します。

   ![](assets/email_designer_subject.png)

1. 対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロック、動的コンテンツを件名行に追加することもできます。 詳しくは、 [パーソナライズ](../../designing/using/personalization.md).

## E メールの E メール送信者の定義 {#email-sender}

送信するメッセージのヘッダーに表示される送信者の名前を定義するには、 **[!UICONTROL Properties]** Email Designer ホームページの「 」タブ（ホームアイコンからアクセス可能）

![](assets/delivery_content_edition16.png)

* この **[!UICONTROL From: name]** 「 」フィールドには、送信者名を入力できます。 デフォルトでは、 **送信者名** ブロックが自動的に「 」フィールドに入力されます。 デフォルトの送信者 E メールアドレスと送信者名は、 **[!UICONTROL Brands]** 詳細設定メニューのAdobe Campaignロゴからアクセス可能 **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   送信者名を変更するには、 **送信者名** ブロック フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これをおこなうには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロック、動的コンテンツを追加します。 詳しくは、 [パーソナライズ](../../designing/using/personalization.md).

* この **[!UICONTROL From: email address]** このセクションからはフィールドを編集できません。 電子メールを変更するには、電子メールのダッシュボードからプロパティを編集します。 詳しくは、 [E メールの詳細設定パラメーターのリスト](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [E メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
