---
title: スケジューラー
description: 「Scheduler」アクティビティを使用すると、ワークフローまたはアクティビティの開始日時を指定できます。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 39f7b216-b3cd-4aa6-b5df-23e6805076df
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 52%

---

# スケジューラー{#scheduler}

## 説明 {#description}

![](assets/scheduler.png)

「**[!UICONTROL Scheduler]**」アクティビティを使用すると、ワークフローまたはアクティビティの開始日時を指定できます。

## 使用コンテキスト {#context-of-use}

「**[!UICONTROL Scheduler]**」アクティビティは、スケジュール済みの開始とみなされます。アクティビティのグラフ内の配置ルールは、「**[!UICONTROL Start]**」アクティビティのルールと同じものです。このアクティビティはインバウンドトランジションを持つことはできません。

ワークフローを作成する場合は、ブランチごとに 1 つの「**[!UICONTROL Scheduler]**」アクティビティのみを使用し、タイムゾーンの設定をおこなってください。これにより、特定のタイムゾーンでワークフローを開始できます。それ以外の場合は、ワークフローのプロパティで定義されたタイムゾーンでワークフローが実行されます（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

>[!CAUTION]
>
>アクティビティの **[!UICONTROL Repetition frequency]** は 10 分以上にする必要があります。つまり、1 つのワークフローを 10 分に1 回以上自動的に実行することはできません。

複数のアクティビティを含むスケジュール済みワークフローを設計する場合は、ワークフローが完了するまで再スケジュールされないようにする必要があります。 これを行うには、以前の実行の 1 つ以上のタスクがまだ保留中の場合に実行を防ぐために、ワークフローを設定する必要があります。 詳しくは、[このページ](../../automating/using/scheduled-workflows-execution.md)を参照してください。

**関連トピック：**

* [ユースケース：プロファイルの作成日での配信の作成](../../automating/using/workflow-creation-date-query.md)
* [ユースケース：毎週火曜日のメール配信の作成](../../automating/using/workflow-weekly-offer.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Scheduler]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. **[!UICONTROL Execution frequency]** を指定します。

   * **[!UICONTROL Once]**：ワークフローは 1 回実行されます。
   * **[!UICONTROL Several times a day]**：ワークフローは 1 日に数回、定期的に実行されます。
   * **[!UICONTROL Daily]**：ワークフローは、特定の時間（1 日 1 回）に実行されます。
   * **[!UICONTROL Weekly]**：ワークフローは、指定された日時（週に 1 回または数回）に実行されます。
   * **[!UICONTROL Monthly]**：ワークフローは、指定された日時（月に 1 回または数回）に実行されます。ワークフローを実行する月を選択できます。月の第 2 火曜日など、月の特定の曜日に実行を設定することもできます。
   * **[!UICONTROL Yearly]**：ワークフローは、指定された日時（年に 1 回または数回）に実行されます。

1. ニーズに合わせて実行設定を指定します。 使用できるオプションは、選択した実行頻度（実行時間や日数、繰り返し頻度など）によって異なる場合があります。

   >[!NOTE]
   >
   >日別および月別の実行頻度で使用できる **[!UICONTROL Repetition frequency]** フィールドを使用すると、ワークフローがトリガーされる時間を空けることができます。 例えば、実行期間を「Daily」に指定し、繰り返し頻度を **2**（日）に設定すると、ワークフローは 2 日ごとにトリガーされます。10 分を下回ることはできません。繰り返し頻度が **0** （デフォルト値）に設定されている場合、このオプションは考慮されず、ワークフローは指定された実行頻度に従って実行されます。

   実行頻度を **[!UICONTROL Several times a day]** に設定すると、特定の時間帯にワークフローを実行するか、1 日を通して定期的に実行するかを柔軟に選択できます。

   +++ **[!UICONTROL "Several times a day"]** 実行頻度を設定する方法を学ぶ

   * 1 日の特定の時間にワークフローを複数回実行するには、「実 **[!UICONTROL Specific times]**」オプションをオンに切り替えてから「実 **[!UICONTROL Add an element]**」をクリックして、目的の実行時間を指定します。 要件に合わせて必要な回数だけ追加します。

   * ワークフローを 1 日を通して定期的に実行するには、「**[!UICONTROL Periodic]**」オプションをオンに切り替えてから、実行頻度を設定します。

      1. **[!UICONTROL Repeat processing according to the following frequency (e.g. 2h)]** フィールドで、ワークフローを実行する間隔を指定します（例：30 分ごと、2 時間ごと）。

         >[!NOTE]
         >
         >このオプションでは、毎日、毎月または毎年の繰り返し頻度も可能です。 この場合、ワークフローは 1 日に数回ではなく、このフィールドで指定した頻度に従って実行されます。
         >
         > ワークフローを 1 日に複数回実行する必要がなく、代わりに日単位、月単位、年単位で実行する必要がある場合は、「**[!UICONTROL Daily]**」ドロップダウンリストで使用できる **[!UICONTROL Monthly]**、**[!UICONTROL Yearly]**、**[!UICONTROL Execution frequency]** のオプションを使用することをお勧めします。

      1. **[!UICONTROL Start]**/**[!UICONTROL End]** 時間フィールドで、ワークフローの実行を開始および終了する時間を定義します。

         終了時刻を指定しない場合は、午前 0 時に実行が終了し、指定した開始時刻に次の実行が開始されます。午前 0 時から午前 0 時 :00: 時までの時間が指定されている場合は、次の実行が開始されます。

      1. 「**[!UICONTROL Start]** 定日」フィールドで、最初の実行を開始する日付を選択します。

   次の例では、アクティビティは、3 月 1 日から午前 8 時～午後 5 時の間、2 時間ごとにワークフローを実行するように設定されています。

   ![](assets/wkf_scheduler_day.png)

   +++

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

