---
title: E メールのレンダリング
description: 電子メールレンダリング機能を見つけます。
page-status-flag: 非活性化の
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: 準備とテストのメッセージ
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# E メールのレンダリング{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

The mobile, messaging and webmail clients available for **Email rendering** in Adobe Campaign are listed on the Litmus [website](https://litmus.com/email-testing) (click **View all email clients**).

## 電子メールレンダリングレポートの確認 {#checking-the-email-rendering-report}

E メール配信を作成し、そのコンテンツとターゲット母集団を定義したら、以下の手順に従います。

1. 「オーディエ **ンス** 」をクリックしてタブにアク **[!UICONTROL Test profiles]** セスします。

   ![](assets/email_rendering_05.png)

1. クエリエディターを使用して、 **Emailレンダリングで使用するテストプロファイルなど、使用するテストプロファイルを定** 義します。 テストプロ [ファイルについてを参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)い。

   ![](assets/email_rendering_06.png)

1. クエリを確認して確認し、変更を保存します。
1. アクションバ **[!UICONTROL Test]** ーのボタンをクリックします。

   ![](assets/email_rendering_07.png)

1. このオプションを選 **[!UICONTROL Email rendering]** 択し、をクリックしま **[!UICONTROL OK]**&#x200B;す。

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >このオ **[!UICONTROL Proof + Email rendering]** プションを使用すると、校正を送信し、電子メールレンダリング機能を同時に使用できます。 メッセージを配達確認の受信者によって承認させると同時に、対象となる受信トレイに応じて、メッセージの受信方法をテストできます。 この場合は、「Proof test profiles」も選択する必要があります。 テストプロ [ファイルについてを参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)い。

   テスト配信が送信されます。

1. レンダリングサムネールは、メッセージの送信後数分で使用できます。 これらにアクセスするには、ドロ **[!UICONTROL Proofs]** ップダウンリスト **[!UICONTROL Summary]** でを選択します。

   ![](assets/email_rendering_03.png)

1. リストでア **[!UICONTROL Proofs]** イコンをクリック **[!UICONTROL Access email rendering]** します。

   ![](assets/email_rendering_04.png)

専用の電子メールレンダリングレポートが表示されます。 電子メールレ [ンダリングレポートの説明を参照してくださ](#email-rendering-report-description)い。

**関連トピック**：

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [テストプロファイルの管理と校正の送信](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [クエリエディター](../../automating/using/editing-queries.md#about-query-editor)

## 電子メールレンダリングレポートの説明 {#email-rendering-report-description}

このレポートは、受信者に表示される電子メールのレンダリングを表示します。 電子メールのレンダリングは、受信者が電子メール配信を開く方法によって異なる場合があります。」をクリックします。

>[!NOTE]
>
>使用できるレンダリングの数は、ライセンス契約に記載されています。Each delivery with **Email rendering** enabled decreases your available renderings (known as tokens) by one. Litmusクライアントの場合は、独自のLitmusアカウントを使用して、Adobe Campaignで電子メールレンダリングをプロビジョニングおよび使用できます。 詳しくは、アドビのアカウント担当者にお問い合わせください。

レポート概要には、受信済みメッセージ、不要なメッセージ（スパム）、受信されていないメッセージまたは受信が保留されているメッセージの数が表示されます。

![](assets/inbox_rendering_report.png)

The report is divided into three parts: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, and **[!UICONTROL Webmails]**. レポートを下へスクロールすると、これらの 3 つのカテゴリにグループ化されたすべてのレンダリングが表示されます。

![](assets/inbox_rendering_report_3.png)

各レポートの詳細を表示するには、対応するカードをクリックします。選択した受信方法のレンダリングが表示されます。

![](assets/inbox_rendering_report_2.png)

このタ **[!UICONTROL Technical data]** ブでは、受信日や取得日、電子メールの完全なヘッダーなど、より多くの情報を取得できます。
