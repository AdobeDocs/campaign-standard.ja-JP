---
title: ワークフローでの繰り返しプッシュ通知の送信
description: この例では、パーソナライズされたプッシュ通知が月の初日の午後 8 時に、それぞれのタイムゾーンに応じてモバイルアプリケーションの購読者に送信されます
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---

# ワークフローでの繰り返しプッシュ通知の送信 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

この例では、パーソナライズされたプッシュ通知は、月の初日の午後 8 時に、それぞれのタイムゾーンに応じて、モバイルアプリケーションの購読者に送信されます。

ワークフローを構築するには、次の手順に従います。

1. この [スケジューラ](../../automating/using/scheduler.md) 「 」アクティビティを使用すると、配信が開始される前のワークフローを何日か開始し、任意のタイムゾーンの午後 8 時にすべての購読者に通知を送信できます。

   * 内 **[!UICONTROL Execution frequency]** 「毎月」を選択します。
   * で午後 8 時を選択します。 **[!UICONTROL Time]** フィールドに入力します。
   * 毎月、配信を送信する日付を選択します。
   * ワークフローの開始日（配信が開始される 1 日以上前）を選択します。 そうしないと、選択した時間が既にタイムゾーンを過ぎている場合は、一部の受信者が 1 日後にメッセージを受け取る可能性があります。
   * 内 **[!UICONTROL Execution options]** 」タブで、ワークフローが開始するタイムゾーンを選択します。 **[!UICONTROL Time zone]** フィールドに入力します。 例えば、ワークフローは太平洋時間の午後 8 時（月の最初の日の 1 週間前）に開始し、該当するすべてのタイムゾーンで配信を作成するのに時間を割くようにします。

   >[!NOTE]
   >
   >デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

   ![](assets/wkf_push_example_5.png)

1. この [クエリ](../../automating/using/query.md) 「 」アクティビティでは、20 ～ 30 歳の、モバイルアプリケーションを購読していて、送信した E メールを開封していないVIP顧客をターゲットに設定できます。

   * オーディエンス (VIPのお客様 ) を選択し、年齢に基づいてフィルタリングします。
   * 次をドラッグ&amp;ドロップ： **アプリケーションの購読** 要素をワークスペースに追加します。 選択 **存在する** をクリックし、使用するモバイルアプリケーションを選択します。
   * 顧客に送信した E メールを選択します。
   * 次をドラッグ&amp;ドロップ： **配信ログ（ログ）** 要素をワークスペースに追加して、 **存在する** ：電子メールを受信したすべての顧客をターゲットにします。
   * 次をドラッグ&amp;ドロップ： **トラッキングログ（トラッキング）** 要素をワークスペースに追加して、 **存在しない** をクリックして、e メールを開封しなかったすべての顧客をターゲットにします。

      ![](assets/wkf_push_example_2.png)

1. この [プッシュ通知配信](../../automating/using/push-notification-delivery.md) 「 」アクティビティでは、メッセージの内容を入力し、使用するパーソナライゼーションフィールドを選択できます。

   * を選択します。 **[!UICONTROL Recurring notification]** オプション。
   * プッシュ通知のコンテンツを定義します。 プッシュ通知のコンテンツについて詳しくは、 [セクション](../../channels/using/preparing-and-sending-a-push-notification.md).
   * 内 **[!UICONTROL Schedule]** ブロック、選択 **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. ここでは、 **[!UICONTROL Time zone of the contact date]** ワークフローと同様に太平洋 **[!UICONTROL Scheduler]**.
   * 「**[!UICONTROL Optimize the sending time per recipient]**」フィールドで「**[!UICONTROL Send at the recipient's time zone]**」を選択します。

      ![](assets/wkf_push_example_4.png)

1. 次をクリック： **[!UICONTROL Start]** ボタンをクリックして、繰り返しワークフローを開始します。

   ![](assets/wkf_push_example_3.png)

これで、ワークフローが実行されています。 開始日は **[!UICONTROL Scheduler]** 太平洋時間の午後 8 時に、顧客のタイムゾーンに応じて、月の初日の午後 8 時に繰り返しのプッシュが送信されます。
