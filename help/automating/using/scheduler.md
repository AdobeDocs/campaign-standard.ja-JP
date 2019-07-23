---
title: スケジューラ
seo-title: スケジューラ
description: スケジューラ
seo-description: スケジューラーアクティビティを使用すると、ワークフローまたはアクティビティを開始するタイミングを設定できます。
page-status-flag: 常にアクティブ化されていない
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行アクティビティ
discoiquuid: 0fb16ina-3941-404f-899c-33f81pound4ed5
context-tags: スケジュール、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3216d09e18cd249e3f2a6aae74254bc172538810

---


# Scheduler{#scheduler}

## 説明 {#description}

![](assets/scheduler.png)

**[!UICONTROL Scheduler]** アクティビティを使用すると、ワークフローまたはアクティビティの開始時にスケジュールを設定できます。

## Context of use {#context-of-use}

**[!UICONTROL Scheduler]** アクティビティは、スケジュールされた開始として見なされます。The activity positioning rules within the chart are the same as for the **[!UICONTROL Start]** activity. このアクティビティにはインバウンドトランジションを含めることができません。

When building your workflow, only use one **[!UICONTROL Scheduler]** activity per branch and remember to set a time zone. それ以外の場合はサーバータイムゾーンで実行されます。

>[!CAUTION]
>
>The **[!UICONTROL Repetition frequency]** of the activity cannot be less than 10 minutes. つまり、ワークフローを10分ごとに複数回実行することはできません。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**:ワークフローが1回実行されます。
   * **[!UICONTROL Several times a day]**:ワークフローは1日に数回定期的に実行されます。特定の時間または定期的に実行を設定できます。
   * **[!UICONTROL Daily]**:ワークフローは、1日に1回特定の時間に実行されます。
   * **[!UICONTROL Weekly]**:ワークフローは、指定された時間、または1週間に数回実行されます。
   * **[!UICONTROL Monthly]**:ワークフローは、指定した時間に1回または複数回実行されます。ワークフローを実行する必要がある場合は、月数を選択できます。月の第2火曜日など、指定した曜日に実行を設定することもできます。
   * **[!UICONTROL Yearly]**:ワークフローは、指定した時間に1回または複数回実行されます。

1. 選択した頻度に従って実行の詳細を定義します。詳細フィールドは、使用頻度（時間、繰り返し頻度、指定日など）によって異なる場合があります。

   >[!NOTE]
   >
   >**[!UICONTROL Repetition frequency]** このフィールドを使用すると、ワークフローがトリガーされた時間を空白にすることができます。For example, if you select a daily execution period and the repetition frequency is set at **2** (days), the workflow will be triggered every two days. 10分未満にすることはできません。If the repetition frequency is set at **0** (also the default value), this option is not taken into account and the workflow will run according to the execution frequency specified.

1. 実行の期限を指定します。

   * **[!UICONTROL Never]**:指定した頻度に応じてワークフローが実行され、時間枠や繰り返し回数に制限されません。
   * **[!UICONTROL After a certain number of iterations]**:ワークフローは、指定した頻度に従って、 **X** の上限に達するまで実行されます。**[!UICONTROL Number of iterations]** したがって、指定する必要があります。
   * **[!UICONTROL On a specific date]**:ワークフローは指定した日付まで、指定した頻度に従って実行されます。したがって、実行のデッドラインを指定する必要があります。

1. Check the schedule of the next ten executions of your workflow by clicking **[!UICONTROL Preview next executions]**.

1. **[!UICONTROL Execution options]** タブで **[!UICONTROL Time zone]** 、フィールド内のスケジューラーのタイムゾーンを設定します。これにより、特定のタイムゾーンでワークフローを開始できます。そうしないと、ワークフローはデフォルトでサーバータイムゾーンで実行されます。

   For more information on sending delivery depending on the recipient's time zone, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) or this [example](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) of a recurring workflow.

1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

次の例では、アクティビティが設定されています。このアクティビティは、1か月ごとに午前7時（午前7時）に、未確定の期間に開始されます。

![](assets/wkf_scheduler_example.png)

