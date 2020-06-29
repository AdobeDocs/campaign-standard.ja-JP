---
title: スケジューラー
description: スケジューラーアクティビティを使用すると、ワークフローまたはアクティビティをいつ開始するかをスケジュールできます。
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
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 2%

---


# スケジューラー{#scheduler}

## 説明 {#description}

![](assets/scheduler.png)

この **[!UICONTROL Scheduler]** アクティビティでは、ワークフローまたはアクティビティがいつ開始されるかをスケジュールできます。

## 使用状況 {#context-of-use}

The **[!UICONTROL Scheduler]** activity should be considered as a scheduled start. The activity positioning rules within the chart are the same as for the **[!UICONTROL Start]** activity. このアクティビティはインバウンドトランジションを持つことはできません。

ワークフローを構築する場合は、ブランチごとに1つの **[!UICONTROL Scheduler]** アクティビティのみを使用し、タイムゾーンの設定を忘れないでください。 これにより、特定のタイムゾーンでワークフローを開始できます。それ以外の場合は、ワークフローのプロパティで定義されたタイムゾーンでワークフローが実行されます(「ワークフローの [構築](../../automating/using/building-a-workflow.md)」を参照)。

>[!CAUTION]
>
>アクティビティ **[!UICONTROL Repetition frequency]** の長さは10分以下にする必要があります。 つまり、1つのワークフローを10分に1回以上自動的に実行することはできません。

**関連トピック：**

* [使用例： プロファイルの作成日に対する配信の作成](../../automating/using/workflow-creation-date-query.md)
* [使用例： 毎週火曜日に電子メール配信を作成する](../../automating/using/workflow-weekly-offer.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Scheduler]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 次を指定し **[!UICONTROL Execution frequency]**&#x200B;ます。

   * **[!UICONTROL Once]**: ワークフローは1回実行されます。
   * **[!UICONTROL Several times a day]**: ワークフローは、1日に数回定期的に実行されます。 実行は、特定の時間や定期的に設定できます。
   * **[!UICONTROL Daily]**: ワークフローは、特定の時刻（1日1回）に実行されます。
   * **[!UICONTROL Weekly]**: ワークフローは、指定された瞬間（週に1回または数回）に実行されます。
   * **[!UICONTROL Monthly]**: ワークフローは、指定された瞬間（月に1回または数回）に実行されます。 ワークフローを実行する必要がある場合は、月を選択できます。 月の第2火曜日など、月の特定の曜日に実行を設定することもできます。
   * **[!UICONTROL Yearly]**: ワークフローは、指定された瞬間に、年に1回または数回実行されます。

1. 選択した頻度に従って実行の詳細を定義します。 詳細フィールドは、使用頻度（時間、繰り返し頻度、指定した日数など）に応じて異なります。

   >[!NOTE]
   >
   >この **[!UICONTROL Repetition frequency]** フィールドを使用すると、ワークフローがトリガーされた時間を空けることができます。 例えば、毎日の実行期間を選択し、繰り返し頻度を **2** （日）に設定すると、ワークフローは2日ごとにトリガーされます。 10分を下回ることはできません。 繰り返し頻度を **0** （またはデフォルト値）に設定した場合、このオプションは考慮されず、指定した実行頻度に従ってワークフローが実行されます。

1. 実行の有効期限を指定します。

   * **[!UICONTROL Never]**: ワークフローは、指定された頻度に従って実行され、時間枠や反復回数に制限はありません。
   * **[!UICONTROL After a certain number of iterations]**: ワークフローは、 **Xの制限に達するまで、指定された頻度に従って実行され** ます。 したがっ **[!UICONTROL Number of iterations]** て、を指定する必要があります。
   * **[!UICONTROL On a specific date]**: ワークフローは、指定された頻度に従って、指定された日付まで実行されます。 したがって、実行デッドラインを指定する必要があります。

1. をクリックして、次に10回実行するワークフローのスケジュールを確認し **[!UICONTROL Preview next executions]**&#x200B;ます。

1. タブの **[!UICONTROL Execution options]** フィールドで、スケジューラーのタイムゾーンを設定し **[!UICONTROL Time zone]** ます。

   受信者のタイムゾーンに応じた配信の送信の詳細については、この [節](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) または定期的なワークフローの [例を参照してください](../../automating/using/recurring-push-notifications.md) 。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例では、アクティビティは、毎週月曜日の午前7時に、未定の期間、ワークフローを週単位で開始するように設定されています。

![](assets/wkf_scheduler_example.png)

