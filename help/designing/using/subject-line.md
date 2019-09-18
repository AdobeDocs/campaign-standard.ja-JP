---
title: 電子メールの件名と送信者の定義
seo-title: 電子メールの件名と送信者の定義
description: 電子メールの件名と送信者の定義
seo-description: 電子メールデザイナで電子メールの件名と送信者を定義する方法を説明します。
page-status-flag: 未活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: 編集，電子メールの内容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 29cbde1a6bb57526f626f2d1fef52695c50de8e6

---


# 電子メールの件名と送信者の定義{#defining-the-subject-line-of-an-email}

メッセージの件名は、メッセージの準備と送信に必須です。

>[!NOTE]
>
>件名行が空の場合、メッセージダッシュボードと電子メールデザイナに警告が表示されます。

電子メールの件名を設定するには、電子メー **[!UICONTROL Properties]** ルデザイナのホームページのタブ（ホームアイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。

**電子メールの件名を定義する手順は、次のとおりです**。

1. 電子メールを作成します。
1. ホームページを閉じます。
1. 電子メール·デ **[!UICONTROL Properties]** ザイナのホームページのタブ（ホーム·アイコンからアクセス可能）に移動し、セクションに入力 **[!UICONTROL Subject]** します。

![](assets/email_designer_subject.png)

対応するアイコンをクリックして、個人用設定フィールド、コンテンツブロック、および動的コンテンツを件名行に追加することもできます。

**関連トピック：**

* [個人用設定フィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックを追加する](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 予測対象行 {#predictive-subject-line}

電子メールを編集する場合は、送信する前に別の件名を試して、開放率の見積もりを得ることができます。

この機能は、デフォルトでは無効になっています。 最初のモデルをインポートするときに有効になります。 モデルは、特定の業界に固有のトレーニング·データ·セットの結果です。 モデルを使用すると、新しい件名行が送信されたときに、電子メールのオープン率を予測できます。

>[!NOTE]
>
>この機能は、電子メールメッセージや英語のコンテンツを含むデータベースに対してのみ使用できます。 訓練されたモデルは矛盾し、インスタンスに他の言語の電子メールが含まれている場合は、誤った結果が生じます。 サブジェクトをテストできるオプションは、モデルがインスタンスで既に使用可能な場合にのみ表示されます。

**関連トピック**

* [件名行のテスト](../../sending/using/testing-subject-line-email.md)

## 電子メール送信者 {#email-sender}

送信されたメッセージのヘッダーに表示される送信者の名前を定義するには、電子メールデザイナのホームページの **[!UICONTROL Properties]** タブ（「ホーム」アイコンからアクセス可能）に移動します。

![](assets/delivery_content_edition16.png)

* このフ **[!UICONTROL From: name]** ィールドには、送信者名を入力できます。 既定では、既定の[送信者名 **** ]ブロックがフィールドに自動的に入力されます。 Adobe Campaignは、この送信者を指定するために、電子メールチャネルの設定(Adobe Campaignロゴを使用し **[!UICONTROL Administration > Channels > Email > Email accounts]** た詳細メニューから)を参照します。

   送信者名を変更するには、[送信者名]ブロックをク **リックし** ます。 フィールドが編集可能になり、使用する名前を入力できます。

   このフィールドは個人用に設定できます。 これを行うには、送信者名の下のアイコンをクリックして、個人用設定フィールド、コンテンツブロック、および動的コンテンツを追加します。

* このセク **[!UICONTROL From: email address]** ションからフィールドを編集することはできません。 ダッシュボードから電子メールのプロパティを編集して、変更できます。 詳細については、「電子メールの詳細パ [ラメータの一覧」を参照してください](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>ヘッダーパラメーターを空にすることはできません。 送信者のアドレスは、電子メールの送信を許可するために必須です（RFC標準）。 Adobe Campaignは、入力した電子メールアドレスの構文を確認します。

**関連トピック：**

* [個人用設定フィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックを追加する](../../designing/using/personalization.md#adding-a-content-block)
* [電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)