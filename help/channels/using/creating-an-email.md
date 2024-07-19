---
title: メールの作成
description: Adobe Campaignで 1 回限りのメールを作成するには、次の手順に従います。
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

メールは、[ キャンペーン ](../../start/using/marketing-activities.md#creating-a-marketing-activity)、Adobe Campaign[ ホームページ ](../../start/using/interface-description.md#home-page) または [ マーケティングアクティビティリスト ](../../start/using/marketing-activities.md#about-marketing-activities) から作成できます。 ワークフローから 1 回送信のメールや繰り返しメールを作成することもできます。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

1. メールマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   デフォルトでは、各マーケティングアクティビティに対して複数のテンプレートから選択できます。 これにより、ニーズに応じて特定のパラメーターを事前設定し、配信にブランドを割り当てることもできます。 詳しくは、[ テンプレートの管理 ](../../start/using/marketing-activity-templates.md) を参照してください。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップおよび A/B テストテンプレートは、デフォルトで非表示になっています。左側のチェックボックス（横パネル） **[!UICONTROL Filter]** オンにして表示します。

1. メールの一般プロパティを入力します。 「**ラベル**」フィールドに名前を入力し、ID を編集できます。

   >[!NOTE]
   >
   >アクティビティ名と ID の両方がインターフェイスに表示されますが、メッセージ受信者には表示されません。
   >
   >Adobe Analyticsと統合する場合など、不一致を避けるために、ID フィールドに空白が含まれていないことを確認します。

   キャンペーンコンテンツに表示される説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >親キャンペーン内にホームページまたはマーケティングアクティビティのリストからメールを作成できます。 作成済みのキャンペーンから選択します。

1. ビジネス条件に基づいてメッセージのターゲットを定義します。 [ プロファイルについて ](../../audiences/using/about-profiles.md) を参照してください。

   また、メッセージを検証するテストプロファイルを定義することもできます。 [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

   ![](assets/email_creation_3.png)

1. [ メールDesigner](../../designing/using/designing-content-in-adobe-campaign.md) を使用して、メッセージのコンテンツ、送信者名、件名を定義およびパーソナライズします。 詳しくは、[ メールコンテンツデザインについて ](../../designing/using/designing-content-in-adobe-campaign.md) を参照してください。

   ![](assets/email_creation_4.png)

   事前定義済みのコンテンツテンプレートを使用するか、DreamweaverまたはAdobe Experience Managerを使用して、メッセージを直接デザインできます。 デザイナーではない場合は、事前に用意したコンテンツをアップロードしたり、URL から既存のコンテンツを読み込んだりすることもできます。 詳しくは、[既存のコンテンツの選択](../../designing/using/using-existing-content.md)を参照してください。

1. メッセージのプレビュー。 [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。
1. メールの作成を確認します。

   >[!NOTE]
   >
   >メールを保存するには、まずコンテンツを編集する必要があります。 この時点で [**[!UICONTROL Cancel]**] をクリックすると、ウィザードは完了せず、電子メールは作成されません。

   メールダッシュボードが表示されます。 メッセージを確認し [ 送信を準備 ](../../sending/using/preparing-the-send.md) できます。

   右上隅の「**[!UICONTROL Edit properties]**」ボタンを使用すると、メールのプロパティを編集できます。 例えば、配信準備時にラベルが計算されるようにメールを設定できます。  使用可能なパラメーターは [ この節 ](../../administration/using/configuring-email-channel.md#list-of-email-properties) に記載されています。

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。[メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。

   ![](assets/delivery_planning.png)

1. ターゲットを分析するためのメッセージを準備します。 [ 送信の準備 ](../../sending/using/confirming-the-send.md) を参照してください。

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >過剰に配信を受けているプロファイルをキャンペーンから自動的に除外するグローバルなクロスチャネル疲労ルールを設定できます。詳しくは、[ 疲労ルール ](../../sending/using/fatigue-rules.md) を参照してください。

1. 配達確認を送信してメッセージを確認および検証し、インボックスのレンダリングを監視します。[ 配達確認の送信 ](../../sending/using/sending-proofs.md) を参照してください。

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージダッシュボードとログで配信を確認します。 [ メッセージの送信 ](../../sending/using/confirming-the-send.md) を参照してください。

   ![](assets/confirm_delivery.png)

1. 配信レポートを使用して、メッセージの影響を測定します。 レポートについて詳しくは、[ この節 ](../../reporting/using/about-dynamic-reports.md) を参照してください。

**関連トピック**：

* [ パーソナライズされたメールの作成 ](../../channels/using/key-steps-to-send-a-message.md) 手順ガイド
* [Adobe CampaignとDreamweaverの統合](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Adobe Experience Managerとの統合](../../integrating/using/integrating-with-experience-manager.md)

## チュートリアルビデオ {#video}

このビデオでは、メールの作成方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

その他のCampaign Standardチュートリアルビデオについては、[ こちら ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。
