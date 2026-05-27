---
title: メールの作成
description: Adobe Campaignで1回送信メールを作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
TQID: https://experienceleague.adobe.com/iqQ7Cbo3tVTu348U1mHHoi7skHMjZF3D4Qw3zvHbLVk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: d8d962e2-fcf3-4f64-82dc-4b50292e7f75
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: beb7a3c1-66ab-4786-b879-7621375b3c40
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 584
ht-degree: 16%

---

# メールの作成{#creating-an-email}

[ キャンペーン ](../../start/using/marketing-activities.md#creating-a-marketing-activity)、Adobe Campaign [ ホームページ ](../../start/using/interface-description.md#home-page)、または[ マーケティングアクティビティリスト ](../../start/using/marketing-activities.md#about-marketing-activities)からメールを作成できます。 ワークフローから1回限りのメールと定期的なメールを作成することもできます。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

1. メールマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   デフォルトでは、各マーケティングアクティビティに対して複数のテンプレートから選択できます。 これにより、ニーズに応じて特定のパラメーターを事前設定したり、配信にブランドを割り当てたりすることができます。 詳しくは、[ テンプレートの管理](../../start/using/marketing-activity-templates.md)を参照してください。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップおよび A/B テストテンプレートは、デフォルトで非表示になっています。 表示する場合は、左側のチェックボックス（**[!UICONTROL Filter]**&#x200B;横パネル）をオンにします。

1. メールの一般的なプロパティを入力します。 **ラベル** フィールドに名前を入力し、IDを編集できます。

   >[!NOTE]
   >
   >アクティビティ名とそのIDの両方がインターフェイスに表示されますが、メッセージ受信者には表示されません。
   >
   >例えばAdobe Analyticsと統合する場合などに、ID フィールドに空白が含まれていないことを確認して、差異を回避します。

   キャンペーンコンテンツに表示される説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >ホームページまたはマーケティングアクティビティのリストから、親キャンペーン内にメールを作成できます。 作成済みのキャンペーンから選択します。

1. ビジネス基準にもとづいて、メッセージのターゲットを定義します。 [ プロファイルについて](../../audiences/using/about-profiles.md)を参照してください。

   メッセージを検証するテストプロファイルを定義することもできます。 [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

   ![](assets/email_creation_3.png)

1. [電子メール Designer](../../designing/using/designing-content-in-adobe-campaign.md)を使用して、メッセージの内容、送信者名、件名を定義し、パーソナライズします。 詳しくは、[電子メールコンテンツデザインについて](../../designing/using/designing-content-in-adobe-campaign.md)を参照してください。

   ![](assets/email_creation_4.png)

   メッセージは、定義済みのコンテンツテンプレートを使用するか、DreamweaverまたはAdobe Experience Managerを使用して直接デザインできます。 デザイナーではない人でも、用意されたコンテンツをアップロードしたり、URLから既存のコンテンツをインポートしたりできます。 詳しくは、[既存のコンテンツの選択](../../designing/using/using-existing-content.md)を参照してください。

1. メッセージをプレビューします。 [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。
1. メールの作成を確認します。

   >[!NOTE]
   >
   >メールを保存できるようにするには、まずコンテンツを編集する必要があります。 この時点で&#x200B;**[!UICONTROL Cancel]**&#x200B;をクリックすると、ウィザードが完了せず、電子メールは作成されません。

   次に、メールダッシュボードが表示されます。 メッセージを確認し、[送信](../../sending/using/preparing-the-send.md)を準備できます。

   右上隅の&#x200B;**[!UICONTROL Edit properties]** ボタンを使用すると、メールのプロパティを編集できます。 例えば、配信準備時にラベルが計算されるように、メールを設定できます。  使用可能なパラメーターは、[このセクション ](../../administration/using/configuring-email-channel.md#list-of-email-properties)に記載されています。

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。 [メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。

   ![](assets/delivery_planning.png)

1. メッセージのターゲットを分析する準備を整えます。 [送信準備](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >過剰に配信を受けているプロファイルをキャンペーンから自動的に除外するグローバルなクロスチャネル疲労ルールを設定できます。 詳しくは、[疲労ルール ](../../sending/using/fatigue-rules.md)を参照してください。

1. 配達確認を送信してメッセージを確認および検証し、インボックスのレンダリングを監視します。 [ プルーフの送信](../../sending/using/sending-proofs.md)を参照してください。

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージダッシュボードとログを通じて配信を確認します。 [ メッセージの送信](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/confirm_delivery.png)

1. 配信レポートでメッセージの影響を測定。 レポートについて詳しくは、[このセクション ](../../reporting/using/about-dynamic-reports.md)を参照してください。

**関連トピック**：

* [ パーソナライズされた電子メールの作成](../../channels/using/key-steps-to-send-a-message.md) ステップバイステップガイド
* [Adobe CampaignとDreamweaverの統合](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Adobe Experience Managerとの統合](../../integrating/using/integrating-with-experience-manager.md)

## チュートリアルビデオ {#video}

このビデオでは、メールの作成方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

その他のCampaign Standardのハウツー動画は[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)でご覧いただけます。
