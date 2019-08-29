---
title: 「ワークフローのユースケース:プロファイルの作成日に搬送を作成しています」
seo-title: 「ワークフローのユースケース:プロファイルの作成日に搬送を作成しています」
description: 「ワークフローのユースケース:プロファイルの作成日に搬送を作成しています」
seo-description: 「ワークフローのユースケース:プロファイルの作成日に搬送を作成しています」
page-status-flag: 決して活性化されていない
uuid: 396a3de1-6fa-4385- ac9f-15fdee5a366
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: '実行活動 '
discoiquuid: 377821e6-69f8-41cc- a1ad-8a2f5d409
context-tags: ワークフロー、ユースケース、クエリ
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# ワークフローのユースケース:プロファイルの作成日に配送を作成 {#creation-date-query}

お客様のプロファイル作成日に電子メールでオファーを送信できます。

1. で **[!UICONTROL Marketing Activities]**、をクリック **[!UICONTROL Create]** して選択 **[!UICONTROL Workflow]**&#x200B;します。
1. ワークフロータイプ **[!UICONTROL New Workflow]** として選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. ワークフローのプロパティを入力し、をクリック **[!UICONTROL Create]**&#x200B;します。

## スケジューラ・アクティビティの作成 {#creating-a-scheduler-activity}

1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Execution]**、をドラッグアンドドロップ **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png)します。
1. アクティビティをダブルクリックします。
1. 配信の実行を構成します。
1. で、を **[!UICONTROL Execution frequency]**&#x200B;選択 **[!UICONTROL Daily]**&#x200B;します。
1. ワークフローの実行 **[!UICONTROL Time]****[!UICONTROL Repetition frequency]** と実行を選択します。
1. ワークフローの **[!UICONTROL Start]** 日付 **[!UICONTROL Expiration]** と日付を選択します。

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するには、タブ&#x200B;**[!UICONTROL Execution options]**&#x200B;で、フィールド内のスケジューラのタイムゾーンを設定 **[!UICONTROL Time zone]**&#x200B;します。

![](assets/time_zone.png)

1. アクティビティを確認し、ワークフローを保存します。

## クエリアクティビティの作成 {#creating-a-query-activity}

1. 受信者を選択するには、を **[!UICONTROL Query activity]** ドラッグアンドドロップしてダブルクリックします。
1. 値を追加 **[!UICONTROL Profiles]** して選択 **[!UICONTROL no longer contact by email]****[!UICONTROL no]**&#x200B;します。

### 実行日と同じ日に作成されたプロファイルを取得する {#retriving-profiles-created-on-the-same-day}

1. で **[!UICONTROL Profile]**、 **[!UICONTROL Created]** フィールドをドラッグアンドドロップします。をクリックし **[!UICONTROL Advanced Mode]**ます。
   ![](assets/advanced_mode.png)
1. で、 **[!UICONTROL list of functions]**&#x200B;ノード&#x200B;**[!UICONTROL Day]** からダブルクリック&#x200B;**[!UICONTROL Date]**&#x200B;します。
1. 次に、フィールドを引数 **[!UICONTROL Created]** として挿入します。
1. オペレータ **[!UICONTROL equals to (=)]** として選択します。
1. 「値」（Value）で、のノード&#x200B;**[!UICONTROL Day]** から **[!UICONTROL Date]** 選択 **[!UICONTROL List of functions]**&#x200B;します。
1. 関数を引数&#x200B;**[!UICONTROL GetDate()]**&#x200B;として挿入します。

作成日が現在の日と等しいプロファイルを取得しました。

次のようにしてください。

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

**[!UICONTROL Confirm]**&#x200B;をクリックします。

### 実行月と同じ月に作成されたプロファイルの取得{#retriving-profiles-created-on-the-same-month}

1. **[!UICONTROL Query]** エディターで、最初のクエリを選択して複製します。
1. 複製を開きます。
1. クエリ **[!UICONTROL Day]****[!UICONTROL Month]** で置き換えます。
次のようにしてください。

``` Month(@created) = Month(GetDate()) ```

1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

![](assets/month_rule.png)

最終クエリが表示されます。

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 電子メール配信の作成{#creating-an-email-delivery}

1. 電子メール配信をドラッグアンドドロップします。
1. アクティビティをクリックし、編集 ![](assets/edit_darkgrey-24px.png) するように選択します。
1. を選択 **[!UICONTROL Recurring email]** してをクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールテンプレートを選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのプロパティを入力し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのレイアウトを作成するには、をクリック **[!UICONTROL Email Designer]**&#x200B;します。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをカスタマイズします。
詳細については、電子メール [の設計](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)を参照してください。
1. クリック **[!UICONTROL Preview]** すると、レイアウトが確認されます。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

**関連トピック:**

* [クエリー](../../automating/using/query.md)
* [スケジューラ](../../automating/using/scheduler.md)
* [Eメール配信](../../automating/using/email-delivery.md)
* [Eメールチャネル](../../channels/using/creating-an-email.md)
