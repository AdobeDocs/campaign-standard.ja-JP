---
solution: Campaign Standard
product: campaign
title: 電子メールの件名行と送信者の定義
description: 電子メールデザイナーで電子メールの件名と送信者を定義する方法を確認します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 11%

---


# 電子メール{#defining-the-subject-line-of-an-email}の件名行と送信者の定義

## 電子メールの件名行の定義{#subject-line}

メッセージの件名は、メッセージの準備と送信を行うために必須です。

>[!NOTE]
>
>件名行が空の場合は、メッセージダッシュボードと電子メールデザイナーに警告が表示されます。

1. E メールの作成.
1. 電子メールデザイナーホームページの&#x200B;**[!UICONTROL Properties]**&#x200B;タブに移動します（ホームアイコンからアクセスできます）。
1. **[!UICONTROL Subject]**&#x200B;セクションに入力します。

   ![](assets/email_designer_subject.png)

1. 対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを件名行に追加することもできます。 詳しくは、[パーソナライゼーション](../../designing/using/personalization.md)を参照してください。

## 電子メールの電子メール送信者の定義{#email-sender}

送信されるメッセージのヘッダーに表示される送信者の名前を定義するには、Email Designerホームページの&#x200B;**[!UICONTROL Properties]**&#x200B;タブに移動します（ホームアイコンからアクセスできます）。

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]**&#x200B;フィールドには、送信者名を入力できます。 デフォルトでは、デフォルトの&#x200B;**送信者名**&#x200B;ブロックが自動的にフィールドに入力されます。 デフォルトの送信者の電子メールアドレスと送信者の名前は、**[!UICONTROL Brands]**&#x200B;に定義されており、詳細設定メニュー&#x200B;**[!UICONTROL Administration > Instance settings > Brand configuration]**&#x200B;の下にあるAdobe Campaignロゴからアクセスできます。

   送信者名は、**送信者名**&#x200B;ブロックをクリックして変更できます。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。 詳しくは、[パーソナライゼーション](../../designing/using/personalization.md)を参照してください。

* **[!UICONTROL From: email address]**&#x200B;フィールドは、このセクションでは編集できません。 ダッシュボードから電子メールのプロパティを編集することで、変更できます。 詳しくは、[電子メールの詳細リスト](../../administration/using/configuring-email-channel.md#advanced-parameters)のパラメーターのを参照してください。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
