---
title: プッシュ通知配信
description: プッシュ通知配信アクティビティを使用すると、ワークフロー内で1回のプッシュ通知の送信、または定期的なプッシュ通知の送信を設定できます。
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 3%

---


# プッシュ通知配信{#push-notification-delivery}

## 説明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

この **[!UICONTROL Push notification]** アクティビティでは、ワークフローでのプッシュ通知の送信を設定できます。 これは、 **単一の送信通知で1回だけ送信するか** 、 **** 繰り返し送信するかのいずれかです。

単一送信通知は、標準的なモバイルアプリのプッシュ通知配信で、1回だけ送信されます。

定期的な通知を使用すると、定義した期間に同じモバイルアプリのプッシュ通知配信を複数の異なるターゲットに複数回送信できます。 期間ごとの配信を集計して、ニーズに合ったレポートを取得できます。

## 使用状況 {#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

スケジューラーにリンクした場合、定期的なプッシュ通知を定義できます。

受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフローのアクティビティの上流に定義されます。

メッセージ作成は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動で確認を行ってメッセージを送信するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

**関連トピック**

* [ワークフローを含む定期的なプッシュ通知の送信](../../automating/using/recurring-push-notifications.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Push notification]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、アクティビティの一般的なプロパティや詳細なオプション(配信自体ではなく)にアクセスできます。 このボタンは、 **[!UICONTROL Push notification]** アクティビティに固有です。 プッシュ通知のプロパティは、プッシュダッシュボードのアクションバーからアクセスできます。

1. プッシュ通知送信モードを選択します。

   * **[!UICONTROL Single notification]**: プッシュ通知は1回だけ送信されます。 外部トランジションをアクティビティに追加するかどうかを指定できます。 様々なトランジションタイプについては、この手順の手順7で説明します。
   * **[!UICONTROL Recurring notification]**: プッシュ通知は、 **[!UICONTROL Scheduler]** アクティビティで定義されている頻度に従って、複数回送信されます。 送信の集計期間を選択します。 これにより、定義した期間に発生したすべての送信を、1回の1回のプッシュ通知で再グループ化できます。この通知は **反復実行** と呼ばれ、アプリのマーケティングアクティビティリストからアクセスできます。

      例えば、誕生日の通知を毎日繰り返し送信する場合は、1か月あたりの送信を集計できます。 これにより、毎日通知が送信されるにもかかわらず、配信のレポートを毎月受け取ることができます。

1. 通知タイプを選択します。 これらのタイプは、//メニューで定義されているプッシュ通知テンプレート **[!UICONTROL Resources]** に基づいてい **[!UICONTROL Templates]** ます **[!UICONTROL Delivery templates]** 。
1. プッシュ通知の一般的なプロパティを入力します。 既存のキャンペーンに添付することもできます。 ワークフローの配信アクティビティのラベルが、プッシュ通知ラベルで更新されます。
1. プッシュ通知の内容を定義します。 プッシュ通知の [作成を参照してください。](../../channels/using/preparing-and-sending-a-push-notification.md)
1. デフォルトでは、 **[!UICONTROL Push notification]** アクティビティには送信トランジションは含まれません。 外部トランジションを **[!UICONTROL Push Notification]** アクティビティに追加する場合は、[詳細アクティビティ]タブ(アクティビティのクイックアクションの **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) ボタン)に移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**: これにより、受信トランジションと完全に同じ母集団を含む送信トランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**: これにより、通知の送信先の母集団を含むアウトバウンドトランジションを生成できます。 配信準備中に除外されたターゲットの部材は、このトランジションから除外される。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、直接プッシュ通知ダッシュボードに移動します。 編集できるのは、そのコンテンツだけです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージダッシュボードから、およびメッセージがワークフローから作成された場合のみ、この **[!UICONTROL Request confirmation before sending messages]** オプションを無効にできます。 このオプションをオフにすると、準備が完了した後、メッセージは予告なしに送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストからアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 プッシュ通知の概要ペインのリンクを使用すると、リンクされた要素(ワークフロー、キャンペーンなど)に直接アクセスできます。

マーケティングアクティビティリストからアクセスできる親配信では、処理された送信の総数を表示できます( **[!UICONTROL Push notification]** アクティビティの設定時に指定した集計期間に従います)。 これを行うには、を選択して親配信の **[!UICONTROL Deployment]** ブロックの詳細表示を開き ![](assets/wkf_dlv_detail_button.png)ます。
