---
title: SMSメッセージの作成
seo-title: SMSメッセージの作成
description: SMSメッセージの作成
seo-description: Adobe Campaignで単一の送信SMSメッセージを作成するには、次の手順に従います。
page-status-flag: 常にアクティブ化されていない
uuid: 591ae97e-2d19-4f93- be4b- d8d20f1d2d12
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: sms- messages
discoiquuid: b27381a9-19e5-4b65- b194- c72f475ba54d
delivercontext-tags: DeliveryCreation， wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Creating an SMS message{#creating-an-sms-message}

SMS配信の作成は、通常の電子メールの作成と非常によく似ています。次の手順では、このチャネルに固有の設定について説明します。Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

Advanced SMS parameters are detailed in the [SMS configuration](../../administration/using/configuring-sms-channel.md) section.

SMSメッセージを作成して携帯電話に送信するには、以下が必要です。

* **[!UICONTROL Routing]** モードを使用して **[!UICONTROL Mobile (SMS)]** チャネル上で設定された外部アカウント **[!UICONTROL Bulk delivery]** 。For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* この外部アカウントに正しくリンクされている配信テンプレート。

1. SMS配信を作成します。You can do it from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in the [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   ワークフローでSMSアクティビティを追加することもできます。For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   メッセージを作成すると、最も重要なステップを順を追って説明します。ウィザードで定義した内容は、メッセージダッシュボードからも編集できます。

1. 使用するテンプレートを選択します。あらかじめ用意されているSMSテンプレートまたは独自のテンプレートのいずれかを選択できます。

   ![](assets/sms_creation_1.png)

   携帯電話に配信するには、配信テンプレートが外部アカウントに正しくリンクされている必要があります。

1. SMSの一般的なプロパティを入力します。

   ![](assets/sms_creation_2.png)

   アクティビティラベルとそのIDはインターフェイスに表示されますが、メッセージの受信者には表示されません。

1. ターゲットにするオーディエンスを指定します。既存のオーディエンスを選択するか、ルールを定義して組み合わせることで、訪問者を直接ターゲット設定できます。

   ![](assets/sms_creation_3.png)

1. SMSにコンテンツを追加します。You can also define the content by clicking the **[!UICONTROL Content]** section of the delivery dashboard, once the SMS creation is finalized. See [About SMS content design](../../designing/using/about-sms-and-push-content-design.md).

   パーソナライゼーションフィールドまたは条件テキストをSMSメッセージのコンテンツに挿入する場合、メッセージの長さは受信者によって異なる場合があります。実際には、これらの要因にはGSMエンコーディングによって考慮されない文字が含まれることがあります。そのため、パーソナライゼーションが実行されると、メッセージの長さを評価する必要があります。See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. メッセージの作成を確認します。その後ダッシュボードが表示されます。
1. 送信をスケジュールします。SMSは、メッセージの準備の直後に手動で送信することも、スケジュール済み日付に自動的に送信することもできます。See [Scheduling messages](../../sending/using/about-scheduling-messages.md).
1. メッセージを準備して、有効性、パーソナライゼーションおよびターゲットを分析します。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >グローバルなクロスチャネルの疲労ルールを設定して、キャンペーンから余分なプロファイルを自動的に除外することができます。[疲労ルール](../../administration/using/fatigue-rules.md)を参照してください。

1. メッセージを確認して検証し、インボックスレンダリングを監視するための配達確認を送信します。See the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. メッセージの送信を確認します。送信は、定義したスケジュールに応じて開始されます。

   ![](assets/sms_creation_7.png)

メッセージが送信されます。メッセージのダッシュボードとログを通して配信を確認できます。

送信が完了すると、組み込み配信レポートまたはカスタム配信レポートでのメッセージの影響を測定できます。

**関連トピック:**

* [SMSおよびプッシュコンテンツのエディションについて](../../designing/using/about-sms-and-push-content-design.md)
* [テンプレートの管理](../../start/using/about-templates.md)
* [SMS配信](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html) ビデオの作成

