---
title: 増分クエリ
description: 増分処理クエリアクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 1%

---


# 増分クエリ{#incremental-query}

## 説明 {#description}

![](assets/incremental.png)

この **[!UICONTROL Incremental query]** アクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。 このアクティビティが実行されるたびに、以前の実行の結果が除外されます。 これにより、新しい要素のみをターゲットできます。

専用タブ **[!UICONTROL Additional data]** を使用して、ターゲット母集団を定義できます。 このデータは追加の列に保存され、進行中のワークフローでのみ使用できます。

アクティビティはクエリエディタツールを使用します。 このツールの詳細は、 [専用のセクション](../../automating/using/editing-queries.md#about-query-editor)。

## 使用状況 {#context-of-use}

ワークフロー **[!UICONTROL Incremental query]** の実行頻度、つまりクエリを定義するに **[!UICONTROL Scheduler]** は、ワークフローをとリンクする必要があります。

このアクティビティに固有の **[!UICONTROL Processed data]** タブを使用すると、必要に応じて、アクティビティの以前の実行の結果を表示できます。

この **[!UICONTROL Incremental query]** アクティビティは、次の様々な用途に使用できます。

* 個人をセグメント化して、メッセージ、オーディエンスなどのターゲットを定義する

* データのエクスポート.

   アクティビティを使用して、新しいログインファイルを定期的にエクスポートできます。 **[!UICONTROL Incremental query]** ログデータを外部レポートやBIツールで使用する場合などに便利です。 完全な例は、「ログの [エクスポート](../../automating/using/exporting-logs.md) 」セクションにあります。

**関連トピック**

* [使用例： サービスの購読者の増分処理クエリ](../../automating/using/incremental-query-on-subscribers.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Incremental query]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. プロファイルリソース以外のリソースに対してクエリを実行する場合は、アクティビティの **[!UICONTROL Properties]** タブに移動し、とを選択し **[!UICONTROL Resource]** ま **[!UICONTROL Targeting dimension]**&#x200B;す。

   パレットに表示されるフィルター **[!UICONTROL Resource]** を調整できます。一方、 **[!UICONTROL Targeting dimension]**&#x200B;選択したリソースに関するコンテキストは、取得する母集団のタイプ(特定されたプロファイル、配信、選択したリソースにリンクされたデータなど)に対応します。

1. タブで、ルールを定義 **[!UICONTROL Target]** して組み合わせてクエリを実行します。
1. タブで、次のワークフロー実行に使用する増分モードを選択し **[!UICONTROL Processed data]** ます。

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: 新しい実行のたびに以前に実行された結果が除外されます。
   * **[!UICONTROL Use a date field]**: 次回の実行では、選択した日付フィールドが **[!UICONTROL Incremental query]** アクティビティの最後の実行日以上になる結果のみが考慮されます。 タブで選択したリソースに関連する日付フィールドを選択でき **[!UICONTROL Properties]** ます。 ログデータなどの大きなリソースをクエリする場合、このモードの方がパフォーマンスが向上します。

      ワークフローの最初の実行後、このタブには、次の実行に使用される最後の実行日が表示されます。 ワークフローが実行されるたびに、自動的に更新されます。 必要に応じて新しい値を手動で入力することで、この値を上書きできます。
   >[!NOTE]
   >
   >この **[!UICONTROL Use a date field]** モードでは、選択した日付フィールドに応じて、より柔軟に指定できます。 例えば、選択したフィールドが変更日に対応する場合、日付フィールドモードでは最近更新されたデータを取得でき、他のモードでは、前回の実行から変更された記録も除外されます。

   ![](assets/incremental_query_usedatefield.png)

1. 専用タブ **[!UICONTROL Additional data]** を使用して、ターゲット母集団を定義できます。 このデータは追加の列に保存され、進行中のワークフローでのみ使用できます。 特に、クエリのターゲティングディメンションにリンクされたAdobe Campaignデータベーステーブルからデータを追加できます。 「 [データの富化](../../automating/using/query.md#enriching-data) 」の節を参照してください。
1. アクティビティの設定を確認し、ワークフローを保存します。

## データのエンリッチメント {#enriching-data}

クエリと同様に、からのデータを拡充でき **[!UICONTROL Incremental query]**&#x200B;ます。 「 [データの富化](../../automating/using/query.md#enriching-data) 」の節を参照してください。
