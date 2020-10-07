---
title: プロファイルの作成日に配信を作成する
description: この使用例は、プロファイルの作成日に配信を作成する方法を示します。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---


# プロファイルの作成日の配信作成 {#creation-date-query}

お客様のプロファイルの作成を記念して、電子メールでオファーを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## スケジューラーアクティビティの作成 {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Scheduler](../../automating/using/scheduler.md) activity.
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. 「**[!UICONTROL Execution frequency]**」で、「**[!UICONTROL Daily]**」を選択します。
1. ワークフローの実行 **[!UICONTROL Time]** と実行 **[!UICONTROL Repetition frequency]** を選択します。
1. ワークフローの **[!UICONTROL Start]** 日付と **[!UICONTROL Expiration]** 日付を選択します。
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>To start your workflow at a specific time zone, in the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

![](assets/time_zone.png)

## クエリアクティビティの作成{#creating-a-query-activity}

1. To select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. 値 **[!UICONTROL Profiles]** を使用してを追加選択し **[!UICONTROL no longer contact by email]** ま **[!UICONTROL no]**&#x200B;す。

### 実行日と同じ日に作成されたプロファイルの取得 {#retriving-profiles-created-on-the-same-day}

1. で、フィ **[!UICONTROL Profile]**&#x200B;ールドをドラッグ&amp;ドロップし **[!UICONTROL Created]** ます。 をクリックし **[!UICONTROL Advanced Mode]**ます。
   ![](assets/advanced_mode.png)
1. で、 **[!UICONTROL list of functions]**&#x200B;ノード&#x200B;**[!UICONTROL Day]** から重複クリックし&#x200B;**[!UICONTROL Date]**&#x200B;ます。
1. 次に、フィールドを引数 **[!UICONTROL Created]** として挿入します。
1. Select **[!UICONTROL equals to (=)]** as the operator.
1. [値]で、の&#x200B;**[!UICONTROL Day]** ノードからを選択し **[!UICONTROL Date]****[!UICONTROL List of functions]**&#x200B;ます。
1. 関数を引数として挿入し&#x200B;**[!UICONTROL GetDate()]**&#x200B;ます。

作成日が現在の日と等しいプロファイルを取得しました。

最後に次の文字列が表示されます。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

「**[!UICONTROL Confirm]**」をクリックします。

### 実行月と同じ月に作成されたプロファイルの取得{#retriving-profiles-created-on-the-same-month}

1. エディターで、最初のクエリを選択し、重複します。 **[!UICONTROL Query]**
1. 重複を開きます。
1. クエリ **[!UICONTROL Day]** の「」 **[!UICONTROL Month]** をに置き換えます。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/month_rule.png)

最終的には、次のようになります。

``` Month(@created) = Month(GetDate()) ```

最後のクエリが表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## E メール配信の作成{#creating-an-email-delivery}

1. 「 [電子メール配信](../../automating/using/email-delivery.md) 」アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Recurring email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して E メールをパーソナライズします。詳しくは、[E メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

**関連トピック：**

* [E メールチャネル](../../channels/using/creating-an-email.md)
