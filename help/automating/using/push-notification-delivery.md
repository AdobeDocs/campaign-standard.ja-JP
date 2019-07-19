---
title: プッシュ通知配信
seo-title: プッシュ通知配信
description: プッシュ通知配信
seo-description: プッシュ通知配信アクティビティを使用すると、ワークフローで単一の送信プッシュ通知または定期的なプッシュ通知を送信できます。
page-status-flag: 常にアクティブ化されていない
uuid: 994d8fe3-29f0-4b5c-89ee- c6be7c60a31b
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネルアクティビティ
discoiquuid: e61bdedee-4b48-4845- a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Push notification delivery{#push-notification-delivery}

## 説明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

**[!UICONTROL Push notification]** アクティビティにより、ワークフローでプッシュ通知を送信することができます。This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

単一の送信通知は、標準モバイルアプリプッシュ通知配信で、1回送信されます。

定期的な通知を使用すると、定義済みの期間にわたって、同じモバイルアプリプッシュ通知配信を複数回のターゲットに送信できます。期間ごとの配信を集計して、ニーズに対応するレポートを取得できます。

## Context of use {#context-of-use}

**[!UICONTROL Push notification]** このアクティビティは、通常、同じワークフローで計算されたターゲットに通知を送信するために使用されます。

スケジューラーにリンクすると、定期的なプッシュ通知を定義できます。

クエリ、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティのアップストリームが定義されます。

メッセージの実行パラメーターに従ってメッセージの準備がトリガーされます。メッセージダッシュボードから、メッセージを送信するかどうかを手動で確認できます（デフォルトで必須）。ワークフローを手動で開始することも、ワークフローにスケジューラーアクティビティを配置して実行を自動化することもできます。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Push notification]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Push notification]** activity. プッシュ通知のプロパティには、プッシュダッシュボードのアクションバーを使用してアクセスできます。

1. プッシュ通知送信モードを選択します。

   * **[!UICONTROL Single notification]**:プッシュ通知が1回送信されます。アクティビティにアウトバウンドトランジションを追加するかどうかを指定できます。この手順の手順7では、様々な移行タイプについて説明しています。
   * **[!UICONTROL Recurring notification]**:アクティビティに定義された頻度に応じて、プッシュ通知が数回送信 **[!UICONTROL Scheduler]** されます。送信の集計期間を選択します。This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application's marketing activity list.

      例えば、定期的に誕生日の通知を送信する場合、毎月送信するように選択できます。これにより、毎日通知が送信されるのに対して、レポートを毎月配信することができます。

1. 通知タイプを選択します。These types come from push notifications templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. プッシュ通知の一般プロパティを入力します。既存のキャンペーンにも添付できます。ワークフローの配信アクティビティのラベルが、プッシュ通知ラベルで更新されます。
1. プッシュ通知コンテンツを定義します。See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md)
1. By default, the **[!UICONTROL Push notification]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Push Notification]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションとまったく同じ訪問者を含むアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、通知が送信された母集団を含むアウトバウンドトランジションを生成できます。配信準備中に除外されたターゲットのメンバーは、この移行から除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、プッシュ通知ダッシュボードに直接移動します。編集できるのはコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみが開始されます。ワークフローを開始した後でもワークフローから作成されたメッセージを送信する必要があります。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. このオプションのチェックを解除すると、準備が完了すると、それ以上通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。プッシュ通知サマリペインのリンクを使用すると、リンクされた要素（ワークフロー、キャンペーンなど）に直接アクセスできます。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Sending a recurring push notification with a workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

この例では、パーソナライズされたプッシュ通知が、月の最初の日ごとに、タイムゾーンに応じてモバイルアプリケーションの購読者に送信されます。これを行うには、次の手順に従います。

1. **[!UICONTROL Scheduler]** このアクティビティでは、配信開始前のワークフロー日を開始して、指定したタイムゾーンにあるすべての加入者に通知を送信できます。

   * **[!UICONTROL Execution frequency]** フィールドで「毎月」を選択します。
   * Select 8 pm in the **[!UICONTROL Time]** field.
   * 毎月配信する日を選択します。
   * ワークフローの開始日を少なくとも1日前に選択します。そうしないと、選択した時刻が既にタイムゾーンで渡されている場合、一部の受信者が1日後にメッセージを受信することがあります。
   * **[!UICONTROL Execution options]** タブで、ワークフローがフィールドで **[!UICONTROL Time zone]** 開始するタイムゾーンを選択します。ここでは、例えば、ワークフローが午後8時の午後8時から1週間前に開始し、該当するタイムゾーンすべてに対して配信が作成されるまでに時間がかかることがあります。
   ![](assets/wkf_push_example_5.png)

1. **クエリ** アクティビティを使用すると、20~30歳のユーザーをターゲットにし、モバイルアプリケーションを購読していて、送信した電子メールを開かなかったユーザーをターゲットにすることができます。

   * オーディエンス（VIPユーザー）を選択し、年齢をフィルターします。
   * Drag and drop the **Subscriptions to an application** element into the workspace. Select **Exists** and select the mobile application that you want to use.
   * 顧客に送信した電子メールを選択します。
   * **配信ログ（ログ）** エレメントをワークスペースにドラッグ&amp;ドロップし、 **「存在する」** を選択して電子メールを受信したすべての顧客をターゲットにします。
   * **トラッキングログ（トラッキング）** エレメントをワークスペースにドラッグ&amp;ドロップし、電子メールを開かなかったすべての顧客をターゲットにするために「 **存在** しない」を選択します。

      ![](assets/wkf_push_example_2.png)

1. **プッシュ通知** アクティビティでは、メッセージの内容を入力し、使用するパーソナライゼーションフィールドを選択できます。

   * **[!UICONTROL Recurring notification]** このオプションを選択します。
   * プッシュ通知コンテンツを定義します。For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * **[!UICONTROL Schedule]** ブロック内で、を選択 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**&#x200B;します。Here, we chose the **[!UICONTROL Time zone of the contact date]** Pacific as in the workflow **[!UICONTROL Scheduler]**.
   * **[!UICONTROL Optimize the sending time per recipient]** フィールドで、を選択 **[!UICONTROL Send at the recipient's time zone]**&#x200B;します。

      ![](assets/wkf_push_example_4.png)

1. Click the **[!UICONTROL Start]** button to start your recurring workflow.

   ![](assets/wkf_push_example_3.png)

ワークフローが実行されるようになりました。It will start at the chosen start date of the **[!UICONTROL Scheduler]** at 8 pm Pacific time, the recurring push will then be sent every first day of the month at 8 pm depending on the customers time zone.
