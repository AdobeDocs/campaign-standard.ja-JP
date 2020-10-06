---
title: SMS メッセージの作成
description: Adobe Campaign で単一送信の SMS メッセージを作成するには、次の手順に従います。
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---


# SMS メッセージの作成{#creating-an-sms-message}

SMS 配信の作成は、通常の E メールの作成と非常に似ています。次の手順では、このチャネルに固有の設定について説明します。その他のオプションについて詳しくは、[E メールの作成](../../channels/using/creating-an-email.md)を参照してください。

詳細な SMS パラメーターについて詳しくは、[SMS チャネルの設定](../../administration/using/configuring-sms-channel.md)の節を参照してください。

SMS メッセージを作成して携帯電話に送信するには、次のものが必要です。

* **[!UICONTROL Bulk delivery]**&#x200B;モードで&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;チャネルに設定された&#x200B;**[!UICONTROL Routing]**&#x200B;外部アカウント。詳しくは、[ルーティング](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)の節を参照してください。
* この外部アカウントに正しくリンクされている配信テンプレート。

1. SMS 配信を作成します。Adobe Campaign [ホームページ](../../start/using/interface-description.md#home-page)の[キャンペーン](../../start/using/marketing-activities.md#creating-a-marketing-activity)、または[マーケティングアクティビティリスト](../../start/using/programs-and-campaigns.md#creating-a-campaign)から実行できます。

   SMS アクティビティをワークフローに追加することもできます。詳しくは、[ワークフロー](../../automating/using/sms-delivery.md)ガイドを参照してください。

   メッセージを作成する際には、ウィザードが表示されるので、その指示に従って重要な手順を実行できます。ウィザードで定義した内容は、後でメッセージダッシュボードから編集できます。

1. 使用するテンプレートを選択します。すぐに使用できる SMS テンプレートか、独自のテンプレートのいずれかを選択できます。

   ![](assets/sms_creation_1.png)

   携帯電話に配信するには、配信テンプレートが SMS ルーティング外部アカウントに正しくリンクされている必要があります。

1. SMS の一般的なプロパティを入力します。

   ![](assets/sms_creation_2.png)

   アクティビティラベルとその ID は両方ともインターフェイスに表示されますが、メッセージ受信者には表示されません。

1. ターゲットとするオーディエンスを指定します。既存のオーディエンスを選択するか、ルールを定義および組み合わせて母集団を直接ターゲットにすることができます。

   ![](assets/sms_creation_3.png)

1. SMS に内容を追加します。SMS の作成が完了したら、配信ダッシュボードの「**[!UICONTROL Content]**」セクションをクリックして、コンテンツを定義することもできます。[SMS とプッシュコンテンツのデザインについて](../../channels/using/about-sms-and-push-content-design.md)を参照してください。

   SMS メッセージの内容にパーソナライゼーションフィールドや条件付きテキストを挿入した場合、メッセージの長さは受信者によって異なることがあります。実際、これらの要因によって、GSM エンコーディングでは考慮されない文字が含まれてしまう可能性があります。パーソナライゼーションが実行された後でメッセージの長さを評価する必要があるのは、このためです。[SMS メッセージのパーソナライズ](../../channels/using/personalizing-sms-messages.md)を参照してください。

   ![](assets/sms_creation_4.png)

1. メッセージの作成を確認します。そのダッシュボードが表示されます。
1. 送信をスケジュールします。SMS は、メッセージの準備直後に手動で送信することも、スケジュールされた日に自動的に送信することもできます。[メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。
1. メッセージの有効性、パーソナライゼーション、ターゲットを分析するために、メッセージを準備します。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >過剰に配信を受けているプロファイルをキャンペーンから自動的に除外するグローバルなクロスチャネル疲労ルールを設定できます。[疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

1. 配達確認を送信してメッセージを確認および検証し、インボックスのレンダリングを監視します。[配達確認の送信](../../sending/using/sending-proofs.md)の節を参照してください。
1. メッセージの送信を確認します。送信は、定義したスケジュールに従って開始されます。

   ![](assets/sms_creation_7.png)

メッセージが送信されます。メッセージダッシュボードとログを使用して、配信を確認できます。

送信が完了したら、組み込み配信レポートまたはカスタム配信レポートを使用して、メッセージの影響の測定を開始できます。

**関連トピック：**

* [SMS とプッシュコンテンツのデザインについて](../../channels/using/about-sms-and-push-content-design.md)
* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
* [SMS 配信の作成](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/communication-channels/mobile/sms/sms-delivery.translate.html)ビデオ
