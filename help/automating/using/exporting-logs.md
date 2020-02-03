---
title: ログの書き出し
description: ログデータは、配信に関連するか購読に関連するかに関わらず、単純なワークフローを使用してエクスポートできます。
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
source-git-commit: 5ec3497161e89bad4d2ef1ef8a80a87df69860b6

---


# ログの書き出し{#exporting-logs}

ログデータは、配信に関連するか購読に関連するかに関わらず、単純なワークフローを使用してエクスポートできます。 これにより、独自のレポートまたはBIツールでキャンペーンの結果を分析できます。

ワークフローを **[!UICONTROL Incremental query]****[!UICONTROL Extract file]** 実行するたびに新しいログのみを取得するアクティビティと、出力列を定義する単純なアクティビティを使用すると、必要な形式とすべてのデータを含むファイルを取得できます。 次に、アクティビテ **[!UICONTROL Transfer file]**ィを使用して最終ファイルを取得します。 各ワークフローの実行は、によって計画されま**[!UICONTROL Scheduler]**&#x200B;す。

エクスポートログ操作は、標準ユーザーが実行できます。 次のようなプライベートリソース：プロファイルのブロードログ、追跡ログ、除外ログ、購読ログ、購読履歴ログは **** 、機能管理者のみが管理できます。

1. この節で説明するように、新しいワークフロー [を作成します](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. アクティビティ **[!UICONTROL Scheduler]**を追加し、必要に応じて設定します。 月別の実行例を次に示します。

   ![](assets/export_logs_scheduler.png)

1. アクティビティ **[!UICONTROL Incremental query]**を追加し、必要なログが選択されるように設定します。 例えば、新規または更新されたすべてのブロードログ（プロファイル配信ログ）を選択するには、次の手順に従います。

   * タブで、タ **[!UICONTROL Properties]**ーゲットリソースを「** Delivery logs **(broadLogRcp)」に変更します。

      ![](assets/export_logs_query_properties.png)

   * タブで、 **[!UICONTROL Target]**2016年以降に送信された配信に対応するすべての配信ログを取得する条件を設定します。 For more information, refer to the[Editing queries](../../automating/using/editing-queries.md#creating-queries)section.

      ![](assets/export_logs_query_target.png)

   * タブで、「 **[!UICONTROL Processed data]**lastModified」フィー**[!UICONTROL Use a date field]** ルドを選択 **します** 。 ワークフローの次回の実行時には、最後の実行後に変更または作成されたログのみが取得されます。

      ![](assets/export_logs_query_processeddata.png)

      ワークフローの最初の実行後、このタブには、次の実行に使用される最後の実行日が表示されます。 ワークフローが実行されるたびに、自動的に更新されます。 新しい値を手動で入力して、必要に応じて上書きすることもできます。

1. クエリーされたデ **[!UICONTROL Extract file]**ータをファイルにエクスポートするアクティビティを追加します。

   * タブで、 **[!UICONTROL Extraction]**ファイルの名前を指定します。

      このオプションを選 **[!UICONTROL Add date and time to the file name]**択すると、すべての抽出されたファイルが一意になるように、この名前が書き出し日付と共に自動的に完成します。 ファイルに書き出す列を選択します。 配信やプロファイル情報など、関連するリソースからのデータをここで選択できます。

      >[!NOTE]
      >
      >各ログの一意の識別子を書き出すには、要素を選択し **[!UICONTROL Delivery log ID]**ます。

      最終ファイルを整理するには、並べ替えを適用します。 例えば、次の例に示すように、ログ日付に関する情報です。

      ![](assets/export_logs_extractfile_extraction.png)

   * タブで、 **[!UICONTROL File structure]**必要に応じて出力ファイルの形式を定義します。

      列挙値をエクス **[!UICONTROL Export labels instead of internal values of enumerations]**ポートする場合は、このオプションを選択します。 このオプションを使用すると、IDの代わりに理解しやすい短いラベルを取得できます。

1. アクティビティ **[!UICONTROL Transfer file]**を追加し、新しく作成したファイルをAdobe Campaignサーバーから、SFTPサーバーなど、アクセス可能な別の場所に転送するように設定します。

   * タブで、 **[!UICONTROL General]**ファイルをAdobe Campaign**[!UICONTROL File upload]** から別のサーバーに送信する目的として選択します。
   * タブで、転 **[!UICONTROL Protocol]**送パラメーターを指定し、使用する外部アカ[ウント](../../administration/using/external-accounts.md#creating-an-external-account)を選択します。

1. アクティビティ **[!UICONTROL End]**を追加して、適切に終了することを確認し、ワークフローを保存します。

   ![](assets/export_logs_example_workflow.png)

これで、ワークフローを実行し、外部サーバー上の出力ファイルを取得できます。

**関連トピック：**

[ワークフロー](../../automating/using/discovering-workflows.md)
