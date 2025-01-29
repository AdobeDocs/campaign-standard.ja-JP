---
title: メール配信
description: 「メール配信」アクティビティでは、ワークフローでの単一送信メールまたは繰り返しメールの送信を設定できます。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e38ff3dd-8fb0-419b-9090-a3165852bf83
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 88%

---

# メール配信{#email-delivery}

## 説明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

「**[!UICONTROL Email delivery]**」アクティビティでは、ワークフローでのメールの送信を設定できます。これは、1 回だけ送信する&#x200B;**単一送信**&#x200B;メールか、**繰り返し**&#x200B;メールのどちらかです。

単一送信メールは、1 回だけ送信される標準的なメールです。

繰り返しメールでは、定義済みの期間中に同じメールを異なるターゲットに何度でも送信できます。期間ごとの配信を集計して、ニーズに応じたレポートを取得できます。

## 使用コンテキスト {#context-of-use}

「**[!UICONTROL Email delivery]**」アクティビティは、一般的に、同じワークフロー内で計算されるターゲットへのメール送信を自動化するために使用されます。

スケジューラーにリンクすれば、繰り返しメールを定義できます。

メール受信者は、「クエリ」や「積集合」などのターゲティングアクティビティを通じて、同じワークフロー内のアクティビティの上流で定義されます。

メッセージの準備は、ワークフロー実行パラメーターに従ってトリガーされます。メッセージを送信するために手動確認を要求するかどうかをメッセージダッシュボードで選択できます（デフォルトでは必須）。ワークフローは、手動で開始するか、ワークフロー内に「スケジューラー」アクティビティを配置して自動的に実行することができます。

**関連トピック：**

* [ユースケース：週に 1 回のメール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [ユースケース：場所でセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [ユースケース：補完を含んだ配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [ユースケース：リターゲティングワークフローで開封者以外に新しい配信を送信する](../../automating/using/workflow-cross-channel-retargeting.md)
* [ユースケース：誕生日配信](../../automating/using/birthday-delivery.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Email delivery]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、（配信自体のオプションではなく）アクティビティの一般的なプロパティや詳細設定オプションにアクセスできます。このボタンは「**[!UICONTROL Email delivery]**」アクティビティに固有のものです。メールのプロパティにアクセスするには、メールダッシュボードのアクションバーを使用します。

1. メールの送信モードを次の中から選択します。

   * **[!UICONTROL Email]**：メールは 1 回だけ送信されます。アウトバウンドトランジションをアクティビティに追加するかどうかをここで指定できます。トランジションタイプについては、この手順のステップ 7 で詳しく説明します。
   * **[!UICONTROL Recurring email]**：「**[!UICONTROL Scheduler]**」アクティビティで定義されている頻度に従って、メールが繰り返し送信されます。送信の集計期間を選択します。これにより、定義済みの期間中に発生したすべての送信を 1 つのメールに再グループ化することができます。このメールは&#x200B;**繰り返し実行**&#x200B;とも呼ばれ、アプリケーションのマーケティングアクティビティリストからアクセス可能です。

     例えば、毎日送信する誕生日の繰り返しメールの場合、送信を 1 ヶ月ごとに集計するように選択できます。これにより、毎日送信するメールでも、配信のレポートを月単位で受け取ることができます。

   >[!NOTE]
   >
   >繰り返し配信は、**集計期間** に基づいて準備されます。 例えば、集計期間が「日別」の場合、配信は 1 日に 1 回だけ再準備されます。 このワークフローを 1 日に複数回呼び出す予定がある場合は、[!UICONTROL No aggregation] を使用します。

1. メールのタイプを選択します。メールのタイプは、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Delivery templates]**&#x200B;メニューに定義されているメールテンプレートに基づいています。
1. メールの一般的なプロパティを入力します。既存のキャンペーンに E メールを添付することもできます。ワークフローの配信アクティビティのラベルが、メールのラベルに更新されます。
1. メールコンテンツを定義します。[コンテンツ編集](../../designing/using/designing-content-in-adobe-campaign.md)に関する節を参照してください。
1. デフォルトでは、「**[!UICONTROL Email delivery]**」アクティビティにアウトバウンドトランジションは含まれていません。アウトバウンドトランジションを「**[!UICONTROL Email delivery]**」アクティビティに追加する場合は、アクティビティの詳細設定オプション（アクティビティのクイックアクションにある ![](assets/dlv_activity_params-24px.png) ボタンで開く）の「**[!UICONTROL General]**」タブに移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**：インバウンドトランジションとまったく同じ母集団を含んだアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**：メールの送信先となった母集団を含んだアウトバウンドトランジションを生成できます。配信準備の際に除外されるターゲットのメンバー（強制隔離、無効なメールなど）は、このトランジションから除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くとメールダッシュボードに直接に移動します。そのコンテンツのみ編集可能です。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみトリガーされます。ワークフローで作成したメッセージでも、ワークフローを開始した後で送信の確認をおこなう必要があります。ただし、メッセージダッシュボードから操作している場合と、メッセージをワークフローから作成した場合に限り、「**[!UICONTROL Request confirmation before sending messages]**」オプションを無効にできます。このオプションをオフにした場合は、準備が完了したら、追加の通知なしでそのままメッセージが送信されます。

## 備考 {#remarks}

ワークフロー内で作成された配信には、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを確認できます。メールの概要パネルのリンクを使用すると、リンクされた要素（ワークフロー、キャンペーン、繰り返しメールの場合はさらに親配信）に直接アクセスできます。

![](assets/wkf_display_recurrent_executions_2.png)

ただし、繰り返し配信の実行は、デフォルトで非表示になっています。この配信を表示する場合は、マーケティングアクティビティの検索パネルで「**[!UICONTROL Show recurring executions]**」オプションをオンにします。

![](assets/wkf_display_recurrent_executions.png)

親配信では、「**[!UICONTROL Email delivery]**」アクティビティの設定時に指定した集計期間に従って、処理済みの送信の合計数が表示されます（親配信には、マーケティングアクティビティリストからアクセスすることも、関連する繰り返し実行から直接アクセスすることもできます）。この合計数を表示するには、![](assets/wkf_dlv_detail_button.png) をクリックして、親配信の「**[!UICONTROL Deployment]**」ブロックの詳細表示を開きます。

![](assets/wkf_display_recurrent_executions_3.png)
