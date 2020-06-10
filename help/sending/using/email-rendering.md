---
title: 電子メールのレンダリング
description: 電子メールレンダリング機能を検出します。
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b43e6be265ff2d8ce357ef44672a755028e2e5af
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 30%

---


# 電子メールのレンダリング{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

The mobile, messaging and webmail clients available for **Email rendering** in Adobe Campaign are listed on the Litmus [website](https://litmus.com/email-testing) (click **View all email clients**).

## 電子メールレンダリングレポートの確認 {#checking-the-email-rendering-report}

E メール配信を作成し、そのコンテンツとターゲット母集団を定義したら、以下の手順に従います。

1. 「 **オーディエンス** 」をクリックして **[!UICONTROL Test profiles]** タブにアクセスします。

   ![](assets/email_rendering_05.png)

1. クエリエディターを使用して、 **電子メールレンダリング** 使用用のテストプロファイルなど、使用するテストプロファイルを定義します。 テストプロファイル [についてを参照してください](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_rendering_06.png)

1. クエリを確認し、変更を保存します。
1. アクションバーの **[!UICONTROL Test]** ボタンをクリックします。

   ![](assets/email_rendering_07.png)

1. この **[!UICONTROL Email rendering]** オプションを選択し、をクリックし **[!UICONTROL OK]**&#x200B;ます。

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >この **[!UICONTROL Proof + Email rendering]** オプションを使用すると、配達確認を送信し、電子メールレンダリング機能を同時に使用できます。 メッセージを配達確認受信者に承認してもらうと同時に、対象となる受信トレイに応じてメッセージの受信方法をテストできます。 この場合は、配達確認テストプロファイルも選択する必要があります。 テストプロファイル [についてを参照してください](../../audiences/using/managing-test-profiles.md)。

   テスト配信が送信されます。

1. メッセージの送信後、数分後にレンダリングサムネールが使用可能になります。 これらにアクセスするには、ドロップダウン **[!UICONTROL Proofs]****[!UICONTROL Summary]** リストでを選択します。

   ![](assets/email_rendering_03.png)

1. リストで、アイコンをクリックし **[!UICONTROL Proofs]****[!UICONTROL Access email rendering]** ます。

   ![](assets/email_rendering_04.png)

専用の電子メールレンダリングレポートが表示されます。 「 [電子メールレンダリングレポートの説明](#email-rendering-report-description)」を参照してください。

**関連トピック**：

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [クエリエディター](../../automating/using/editing-queries.md#about-query-editor)

## 電子メールレンダリングレポートの説明 {#email-rendering-report-description}

このレポートは、受信者に表示される電子メールレンダリングを表示します。 電子メールのレンダリングは、受信者が電子メール配信を開く方法によって異なる場合があります。 （ブラウザー、モバイルデバイスまたは電子メールアプリケーション経由）。

>[!NOTE]
>
>使用できるレンダリングの数は、ライセンス契約に記載されています。Each delivery with **Email rendering** enabled decreases your available renderings (known as tokens) by one.

レポート概要には、受信済みメッセージ、不要なメッセージ（スパム）、受信されていないメッセージまたは受信が保留されているメッセージの数が表示されます。

![](assets/inbox_rendering_report.png)

The report is divided into three parts: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, and **[!UICONTROL Webmails]**. レポートを下へスクロールすると、これらの 3 つのカテゴリにグループ化されたすべてのレンダリングが表示されます。

![](assets/inbox_rendering_report_3.png)

各レポートの詳細を表示するには、対応するカードをクリックします。選択した受信方法のレンダリングが表示されます。

![](assets/inbox_rendering_report_2.png)

この **[!UICONTROL Technical data]** タブでは、受信日や取得日、電子メールの完全なヘッダーなどの詳細情報を取得できます。
