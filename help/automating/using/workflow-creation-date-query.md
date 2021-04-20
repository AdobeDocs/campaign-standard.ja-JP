---
solution: Campaign Standard
product: campaign
title: プロファイルの作成日に配信を作成する
description: この使用例は、プロファイルの作成日に配信を作成する方法を示します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 38%

---


# プロファイルの作成日の配信作成 {#creation-date-query}

お客様のプロファイルの作成を記念して、電子メールでオファーを送信できます。

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

## スケジューラーアクティビティの作成 {#creating-a-scheduler-activity}

1. **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;に[スケジューラー](../../automating/using/scheduler.md)アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. 「**[!UICONTROL Execution frequency]**」で、「**[!UICONTROL Daily]**」を選択します。
1. ワークフローの実行の&#x200B;**[!UICONTROL Time]**&#x200B;と&#x200B;**[!UICONTROL Repetition frequency]**&#x200B;を選択します。
1. ワークフローの&#x200B;**[!UICONTROL Start]**&#x200B;日付と&#x200B;**[!UICONTROL Expiration]**&#x200B;を選択します。
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、「**[!UICONTROL Execution options]**」タブの&#x200B;**[!UICONTROL Time zone]**&#x200B;フィールドにスケジューラーのタイムゾーンを設定します。 デフォルトで選択されるタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンです（[ワークフローの作成](../../automating/using/building-a-workflow.md)を参照）。

![](assets/time_zone.png)

## クエリアクティビティの作成{#creating-a-query-activity}

1. 受信者を選択するには、[クエリ](../../automating/using/query.md)アクティビティをドラッグ&amp;ドロップし、重複を押しながらクリックします。
1. 追加&#x200B;**[!UICONTROL Profiles]**&#x200B;を選択し、**[!UICONTROL no]**&#x200B;の値を&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;に設定します。

### 実行日{#retrieving-profiles-created-on-the-same-day}と同じ日に作成されたプロファイルを取得しています

1. **[!UICONTROL Profile]**&#x200B;で、**[!UICONTROL Created]**&#x200B;フィールドをドラッグ&amp;ドロップします。 **[!UICONTROL Advanced Mode]**をクリックします。
   ![](assets/advanced_mode.png)
1. **[!UICONTROL list of functions]**&#x200B;で、**[!UICONTROL Date]**&#x200B;ノードから&#x200B;**[!UICONTROL Day]**&#x200B;を重複クリックします。
1. 次に、フィールド&#x200B;**[!UICONTROL Created]**&#x200B;を引数として挿入します。
1. 演算子として&#x200B;**[!UICONTROL equals to (=)]**&#x200B;を選択します。
1. 「値」で、**[!UICONTROL List of functions]**&#x200B;の&#x200B;**[!UICONTROL Date]**&#x200B;ノードから&#x200B;**[!UICONTROL Day]**&#x200B;を選択します。
1. **[!UICONTROL GetDate()]**&#x200B;関数を引数として挿入します。

作成日が現在の日と等しいプロファイルを取得しました。

最後に次の文字列が表示されます。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

「**[!UICONTROL Confirm]**」をクリックします。

### 実行月と同じ月に作成されたプロファイルを取得しています{#retrieving-profiles-created-on-the-same-month}

1. **[!UICONTROL Query]**&#x200B;エディターで、最初のクエリを選択し、重複します。
1. 重複を開きます。
1. クエリの&#x200B;**[!UICONTROL Day]**&#x200B;を&#x200B;**[!UICONTROL Month]**&#x200B;で置き換えます。
1. 「**[!UICONTROL Confirm]**」をクリックします。

![](assets/month_rule.png)

最終的には、次のようになります。

``` Month(@created) = Month(GetDate()) ```

最後のクエリが表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## E メール配信の作成{#creating-an-email-delivery}

1. [電子メール配信](../../automating/using/email-delivery.md)アクティビティをドラッグ&amp;ドロップします。
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
