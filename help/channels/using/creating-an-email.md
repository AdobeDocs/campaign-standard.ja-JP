---
title: 電子メールの作成
description: Adobe Campaignで単一送信電子メールを作成するには、次の手順に従います。
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# 電子メールの作成{#creating-an-email}

キャンペーン、Adobe Campaignホームページ [、またはマーケティングアクティビティ](../../start/using/marketing-activities.md#creating-a-marketing-activity)リストから [、電子メール](../../start/using/interface-description.md#home-page)を作成できます [](../../start/using/marketing-activities.md#about-marketing-activities)。 ワークフローから単一送信および定期的な電子メールを作成することもできます。

1. 電子メールマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   デフォルトでは、各マーケティングアクティビティに対して複数のテンプレートから選択できます。 これにより、ニーズに応じて特定のパラメーターを事前設定し、ブランドを配信に割り当てることができます。 詳しくは、「テンプレートの管理」を参 [照してください](../../start/using/marketing-activity-templates.md)。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップおよびA/Bテストテンプレートは、デフォルトで非表示になっています。 表示する場合は、左側（横パネル） **[!UICONTROL Filter]**のチェックボックスをオンにします。

1. 電子メールの一般プロパティを入力します。 「ラベル」フィールドに名前を入力し **て** 、IDを編集できます。 アクティビティ名とそのIDは両方ともインターフェイスに表示されますが、メッセージの受信者には表示されません。

   キャンペーンのコンテンツでユーザーが表示できる説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >親キャンペーン内で、ホームページまたはマーケティングアクティビティのリストから電子メールを作成できます。 作成済みのキャンペーンから選択します。

1. ビジネスの基準に基づいてメッセージのターゲットを定義します。 詳しくは、プ [ロファイルの管理を参照してくださ](../../audiences/using/about-profiles.md)い。

   また、メッセージを検証するテストプロファイルを定義することもできます。 詳しくは、テ [ストプロファイルの管理を参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)い。

   ![](assets/email_creation_3.png)

1. 電子メールデザイナーを使用して、メッセージの内容、送信者名、件名を定義し、パーソナラ [イズしま](../../designing/using/designing-content-in-adobe-campaign.md)す。 For more on this, see [About email content design](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   定義済みのコンテンツテンプレートを使用して、またはDreamweaverまたはAdobe Experience Managerを使用して、メッセージを直接デザインできます。 デザイナーの気がない場合は、準備が整ったコンテンツをアップロードしたり、URLから既存のコンテンツを読み込んだりすることもできます。 詳しくは、 [既存のコンテンツの選択を参照してください](../../designing/using/using-existing-content.md)。

1. メッセージをプレビューします。 詳しくは、メッ [セージのプレビューを参照してくださ](../../sending/using/previewing-messages.md)い。
1. 電子メールの作成を確認します。

   >[!NOTE]
   >
   >電子メールを保存するには、まずコンテンツに編集を加える必要があります。 この時点でク **[!UICONTROL Cancel]**リックすると、ウィザードは完了せず、電子メールは作成されません。

   電子メールダッシュボードが表示されます。 メッセージを確認し、送信を準 [備できます](../../sending/using/preparing-the-send.md)。

   右上隅 **[!UICONTROL Edit properties]**のボタンを使用して、電子メールのプロパティを編集できます。 例えば、電子メールを設定して、配信の準備時にラベルが計算されるようにすることができます。  Available parameters are listed in[this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。 詳しくは、メッ [セージのスケジュールを参照してくださ](../../sending/using/about-scheduling-messages.md)い。

   ![](assets/delivery_planning.png)

1. ターゲットを分析するメッセージを準備します。 See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >キャンペーンから過剰に要求されるプロファイルを自動的に除外する、グローバルなチャネル間疲労ルールを設定できます。 詳しくは、疲労ルールを参照し [てください](../../administration/using/fatigue-rules.md)。

1. 校正を送信して、メッセージを確認および検証し、インボックスのレンダリングを監視します。 「証明 [の送信」を参照](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)。

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージのダッシュボードとログを通じて配信を確認します。 メッセージ [の送信を参照してくださ](../../sending/using/confirming-the-send.md)い。

   ![](assets/confirm_delivery.png)

1. 配信レポートを使用して、メッセージの影響を測定します。 レポートの詳細については、この節を参 [照してください](../../reporting/using/about-dynamic-reports.md)。

**関連トピック**：

* [電子メールビデオの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html) （英語のみ）
* [パーソナライズされた電子メール](https://helpx.adobe.com/campaign/kb/acs-get-started-with-emails.html) ・ステップ・バイ・ステップ・ガイドの作成
* [Adobe CampaignとDreamweaverの統合に関するビデオ](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html) （英語のみ）
* [Adobe Experience Managerとの連携](../../integrating/using/integrating-with-experience-manager.md)
