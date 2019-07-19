---
title: ダイレクトメールの作成
seo-title: ダイレクトメールの作成
description: ダイレクトメールの作成
seo-description: Adobe Campaignでダイレクトメール配信を作成するには、次の手順に従います。
page-status-flag: 常にアクティブ化されていない
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ダイレクトメール
discoiquuid: 5b02227f-9438-4001- bc2f-3d8661d173b3
context-tags: delivery， directMailContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Creating the direct mail{#creating-the-direct-mail}

ダイレクトメール配信の作成は、通常の電子メールの作成と非常によく似ています。次の手順では、このチャネルに固有の設定について説明します。Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

1. 新しいダイレクトメール配信を作成します。You can create one from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in a [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >ワークフローでダイレクトメールアクティビティを追加することもできます。For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Choose either the out-of-the-box **[!UICONTROL Direct mail]** template or one of your own templates. For more information on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

   ![](assets/direct_mail_2.png)

1. 配信の一般的なプロパティを入力します。

   ![](assets/direct_mail_3.png)

1. 抽出ファイルに含めるオーディエンスとテストおよびトラッププロファイルを定義します。See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >オーディエンスの定義は、通常の電子メールオーディエンスの定義と非常に似ています。See [Creating audiences](../../audiences/using/creating-audiences.md).

1. ファイルのコンテンツを編集します。列に、各プロファイル、ファイル構造、ヘッダーとフッターを含めることができます。See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Click on the **[!UICONTROL Schedule]** section of the delivery dashboard to define the contact date. ダイレクトメールの場合、連絡先日は必須です。For more information, refer to [Scheduling the send](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. If you added test profiles (refer to [Adding test and trap profiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), you can test your delivery before preparing the final file. 選択したテストプロファイルのみを含むサンプルファイルを作成できます。

   Click on **[!UICONTROL Test]** to generate the sample file. Click on **[!UICONTROL Summary]**, in the top left corner, then select **[!UICONTROL Proofs]**. On the left part of the screen, select the proof and click on **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >**[!UICONTROL Export]** このロールは、Adobe Campaignがファイルをエクスポートしてダウンロードできるようにするために必要です。管理者に問い合わせてください。

   ![](assets/direct_mail_19.png)

1. Once you have defined your delivery content, audience and contact date, click on the **[!UICONTROL Prepare]** button, on the delivery dashboard.

   ![](assets/direct_mail_16.png)

   タイポロジルールが適用されます。例えば、すべての指定されていない住所はターゲットから除外されます。This is why you need to make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information (see [Recommendations](../../channels/using/about-direct-mail.md#recommendations)). If you have defined a **[!UICONTROL Maximum volume of message]** in the direct mail properties or at the template level, it will also be applied here.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >グローバルなクロスチャネルの疲労ルールを設定して、キャンペーンから余分なプロファイルを自動的に除外することができます。[疲労ルール](../../administration/using/fatigue-rules.md)を参照してください。

1. Click on **[!UICONTROL Explore file]** to preview the first 100 lines of the file.

   ![](assets/direct_mail_18.png)

   画面の左部分では、完全なファイルにアクセスできます。Downloading the file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

   >[!NOTE]
   >
   >**[!UICONTROL Export]** このロールは、Adobe Campaignがファイルをエクスポートしてダウンロードできるようにするために必要です。管理者に問い合わせてください。

   If you need to change the delivery content, you only have to click on the **[!UICONTROL Regenerate file]** button to take the change into account. 準備をやり直す必要はありません。

   ![](assets/direct_mail_21.png)

1. To confirm that the file is final, click on **[!UICONTROL Confirm]** in the delivery dashboard.

   ![](assets/direct_mail_20.png)

これで、抽出ファイルをダイレクトメールプロバイダーに送信する準備が整いました。これには、いくつかのオプションがあります。

* ファイルを添付して通常の電子メールを送信
* Send it via Campaign: perform your direct mail within a campaign [workflow](../../automating/using/direct-mail-delivery.md) and add a **[!UICONTROL Transfer file]** to send the file via FTP for example. See [Transfer file](../../automating/using/transfer-file.md).

プロバイダーは、誤ったアドレスのリストを取得し、この情報をAdobe Campaignに送信して、誤ったアドレスを自動的にブラックリストに入れます。See [Return to sender](../../channels/using/return-to-sender.md).
