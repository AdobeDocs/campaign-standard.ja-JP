---
solution: Campaign Standard
product: campaign
title: プッシュ通知配信
description: プッシュ通知配信アクティビティを使用すると、ワークフロー内で1回のプッシュ通知の送信、または定期的なプッシュ通知の送信を設定できます。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---


# プッシュ通知配信{#push-notification-delivery}

## 説明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** activity allows you to configure sending a push notification in a workflow. これは、1回の送信通知で1回だけ送信するか、定期的な通知にすることができます。

* **単一** 送信通知は、標準のモバイルアプリプッシュ通知配信で、1回だけ送信されます。
* **定期的な通知を使用すると** 、定義した期間に同じモバイルアプリのプッシュ通知配信を複数の異なるターゲットに複数回送信できます。 期間ごとの配信を集計して、ニーズに応じたレポートを取得できます。

## 使用状況 {#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

スケジューラーにリンクした場合、定期的なプッシュ通知を定義できます。

受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフローのアクティビティの上流に定義されます。

メッセージの準備は、ワークフロー実行パラメーターに従ってトリガーされます。メッセージを送信するために手動確認を要求するかどうかをメッセージダッシュボードで選択できます（デフォルトでは必須）。ワークフローは、手動で開始するか、ワークフロー内に「スケジューラー」アクティビティを配置して自動的に実行することができます。

**関連トピック**

* [ワークフローを含む定期的なプッシュ通知の送信](../../automating/using/recurring-push-notifications.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Push notification]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、（配信自体のオプションではなく）アクティビティの一般的なプロパティや詳細設定オプションにアクセスできます。このボタンは「**[!UICONTROL Push notification]**」アクティビティに固有のものです。プッシュ通知のプロパティは、プッシュダッシュボードのアクションバーからアクセスできます。

1. プッシュ通知送信モードを選択します。

   * **[!UICONTROL Single notification]**:プッシュ通知は1回だけ送信されます。 アウトバウンドトランジションをアクティビティに追加するかどうかをここで指定できます。トランジションタイプについては、この手順のステップ 7 で詳しく説明します。
   * **[!UICONTROL Recurring notification]**:プッシュ通知は、 **[!UICONTROL Scheduler]** アクティビティで定義されている頻度に従って、複数回送信されます。 送信の集計期間を選択します。This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application&#39;s marketing activity list.

      例えば、誕生日の通知を毎日繰り返し送信する場合は、1か月あたりの送信を集計できます。 これにより、毎日通知が送信されるにもかかわらず、配信のレポートを毎月受け取ることができます。

1. 通知タイプを選択します。 これらのタイプは、//メニューで定義されているプッシュ通知テンプレート **[!UICONTROL Resources]** に基づいてい **[!UICONTROL Templates]** ます **[!UICONTROL Delivery templates]** 。
1. プッシュ通知の一般的なプロパティを入力します。 既存のキャンペーンに SMS を添付することもできます。ワークフローの配信アクティビティのラベルが、プッシュ通知ラベルで更新されます。
1. プッシュ通知の内容を定義します。 プッシュ通知の [作成を参照してください。](../../channels/using/preparing-and-sending-a-push-notification.md)
1. デフォルトでは、「**[!UICONTROL Push notification]**」アクティビティにアウトバウンドトランジションは含まれていません。アウトバウンドトランジションを「**[!UICONTROL Push Notification]**」アクティビティに追加する場合は、アクティビティの詳細設定オプション（アクティビティのクイックアクションにある ![](assets/dlv_activity_params-24px.png) ボタンで開く）の「**[!UICONTROL General]**」タブに移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**：インバウンドトランジションとまったく同じ母集団を含んだアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、通知の送信先の母集団を含むアウトバウンドトランジションを生成できます。 配信準備中に除外されたターゲットの部材は、このトランジションから除外される。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、直接プッシュ通知ダッシュボードに移動します。 そのコンテンツのみ編集可能です。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみトリガーされます。ワークフローで作成したメッセージでも、ワークフローを開始した後で送信の確認をおこなう必要があります。ただし、メッセージダッシュボードから操作している場合と、メッセージをワークフローから作成した場合に限り、「**[!UICONTROL Request confirmation before sending messages]**」オプションを無効にできます。このオプションをオフにした場合は、準備が完了したら、追加の通知なしでそのままメッセージが送信されます。

## 備考 {#remarks}

ワークフロー内で作成された配信には、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを確認できます。プッシュ通知の概要ペインのリンクを使用すると、リンクされた要素(ワークフロー、キャンペーンなど)に直接アクセスできます。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). この合計数を表示するには、![](assets/wkf_dlv_detail_button.png) をクリックして、親配信の「**[!UICONTROL Deployment]**」ブロックの詳細表示を開きます。
