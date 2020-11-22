---
solution: Campaign Standard
product: campaign
title: ワークフローを含む定期的なプッシュ通知の送信
description: この例では、パーソナライズされたプッシュ通知が月の初日の午後8時に、タイムゾーンに応じてモバイルアプリの購読者に送信されます。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# ワークフローを含む定期的なプッシュ通知の送信 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

この例では、パーソナライズされたプッシュ通知が月の初日の午後8時に、タイムゾーンに応じてモバイルアプリの購読者に送信されます。

ワークフローを構築するには、次の手順に従います。

1. スケジューラー [](../../automating/using/scheduler.md) アクティビティを使用すると、配信の開始前の日数を開始して、任意のタイムゾーンの午後8時にすべての加入者に通知を送信できます。

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * フィールドで[午後8時]を選択し **[!UICONTROL Time]** ます。
   * 配信を毎月送信する日を選択します。
   * ワークフローの開始日を、配信の開始の少なくとも1日前に選択します。 そうしないと、選択した時間が既にタイムゾーンを超えている場合、一部の受信者は1日後にメッセージを受け取る可能性があります。
   * タブで、ワークフローが開始するタイムゾーンを **[!UICONTROL Execution options]** フィールドで選択し **[!UICONTROL Time zone]** ます。 例えば、太平洋標準時の午後8時、月の最初の日の1週間前に開始され、該当するすべてのタイムゾーンに対して配信を作成できる時間が与えられます。

   >[!NOTE]
   >
   >デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

   ![](assets/wkf_push_example_5.png)

1. この [クエリ](../../automating/using/query.md) アクティビティを使用すると、20 ～ 30歳のVIPユーザーをターゲットできます。この顧客は、モバイルアプリケーションを購読しており、送信した電子メールを開いていないユーザーです。

   * オーディエンス(VIPのお客様)を選択し、年齢に基づいてフィルターします。
   * ワークスペース内のapplication **** 購読に要素をドラッグ&amp;ドロップします。 「 **存在する」を選択し** 、使用するモバイルアプリケーションを選択します。
   * 顧客に送信した電子メールを選択します。
   * 「 **配信ログ（ログ）** 」要素をワークスペースにドラッグ&amp;ドロップし、「 **存在する** 」を選択して、電子メールを受信したすべての顧客をターゲットします。
   * 「 **トラッキングログ（トラッキング）****** 」要素をワークスペースにドラッグ&amp;ドロップし、「存在しない」を選択して、電子メールを開かなかったすべての顧客をターゲットします。

      ![](assets/wkf_push_example_2.png)

1. プ [ッシュ通知配信](../../automating/using/push-notification-delivery.md) アクティビティを使用すると、メッセージの内容を入力し、使用するパーソナライゼーションフィールドを選択できます。

   * Select the **[!UICONTROL Recurring notification]** option.
   * プッシュ通知の内容を定義します。 プッシュ通知の内容について詳しくは、この [節を参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. ここでは、ワークフローの **[!UICONTROL Time zone of the contact date]** 太平洋を選択し **[!UICONTROL Scheduler]**&#x200B;ます。
   * 「**[!UICONTROL Optimize the sending time per recipient]**」フィールドで「**[!UICONTROL Send at the recipient's time zone]**」を選択します。

      ![](assets/wkf_push_example_4.png)

1. 定期的なワークフローを開始するには、 **[!UICONTROL Start]** ボタンをクリックします。

   ![](assets/wkf_push_example_3.png)

ワークフローが実行中です。 太平洋標準時の午後8時に開始した日付に開始 **[!UICONTROL Scheduler]** し、その後、お客様のタイムゾーンに応じて月の初日の午後8時に繰り返しプッシュが送信されます。
