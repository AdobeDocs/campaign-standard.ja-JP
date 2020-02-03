---
title: スケジューラー
description: スケジューラーアクティビティでは、ワークフローまたはアクティビティがいつ開始されるかをスケジュールできます。
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 41ba6fa44807541dd749f4effca44ae2b4d147ae

---


# スケジューラー{#scheduler}

## 説明 {#description}

![](assets/scheduler.png)

アクティビティ **[!UICONTROL Scheduler]**では、ワークフローまたはアクティビティがいつ開始されるかをスケジュールできます。

## 使用状況 {#context-of-use}

The **[!UICONTROL Scheduler]**activity should be considered as a scheduled start. The activity positioning rules within the chart are the same as for the**[!UICONTROL Start]** activity. このアクティビティはインバウンドトランジションを持つことはできません。

ワークフローを構築する場合は、ブランチごとに1つのア **[!UICONTROL Scheduler]**クティビティのみを使用し、タイムゾーンを設定することを忘れないでください。 これにより、特定のタイムゾーンでワークフローを開始できます。そうでない場合、ワークフローは、ワークフローのプロパティで定義されたタイムゾーンで実行されます(「ワークフ[ローの構築](../../automating/using/building-a-workflow.md)」を参照)。

>[!CAUTION]
>
>アクテ **[!UICONTROL Repetition frequency]**ィビティの長さは10分以内にしてください。 つまり、1つのワークフローを10分に1回以上自動的に実行することはできません。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Scheduler]**にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 次を指定しま **[!UICONTROL Execution frequency]**す。

   * **[!UICONTROL Once]**:ワークフローは1回だけ実行されます。
   * **[!UICONTROL Several times a day]**:ワークフローは、1日に数回定期的に実行されます。 実行は、特定の時間に設定することも、定期的に設定することもできます。
   * **[!UICONTROL Daily]**:ワークフローは、特定の時間に1日1回実行されます。
   * **[!UICONTROL Weekly]**:ワークフローは、指定された時点（週に1回または数回）で実行されます。
   * **[!UICONTROL Monthly]**:ワークフローは、指定された時点で、月に1回または数回実行されます。 ワークフローの実行が必要な場合は、月を選択できます。 また、月の指定された曜日（例：第2火曜日）に実行を設定することもできます。
   * **[!UICONTROL Yearly]**:ワークフローは、指定された時点で、年に1回または数回実行されます。

1. 選択した頻度に従って実行の詳細を定義します。 詳細フィールドは、使用頻度（時間、繰り返し頻度、指定した日数など）によって異なる場合があります。

   >[!NOTE]
   >
   >このフ **[!UICONTROL Repetition frequency]**ィールドを使用すると、ワークフローがトリガーされた時間を空けることができます。 例えば、毎日の実行期間を選択し、繰り返し頻度を** 2 **（日）に設定した場合、ワークフローは2日ごとにトリガーされます。 10分未満にすることはできません。 繰り返し頻度を** 0 **（またはデフォルト値）に設定した場合、このオプションは考慮されず、ワークフローは指定された実行頻度に従って実行されます。

1. 実行の有効期限を指定します。

   * **[!UICONTROL Never]**:ワークフローは、指定された頻度に従って実行され、時間枠や反復回数に制限はありません。
   * **[!UICONTROL After a certain number of iterations]**:ワークフローは、** Xの制限に達するまで、指定された頻度に従って実行さ&#x200B;**れます。 そのた**[!UICONTROL Number of iterations]** め、を指定する必要があります。
   * **[!UICONTROL On a specific date]**:ワークフローは、指定した頻度（指定した日付まで）に従って実行されます。 したがって、実行デッドラインを指定する必要があります。

1. をクリックして、ワークフローの次の10回の実行のスケジュールを確認しま **[!UICONTROL Preview next executions]**す。

1. タブで、 **[!UICONTROL Execution options]**フィールドにスケジューラーのタイムゾーンを設定し**[!UICONTROL Time zone]** ます。

   受信者のタイムゾーンに応じた配信の送信の詳細については、この節または定期的なワ [ーク](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) フロー [の例を参照してください](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) 。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例では、アクティビティは、毎週月曜日の午前7時に、未定期間にわたってワークフローを週単位で開始するように設定されています。

![](assets/wkf_scheduler_example.png)

