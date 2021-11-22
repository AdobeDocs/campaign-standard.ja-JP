---
title: プロファイル作成日の配信作成
description: このユースケースは、プロファイルの作成日に配信を作成する方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f611e023-f74c-476e-83b9-aff451f68c81
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---

# プロファイルの作成日での配信作成 {#creation-date-query}

顧客のプロファイル作成記念日に E メールでオファーを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## スケジューラーアクティビティの作成 {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**、ドラッグ&amp;ドロップ [スケジューラ](../../automating/using/scheduler.md) アクティビティ。
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. 「**[!UICONTROL Execution frequency]**」で、「**[!UICONTROL Daily]**」を選択します。
1. を選択します。 **[!UICONTROL Time]** そして **[!UICONTROL Repetition frequency]** 実行されます。
1. を選択します。 **[!UICONTROL Start]** 日付と **[!UICONTROL Expiration]** ワークフローの
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、 **[!UICONTROL Execution options]** 」タブで、 **[!UICONTROL Time zone]** フィールドに入力します。 デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

![](assets/time_zone.png)

## クエリアクティビティの作成 {#creating-a-query-activity}

1. 受信者を選択するには、 [クエリ](../../automating/using/query.md) 「 」アクティビティをクリックし、ダブルクリックします。
1. 追加 **[!UICONTROL Profiles]** を選択し、 **[!UICONTROL no longer contact by email]** 値 **[!UICONTROL no]**.

### 実行日と同じ日に作成されたプロファイルの取得 {#retrieving-profiles-created-on-the-same-day}

1. In **[!UICONTROL Profile]**、ドラッグ&amp;ドロップ **[!UICONTROL Created]** フィールドに入力します。 をクリックし、 **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. 内 **[!UICONTROL list of functions]**，ダブルクリック **[!UICONTROL Day]** から **[!UICONTROL Date]** ノード。
1. 次に、フィールドを挿入します **[!UICONTROL Created]** 引数として。
1. 選択 **[!UICONTROL equals to (=)]** を演算子として使用します。
1. [ 値 ] で、を選択します。 **[!UICONTROL Day]** から **[!UICONTROL Date]** ノードを **[!UICONTROL List of functions]**.
1. を **[!UICONTROL GetDate()]** 関数の引数として渡されます。

作成日が現在の日と等しいプロファイルを取得しました。

最終的には次のようになります。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

「**[!UICONTROL Confirm]**」をクリックします。

### 実行月と同じ月に作成されたプロファイルの取得{#retrieving-profiles-created-on-the-same-month}

1. の **[!UICONTROL Query]** エディターで、最初のクエリを選択して複製します。
1. 複製を開きます。
1. 置換 **[!UICONTROL Day]** 作成者 **[!UICONTROL Month]** 」と入力します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/month_rule.png)

最終的には、次のようになります。

``` Month(@created) = Month(GetDate()) ```

最後のクエリが表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## E メール配信の作成{#creating-an-email-delivery}

1. ドラッグ&amp;ドロップ [E メール配信](../../automating/using/email-delivery.md) アクティビティ。
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

* [メールチャネル](../../channels/using/creating-an-email.md)
