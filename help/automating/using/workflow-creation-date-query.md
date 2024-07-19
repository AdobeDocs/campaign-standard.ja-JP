---
title: プロファイルの作成日での配信の作成
description: このユースケースは、プロファイルの作成日に配信を作成する方法を示しています。
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
ht-degree: 33%

---

# プロファイルの作成日での配信作成 {#creation-date-query}

顧客のプロファイル作成の記念日に、メールでオファーを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## スケジューラーアクティビティの作成 {#creating-a-scheduler-activity}

1. **[!UICONTROL Activities]**/**[!UICONTROL Execution]** で、「[ スケジューラー ](../../automating/using/scheduler.md)」アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. 「**[!UICONTROL Execution frequency]**」で、「**[!UICONTROL Daily]**」を選択します。
1. ワークフローの **[!UICONTROL Time]** と実行 **[!UICONTROL Repetition frequency]** を選択します。
1. ワークフローの **[!UICONTROL Start]** 定日 **[!UICONTROL Expiration]** を選択します。
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、「**[!UICONTROL Execution options]**」タブで、「**[!UICONTROL Time zone]**」フィールドにスケジューラーのタイムゾーンを設定します。 デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

![](assets/time_zone.png)

## クエリ アクティビティの作成 {#creating-a-query-activity}

1. 受信者を選択するには、[ クエリ ](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップし、ダブルクリックします。
1. **[!UICONTROL Profiles]** を追加し、値が **[!UICONTROL no]** の **[!UICONTROL no longer contact by email]** を選択します。

### 実行日と同じ日に作成されたプロファイルを取得 {#retrieving-profiles-created-on-the-same-day}

1. **[!UICONTROL Profile]** で、**[!UICONTROL Created]** フィールドをドラッグ&amp;ドロップします。 「**[!UICONTROL Advanced Mode]**」をクリックします。
   ![](assets/advanced_mode.png)
1. **[!UICONTROL list of functions]** で、**[!UICONTROL Date]** ノードの **[!UICONTROL Day]** をダブルクリックします。
1. 次に、フィールド **[!UICONTROL Created]** を引数として挿入します。
1. 演算子として「**[!UICONTROL equals to (=)]**」を選択します。
1. 「値」で、**[!UICONTROL List of functions]** の **[!UICONTROL Date]** ノードから「**[!UICONTROL Day]**」を選択します。
1. **[!UICONTROL GetDate()]** 関数を引数として挿入します。

作成日が現在の日付に等しいプロファイルを取得しました。

最終的には、次のようになります。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

「**[!UICONTROL Confirm]**」をクリックします。

### 実行月と同じ月に作成されたプロファイルの取得{#retrieving-profiles-created-on-the-same-month}

1. **[!UICONTROL Query]** エディターで、最初のクエリを選択し、複製します。
1. 複製を開きます。
1. **[!UICONTROL Day]** をクエリの **[!UICONTROL Month]** で置き換えます。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/month_rule.png)

最終的には、次のようになります。

``` Month(@created) = Month(GetDate()) ```

最終的なクエリには、次の内容が表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## メール配信の作成{#creating-an-email-delivery}

1. [ メール配信 ](../../automating/using/email-delivery.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、![](assets/edit_darkgrey-24px.png) を選択して編集します。
1. 「**[!UICONTROL Recurring email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. メールのレイアウトを作成するには、「**[!UICONTROL Email Designer]**」をクリックします。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用してメールをパーソナライズします。
詳しくは、[メールのデザイン](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)を参照してください。
1. 「**[!UICONTROL Preview]**」をクリックして、レイアウトを確認します。
1. 「**[!UICONTROL Save]**」をクリックします。

**関連トピック：**

* [メールチャネル](../../channels/using/creating-an-email.md)
