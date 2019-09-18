---
title: 電子メール配信
seo-title: 電子メール配信
description: 電子メール配信
seo-description: 電子メール配信アクティビティを使用すると、ワークフロー内で1つの送信電子メールまたは定期的な電子メールを送信するように構成できます。
page-status-flag: 未活性化の
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネル活動
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: 配信，ワークフロー，メイン
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# 電子メール配信{#email-delivery}

## 説明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

このア **[!UICONTROL Email delivery]** クティビティを使用して、ワークフローで電子メールを送信するように構成できます。 1回の送信メ **ール** 、1回の送信メール、または繰り返しの電子メールの場合もあ **ります** 。

1通の電子メールは標準の電子メールで、1回送信されます。

定期的な電子メールを使用すると、定義した期間に同じ電子メールを複数回、異なるターゲットに送信できます。 各期間の搬送を集計して、必要に応じたレポートを取得できます。

## 使用状況 {#context-of-use}

通常、こ **[!UICONTROL Email delivery]** のアクティビティは、同じワークフローで計算されたターゲットに電子メールを送信する際に自動化するために使用されます。

スケジューラにリンクされている場合は、定期的な電子メールを定義できます。

電子メールの受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフローのアクティビティの上流に定義されます。

メッセージの準備は、ワークフロー実行パラメータに従ってトリガされます。 メッセージ·ダッシュボードから、メッセージを送信する手動確認を要求するかどうかを選択できます（デフォルトで必要）。 ワークフローを手動で開始するか、スケジューラ·アクティビティをワークフローに配置して実行を自動化できます。

## 構成 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Email delivery]** にドラッグアンドドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションからボタンを使用して、アクティビティの一般プロパティと詳細オプション(配信自体ではな ![](assets/dlv_activity_params-24px.png) い)にアクセスできます。 このボタンはアクティビティに固有 **[!UICONTROL Email delivery]** です。 電子メールのプロパティは、電子メールダッシュボードのアクションバーからアクセスできます。

1. 電子メール送信モードを選択してください：

   * **[!UICONTROL Email]**:メールは1回だけ送信されます。 ここで、アクティビティに外部遷移を追加するかどうかを指定できます。 この手順の手順7では、異なる遷移タイプについて詳しく説明します。
   * **[!UICONTROL Recurring email]**:アクティビティで定義された頻度に従って、電子メールが複数回送信さ **[!UICONTROL Scheduler]** れます。 送信の集計期間を選択します。 これにより、定義された期間中に発生したすべての送信を1つのEメールで再グループ化できます。このEメールは **Recurring Execution** （繰り返し実行）とも呼ばれ、アプリケーションのマーケティング活動リストからアクセスできます。

      たとえば、定期的な誕生日の電子メール（毎日送信）の場合は、1か月あたりの送信を集計するように選択できます。 これにより、毎日メールが送信されるのに、毎月の配信に関するレポートを受け取ることができます。

1. 電子メールの種類を選択します。 電子メールの種類は、 &gt; &gt; **[!UICONTROL Resources]** &gt;メニューで定義された電子メールテン **[!UICONTROL Templates]** プレートか **[!UICONTROL Delivery templates]** ら取得します。
1. 電子メールの全般プロパティを入力します。 既存のキャンペーンに添付することもできます。 ワークフローの配信活動のラベルが電子メールラベルで更新されます。
1. 電子メールの内容を定義します。 内容編集の項を参 [照](../../designing/using/overview.md)。
1. デフォルトでは、アクティビティ **[!UICONTROL Email delivery]** にはアウトバウンド遷移は含まれません。 アクティビティにアウトバウンド遷移を追加する場合は、アクティビティの **[!UICONTROL Email delivery]** クイックアクションの「アクティビティの詳細」(Advanced Activity)オプションの **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) タブ（アクティビティのクイックアクションのボタン）に移動し、次のいずれかのオプションを選択します。

   * **[!UICONTROL Add outbound transition without the population]**:これにより、着信推移とまったく同じ母集団を含む発信推移を生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、電子メールの送信先の母集団を含む送信遷移を生成できます。 配信準備中に除外されたターゲットのメンバー（検疫、無効な電子メールなど）はこの遷移から除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再び開くと、電子メールダッシュボードに直接移動します。 コンテンツのみを編集できます。

既定では、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローから作成されたメッセージの送信は、ワークフローの開始後も確認する必要があります。 ただし、メッセージダッシュボードから、ワークフローからメッセージが作成された場合にのみ、このオプションを無効にで **[!UICONTROL Request confirmation before sending messages]** きます。 このオプションをオフにすると、準備が完了した後に、通知なしでメッセージが送信されます。

## 備考 {#remarks}

ワークフロー内で作成された搬送には、アプリケーションのマーケティング活動リストからアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 電子メールの概要ウィンドウのリンクを使用すると、リンクされた要素（定期的な電子メールの場合は、ワークフロー、キャンペーン、親の配信）に直接アクセスできます。

![](assets/wkf_display_recurrent_executions_2.png)

ただし、繰り返し送信の実行はデフォルトでマスクされます。 これらを表示するには、マーケティン **[!UICONTROL Show recurring executions]** グ活動の検索パネルのオプションを確認します。

![](assets/wkf_display_recurrent_executions.png)

マーケティング活動リストから、または関連する繰り返し実行を介して直接アクセスできる親搬送では、処理された送信の合計数を（アクティビティが構成されたときに指定された集計期間に従って）表示で **[!UICONTROL Email delivery]** きます。 これを行うには、を選択して親搬送のブロックの詳細ビュー **[!UICONTROL Deployment]** を開きます ![](assets/wkf_dlv_detail_button.png)。

![](assets/wkf_display_recurrent_executions_3.png)

## 例 {#example}

![](assets/wkf_delivery_example_1.png)

この例は、誕生日ワークフローです。 毎日、誕生日がその日のプロファイルにメールが送られます。 これを行うには、次の手順に従います。

* では、 **[!UICONTROL Scheduler]** 毎日午前8時にワークフローを開始できます。

   ![](assets/wkf_delivery_example_2.png)

* このア **[!UICONTROL Query]** クティビティでは、ワークフローが実行されるたびに、電子メールを提供し、その誕生日が現在の日にあるプロファイルを計算できます。 誕生日の計算は、クエリ編集ツールのパレットで使用可能な定義済みフィルタを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* が繰り返 **[!UICONTROL Email]** し発生します。 送信は月別に集計されます。 したがって、1か月で送信されるすべてのEメールは、1つのビューに集約されます。 そのため、1年間で365個の配信が実行されますが、Adobe Campaignインターフェイスで12個のビュー(繰り返し実行 ****)に再グループ化されます。 履歴とレポートの詳細は、送信ごとに表示されるのではなく、毎月表示されます。

   ![](assets/wkf_delivery_example_4.png)

**関連トピック**

* [ユースケース：週1回の電子メール配信を作成する](../../automating/using/workflow-weekly-offer.md)
* [ユースケース：場所にセグメント化された搬送の作成](../../automating/using/workflow-segmentation-location.md)
* [ユースケース：補完を含む搬送の作成](../../automating/using/workflow-created-query-with-complement.md)
* [ユースケース：未開封者に新しい配送を送信するワークフローを再ターゲットする](../../automating/using/workflow-cross-channel-retargeting.md)