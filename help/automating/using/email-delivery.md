---
solution: Campaign Standard
product: campaign
title: E メール配信
description: 「E メール配信」アクティビティでは、ワークフローでの単一送信 E メールまたは繰り返し E メールの送信を設定できます。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# E メール配信{#email-delivery}

## 説明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

「**[!UICONTROL Email delivery]**」アクティビティでは、ワークフローでの E メールの送信を設定できます。これは、1 回だけ送信する&#x200B;**単一送信** E メールか、**繰り返し** E メールのどちらかです。

単一送信 E メールは、1 回だけ送信される標準的な E メールです。

繰り返し E メールでは、定義済みの期間中に同じ E メールを異なるターゲットに何度でも送信できます。期間ごとの配信を集計して、ニーズに応じたレポートを取得できます。

## 使用状況 {#context-of-use}

「**[!UICONTROL Email delivery]**」アクティビティは、一般的に、同じワークフロー内で計算されるターゲットへの E メール送信を自動化するために使用されます。

スケジューラーにリンクすれば、繰り返し E メールを定義できます。

E メール受信者は、「クエリ」や「積集合」などのターゲティングアクティビティを通じて、同じワークフロー内のアクティビティの上流で定義されます。

メッセージの準備は、ワークフロー実行パラメーターに従ってトリガーされます。メッセージを送信するために手動確認を要求するかどうかをメッセージダッシュボードで選択できます（デフォルトでは必須）。ワークフローは、手動で開始するか、ワークフロー内に「スケジューラー」アクティビティを配置して自動的に実行することができます。

**関連トピック：**

* [ユースケース：週 1 回の E メール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [ユースケース：ロケーション別にセグメント化した配信の作成](../../automating/using/workflow-segmentation-location.md)
* [ユースケース：補集合を使用した配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [ユースケース：メールを開封していないユーザーに新しい配信を送信する再ターゲティングワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)
* [使用例：誕生日配信](../../automating/using/birthday-delivery.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Email delivery]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、（配信自体のオプションではなく）アクティビティの一般的なプロパティや詳細設定オプションにアクセスできます。このボタンは「**[!UICONTROL Email delivery]**」アクティビティに固有のものです。E メールのプロパティにアクセスするには、E メールダッシュボードのアクションバーを使用します。

1. E メールの送信モードを次の中から選択します。

   * **[!UICONTROL Email]**：E メールは 1 回だけ送信されます。アウトバウンドトランジションをアクティビティに追加するかどうかをここで指定できます。トランジションタイプについては、この手順のステップ 7 で詳しく説明します。
   * **[!UICONTROL Recurring email]**：「**[!UICONTROL Scheduler]**」アクティビティで定義されている頻度に従って、E メールが繰り返し送信されます。送信の集計期間を選択します。これにより、定義済みの期間中に発生したすべての送信を 1 つの E メールに再グループ化することができます。この E メールは&#x200B;**繰り返し実行**&#x200B;とも呼ばれ、アプリケーションのマーケティングアクティビティリストからアクセス可能です。

      例えば、毎日送信する誕生日の繰り返し E メールの場合、送信を 1 ヶ月ごとに集計するように選択できます。これにより、毎日送信する E メールでも、配信のレポートを月単位で受け取ることができます。
   >[!NOTE]
   >
   >**集約期間**&#x200B;に基づいて反復配信を作成する。 たとえば、集計期間が「日別」の場合、配信は1日に1回のみ再準備されます。 このワークフローを1日に複数回呼び出す場合は、[!UICONTROL No aggregation]を使用してください。

1. E メールのタイプを選択します。E メールのタイプは、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Delivery templates]**&#x200B;メニューに定義されている E メールテンプレートに基づいています。
1. E メールの一般的なプロパティを入力します。既存のキャンペーンに E メールを添付することもできます。ワークフローの配信アクティビティのラベルが、E メールのラベルに更新されます。
1. E メールコンテンツを定義します。[コンテンツ編集](../../designing/using/designing-content-in-adobe-campaign.md)に関する節を参照してください。
1. デフォルトでは、「**[!UICONTROL Email delivery]**」アクティビティにアウトバウンドトランジションは含まれていません。アウトバウンドトランジションを「**[!UICONTROL Email delivery]**」アクティビティに追加する場合は、アクティビティの詳細設定オプション（アクティビティのクイックアクションにある ![](assets/dlv_activity_params-24px.png) ボタンで開く）の「**[!UICONTROL General]**」タブに移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**：インバウンドトランジションとまったく同じ母集団を含んだアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**：E メールの送信先となった母集団を含んだアウトバウンドトランジションを生成できます。配信の準備中に（強制隔離、無効な E メールなどにより）ターゲットから除外されたメンバーは、このトランジションから除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと E メールダッシュボードに直接に移動します。そのコンテンツのみ編集可能です。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみトリガーされます。ワークフローで作成したメッセージでも、ワークフローを開始した後で送信の確認をおこなう必要があります。ただし、メッセージダッシュボードから操作している場合と、メッセージをワークフローから作成した場合に限り、「**[!UICONTROL Request confirmation before sending messages]**」オプションを無効にできます。このオプションをオフにした場合は、準備が完了したら、追加の通知なしでそのままメッセージが送信されます。

## 備考 {#remarks}

ワークフロー内で作成された配信には、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを確認できます。E メールの概要パネルのリンクを使用すると、リンクされた要素（ワークフロー、キャンペーン、繰り返し E メールの場合はさらに親配信）に直接アクセスできます。

![](assets/wkf_display_recurrent_executions_2.png)

ただし、繰り返し配信の実行は、デフォルトで非表示になっています。この配信を表示する場合は、マーケティングアクティビティの検索パネルで「**[!UICONTROL Show recurring executions]**」オプションをオンにします。

![](assets/wkf_display_recurrent_executions.png)

親配信では、「**[!UICONTROL Email delivery]**」アクティビティの設定時に指定した集計期間に従って、処理済みの送信の合計数が表示されます（親配信には、マーケティングアクティビティリストからアクセスすることも、関連する繰り返し実行から直接アクセスすることもできます）。この合計数を表示するには、![](assets/wkf_dlv_detail_button.png) をクリックして、親配信の「**[!UICONTROL Deployment]**」ブロックの詳細表示を開きます。

![](assets/wkf_display_recurrent_executions_3.png)
