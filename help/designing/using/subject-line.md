---
title: 電子メールの件名と送信者の定義
description: 電子メールデザイナーで電子メールの件名と送信者を定義する方法を確認します。
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
source-git-commit: 259f7033310982298024462c0134989404c096f4

---


# 電子メールの件名と送信者の定義{#defining-the-subject-line-of-an-email}

メッセージの件名は、メッセージの準備と送信を行うために必須です。

>[!NOTE]
>
>件名行が空の場合は、メッセージダッシュボードと電子メールデザイナーに警告が表示されます。

電子メールの件名を設定するには、電子メールデザ **[!UICONTROL Properties]**イナーのホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力**[!UICONTROL Subject]** します。

**電子メールの件名行を定義するには**:

1. 電子メールを作成します。
1. ホームページを閉じます。
1. 電子メールデ **[!UICONTROL Properties]**ザイナのホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力**[!UICONTROL Subject]** します。

![](assets/email_designer_subject.png)

また、対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを件名行に追加することもできます。

## 予測件名行 {#predictive-subject-line}

電子メールを編集する場合は、送信する前に別の件名を試して、開封率の見積もりを受け取ることができます。

この機能はデフォルトで無効になっています。 最初のモデルが読み込まれると有効になります。 モデルは、特定の業界に固有のトレーニングデータセットの結果です。 モデルを使用すると、新しい件名行が送信された場合の電子メールの開封率を予測できます。

>[!NOTE]
>
>この機能は、電子メールメッセージおよび英語のコンテンツのみを含むデータベースで使用できます。 トレーニングを受けたモデルは一貫性がなく、インスタンスに他の言語の電子メールが含まれている場合は、誤った結果を招きます。 サブジェクトをテストするオプションは、モデルが既にインスタンスで使用可能な場合にのみ表示されます。

**関連トピック**

* [電子メールの件名行のテスト](../../sending/using/testing-subject-line-email.md)

## 電子メールの電子メール送信者の定義 {#email-sender}

送信するメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナーのホームページのタブに移動します( **[!UICONTROL Properties]**ホームアイコンからアクセスできます)。

![](assets/delivery_content_edition16.png)

* このフ **[!UICONTROL From: name]**ィールドには、送信者名を入力できます。 デフォルトでは、デフォルトの** Sender name **blockが自動的にフィールドに入力されます。 デフォルトの送信者の電子メールアドレスと送信者名は、アドバンスメ**[!UICONTROL Brands]** ニューの下にあるAdobe Campaignロゴを使用してアクセス可能な形で定義されま **[!UICONTROL Administration > Instance settings > Brand configuration]**す。

   送信者名は、[送信者名]ブロックをクリックして **変更できます** 。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドはパーソナライズできます。 これを行うには、送信者名の下のアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを追加します。

* このセ **[!UICONTROL From: email address]**クションではフィールドを編集できません。 電子メールのプロパティをダッシュボードから編集することで変更できます。 詳しくは、電子メールの詳細パラ[メーターのリストを参照してください](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>ヘッダーパラメーターの値は省略できません。送信者のアドレスは、E メールを送信するための必須情報です（RFC 標準規格）。入力した E メールアドレスの形式はチェックされます。

**関連トピック：**

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
