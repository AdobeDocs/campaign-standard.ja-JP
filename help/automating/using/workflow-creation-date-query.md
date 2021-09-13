---
title: プロファイルの作成日に配信を作成する
description: この使用例では、プロファイルの作成日に配信を作成する方法を示します。
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

顧客のプロファイル作成の記念日に、Eメールでオファーを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## スケジューラーアクティビティの作成 {#creating-a-scheduler-activity}

1. **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;で、[スケジューラー](../../automating/using/scheduler.md)アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. 「**[!UICONTROL Execution frequency]**」で、「**[!UICONTROL Daily]**」を選択します。
1. ワークフローの&#x200B;**[!UICONTROL Time]**&#x200B;と実行の&#x200B;**[!UICONTROL Repetition frequency]**&#x200B;を選択します。
1. ワークフローの&#x200B;**[!UICONTROL Start]**&#x200B;日付と&#x200B;**[!UICONTROL Expiration]**&#x200B;を選択します。
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、「**[!UICONTROL Execution options]**」タブの「**[!UICONTROL Time zone]**」フィールドで、スケジューラーのタイムゾーンを設定します。 デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

![](assets/time_zone.png)

## クエリアクティビティの作成 {#creating-a-query-activity}

1. 受信者を選択するには、[クエリ](../../automating/using/query.md)アクティビティをドラッグ&amp;ドロップし、ダブルクリックします。
1. **[!UICONTROL Profiles]**&#x200B;を追加し、値&#x200B;**[!UICONTROL no]**&#x200B;を&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;として選択します。

### 実行日と同じ日に作成されたプロファイルの取得 {#retrieving-profiles-created-on-the-same-day}

1. **[!UICONTROL Profile]**&#x200B;で、**[!UICONTROL Created]**&#x200B;フィールドをドラッグ&amp;ドロップします。 **[!UICONTROL Advanced Mode]**をクリックします。
   ![](assets/advanced_mode.png)
1. **[!UICONTROL list of functions]**&#x200B;で、**[!UICONTROL Date]**&#x200B;ノードから&#x200B;**[!UICONTROL Day]**&#x200B;をダブルクリックします。
1. 次に、引数としてフィールド&#x200B;**[!UICONTROL Created]**&#x200B;を挿入します。
1. 演算子として&#x200B;**[!UICONTROL equals to (=)]**&#x200B;を選択します。
1. 「値」で、**[!UICONTROL List of functions]**&#x200B;の&#x200B;**[!UICONTROL Date]**&#x200B;ノードから&#x200B;**[!UICONTROL Day]**&#x200B;を選択します。
1. **[!UICONTROL GetDate()]**&#x200B;関数を引数として挿入します。

作成日が現在の日と等しいプロファイルを取得した。

最後に、次のようになります。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

「**[!UICONTROL Confirm]**」をクリックします。

### 実行月と同じ月に作成されたプロファイルの取得{#retrieving-profiles-created-on-the-same-month}

1. **[!UICONTROL Query]**&#x200B;エディターで、最初のクエリを選択して複製します。
1. 複製を開きます。
1. クエリで&#x200B;**[!UICONTROL Day]**&#x200B;を&#x200B;**[!UICONTROL Month]**&#x200B;に置き換えます。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/month_rule.png)

最後に、次のようになります。

``` Month(@created) = Month(GetDate()) ```

最後のクエリが表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## E メール配信の作成{#creating-an-email-delivery}

1. [Eメール配信](../../automating/using/email-delivery.md)アクティビティをドラッグ&amp;ドロップします。
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
