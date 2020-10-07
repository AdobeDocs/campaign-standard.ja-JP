---
title: E メールの作成
description: Adobe Campaignで単一送信の電子メールを作成するには、次の手順に従います。
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 20%

---


# E メールの作成{#creating-an-email}

電子メールは、 [キャンペーン](../../start/using/marketing-activities.md#creating-a-marketing-activity)、Adobe Campaign [ホームページ](../../start/using/interface-description.md#home-page)、または [マーケティングアクティビティリストから作成できます](../../start/using/marketing-activities.md#about-marketing-activities)。 ワークフローから単一送信および定期的な電子メールを作成することもできます。

1. 電子メールマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   デフォルトでは、各マーケティングアクティビティに対して複数のテンプレートから選択できます。 これにより、ニーズに応じて特定のパラメーターを事前設定し、配信にブランドを割り当てることができます。 For more on this, see [Managing templates](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップおよび A/B テストテンプレートは、デフォルトで非表示になっています。左側( **[!UICONTROL Filter]** 横パネル)のチェックボックスをオンにして、表示したい場合に選択します。

1. 電子メールの一般的なプロパティを入力します。 You can enter a name in the **Label** field and edit the ID. アクティビティ名とそのIDは両方ともインターフェイスに表示されますが、メッセージ受信者には表示されません。

   キャンペーンコンテンツに表示される説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >親キャンペーン内に、マーケティングアクティビティのホームページまたはリストから電子メールを作成できます。 作成済みのキャンペーンから選択します。

1. ビジネスの基準に基づいてメッセージのターゲットを定義します。 See [About profiles](../../audiences/using/about-profiles.md).

   メッセージを検証するテストプロファイルを定義することもできます。 [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

   ![](assets/email_creation_3.png)

1. 電子メールデザイナーを使用して、メッセージの内容、送信者名、件名を定義してパーソナライズし [ます](../../designing/using/designing-content-in-adobe-campaign.md)。 For more on this, see [About email content design](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   定義済みのコンテンツテンプレートを使用して、またはDreamweaverやAdobe Experience Managerを使用して、メッセージを直接デザインできます。 デザイナーに似ていない場合は、用意済みのコンテンツをアップロードするか、URLから既存のコンテンツを読み込むこともできます。 詳しくは、[既存のコンテンツの選択](../../designing/using/using-existing-content.md)を参照してください。

1. メッセージのプレビュー. [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。
1. E メールの作成を確認します。

   >[!NOTE]
   >
   >電子メールを保存するには、まずコンテンツに編集を加える必要があります。 この時点でクリック **[!UICONTROL Cancel]** すると、ウィザードは完了せず、電子メールは作成されません。

   電子メールダッシュボードが表示されます。 メッセージを確認し、送信を [準備できます](../../sending/using/preparing-the-send.md)。

   右上隅の **[!UICONTROL Edit properties]** ボタンを使用して、電子メールのプロパティを編集できます。 例えば、電子メールを設定して、配信の準備時にラベルが計算されるようにできます。  Available parameters are listed in [this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。[メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。

   ![](assets/delivery_planning.png)

1. メッセージのターゲットを分析するための準備を行います。 See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >過剰に配信を受けているプロファイルをキャンペーンから自動的に除外するグローバルなクロスチャネル疲労ルールを設定できます。For more on this, see [Fatigue rules](../../sending/using/fatigue-rules.md).

1. 配達確認を送信してメッセージを確認および検証し、インボックスのレンダリングを監視します。配達確認 [の送信を参照してください](../../sending/using/sending-proofs.md)。

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージダッシュボードとログを通じて配信を確認します。 メッセージ [の送信を参照してください](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 配信レポートを使用して、メッセージの影響を測定します。 For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**関連トピック**：

* [E メールの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html) ビデオ
* [パーソナライズされた電子メールの作成](https://helpx.adobe.com/jp/campaign/kb/acs-get-started-with-emails.html) （ステップバイステップ）ガイド
* [Adobe CampaignとDreamweaverの統合](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html) （ビデオ）
* [Adobe Experience Managerとの統合](../../integrating/using/integrating-with-experience-manager.md)
