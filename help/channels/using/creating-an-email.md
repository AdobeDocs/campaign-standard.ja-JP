---
title: E メールの作成
description: Adobe Campaignで単一送信Eメールを作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 20%

---

# E メールの作成{#creating-an-email}

[キャンペーン](../../start/using/marketing-activities.md#creating-a-marketing-activity)、Adobe Campaignの[ホームページ](../../start/using/interface-description.md#home-page)、または[マーケティングアクティビティリスト](../../start/using/marketing-activities.md#about-marketing-activities)から電子メールを作成できます。 ワークフローから 1 回限りの電子メールや定期的な電子メールを作成することもできます。

![](assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

1. 電子メールマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   デフォルトでは、各マーケティングアクティビティに対して複数のテンプレートから選択できます。 これにより、ニーズに応じて特定のパラメーターを事前設定し、ブランドを配信に割り当てることもできます。 詳しくは、[テンプレートの管理](../../start/using/marketing-activity-templates.md)を参照してください。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >フォローアップおよび A/B テストテンプレートは、デフォルトで非表示になっています。左側（**[!UICONTROL Filter]**&#x200B;横パネル）のチェックボックスをオンにして表示します。

1. Eメールの一般的なプロパティを入力します。 「**ラベル**」フィールドに名前を入力し、IDを編集します。 アクティビティ名とそのIDは両方ともインターフェイスに表示されますが、メッセージ受信者には表示されません。

   キャンペーンコンテンツに表示される説明を追加できます。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >親キャンペーン内に、ホームページまたはマーケティングアクティビティのリストからEメールを作成できます。 作成済みのキャンペーンから選択します。

1. ビジネス上の基準に基づいて、メッセージのターゲットを定義します。 [プロファイルについて](../../audiences/using/about-profiles.md)を参照してください。

   また、メッセージを検証するテストプロファイルを定義することもできます。 [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

   ![](assets/email_creation_3.png)

1. [Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)を使用して、メッセージの内容、送信者名、件名を定義し、パーソナライズします。 詳しくは、[Eメールコンテンツのデザインについて](../../designing/using/designing-content-in-adobe-campaign.md)を参照してください。

   ![](assets/email_creation_4.png)

   事前定義済みのコンテンツテンプレートを使用して、またはDreamweaverやAdobe Experience Managerを使用して、メッセージを直接デザインできます。 デザイナーに似ていない場合は、準備済みのコンテンツをアップロードしたり、URLから既存のコンテンツをインポートしたりできます。 詳しくは、[既存のコンテンツの選択](../../designing/using/using-existing-content.md)を参照してください。

1. メッセージのプレビュー. [メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。
1. E メールの作成を確認します。

   >[!NOTE]
   >
   >Eメールを保存するには、まずコンテンツを編集する必要があります。 この時点で&#x200B;**[!UICONTROL Cancel]**&#x200B;をクリックした場合、ウィザードは完了せず、電子メールは作成されません。

   Eメールダッシュボードが表示されます。 メッセージを確認し、[送信の準備](../../sending/using/preparing-the-send.md)を行うことができます。

   右上隅の「**[!UICONTROL Edit properties]**」ボタンを使用すると、Eメールのプロパティを編集できます。 例えば、配信の準備時にラベルが計算されるようにEメールを設定できます。  使用可能なパラメーターは、[この節](../../administration/using/configuring-email-channel.md#list-of-email-properties)に記載されています。

   ![](assets/delivery_dashboard_2.png)

1. 送信をスケジュールします。[メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。

   ![](assets/delivery_planning.png)

1. メッセージを準備して、ターゲットを分析します。 [送信の準備](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >過剰に配信を受けているプロファイルをキャンペーンから自動的に除外するグローバルなクロスチャネル疲労ルールを設定できます。詳しくは、[疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

1. 配達確認を送信してメッセージを確認および検証し、インボックスのレンダリングを監視します。[配達確認の送信](../../sending/using/sending-proofs.md)を参照してください。

   ![](assets/bat_select.png)

1. メッセージを送信し、メッセージダッシュボードとログを使用して配信を確認します。 [メッセージの送信](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/confirm_delivery.png)

1. 配信レポートを使用して、メッセージの影響を測定します。 レポートについて詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。

**関連トピック**：

* [パーソナライズされ](https://helpx.adobe.com/jp/campaign/kb/acs-get-started-with-emails.html) たEメールの作成手順ガイド
* [Adobe CampaignとDreamweaverの統合](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Adobe Experience Managerとの統合](../../integrating/using/integrating-with-experience-manager.md)

## チュートリアルビデオ {#video}

このビデオでは、Eメールの作成方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)からご覧いただけます。
