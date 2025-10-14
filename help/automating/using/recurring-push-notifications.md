---
title: ワークフローでの繰り返しプッシュ通知の送信
description: この例では、パーソナライズされたプッシュ通知が、月の初日の午後 8 時に、タイムゾーンに応じてモバイルアプリケーションの購読者に送信されます
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 4%

---

# ワークフローでの繰り返しプッシュ通知の送信 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

この例では、パーソナライズされたプッシュ通知が、月の初日の午後 8 時に、タイムゾーンに応じてモバイルアプリケーションの購読者に送信されます。

ワークフローを作成するには、次の手順に従います。

1. [&#x200B; スケジューラー &#x200B;](../../automating/using/scheduler.md) アクティビティを使用すると、配信開始の日前のワークフローを開始して、任意のタイムゾーンの午後 8 時にすべての購読者に通知を送信できます。

   * 「**[!UICONTROL Execution frequency]**」フィールドで、「毎月」を選択します。
   * 「**[!UICONTROL Time]**」フィールドで「午後 8 時」を選択します。
   * 毎月配信を送信する日を選択します。
   * ワークフローの開始日（配信の開始の 1 日以上前）を選択します。 そうしないと、選択した時間がタイムゾーンで既に経過している場合、一部の受信者が 1 日後にメッセージを受信する可能性があります。
   * 「**[!UICONTROL Execution options]**」タブの「**[!UICONTROL Time zone]**」フィールドで、ワークフローを開始するタイムゾーンを選択します。 例えば、ワークフローは月の初日の 1 週間前である太平洋標準時の午後 8 時に開始され、該当するすべてのタイムゾーンに対して配信が作成されるまでしばらく時間がかかります。

   >[!NOTE]
   >
   >デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

   ![](assets/wkf_push_example_5.png)

1. [&#x200B; クエリ &#x200B;](../../automating/using/query.md) アクティビティを使用すると、20～30 歳でモバイルアプリケーションを購読しており、送信したメールを開いていないVIP顧客をターゲットにすることができます。

   * オーディエンス（VIP顧客）を選択し、年齢でフィルタリングします。
   * **購読をアプリケーションに** 要素をワークスペースにドラッグ&amp;ドロップします。 「**存在する**」を選択し、使用するモバイルアプリケーションを選択します。
   * 顧客に送信したメールを選択します。
   * **配信ログ（ログ）** 要素をワークスペースにドラッグ&amp;ドロップし、「**存在**」を選択して、メールを受信したすべての顧客をターゲットにします。
   * **トラッキングログ （トラッキング）** 要素をワークスペースにドラッグ&amp;ドロップし、「**存在しない**」を選択して、メールを開いていなかったすべての顧客をターゲットにします。

     ![](assets/wkf_push_example_2.png)

1. [&#x200B; プッシュ通知配信 &#x200B;](../../automating/using/push-notification-delivery.md) アクティビティでは、メッセージの内容を入力し、使用するパーソナライゼーションフィールドを選択できます。

   * **[!UICONTROL Recurring notification]** オプションを選択します。
   * プッシュ通知の内容を定義します。 プッシュ通知コンテンツについて詳しくは、この [&#x200B; 節 &#x200B;](../../channels/using/preparing-and-sending-a-push-notification.md) を参照してください。
   * **[!UICONTROL Schedule]** ブロックで、[**[!UICONTROL Messages to be sent automatically on the time zone specified below]**] を選択します。 ここでは、ワークフロー **[!UICONTROL Scheduler]** ードで **[!UICONTROL Time zone of the contact date]** 太平洋を選択しました。
   * 「**[!UICONTROL Optimize the sending time per recipient]**」フィールドで「**[!UICONTROL Send at the recipient's time zone]**」を選択します。

     ![](assets/wkf_push_example_4.png)

1. 「**[!UICONTROL Start]**」ボタンをクリックして、繰り返しワークフローを開始します。

   ![](assets/wkf_push_example_3.png)

ワークフローは現在実行中です。 太平洋時間の午後 8 時に、選択した **[!UICONTROL Scheduler]** の開始日に開始され、顧客のタイムゾーンに応じて、毎月 1 日の午後 8 時に繰り返しプッシュが送信されます。
