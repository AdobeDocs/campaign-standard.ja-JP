---
title: メールの作成
description: Adobe Campaignで単一送信 E メールを作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 15%

---

# メールの作成{#creating-an-email}

E メールは、 [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity)(Adobe Campaignから ) [ホームページ](../../start/using/interface-description.md#home-page)、または [マーケティングアクティビティリスト](../../start/using/marketing-activities.md#about-marketing-activities). また、ワークフローから単一送信 E メールと繰り返し E メールを作成することもできます。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

1. 電子メールマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   デフォルトでは、各マーケティングアクティビティに対して複数のテンプレートから選択できます。 これにより、必要に応じて特定のパラメーターを事前設定し、ブランドを配信に割り当てることができます。 詳しくは、 [テンプレートの管理](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップおよび A/B テストテンプレートは、デフォルトで非表示になっています。左側のチェックボックスをオンにします ( **[!UICONTROL Filter]** 横置きパネルを参照 )。

1. E メールの一般的なプロパティを入力します。 名前を **ラベル** 「 」フィールドに値を入力し、ID を編集します。

   >[!NOTE]
   >
   >アクティビティ名とアクティビティ ID は両方ともインターフェイスに表示されますが、メッセージ受信者には表示されません。
   >
   >例えば、Adobe Analyticsとの統合時など、不一致が生じるのを避けるために、ID フィールドに空白を含めないようにしてください。

   キャンペーンコンテンツに表示される説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >親キャンペーン内に、ホームページまたはマーケティングアクティビティのリストから電子メールを作成できます。 作成済みのキャンペーンから選択します。

1. ビジネス上の基準に基づいて、メッセージのターゲットを定義します。 詳しくは、 [プロファイルについて](../../audiences/using/about-profiles.md).

   また、メッセージを検証するテストプロファイルを定義することもできます。 [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

   ![](assets/email_creation_3.png)

1. を使用して、メッセージの内容、送信者名、件名を定義し、パーソナライズします。 [E メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md). 詳しくは、 [E メールコンテンツデザインについて](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   事前定義済みのコンテンツテンプレートを使用して、またはDreamweaverやAdobe Experience Managerを使用して、メッセージを直接デザインできます。 デザイナーのような気がしない場合は、準備済みのコンテンツをアップロードしたり、URL から既存のコンテンツを読み込んだりすることもできます。 詳しくは、[既存のコンテンツの選択](../../designing/using/using-existing-content.md)を参照してください。

1. メッセージをプレビューします。 [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。
1. E メールの作成を確認します。

   >[!NOTE]
   >
   >E メールを保存するには、まずコンテンツを編集する必要があります。 次をクリックした場合： **[!UICONTROL Cancel]** この時点では、ウィザードは完了せず、メールは作成されません。

   E メールダッシュボードが表示されます。 メッセージを確認し、 [送信の準備](../../sending/using/preparing-the-send.md).

   The **[!UICONTROL Edit properties]** ボタンを使用して、E メールのプロパティを編集できます。 例えば、配信準備時にラベルが計算されるように E メールを設定できます。  使用可能なパラメーターは、 [この節](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。[メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。

   ![](assets/delivery_planning.png)

1. メッセージのターゲットを分析するための準備をします。 詳しくは、 [送信の準備](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >過剰に配信を受けているプロファイルをキャンペーンから自動的に除外するグローバルなクロスチャネル疲労ルールを設定できます。詳しくは、 [疲労ルール](../../sending/using/fatigue-rules.md).

1. 配達確認を送信してメッセージを確認および検証し、インボックスのレンダリングを監視します。詳しくは、 [配達確認の送信](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージダッシュボードとログを使用して配信を確認します。 詳しくは、 [メッセージの送信](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. 配信レポートを使用して、メッセージの影響を測定します。 レポートについて詳しくは、 [この節](../../reporting/using/about-dynamic-reports.md).

**関連トピック**：

* [パーソナライズされた E メールの作成](../../channels/using/key-steps-to-send-a-message.md) ステップバイステップガイド
* [Adobe CampaignとDreamweaverの統合](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Adobe Experience Managerとの統合](../../integrating/using/integrating-with-experience-manager.md)

## チュートリアルビデオ {#video}

このビデオでは、E メールの作成方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

その他のCampaign Standardのハウツービデオも利用できます [ここ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja).
