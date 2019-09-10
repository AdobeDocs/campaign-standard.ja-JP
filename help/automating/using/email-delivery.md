---
title: Eメール配信
seo-title: Eメール配信
description: Eメール配信
seo-description: 電子メール配信活動では、ワークフローで単一の送信電子メールまたは定期的な電子メールを送信するように構成できます。
page-status-flag: 決して活性化されていない
uuid: 7de53431-84e-4d21-8361-2775ad314ed2
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: チャンネル活動
discoiquuid: 5f288cf6- f8ff-4ac-9c1a-8010260554bb
context-tags: 配送、ワークフロー、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Eメール配信{#email-delivery}

## 説明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

**[!UICONTROL Email delivery]** このアクティビティでは、ワークフローで電子メールを送信するように構成できます。これは **1回の送信** 電子メールで送信することも、1回だけ送信することも **、定期的** に送信することもできます。

一回のメールは標準のメールで、一度送った。

定期的な電子メールでは、定義された期間にわたって同じ電子メールを異なるターゲットに複数回送信できます。必要に応じたレポートを取得するには、期間ごとの搬送を集計できます。

## 使用状況 {#context-of-use}

**[!UICONTROL Email delivery]** このアクティビティは通常、同じワークフローで計算されたターゲットへの電子メールの送信を自動化するために使用されます。

スケジューラにリンクすると、定期的な電子メールを定義できます。

電子メール受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティの上流に定義されます。

メッセージ準備は、ワークフロー実行パラメーターに従ってトリガーされます。メッセージ・ダッシュボードから、メッセージを送信するかどうかを手動で確認するかどうかを選択できます（デフォルトでは必須）。ワークフローを手動で開始するか、ワークフローにスケジューラアクティビティを配置して実行を自動化できます。

## 構成 {#configuration}

1. **[!UICONTROL Email delivery]** アクティビティをワークフローにドラッグアンドドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを介して、アクティビティの全般的なプロパティおよび詳細オプションにアクセスできます（配信自体ではありません）。このボタンは **[!UICONTROL Email delivery]** アクティビティに固有です。電子メールのプロパティには、電子メールダッシュボードのアクションバーを介してアクセスできます。

1. 電子メール送信モードを選択:

   * **[!UICONTROL Email]**:メールが一回送られた。ここでは、アクティビティに送信遷移を追加するかどうかを指定できます。異なる遷移タイプについては、手順7で詳しく説明します。
   * **[!UICONTROL Recurring email]**:電子メールは、 **[!UICONTROL Scheduler]** アクティビティで定義された頻度に従って数回送信されます。送信の集計期間を選択します。これにより、定義済みの期間中に発生したすべての送信を1つの電子メールで再グループ化できます。これは **定期的な実行** とも呼ばれ、アプリケーションのマーケティング活動リストからアクセスできます。

      たとえば、定期的な誕生日電子メールで送信される定期的な電子メールの場合は、毎月送信するように選択できます。これにより、電子メールは毎日送信されますが、毎月の配信に関するレポートを受け取ることができます。

1. 電子メールの種類を選択します。電子メールの種類は、&gt; **[!UICONTROL Resources]****[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** メニューで定義された電子メールテンプレートから取得します。
1. 電子メールの一般的なプロパティを入力します。既存のキャンペーンにアタッチすることもできます。ワークフローの配信アクティビティのラベルが電子メールラベルで更新されます。
1. 電子メールの内容を定義します。[コンテンツ編集](../../designing/using/about-email-content-design.md)に関するセクションを参照してください。
1. 既定では、アクティビティ **[!UICONTROL Email delivery]** には送信遷移は含まれません。**[!UICONTROL Email delivery]** アクティビティに送信遷移を追加する場合は、詳細アクティビティ **[!UICONTROL General]** のオプション（アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタン）のタブに移動し、次のいずれかのオプションを確認します。

   * **[!UICONTROL Add outbound transition without the population]**:これにより、着信遷移とまったく同じ人口を含む送信遷移を生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、電子メールが送信された人口を含む送信推移を生成できます。配信準備中に除外されたターゲットのメンバー（検疫、無効な電子メールなど）この遷移から除外されます。

1. アクティビティの構成を確認し、ワークフローを保存します。

アクティビティを再度開くと、電子メールダッシュボードに直接移動します。編集できるのはそのコンテンツだけです。

既定では、配信ワークフローを開始するとメッセージの準備のみがトリガーされます。ワークフローから作成されたメッセージの送信は、ワークフローの開始後も確認する必要があります。メッセージのダッシュボードから、メッセージがワークフローから作成された場合にのみ、オプション **[!UICONTROL Request confirmation before sending messages]** を無効にできます。このオプションをオフにすると、準備が完了するとメッセージが送信されなくなります。

## 解説 {#remarks}

ワークフロー内で作成された搬送は、アプリケーションのマーケティング活動リストでアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。電子メール要約ペインのリンクでは、リンクされた要素（ワークフロー、キャンペーン、定期的な電子メールの場合）に直接アクセスできます。

![](assets/wkf_display_recurrent_executions_2.png)

ただし、定期的な搬送の実行はデフォルトでマスクされます。これらを表示するには、マーケティング活動の「検索パネル」の **[!UICONTROL Show recurring executions]** オプションを確認します。

![](assets/wkf_display_recurrent_executions.png)

マーケティング活動リストからアクセス可能な親搬送の場合、または関連する定期実行を介して直接実行できる場合は、処理された送信の合計数（ **[!UICONTROL Email delivery]** アクティビティの構成時に指定した集計期間に従って）を表示できます。これを行うには、親配送の **[!UICONTROL Deployment]** ブロックの詳細ビューを選択して開き ![](assets/wkf_dlv_detail_button.png)ます。

![](assets/wkf_display_recurrent_executions_3.png)

## 例 {#example}

![](assets/wkf_delivery_example_1.png)

この例は、誕生日ワークフローです。毎日、その日に誕生日があるプロフィールに電子メールが送られます。これを行うには:

* では **[!UICONTROL Scheduler]** 、毎日8mでワークフローを開始できます。

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** このアクティビティを使用すると、電子メールを提供したプロファイルを計算し、ワークフローを実行するたびに現在の日にその誕生日を設定できます。誕生日の計算は、クエリ編集ツールのパレットで使用可能な定義済みフィルターを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* 繰り返し **[!UICONTROL Email]** ます。送信は月単位で集計されます。したがって、1か月で送信されるすべての電子メールは単一のビューに集約されます。1年間で365の配信が実行されますが、Adobe Campaignインターフェイスでは12ビュー（ **定期的な実行**&#x200B;とも呼ばれます）に再グループ化されます。履歴およびレポートの詳細は毎月表示され、送信ごとには表示されません。

   ![](assets/wkf_delivery_example_4.png)

**関連トピック**

* [ユースケース:1週間の電子メール配信を作成する](../../automating/using/workflow-weekly-offer.md)
* [ユースケース:場所にセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [ユースケース:補足を使用した搬送の作成](../../automating/using/workflow-created-query-with-complement.md)
* [ユースケース:新しい配送を非公開者に送信するワークフローの再ターゲット](../../automating/using/workflow-cross-channel-retargeting.md)