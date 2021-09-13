---
title: Eメールの件名行と送信者の定義
description: EメールデザイナーでEメールの件名行と送信者を定義する方法を説明します。
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

# Eメールの件名行と送信者の定義{#defining-the-subject-line-of-an-email}

## Eメールの件名行の定義 {#subject-line}

メッセージの件名は、メッセージの準備と送信に必須です。

>[!NOTE]
>
>件名行が空の場合は、メッセージダッシュボードとEメールデザイナーに警告が表示されます。

1. メールの作成.
1. Eメールデザイナーホームページの「**[!UICONTROL Properties]**」タブに移動します（ホームアイコンからアクセス可能）。
1. **[!UICONTROL Subject]**&#x200B;セクションに入力します。

   ![](assets/email_designer_subject.png)

1. 対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを件名行に追加することもできます。 詳しくは、[パーソナライゼーション](../../designing/using/personalization.md)を参照してください。

## EメールのEメール送信者の定義 {#email-sender}

送信するメッセージのヘッダーに表示される送信者の名前を定義するには、Eメールデザイナーホームページ（ホームアイコンからアクセス可能）の「**[!UICONTROL Properties]**」タブに移動します。

![](assets/delivery_content_edition16.png)

* 「**[!UICONTROL From: name]**」フィールドには、送信者名を入力できます。 デフォルトでは、「**送信者名**」ブロックが自動的にフィールドに入力されます。 デフォルトの送信者Eメールアドレスと送信者名は、詳細設定メニュー&#x200B;**[!UICONTROL Administration > Instance settings > Brand configuration]**&#x200B;のAdobe Campaignのロゴからアクセスできる&#x200B;**[!UICONTROL Brands]**&#x200B;に定義されています。

   送信者名は、**送信者名**&#x200B;ブロックをクリックして変更できます。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これをおこなうには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。 詳しくは、[パーソナライゼーション](../../designing/using/personalization.md)を参照してください。

* **[!UICONTROL From: email address]**&#x200B;フィールドは、このセクションからは編集できません。 電子メールのプロパティをダッシュボードから編集することで、変更できます。 詳しくは、[Eメールの詳細設定パラメーターのリスト](../../administration/using/configuring-email-channel.md#advanced-parameters)を参照してください。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [Eメールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
