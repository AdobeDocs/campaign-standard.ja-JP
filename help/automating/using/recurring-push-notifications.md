---
title: ワークフローを含む繰り返しのプッシュ通知の送信
description: この例では、パーソナライズされたプッシュ通知が月の初日の午後8時に、それぞれのタイムゾーンに応じてモバイルアプリケーションの購読者に送信されます。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---

# ワークフローを含む繰り返しのプッシュ通知の送信 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

この例では、パーソナライズされたプッシュ通知が月の初日の午後8時に、それぞれのタイムゾーンに応じてモバイルアプリケーションの購読者に送信されます。

ワークフローを構築するには、次の手順に従います。

1. 「[スケジューラー](../../automating/using/scheduler.md)」アクティビティを使用すると、配信開始の前にワークフローを開始し、任意のタイムゾーンの午後8時にすべての購読者に通知を送信できます。

   * **[!UICONTROL Execution frequency]**&#x200B;フィールドで、「月別」を選択します。
   * **[!UICONTROL Time]**&#x200B;フィールドで「午後8時」を選択します。
   * 毎月配信を送信する日を選択します。
   * ワークフローの開始日（配信開始の1日前）を選択します。 そうしないと、選択した時間が既にタイムゾーンを超えている場合に、1日後にメッセージを受け取る受信者もいる可能性があります。
   * 「**[!UICONTROL Execution options]**」タブの「**[!UICONTROL Time zone]**」フィールドで、ワークフローの開始タイムゾーンを選択します。 例えば、ワークフローは太平洋時間の午後8時（月の最初の日の1週間前）に開始され、該当するすべてのタイムゾーンで配信が作成されるまでの時間を考慮します。

   >[!NOTE]
   >
   >デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

   ![](assets/wkf_push_example_5.png)

1. 「[クエリ](../../automating/using/query.md)」アクティビティを使用すると、20～30歳のVIPの顧客（モバイルアプリケーションを購読し、送信したEメールを開封していない顧客）をターゲットに設定できます。

   * オーディエンス(VIPのお客様)を選択し、年齢に基づいてフィルターします。
   * 「**Subscriptions to an application**」要素をワークスペースにドラッグ&amp;ドロップします。 「**存在する**」を選択し、使用するモバイルアプリケーションを選択します。
   * 顧客に送信したEメールを選択します。
   * **配信ログ(logs)**&#x200B;要素をワークスペースにドラッグ&amp;ドロップし、「**存在する**」を選択して、Eメールを受信したすべての顧客をターゲットにします。
   * **トラッキングログ（トラッキング）**&#x200B;要素をワークスペースにドラッグ&amp;ドロップし、「**存在しない**」を選択して、Eメールを開封していないすべての顧客をターゲットにします。

      ![](assets/wkf_push_example_2.png)

1. [プッシュ通知配信](../../automating/using/push-notification-delivery.md)アクティビティを使用すると、メッセージの内容を入力し、使用するパーソナライゼーションフィールドを選択できます。

   * **[!UICONTROL Recurring notification]**&#x200B;オプションを選択します。
   * プッシュ通知のコンテンツを定義します。 プッシュ通知のコンテンツの詳細については、[](../../channels/using/preparing-and-sending-a-push-notification.md)を参照してください。
   * **[!UICONTROL Schedule]**&#x200B;ブロックで、**[!UICONTROL Messages to be sent automatically on the time zone specified below]**&#x200B;を選択します。 ここでは、ワークフロー&#x200B;**[!UICONTROL Scheduler]**&#x200B;のように、「**[!UICONTROL Time zone of the contact date]**&#x200B;太平洋」を選択します。
   * 「**[!UICONTROL Optimize the sending time per recipient]**」フィールドで「**[!UICONTROL Send at the recipient's time zone]**」を選択します。

      ![](assets/wkf_push_example_4.png)

1. 「**[!UICONTROL Start]**」ボタンをクリックして、繰り返しワークフローを開始します。

   ![](assets/wkf_push_example_3.png)

ワークフローが実行中です。 太平洋時間の午後8時に、**[!UICONTROL Scheduler]**&#x200B;の指定された開始日に開始し、顧客のタイムゾーンに応じて、月の初日の午後8時に繰り返しプッシュが送信されます。
