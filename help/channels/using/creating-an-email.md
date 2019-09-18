---
title: 電子メールの作成
seo-title: 電子メールの作成
description: 電子メールの作成
seo-description: 次の手順に従って、Adobe Campaignで1回送信の電子メールを作成します。
page-status-flag: 未活性化の
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: E-メールメッセージ
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 68d96b23f34f505c0a47a74a5e33bc3530fc4d72

---


# 電子メールの作成{#creating-an-email}

キャンペーン、Adobe Campaignのホームページ [、またはマーケティング活動リストから](../../start/using/marketing-activities.md#creating-a-marketing-activity)電子メールを作 [成できます](../../start/using/interface-description.md#home-page)[](../../start/using/marketing-activities.md#about-marketing-activities)。 ワークフローから、1回送信および定期的な電子メールを作成することもできます。

1. 電子メールマーケティング活動の作成を開始したら、使用するテンプレートを選択します。

   既定では、各マーケティング活動に対して複数のテンプレートから選択できます。 これにより、ニーズに応じて特定のパラメータを事前に設定し、配信にブランドを割り当てることができます。 詳細は、「テンプレートを管理する」を参 [照してください](../../start/using/about-templates.md)。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップとA/Bテストテンプレートは、既定では非表示になっています。 左側のボックス（横パネル）を表 **[!UICONTROL Filter]** 示する場合は、チェックボックスをオンにします。

1. 電子メールの全般プロパティを入力します。 「ラベル」( **Label** )フィールドに名前を入力し、IDを編集できます。 アクティビティ名とそのIDの両方がインターフェイスに表示されますが、メッセージの受信者には表示されません。

   ユーザーがキャンペーンのコンテンツで表示できる説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >親キャンペーン内の電子メールは、ホームページまたはマーケティング活動のリストから作成できます。 作成済のキャンペーンから選択します。

1. ビジネス基準に基づいて、メッセージのターゲットを定義します。 プロファイル [の管理を参照してくださ](../../audiences/using/about-profiles.md)い。

   また、メッセージを検証するテストプロファイルを定義することもできます。 「テスト·プ [ロファイルの管理」を参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)い。

   ![](assets/email_creation_3.png)

1. 電子メールデザイナを使用して、メッセージの内容、送信者名、件名を定義し、パーソナラ [イズします](../../designing/using/overview.md)。 詳細については、「電子メールコンテンツデザ [インについて」を参照してくださ](../../designing/using/overview.md)い。

   ![](assets/email_creation_4.png)

   定義済みのコンテンツテンプレートを使用して、またはDreamweaverまたはAdobe Experience Managerを使用して、メッセージを直接デザインできます。 デザイナーのように感じない場合は、準備済みのコンテンツをアップロードしたり、URLから既存のコンテンツをインポートしたりすることもできます。 既存のコ [ンテンツの選択を参照](../../designing/using/using-existing-content.md)。

1. メッセージをプレビューします。 メッセージのプ [レビューを参照してくださ](../../sending/using/previewing-messages.md)い。
1. 電子メールの作成を確認します。

   >[!NOTE]
   >
   >電子メールを保存するには、まずコンテンツを編集する必要があります。 この時点でク **[!UICONTROL Cancel]** リックすると、ウィザードは完了せず、電子メールは作成されません。

   次に、電子メールのダッシュボードが表示されます。 メッセージを確認し、送信を準 [備できます](../../sending/using/preparing-the-send.md)。

   右上 **[!UICONTROL Edit properties]** 隅のボタンを使用して、電子メールのプロパティを編集できます。 たとえば、配信準備時にラベルが計算されるように電子メールを構成できます。  使用可能なパラメータは、このセクショ [ンで示します](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。 「メッセージの [スケジュール」を参照](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. メッセージを準備して、ターゲットを分析します。 送信の準 [備を参照してください](../../sending/using/confirming-the-send.md)。

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >キャンペーンから過剰に発光するプロファイルを自動的に除外する、グローバルなチャネル間疲労規則を設定できます。 詳細は、「疲労規則」を参照し [てください](../../administration/using/fatigue-rules.md)。

1. 校正を送信して、メッセージを確認し、確認し、受信トレイの表示を監視します。 「証明の [送信」を参照](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)。

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージのダッシュボードとログを通じてメッセージの配信を確認します。 「メッセージ [の送信」を参照](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 配信レポートを使用して、メッセージの影響を測定します。 レポートの詳細については、このセクションを参 [照してくださ](../../reporting/using/about-dynamic-reports.md)い。

**関連トピック**:

* [電子メールビデオの作成](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) ..
* [個人用のEメール](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) ·ガイドの作成
* [Adobe CampaignとDreamweaverの統合ビデオ](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html)
* [Adobe Experience Managerとの統合](../../integrating/using/integrating-with-experience-manager.md)

