---
title: 増分クエリ
seo-title: 増分クエリ
description: 増分クエリ
seo-description: 増分クエリアクティビティを使用すると、Adobe Campaignデータベースから要素の集合をフィルタして抽出できます。
page-status-flag: 未活性化の
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 標的活動
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: 増分、メイン
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# 増分クエリ{#incremental-query}

## 説明 {#description}

![](assets/incremental.png)

このア **[!UICONTROL Incremental query]** クティビティでは、Adobe Campaignデータベースから要素の集団をフィルタして抽出できます。 このアクティビティが実行されるたびに、前の実行の結果が除外されます。 これにより、新しい要素のみをターゲットにすることができます。

専用のタブを使 **[!UICONTROL Additional data]** 用して、対象の母集団を定義できます。 このデータは追加の列に格納され、進行中のワークフローにのみ使用できます。

アクティビティは、クエリエディタツールを使用します。 このツールの詳細は、専用のセクション [で説明します](../../automating/using/editing-queries.md#about-query-editor)。

## 使用状況 {#context-of-use}

ワーク **[!UICONTROL Incremental query]** フローの実行頻度を定義するた **[!UICONTROL Scheduler]** めに、とをにリンクする必要があります。したがって、クエリは、

このア **[!UICONTROL Processed data]** クティビティに固有のタブを使用すると、必要に応じて、アクティビティの前の実行結果を表示できます。

このアク **[!UICONTROL Incremental query]** ティビティは、さまざまな種類の用途に使用できます。

* 個人をセグメント化して、メッセージ、対象者などのターゲットを定義します。
* データを書き出し中。

## 構成 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Incremental query]** にドラッグアンドドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. プロファイルリソース以外のリソースに対してクエリを実行する場合は、アクティビティのタブに移動し、とを **[!UICONTROL Properties]** 選択してく **[!UICONTROL Resource]** ださい **[!UICONTROL Targeting dimension]**。

   では **[!UICONTROL Resource]****[!UICONTROL Targeting dimension]**、パレットに表示されるフィルタを調整できます。ただし、選択したリソースに関するコンテキストは、取得する母集団のタイプ（識別されたプロファイル、配信、選択したリソースにリンクされたデータなど）に対応します。

1. タブで、ル **[!UICONTROL Target]** ールを定義し、結合してクエリを実行します。
1. タブで、 **[!UICONTROL Processed data]** 次にワークフローを実行するときに使用する増分モードを選択します。

   * **[!UICONTROL Use the exclusion of the results of previous executions]**:新しい実行ごとに前に実行した結果は除外されます。
   * **[!UICONTROL Use a date field]**:次の実行では、選択した日付フィールドがアクティビティの最後の実行日以上の結果のみが考慮され **[!UICONTROL Incremental query]** ます。 タブで選択したリソースに関連する任意の日付フィールドを選択で **[!UICONTROL Properties]** きます。 このモードは、ログ·データなどの大規模なリソースを問い合わせる際のパフォーマンスが向上します。

      ワークフローの最初の実行後、このタブには、次の実行に使用される最後の実行日が表示されます。 ワークフローが実行されるたびに、自動的に更新されます。 新しい値を手動で入力して、必要に応じてこの値を上書きする可能性があります。
   >[!NOTE]
   >
   >選択し **[!UICONTROL Use a date field]** た日付フィールドに応じて、より柔軟なモードを使用できます。 たとえば、選択したフィールドが変更日に対応する場合、日付フィールドモードでは、最近更新されたデータを取得でき、他のモードでは、前回の実行以降に変更されたレコーディングを除外できます。

   ![](assets/incremental_query_usedatefield.png)

1. 専用のタブを使 **[!UICONTROL Additional data]** 用して、対象の母集団を定義できます。 このデータは追加の列に格納され、進行中のワークフローにのみ使用できます。 特に、クエリのターゲットディメンションにリンクされたAdobe Campaignデータベーステーブルからデータを追加できます。 「データの濃縮」セ [クションを参照して](../../automating/using/query.md#enriching-data) ください。
1. アクティビティの設定を確認し、ワークフローを保存します。

## データの強化 {#enriching-data}

クエリと同様に、からのデータをリッチできます **[!UICONTROL Incremental query]**。 「データの濃縮」セ [クションを参照して](../../automating/using/query.md#enriching-data) ください。

## 例：サービスのサブスクライバーに対する増分クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、 **[!UICONTROL Incremental query]** Running Newsleter **** Serviceに登録されているAdobe Campaignデータベース内のプロファイルをフィルタし、プロモーションコードを含むようこそ電子メールを送信するアクティビティの構成を示しています。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* 毎週月 **[!UICONTROL Scheduler]** 曜の午前6時にワークフローを実行するアクティビティ。

   ![](assets/incremental_query_example2.png)

* 最初の **[!UICONTROL Incremental query]** 実行時に現在のすべてのサブスクライバをターゲットにし、次の実行時にその週の新しいサブスクライバのみをターゲットにするアクティビティ。

   ![](assets/incremental_query_example3.png)

* アクテ **[!UICONTROL Email delivery]** ィビティ。 ワークフローは週に1回実行されますが、1か月に1回だけでなく、1か月にわたってレポートを生成するなど、送信された電子メールと1か月ごとの結果を集約できます。

   この操作を行うには、電子メールと結果をここで **[!UICONTROL Recurring email]** 再グループ化するように選択しま **[!UICONTROL By month]**&#x200B;す。

   電子メールの内容を定義し、ウェルカムプロモーションコードを挿入します。

   詳細については、「電子メール配信」および「電子メ [ールコンテンツ](../../automating/using/email-delivery.md)[の定義」の項を参照してください](../../designing/using/personalization.md) 。

次に、ワークフローの実行を開始します。 新しい購読者は毎週、プロモーションコードを含むウェルカムメールを受け取ります。

## 例：配信ログに対する増分クエリ {#example--incremental-query-on-delivery-logs}

アクティビティを使用して、フ **[!UICONTROL Incremental query]** ァイル内の新しいログを定期的にエクスポートできます。 たとえば、外部レポートやBIツールでログデータを使用する場合に便利です。

完全な例は、「ログのエクスポート」セクシ [ョンにありま](../../automating/using/exporting-logs.md) す。
