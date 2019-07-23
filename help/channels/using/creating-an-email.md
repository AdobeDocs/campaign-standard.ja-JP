---
title: 電子メールの作成
seo-title: 電子メールの作成
description: 電子メールの作成
seo-description: Adobe Campaignで単一の送信電子メールを作成するには、次の手順に従います。
page-status-flag: 常にアクティブ化されていない
uuid: 74c7ef35-82c0-4bc4- b1f6-8e74fdaea3c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: 電子メールメッセージ
discoiquuid: b27e0170- e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f4c849adf1852d8a23c5ff5252da25c175faa84

---


# Creating an email{#creating-an-email}

You can create an email from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity), from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), or in the [marketing activity list](../../start/using/marketing-activities.md#about-marketing-activities). ワークフローから単一送信および繰り返し電子メールを作成することもできます。

1. 電子メールマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   デフォルトでは、各マーケティングアクティビティのテンプレートから選択できます。これにより、ニーズに応じて特定のパラメーターを事前設定し、配信にブランドを割り当てることができます。For more on this, see [Managing templates](../../start/using/about-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップおよびA/Bテストテンプレートは、デフォルトでは非表示です。Check the boxes on the left side ( **[!UICONTROL Filter]** lateral panel) if you want to display them.

1. 電子メールの一般的なプロパティを入力します。**「ラベル」** フィールドに名前を入力し、IDを編集できます。アクティビティ名とそのIDはインターフェイスに表示されますが、メッセージの受信者には表示されません。

   キャンペーンコンテンツでユーザーに表示できる説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >ホームページまたはマーケティングアクティビティのリストから、親キャンペーン内に電子メールを作成できます。作成済みのキャンペーンから選択します。

1. ビジネス条件に基づいてメッセージのターゲットを定義します。See [Managing profiles](../../audiences/using/about-profiles.md).

   また、メッセージを検証するテストプロファイルを定義することもできます。See [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

   ![](assets/email_creation_3.png)

1. [電子メールデザイナーを使用して、メッセージコンテンツ、送信者名および件名を定義してパーソナライズ](../../designing/using/about-email-content-design.md#about-the-email-designer)します。For more on this, see [About email content design](../../designing/using/about-email-content-design.md).

   ![](assets/email_creation_4.png)

   事前定義済みのコンテンツテンプレートを使用して、またはDreamweaverまたはAdobe Experience Managerを使用して、メッセージを直接デザインできます。デザイナーのように動作しない場合は、準備が整ったコンテンツをアップロードすることも、URLから既存のコンテンツを読み込むこともできます。See [Selecting an existing content](../../designing/using/selecting-an-existing-content.md).

1. メッセージをプレビューします。See [Previewing messages](../../sending/using/previewing-messages.md).
1. 電子メールの作成を確認します。

   >[!NOTE]
   >
   >電子メールを保存できるようにするには、まずコンテンツに編集を加える必要があります。If you click **[!UICONTROL Cancel]** at this point, you will not complete the wizard and your email will not be created.

   その後、電子メールダッシュボードが表示されます。It allows you to check your message and [prepare the send](../../sending/using/preparing-the-send.md).

   The **[!UICONTROL Edit properties]** button in the upper-right corner allows you to edit the properties of the email. 例えば、配信の準備時にラベルが計算されるように電子メールを設定できます。Available parameters are listed in [this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。See [Scheduling messages](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. ターゲットを分析するメッセージを準備します。See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >グローバルなクロスチャネルの疲労ルールを設定して、キャンペーンから余分なプロファイルを自動的に除外することができます。For more on this, see [Fatigue rules](../../administration/using/fatigue-rules.md).

1. メッセージを確認して検証し、インボックスレンダリングを監視するための配達確認を送信します。See [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージのダッシュボードとログを通して配信をチェックします。See [Sending messages](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. 配信レポートでメッセージの影響を測定します。For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**関連トピック**:

* [電子メール](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) ビデオの作成
* [パーソナライズされた電子メール](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) ステップバイステップガイドの作成
* [Adobe CampaignとDreamweaverの統合](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) ビデオ
* [Adobe Experience Managerとの統合](../../integrating/using/integrating-with-experience-manager.md)

