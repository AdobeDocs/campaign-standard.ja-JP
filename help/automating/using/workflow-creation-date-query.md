---
title: '"ワークフローの使用例：プロファイルの作成日に搬送を作成する'
seo-title: '"ワークフローの使用例：プロファイルの作成日に搬送を作成する'
description: '"ワークフローの使用例：プロファイルの作成日に搬送を作成する'
seo-description: '"ワークフローの使用例：プロファイルの作成日に搬送を作成する'
page-status-flag: 未活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: '実行活動 '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: ワークフロー，ユースケース，クエリ
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# ワークフローのユースケース：プロファイルの作成日に配信を作成 {#creation-date-query}

お客様のプロファイル作成の記念日に、Eメールでオファーを送信できます。

1. で、をク **[!UICONTROL Marketing Activities]**&#x200B;リックして **[!UICONTROL Create]** を選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** の種類としてを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## スケジューラ·アクティビティの作成 {#creating-a-scheduler-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Execution]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Scheduler activity]**&#x200B;す。
1. アクティビティをダブルクリックします。
1. 配信の実行を構成します。
1. でを選 **[!UICONTROL Execution frequency]**&#x200B;択します **[!UICONTROL Daily]**。
1. ワークフロ **[!UICONTROL Time]** ーのと実 **[!UICONTROL Repetition frequency]** 行のを選択します。
1. ワークフローの **[!UICONTROL Start]** 日付と日 **[!UICONTROL Expiration]** 付を選択してください。
1. アクティビティを確認し、ワークフローを保存します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、タブで、**[!UICONTROL Execution options]**&#x200B;スケジューラのタイムゾーンをフィールドに設定 **[!UICONTROL Time zone]**&#x200B;します。

![](assets/time_zone.png)

## クエリアクティビティの作成 {#creating-a-query-activity}

1. 受信者を選択するには、宛先をドラッグアンドドロップし **[!UICONTROL Query activity]** て、その宛先をダブルクリックします。
1. 値を追 **[!UICONTROL Profiles]** 加し、値 **[!UICONTROL no longer contact by email]** で選択します **[!UICONTROL no]**。

### 実行日と同じ日に作成されたプロファイルを取得しています {#retriving-profiles-created-on-the-same-day}

1. で、フ **[!UICONTROL Profile]**&#x200B;ィールドをドラッグアンドドロップ **[!UICONTROL Created]** します。 をクリックしま **[!UICONTROL Advanced Mode]**す。
   ![](assets/advanced_mode.png)
1. で、ノー **[!UICONTROL list of functions]**&#x200B;ドからダブルク&#x200B;**[!UICONTROL Day]** リックし&#x200B;**[!UICONTROL Date]**&#x200B;ます。
1. 次に、フィールドを引数として **[!UICONTROL Created]** 挿入します。
1. 演算子と **[!UICONTROL equals to (=)]** してを選択します。
1. [値]で、のノ&#x200B;**[!UICONTROL Day]** ードか **[!UICONTROL Date]** らを選択します **[!UICONTROL List of functions]**。
1. 関数を引数&#x200B;**[!UICONTROL GetDate()]**&#x200B;として挿入します。

作成日が現在の日と等しいプロファイルを取得しました。

最後に、次の文字列が表示されます。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### 実行月と同じ月に作成されたプロファイルを取得しています{#retriving-profiles-created-on-the-same-month}

1. エディタ **[!UICONTROL Query]** で最初のクエリを選択し、複製します。
1. 複製を開きます。
1. クエリ **[!UICONTROL Day]** 内で **[!UICONTROL Month]** に置き換えます。
1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

最後に、次のようにします。

``` Month(@created) = Month(GetDate()) ```

最後のクエリーには、次のように表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 電子メール配信の作成{#creating-an-email-delivery}

1. 電子メール配信をドラッグ·アンド·ドロップします。
1. アクティビティをクリックし、編集するア ![](assets/edit_darkgrey-24px.png) クティビティを選択します。
1. を選択し、 **[!UICONTROL Recurring email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、をクリックしま **[!UICONTROL Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをカスタマイズします。
詳細については、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. レイアウトを **[!UICONTROL Preview]** 確認するには、をクリックします。
1. Click **[!UICONTROL Save]**.

**関連トピック：**

* [クエリ](../../automating/using/query.md)
* [スケジューラ](../../automating/using/scheduler.md)
* [電子メール配信](../../automating/using/email-delivery.md)
* [電子メールチャネル](../../channels/using/creating-an-email.md)
