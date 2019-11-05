---
title: 増分クエリ
description: Incrementalクエリアクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルターおよび抽出できます。
page-status-flag: 非活性化の
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲティング活動
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 増分クエリ{#incremental-query}

## 説明 {#description}

![](assets/incremental.png)

このア **[!UICONTROL Incremental query]** クティビティでは、Adobe Campaignデータベースから要素の母集団をフィルターして抽出できます。 このアクティビティが実行されるたびに、以前の実行の結果が除外されます。 これにより、新しい要素のみをターゲットにすることができます。

専用タブを使用し **[!UICONTROL Additional data]** て、ターゲット母集団を定義できます。 このデータは追加の列に保存され、処理中のワークフローでのみ使用できます。

アクティビティでは、クエリーエディターツールを使用します。 このツールの詳細は、専用のセクシ [ョンで説明します](../../automating/using/editing-queries.md#about-query-editor)。

## 使用状況 {#context-of-use}

ワー **[!UICONTROL Incremental query]** クフローの実行頻度、つまりク **[!UICONTROL Scheduler]** エリを定義するには、をにリンクする必要があります。

このア **[!UICONTROL Processed data]** クティビティに固有のタブを使用すると、必要に応じて、アクティビティの以前の実行の結果を表示できます。

アクテ **[!UICONTROL Incremental query]** ィビティは、様々な種類の使用に使用できます。

* 個人をセグメント化して、メッセージ、オーディエンスなどのターゲットを定義します。
* データのエクスポート.

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Incremental query]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. プロファイルリソース以外のリソースに対してクエリーを実行する場合は、アクティビティのタブに移動し、とを **[!UICONTROL Properties]** 選択して **[!UICONTROL Resource]** ください **[!UICONTROL Targeting dimension]**。

   を使 **[!UICONTROL Resource]****[!UICONTROL Targeting dimension]**&#x200B;用すると、パレットに表示されるフィルターを絞り込むことができます。一方、選択したリソースに関するコンテキストは、取得する母集団のタイプ（特定されたプロファイル、配信、選択したリソースにリンクされたデータなど）に対応します。

1. タブで、ル **[!UICONTROL Target]** ールを定義して組み合わせてクエリーを実行します。
1. タブで、 **[!UICONTROL Processed data]** 次のワークフロー実行に使用する増分モードを選択します。

   * **[!UICONTROL Use the exclusion of the results of previous executions]**:新しい実行ごとの以前の実行の結果は除外されます。
   * **[!UICONTROL Use a date field]**:次の実行では、選択した日付フィールドがアクティビティの最後の実行日以上の結果のみが考慮され **[!UICONTROL Incremental query]** ます。 タブで選択したリソースに関連する日付フィールドを選択でき **[!UICONTROL Properties]** ます。 ログデータなどの大きなリソースをクエリする場合、このモードの方がパフォーマンスが向上します。

      ワークフローの最初の実行後、このタブには、次の実行に使用される最後の実行日が表示されます。 ワークフローが実行されるたびに、自動的に更新されます。 新しい値を手動で入力して、必要に応じて上書きすることもできます。
   >[!NOTE]
   >
   >このモ **[!UICONTROL Use a date field]** ードでは、選択した日付フィールドに応じて、より柔軟に対応できます。 例えば、選択したフィールドが変更日に対応する場合、日付フィールドモードでは最近更新されたデータを取得でき、他のモードでは、ワークフローの最後の実行以降に変更された記録も含め、前の実行で既にターゲットにされている記録が除外されます。

   ![](assets/incremental_query_usedatefield.png)

1. 専用タブを使用し **[!UICONTROL Additional data]** て、ターゲット母集団を定義できます。 このデータは追加の列に保存され、処理中のワークフローでのみ使用できます。 特に、クエリーのターゲットディメンションにリンクされたAdobe Campaignデータベーステーブルからデータを追加できます。 「データを豊 [富にする](../../automating/using/query.md#enriching-data) 」を参照。
1. アクティビティの設定を確認し、ワークフローを保存します。

## データのエンリッチメント {#enriching-data}

クエリーと同様に、からのデータをエンリッチできます **[!UICONTROL Incremental query]**。 「データを豊 [富にする](../../automating/using/query.md#enriching-data) 」を参照。

## 例：サービスのサブスクライバーに対する増分クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、実行中のニュースレターサービスに登録されているAdobe Campaignデータベース内のプロファイルをフィルターし **[!UICONTROL Incremental query]** 、プロモーションコードを含むご案内の電子メールを送信するアクティビティの設定を示しています **** 。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* 毎週月 **[!UICONTROL Scheduler]** 曜日の午前6時にワークフローを実行するアクティビティ。

   ![](assets/incremental_query_example2.png)

* アクティビテ **[!UICONTROL Incremental query]** ィ。最初の実行時に現在のすべてのサブスクライバーをターゲットにし、次の実行時にその週の新しいサブスクライバーのみをターゲットにします。

   ![](assets/incremental_query_example3.png)

* アクテ **[!UICONTROL Email delivery]** ィビティ。 ワークフローは週に1回実行されますが、1か月のみでなく、1か月全体の期間にわたってレポートを生成するなど、送信された電子メールと1か月の結果を集計できます。

   これを行うには、電子メールと結果を再グル **[!UICONTROL Recurring email]** ープ化する「ここ」を選択しま **[!UICONTROL By month]**&#x200B;す。

   電子メールの内容を定義し、ウェルカムプロモーションコードを挿入します。

   詳しくは、「電子メール配信」および「電子メ [ールコンテンツの定義](../../automating/using/email-delivery.md) 」 [の項を参照してください](../../designing/using/personalization.md) 。

次に、ワークフローの実行を開始します。 新しい購読者は毎週、プロモーションコードが記載されたご案内の電子メールを受信します。

## 例：配信ログの増分クエリ {#example--incremental-query-on-delivery-logs}

アクティビティを使用して、 **[!UICONTROL Incremental query]** 新しいログインファイルを定期的にエクスポートできます。 ログデータを外部レポートやBIツールで使用する場合などに役立ちます。

詳細な例は、「ログのエクスポート」セクシ [ョンにあります](../../automating/using/exporting-logs.md) 。
