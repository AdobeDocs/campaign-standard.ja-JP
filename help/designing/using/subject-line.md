---
title: メールの件名と送信者の定義
description: メールDesignerでメールの件名と送信者を定義する方法を説明します。
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
ht-degree: 6%

---

# メールの件名と送信者の定義{#defining-the-subject-line-of-an-email}

## メールの件名の定義 {#subject-line}

メッセージの件名は、メッセージの準備と送信に必須です。

>[!NOTE]
>
>件名が空の場合、メッセージダッシュボードと電子メールDesignerに警告が表示されます。

1. メールを作成します。
1. メールDesignerのホームページの「**[!UICONTROL Properties]**」タブに移動します（「ホーム」アイコンからアクセスできます）。
1. 「**[!UICONTROL Subject]**」セクションに入力します。

   ![](assets/email_designer_subject.png)

1. 対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロック、動的コンテンツを件名に追加することもできます。 詳しくは、[Personalization](../../designing/using/personalization.md) を参照してください。

## メールの送信者の定義 {#email-sender}

送信されるメッセージのヘッダーに表示される送信者名を定義するには、メールDesignerのホームページの「**[!UICONTROL Properties]**」タブ（「ホーム」アイコンからアクセスできます）に移動します。

![](assets/delivery_content_edition16.png)

* 「**[!UICONTROL From: name]**」フィールドには、送信者名を入力できます。 デフォルトでは、デフォルトの **送信者名** ブロックがフィールドに自動的に入力されます。 デフォルトの送信者のメールアドレスと送信者名は、の詳細メニューでAdobe Campaign ロゴからアクセスできる **[!UICONTROL Brands]** で定義され **[!UICONTROL Administration > Instance settings > Brand configuration]** す。

  送信者名を変更するには、「送信者名 **ブロックをクリックし** す。 その後、フィールドが編集可能になり、使用する名前を入力できます。

  このフィールドはパーソナライズできます。 これを行うには、送信者名の下にあるアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロック、動的コンテンツを追加します。 詳しくは、[Personalization](../../designing/using/personalization.md) を参照してください。

* このセクションから **[!UICONTROL From: email address]** フィールドを編集することはできません。 ダッシュボードからメールのプロパティを編集することで変更できます。 詳しくは、[&#x200B; メールの詳細設定パラメーターのリスト &#x200B;](../../administration/using/configuring-email-channel.md#advanced-parameters) を参照してください。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。メールの送信を許可するには、送信者のアドレスが必須です（RFC 標準）。 入力したメールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [メールの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
