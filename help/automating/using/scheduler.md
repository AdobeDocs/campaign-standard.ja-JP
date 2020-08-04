---
title: スケジューラー
description: 「Scheduler」アクティビティを使用すると、ワークフローまたはアクティビティの開始日時を指定できます。
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
ht-degree: 97%

---


# スケジューラー{#scheduler}

## 説明{#description}

![](assets/scheduler.png)

「**[!UICONTROL Scheduler]**」アクティビティを使用すると、ワークフローまたはアクティビティの開始日時を指定できます。

## 使用状況{#context-of-use}

「**[!UICONTROL Scheduler]**」アクティビティは、予約済みの開始とみなされます。アクティビティのグラフ内の配置ルールは、「**[!UICONTROL Start]**」アクティビティのルールと同じものです。このアクティビティはインバウンドトランジションを持つことはできません。

ワークフローを作成する場合は、ブランチごとに 1 つの「**[!UICONTROL Scheduler]**」アクティビティのみを使用し、タイムゾーンの設定をおこなってください。これにより、特定のタイムゾーンでワークフローを開始できます。それ以外の場合は、ワークフローのプロパティで定義されたタイムゾーンでワークフローが実行されます（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

>[!CAUTION]
>
>アクティビティの **[!UICONTROL Repetition frequency]** は 10 分以上にする必要があります。つまり、1 つのワークフローを 10 分に1 回以上自動的に実行することはできません。

**関連トピック：**

* [使用例： プロファイルの作成日に対する配信の作成](../../automating/using/workflow-creation-date-query.md)
* [使用例： 毎週火曜日に電子メール配信を作成する](../../automating/using/workflow-weekly-offer.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Scheduler]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. **[!UICONTROL Execution frequency]** を指定します。

   * **[!UICONTROL Once]**：ワークフローは 1 回実行されます。
   * **[!UICONTROL Several times a day]**：ワークフローは、1 日に数回定期的に実行されます。特定の時間を指定するか、定期的に実行されるように設定できます。
   * **[!UICONTROL Daily]**：ワークフローは、特定の時間（1 日 1 回）に実行されます。
   * **[!UICONTROL Weekly]**：ワークフローは、指定された日時（週に 1 回または数回）に実行されます。
   * **[!UICONTROL Monthly]**：ワークフローは、指定された日時（月に 1 回または数回）に実行されます。ワークフローを実行する月を選択できます。月の第 2 火曜日など、月の特定の曜日に実行を設定することもできます。
   * **[!UICONTROL Yearly]**：ワークフローは、指定された日時（年に 1 回または数回）に実行されます。

1. 選択した頻度に従って実行の詳細を定義します。詳細フィールドは、指定する頻度（時間、繰り返し頻度、指定した日数など）に応じて異なります。

   >[!NOTE]
   >
   >「**[!UICONTROL Repetition frequency]**」フィールドを使用すると、一定の間隔でワークフローをトリガーすることができます。例えば、実行期間を「Daily」に指定し、繰り返し頻度を **2**（日）に設定すると、ワークフローは 2 日ごとにトリガーされます。10 分を下回ることはできません。繰り返し頻度を **0**（またはデフォルト値）に設定した場合、このオプションは考慮されず、指定した実行頻度に従ってワークフローが実行されます。

1. 実行の有効期限を指定します。

   * **[!UICONTROL Never]**：ワークフローは、指定された頻度に従って実行され、時間枠や反復回数に制限はありません。
   * **[!UICONTROL After a certain number of iterations]**：ワークフローは、**X** の制限に達するまで、指定された頻度に従って実行されます。**[!UICONTROL Number of iterations]** を指定する必要があります。
   * **[!UICONTROL On a specific date]**：ワークフローは、指定された頻度に従って、指定された日付まで実行されます。実行期限を指定する必要があります。

1. 「**[!UICONTROL Preview next executions]**」をクリックして、ワークフローの実行スケジュール（次の 10 回）を確認します。

1. 「**[!UICONTROL Execution options]**」タブの「**[!UICONTROL Time zone]**」フィールドで、スケジューラーのタイムゾーンを設定します。

   受信者のタイムゾーンに応じた配信の送信について詳しくは、この[節](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)または繰り返しワークフローの[例](../../automating/using/recurring-push-notifications.md)を参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

次の例では、アクティビティは、毎週月曜日の午前 7 時に、未定の期間、ワークフローを週単位で開始するように設定されています。

![](assets/wkf_scheduler_example.png)

