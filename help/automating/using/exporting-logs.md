---
title: ログの書き出し
description: ログデータは、配信と購読のどちらに関連するものであっても、単純なワークフローを通してエクスポートできます。
page-status-flag: never-activated
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: ca8a95d8-523f-4085-a2fc-e1d8262cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3895755aa2eeceb837f78f591bb6504d3eadec1f
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---


# ログの書き出し{#exporting-logs}

ログデータは、配信と購読のどちらに関連するものであっても、単純なワークフローを通してエクスポートできます。 独自のレポートまたはBIツールでキャンペーンの結果を分析できます。

>[!CAUTION]
>
>役割と [すべてのユニットへのアクセス権を持つ機能](../../administration/using/users-management.md#functional-administrators)管理者 **[!UICONTROL Administration]** ( **** 役割を持つ)のみが、送信ログ、メッセージログ、トラッキングログ、除外ログ、または購読ログにアクセスできます。 管理者以外のユーザーは、これらのログにターゲットできますが、リンクされたテーブル(プロファイル、配信)から開始できます。

ワークフローを実行するたび **[!UICONTROL Incremental query]** に新しいログのみを取得するURLと、出力列を定義する単純な **[!UICONTROL Extract file]** アクティビティを使用すると、必要な形式とすべてのデータを含むファイルを取得できます。 次に、 **[!UICONTROL Transfer file]** アクティビティを使用して最終ファイルを取得します。 各ワークフローの実行は、によって計画され **[!UICONTROL Scheduler]**&#x200B;ます。

エクスポートログ操作は、標準ユーザーが実行できます。 次のようなプライベートリソース。ブロードログ、トラッキングログ、除外ログ購読ログ、 **プロファイルの購読履歴ログは、機能管理者のみが管理できます** 。

1. この節で詳しく説明するように、新しいワークフロー [を作成します](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 追加 **[!UICONTROL Scheduler]** アクティビティを作成し、必要に応じて設定します。 月別の実行例を以下に示します。

   ![](assets/export_logs_scheduler.png)

1. 追加 **[!UICONTROL Incremental query]** アクティビティを作成し、必要なログが選択されるように設定します。 例えば、新しいブロードログまたは更新されたブロードログをすべて選択するには(プロファイル配信ログ):

   * 「 **[!UICONTROL Properties]** 」タブで、ターゲットリソースを **配信ログ** (broadLogRcp)に変更します。

      ![](assets/export_logs_query_properties.png)

   * 「 **[!UICONTROL Target]** 」タブで、2016以降に送信された配信に対応するすべての配信ログを取得する条件を設定します。 For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * タブで、「 **[!UICONTROL Processed data]** lastModified **[!UICONTROL Use a date field]** 」フィールドを選択 **** して選択します。 ワークフローの次回の実行時には、最後の実行後に変更または作成されるログのみが取得されます。

      ![](assets/export_logs_query_processeddata.png)

      ワークフローの初回実行後は、このタブに表示される最後の実行日が次回の実行に使用されます。この日付は、ワークフローが実行されるたびに、自動的に更新されます。それでも、必要に応じて手動で別の値を入力すれば、この値を上書きすることはできます。

1. クエリーを追加行ったデータをファイルにエクスポートするアクティビティ: **[!UICONTROL Extract file]**

   * タブで、ファイルの名前を指定し **[!UICONTROL Extraction]** ます。

      この **[!UICONTROL Add date and time to the file name]** オプションを選択すると、すべての抽出ファイルが一意になるように、エクスポートの日付と共に、この名前が自動的に完了します。 ファイルに書き出す列を選択します。 配信情報やプロファイル情報などの関連リソースからのデータをここで選択できます。

      >[!NOTE]
      >
      >各ログに一意の識別子を書き出すには、 **[!UICONTROL Delivery log ID]** 要素を選択します。

      最終的なファイルを整理するために、並べ替えを適用できます。 例えば、次の例に示すように、ログ日に表示されます。

      ![](assets/export_logs_extractfile_extraction.png)

   * タブで、必要に応じて出力ファイルの形式を定義し **[!UICONTROL File structure]** ます。

      定義済みリストの値を書き出す場合は、「**[!UICONTROL Export labels instead of internal values of enumerations]**」オプションを選択します。このオプションを使用すると、ID の代わりに短くてわかりやすいラベルを取得できます。

1. 追加 **[!UICONTROL Transfer file]** アクティビティを作成し、新しく作成したファイルを、Adobe Campaignサーバーから、SFTPサーバーなど、アクセス可能な別の場所に転送するように設定します。

   * 「 **[!UICONTROL General]** 」タブで、ファイルをAdobe Campaignから別のサーバに送信す **[!UICONTROL File upload]** る目的で選択します。
   * 「 **[!UICONTROL Protocol]** 」タブで、転送パラメーターを指定し、使用する [外部アカウントを選択します](../../administration/using/external-accounts.md#creating-an-external-account) 。

1. 適切に終了し、ワークフローを追加保存するための **[!UICONTROL End]** アクティビティ。

   ![](assets/export_logs_example_workflow.png)

これで、ワークフローを実行し、外部サーバーで出力ファイルを取得できます。

**関連トピック：**

[ワークフロー](../../automating/using/get-started-workflows.md)
