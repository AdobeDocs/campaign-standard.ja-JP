---
title: 「ワークフローの使用例：プロファイル作成日に配信を作成する」
description: 「ワークフローの使用例：プロファイル作成日に配信を作成する」
page-status-flag: 非活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: '実行活動 '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローの使用例：プロファイルの作成日に配信を作成 {#creation-date-query}

顧客のプロファイル作成の契約応当日に、電子メールでオファーを送信できます。

1. で、を **[!UICONTROL Marketing Activities]**&#x200B;クリックし **[!UICONTROL Create]** てを選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** タイプとして選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## スケジューラーアクティビティの作成 {#creating-a-scheduler-activity}

1. /で、 **[!UICONTROL Activities]** をドラ **[!UICONTROL Execution]**&#x200B;ッグ&amp;ドロップしま **[!UICONTROL Scheduler activity]**&#x200B;す。
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. で、を **[!UICONTROL Execution frequency]**&#x200B;選択しま **[!UICONTROL Daily]**&#x200B;す。
1. ワークフ **[!UICONTROL Time]** ローの実行 **[!UICONTROL Repetition frequency]** のとを選択します。
1. ワークフロー **[!UICONTROL Start]** の日付と **[!UICONTROL Expiration]** 日付を選択します。
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、タブの&#x200B;**[!UICONTROL Execution options]**&#x200B;フィールドでスケジューラーのタイムゾーンを設定 **[!UICONTROL Time zone]**&#x200B;します。

![](assets/time_zone.png)

## クエリーアクティビティの作成 {#creating-a-query-activity}

1. 受信者を選択するには、受信者をドラッグ&amp;ドロッ **[!UICONTROL Query activity]** プしてダブルクリックします。
1. を追加 **[!UICONTROL Profiles]** し、値を使 **[!UICONTROL no longer contact by email]** 用して選択しま **[!UICONTROL no]**&#x200B;す。

### 実行日と同じ日に作成されたプロファイルの取得 {#retriving-profiles-created-on-the-same-day}

1. で、フ **[!UICONTROL Profile]**&#x200B;ィールドをドラッグ&amp;ドロップ **[!UICONTROL Created]** します。 をクリックしま **[!UICONTROL Advanced Mode]**す。
   ![](assets/advanced_mode.png)
1. で、ノ **[!UICONTROL list of functions]**&#x200B;ードをダブルク&#x200B;**[!UICONTROL Day]** リックし&#x200B;**[!UICONTROL Date]**&#x200B;ます。
1. 次に、フィールドを引数とし **[!UICONTROL Created]** て挿入します。
1. 演算子 **[!UICONTROL equals to (=)]** として選択します。
1. 「値」で、内のノ&#x200B;**[!UICONTROL Day]** ードか **[!UICONTROL Date]** ら選択します **[!UICONTROL List of functions]**。
1. 関数を引数&#x200B;**[!UICONTROL GetDate()]**&#x200B;として挿入します。

作成日が現在の日と等しいプロファイルを取得しました。

最後に、次のように指定します。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### 実行月と同じ月に作成されたプロファイルの取得{#retriving-profiles-created-on-the-same-month}

1. エディター **[!UICONTROL Query]** で、最初のクエリーを選択し、複製します。
1. 複製を開きます。
1. クエリ **[!UICONTROL Day]** 内ので **[!UICONTROL Month]** 置き換えます。
1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

最終的には、次のようになります。

``` Month(@created) = Month(GetDate()) ```

最後のクエリーが表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. 電子メール配信をドラッグ&amp;ドロップします。
1. アクティビティをクリックし、編集する ![](assets/edit_darkgrey-24px.png) 対象を選択します。
1. を選択し、 **[!UICONTROL Recurring email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、[オン]をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをパーソナライズします。
詳しくは、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. をクリック **[!UICONTROL Preview]** して、レイアウトを確認します。
1. Click **[!UICONTROL Save]**.

**関連トピック：**

* [クエリ](../../automating/using/query.md)
* [スケジューラー](../../automating/using/scheduler.md)
* [E メール配信](../../automating/using/email-delivery.md)
* [E メールチャネル](../../channels/using/creating-an-email.md)
