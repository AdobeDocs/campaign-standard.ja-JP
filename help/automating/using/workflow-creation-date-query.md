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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---


# Creating deliveries on profiles&#39; creation date {#creation-date-query}

お客様のプロファイルの作成を記念して、電子メールでオファーを送信できます。

1. で、 **[!UICONTROL Marketing Activities]**&#x200B;をクリック **[!UICONTROL Create]** してを選択し **[!UICONTROL Workflow]**&#x200B;ます。
1. ワークフローのタイプ **[!UICONTROL New Workflow]** として選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. ワークフローのプロパティを入力し、をクリックし **[!UICONTROL Create]**&#x200B;ます。

## スケジューラーアクティビティの作成 {#creating-a-scheduler-activity}

1. /で、 **[!UICONTROL Activities]** スケジューラー **[!UICONTROL Execution]**[](../../automating/using/scheduler.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを重複クリックします。
1. 配信の実行を設定します。
1. で、 **[!UICONTROL Execution frequency]**&#x200B;を選択し **[!UICONTROL Daily]**&#x200B;ます。
1. ワークフローの実行 **[!UICONTROL Time]** と実行 **[!UICONTROL Repetition frequency]** を選択します。
1. ワークフローの **[!UICONTROL Start]** 日付と **[!UICONTROL Expiration]** 日付を選択します。
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、**[!UICONTROL Execution options]**&#x200B;タブのフィールドでスケジューラーのタイムゾーンを設定し **[!UICONTROL Time zone]**&#x200B;ます。 デフォルトでは、選択したタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンになります(「ワークフローの [構築](../../automating/using/building-a-workflow.md)」を参照)。

![](assets/time_zone.png)

## Creating a Query activity {#creating-a-query-activity}

1. 受信者を選択するには、 [クエリ](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップし、重複キーを押しながらクリックします。
1. 値 **[!UICONTROL Profiles]** を使用してを追加選択し **[!UICONTROL no longer contact by email]** ま **[!UICONTROL no]**&#x200B;す。

### 実行日と同じ日に作成されたプロファイルの取得 {#retriving-profiles-created-on-the-same-day}

1. で、フィ **[!UICONTROL Profile]**&#x200B;ールドをドラッグ&amp;ドロップし **[!UICONTROL Created]** ます。 をクリックし **[!UICONTROL Advanced Mode]**ます。
   ![](assets/advanced_mode.png)
1. で、 **[!UICONTROL list of functions]**&#x200B;ノード&#x200B;**[!UICONTROL Day]** から重複クリックし&#x200B;**[!UICONTROL Date]**&#x200B;ます。
1. 次に、フィールドを引数 **[!UICONTROL Created]** として挿入します。
1. 演算子 **[!UICONTROL equals to (=)]** として選択します。
1. [値]で、の&#x200B;**[!UICONTROL Day]** ノードからを選択し **[!UICONTROL Date]****[!UICONTROL List of functions]**&#x200B;ます。
1. 関数を引数として挿入し&#x200B;**[!UICONTROL GetDate()]**&#x200B;ます。

作成日が現在の日と等しいプロファイルを取得しました。

最後に次の文字列が表示されます。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

クリック **[!UICONTROL Confirm]** .

### 実行月と同じ月に作成されたプロファイルの取得{#retriving-profiles-created-on-the-same-month}

1. エディターで、最初のクエリを選択し、重複します。 **[!UICONTROL Query]**
1. 重複を開きます。
1. クエリ **[!UICONTROL Day]** の「」 **[!UICONTROL Month]** をに置き換えます。
1. クリック **[!UICONTROL Confirm]** .

![](assets/month_rule.png)

最終的には、次のようになります。

``` Month(@created) = Month(GetDate()) ```

最後のクエリが表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. 「 [電子メール配信](../../automating/using/email-delivery.md) 」アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、「編集」 ![](assets/edit_darkgrey-24px.png) を選択します。
1. を選択 **[!UICONTROL Recurring email]** し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールテンプレートを選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのプロパティを入力し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのレイアウトを作成するには、[オン]をクリックし **[!UICONTROL Email Designer]**&#x200B;ます。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをパーソナライズします。
詳しくは、「電子メールの [設計](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)」を参照してください。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. クリック **[!UICONTROL Save]** .

**関連トピック：**

* [E メールチャネル](../../channels/using/creating-an-email.md)
