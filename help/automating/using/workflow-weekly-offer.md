---
title: 週次配信の作成
description: このユースケースでは、週次配信の作成方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,delivery,scheduler
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 32d9d174-8438-48d7-b876-33a0c35d9549
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 76%

---

# 毎週火曜日のメール配信の作成{#creating-email-every-tuesday}

毎週火曜日にすべての顧客あてに特別オファーのメールを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## スケジューラーアクティビティの作成{#creating-a-scheduler-activity}

1. **[!UICONTROL Activities]**/**[!UICONTROL Execution]** で、「[ スケジューラー ](../../automating/using/scheduler.md)」アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. 「**[!UICONTROL Execution frequency]**」で、「**[!UICONTROL Weekly]**」を選択します。
1. 配信の **[!UICONTROL Time]** と **[!UICONTROL Repetition frequency]** を選択します。
1. 「**[!UICONTROL Days of the week]**」で、「**[!UICONTROL Tuesday]**」を選択します。
1. ワークフローの「**[!UICONTROL Start]**」および「**[!UICONTROL Expiration]**」パラメーターを指定します。
1. アクティビティを確認し、ワークフローを保存します。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>特定の **[!UICONTROL Time Zone]** でワークフローを開始するには、「**[!UICONTROL Execution options]**」タブの「タイムゾーン」フィールドで、スケジューラーのタイムゾーンを設定します。デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

## クエリ アクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]**/**[!UICONTROL Targeting]** で受信者を選択するには、[ クエリ ](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップし、ダブルクリックします。
1. **[!UICONTROL Shortcuts]**／**[!UICONTROL Profile]**&#x200B;で、**[!UICONTROL Email]** をドラッグ＆ドロップします。
1. 演算子として「**[!UICONTROL is not empty]**」を選択します。
1. **[!UICONTROL Shortcuts]**／**[!UICONTROL General]** でプロファイルを追加し、「**[!UICONTROL no longer contact by email]**」を選択して、値を「**[!UICONTROL No]**」に設定します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/wf-complement-query.png)

## メール配信の作成{#creating-an-email-delivery}

1. **[!UICONTROL Activities]**/**[!UICONTROL Channels]** で [ メール配信 ](../../automating/using/email-delivery.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Recurring email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. メールのレイアウトを作成するには、「**[!UICONTROL Use Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用してメールをパーソナライズします。
1. 「**[!UICONTROL Save]**」をクリックします。

詳しくは、[メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。

**関連トピック：**

* [メールチャネル](../../channels/using/creating-an-email.md)
