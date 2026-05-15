---
title: 電子メールの件名と送信者を定義する
description: 電子メール Designerで、件名と電子メールの送信者を定義する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
TQID: https://experienceleague.adobe.com/yT1UWD2C-BxfMymuwxE0vL3dYIOnnAjTf3O8Owx2S4g
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 12%

---

# 電子メールの件名と送信者を定義する{#defining-the-subject-line-of-an-email}

## メールの件名の定義 {#subject-line}

メッセージの件名は、メッセージを準備して送信するために必須です。

>[!NOTE]
>
>件名が空の場合、メッセージダッシュボードと電子メールDesignerに警告が表示されます。

1. メールの作成。
1. 電子メールDesignerのホームページの「**[!UICONTROL Properties]**」タブに移動します（ホームアイコンからアクセスできます）。
1. 「**[!UICONTROL Subject]**」セクションに入力します。

   ![](assets/email_designer_subject.png)

1. 対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロック、動的コンテンツを件名に追加することもできます。 詳しくは、[Personalization](../../designing/using/personalization.md)を参照してください。

## メールのメール送信者の定義 {#email-sender}

送信されたメッセージのヘッダーに表示される送信者の名前を定義するには、「メールDesigner」ホームページの「**[!UICONTROL Properties]**」タブに移動します（ホームアイコンからアクセスできます）。

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]** フィールドでは、送信者名を入力できます。 デフォルトでは、デフォルトの&#x200B;**送信者名** ブロックがフィールドに自動的に入力されます。 デフォルトの送信者の電子メールアドレスと送信者名は、詳細メニュー&#x200B;**[!UICONTROL Administration > Instance settings > Brand configuration]**&#x200B;の下にあるAdobe Campaign ロゴを介してアクセス可能な&#x200B;**[!UICONTROL Brands]**&#x200B;で定義されています。

  送信者の名前を変更するには、**送信者の名前** ブロックをクリックします。 その後、フィールドは編集可能になり、使用する名前を入力できます。

  このフィールドはパーソナライズできます。 これには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロック、動的コンテンツを追加できます。 詳しくは、[Personalization](../../designing/using/personalization.md)を参照してください。

* このセクションから&#x200B;**[!UICONTROL From: email address]** フィールドを編集できません。 ダッシュボードからメールのプロパティを編集することで、変更できます。 詳しくは、[&#x200B; メールの詳細パラメーターのリスト &#x200B;](../../administration/using/configuring-email-channel.md#advanced-parameters)を参照してください。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。 送信者のアドレスは、メールを送信するための必須情報です（RFC 標準規格）。 入力したメールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
