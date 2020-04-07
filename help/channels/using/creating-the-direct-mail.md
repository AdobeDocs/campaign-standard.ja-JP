---
title: ダイレクトメールの作成
description: 次の手順に従って、ダイレクトメール配信をAdobe Campaignします。
page-status-flag: never-activated
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5b02227f-9438-4001-bc2f-3d8661d173b3
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# ダイレクトメールの作成{#creating-the-direct-mail}

ダイレクトメール配信の作成は、通常の電子メールの作成と非常に似ています。 次の手順で、この設定に固有の設定を説明します。チャネル その他のオプ [ションの詳細については](../../channels/using/creating-an-email.md) 、「電子メールの作成」を参照してください。

1. 新しいダイレクトメール配信を作成する Adobe Campaign [ホームページ](../../start/using/interface-description.md#home-page)、キャンペーン [、またはマーケティング](../../start/using/marketing-activities.md#creating-a-marketing-activity) アクティビティ [リストで作成できます](../../start/using/programs-and-campaigns.md#creating-a-campaign)。

   >[!NOTE]
   >
   >ワークフローにダイレクトメールアクティビティを追加することもできます。 詳しくは、[ワークフロー](../../automating/using/direct-mail-delivery.md)ガイドを参照してください。

   ![](assets/direct_mail_1.png)

1. 標準搭載のテンプレートまたは独自のテンプレ **[!UICONTROL Direct mail]** ートのいずれかを選択します。 テンプレートの詳細については、「テンプレートの管理」の節を [参照してくださ](../../start/using/marketing-activity-templates.md) い。

   ![](assets/direct_mail_2.png)

1. プロパティの一般的なプロパティを配信します。

   ![](assets/direct_mail_3.png)

1. オーディエンスファイルに含める抽出と、テストおよびトラップのプロファイルを定義します。 See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >オーディエンスの定義は、通常の電子メールの定義と非常に似ています。オーディエンスの定義は、 詳しくは、 [オーディエンスの作成](../../audiences/using/creating-audiences.md)。

1. ファイルの内容を編集します。各ヘッダー、ファイル構造、プロファイルーおよびフッターに含める列。 See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. 連絡日を定義するに **[!UICONTROL Schedule]** は、配信ダッシュボードのセクションをクリックします。 ダイレクトメールの場合、連絡先の日付は必須です。 詳しくは、送信のスケジュールを参 [照してください](../../sending/using/about-scheduling-messages.md)。

   ![](assets/direct_mail_8.png)

1. テストプロファイルを追加した場合(「テストプロファイル [とトラップオプションの追加](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)」を参照)は、最終的なファイルを準備する前に配信をテストできます。 選択したテストプロファイルのみを含むサンプルファイルを作成できます。

   をクリックし **[!UICONTROL Test]** て、サンプルファイルを生成します。 左上隅 **[!UICONTROL Summary]**&#x200B;のをクリックし、を選択します **[!UICONTROL Proofs]**。 画面の左側で、配達確認を選択し、をクリックします **[!UICONTROL Download file]**。

   >[!NOTE]
   >
   >役割は、 **[!UICONTROL Export]** Adobe Campaignがファイルを書き出し、ダウンロード可能にするために必要です。 管理者に問い合わせてください。

   ![](assets/direct_mail_19.png)

1. 配信の内容、オーディエンス、連絡先の日付を定義したら、配信 **[!UICONTROL Prepare]** ダッシュボードのボタンをクリックします。

   ![](assets/direct_mail_16.png)

   タイポロジルールが適用されます。 例えば、指定されていないすべての住所はターゲットから除外されます。 このため、プロファイルの情報のボックスがオンになってい **[!UICONTROL Address specified]** ることを確認する必要があり [ます(Recommendations](../../channels/using/about-direct-mail.md#recommendations)を参照)。 ダイレクトメールのプロパティ **[!UICONTROL Maximum volume of message]** またはテンプレートレベルでを定義した場合は、ここでも適用されます。

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >訪問者から過剰訪問のプロファイルを自動的に除外する、チャネル間の疲労ルールをグローバルに設定できます。 疲労ルー [ルを参照してくださ](../../sending/using/fatigue-rules.md)い。

1. をクリックし **[!UICONTROL Explore file]** て、ファイルの最初の100行をプレビューします。

   ![](assets/direct_mail_18.png)

   完全なファイルは、画面の左側でローカルダウンロード用にアクセスできます。 ファイルをダウンロードすると、メニューにログエントリが生成 **[!UICONTROL Export audits]** されます。 エクスポート監査の詳細については、「エクスポートの監査 [](../../administration/using/auditing-export-logs.md) 」を参照してください。

   >[!NOTE]
   >
   >役割は、 **[!UICONTROL Export]** Adobe Campaignがファイルを書き出し、ダウンロード可能にするために必要です。 管理者に問い合わせてください。

   配信の内容を変更する必要がある場合は、ボタンをクリックするだ **[!UICONTROL Regenerate file]** けで変更を反映できます。 もう準備を進める必要はない。

   ![](assets/direct_mail_21.png)

1. ファイルが最終版であることを確認するには、配信 **[!UICONTROL Confirm]** ダッシュボードのをクリックします。

   ![](assets/direct_mail_20.png)

これで、ダイレクトメールプロバイダに抽出ファイルを送信する準備が整いました。 この場合、次のいくつかのオプションがあります。

* ファイルを添付して、通常の電子メールで送信します。
* キャンペーン:キャンペーンワークフロー内でダイレクトメ [ールを](../../automating/using/direct-mail-delivery.md) 実行し、FTP経由でフ **[!UICONTROL Transfer file]** ァイルを送信するためのを追加します。 ファイルの [転送を参照してくださ](../../automating/using/transfer-file.md)い。

プロバイダは、誤ったアドレスのリストを取得し、この情報をAdobe Campaignに送信し、誤ったアドレスを自動的にブラックリストします。 See [Return to sender](../../channels/using/return-to-sender.md).
