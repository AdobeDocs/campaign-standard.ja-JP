---
title: SMSメッセージの作成
seo-title: SMSメッセージの作成
description: SMSメッセージの作成
seo-description: 次の手順に従って、Adobe Campaignで単一送信SMSメッセージを作成します。
page-status-flag: 未活性化の
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: SMSメッセージ
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: 配信の作成，ウィザード
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: aa52fcca887c9423476a1bc0160d340f255b9ac8

---


# SMSメッセージの作成{#creating-an-sms-message}

SMS配信の作成は、通常の電子メールの作成と非常に似ています。 次の手順では、このチャネルに固有の設定について説明します。 その他のオプ [ションの詳細は](../../channels/using/creating-an-email.md) 、「電子メールの作成」を参照してください。

詳細なSMSパラメータの詳細については、 [SMS構成セクション](../../administration/using/configuring-sms-channel.md) を参照してください。

SMSメッセージを作成して携帯電話に送信するには、次の操作を行う必要があります。

* モード **[!UICONTROL Routing]** でチャネル上に構成さ **[!UICONTROL Mobile (SMS)]** れた外部アカウ **[!UICONTROL Bulk delivery]** ント。 詳細は、「ルーティング」の項を参照して [ください](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) 。
* この外部アカウントに正しくリンクされた配信テンプレート。

1. SMS配信を作成します。 この操作は、Adobe Campaignのホームページ、キャンペーン [、またはマーケティング](../../start/using/interface-description.md#home-page)活動リストか [ら実行でき](../../start/using/marketing-activities.md#creating-a-marketing-activity) ます [](../../start/using/programs-and-campaigns.md#creating-a-campaign)。

   ワークフローにSMSアクティビティを追加することもできます。 詳細については、『ワークフローガイド [](../../automating/using/sms-delivery.md) 』を参照してください。

   メッセージを作成する際に、最も重要な手順に従ってウィザードが表示されます。 ウィザードで定義した内容は、後でメッセージダッシュボードから編集できます。

1. 使用するテンプレートを選択します。 標準のSMSテンプレートか、独自のテンプレートを選択できます。

   ![](assets/sms_creation_1.png)

   携帯電話に配信するには、配信テンプレートがSMSルーティング外部アカウントに正しくリンクされている必要があります。

1. SMSの一般プロパティを入力します。

   ![](assets/sms_creation_2.png)

   アクティビティラベルとそのIDの両方がインターフェイスに表示されますが、メッセージの受信者には表示されません。

1. ターゲットにする対象ユーザーを指定します。 既存の対象ユーザーを選択するか、ルールを定義して組み合わせることで、母集団を直接ターゲットにすることができます。

   ![](assets/sms_creation_3.png)

1. SMSにコンテンツを追加します。 SMSの作成が完了したら、配信ダッシュボードのセ **[!UICONTROL Content]** クションをクリックして、コンテンツを定義することもできます。 「 SMSコンテ [ンツデザインについて](../../channels/using/about-sms-and-push-content-design.md)」を参照。

   SMSメッセージの内容に個人用設定フィールドまたは条件付きテキストを挿入した場合、メッセージの長さは受信者によって異なる場合があります。 実際、これらの要因は、GSMエンコードで考慮されない文字を導入する可能性があります。 このため、個人化を行った後にメッセージの長さを評価する必要があります。 「SMSメッ [セージの個人用設定」を参照](../../channels/using/personalizing-sms-messages.md)。

   ![](assets/sms_creation_4.png)

1. メッセージの作成を確認します。 ダッシュボードが表示されます。
1. 送信をスケジュールします。 SMSは、メッセージの準備直後に手動で送信することも、スケジュールされた日付に自動的に送信することもできます。 「メッセージの [スケジュール」を参照](../../sending/using/about-scheduling-messages.md)。
1. メッセージの妥当性、パーソナライズ、ターゲットを分析する準備をします。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >キャンペーンから過剰に発光するプロファイルを自動的に除外する、グローバルなチャネル間疲労規則を設定できます。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

1. 校正を送信して、メッセージを確認し、確認し、受信トレイの表示を監視します。 「Sending prof」の項 [を参照してください](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) 。
1. メッセージの送信を確認します。 指定したスケジュールに従って送信が開始されます。

   ![](assets/sms_creation_7.png)

メッセージが送信されます。 メッセージのダッシュボードとログを使用して、その配信を確認できます。

送信が完了したら、組み込みの配信レポートやカスタム配信レポートを使用して、メッセージの影響を測定し始めることができます。

**関連トピック：**

* [SMSとプッシュコンテンツエディションについて](../../channels/using/about-sms-and-push-content-design.md)
* [テンプレートの管理](../../start/using/about-templates.md)
* [SMS配信ビデオの作成](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html)

