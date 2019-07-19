---
title: ログの書き出し
seo-title: ログの書き出し
description: ログの書き出し
seo-description: 配信に関連するデータ（配信に関連するか購読に関連するか）は、単純なワークフローでエクスポートできます。
page-status-flag: 常にアクティブ化されていない
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: importing- and- exporting- data
discoiquuid: ca8a95d8-523f-4085- a2fc- e1d8262cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting logs{#exporting-logs}

配信に関連するデータ（配信に関連するか購読に関連するか）は、単純なワークフローでエクスポートできます。これにより、独自のレポートまたはBIツールでキャンペーンの結果を分析できます。

By using an **[!UICONTROL Incremental query]** that only retrieves new logs every time the workflow is executed and a simple **[!UICONTROL Extract file]** activity to define the output columns, you can get a file with the format and all the data you need. Then use a **[!UICONTROL Transfer file]** activity to retrieve the final file. Each workflow execution is planned by a **[!UICONTROL Scheduler]**.

エクスポートログ操作は、標準ユーザーによって実行できます。Private resources such as: broadlogs, tracking logs, exclusion logs subscription logs and subscription history logs on **Profiles** can only be managed by functional administrator.

1. Create a new workflow as detailed in [this section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. **[!UICONTROL Scheduler]** アクティビティを追加し、必要に応じて設定します。月別実行の例を以下に示します。

   ![](assets/export_logs_scheduler.png)

1. **[!UICONTROL Incremental query]** アクティビティを追加し、必要なログを選択するように設定します。例えば、新しいまたは更新されたすべてのログ（プロファイル配信ログ）を選択するには:

   * **[!UICONTROL Properties]** タブで、ターゲットリソースを **Delivery logs** （BroadlogRcp）に変更します。

      ![](assets/export_logs_query_properties.png)

   * **[!UICONTROL Target]** タブで、2016年以降の配信に対応する配信に対応するすべての配信ログを取得する条件を設定します。For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * **[!UICONTROL Processed data]** タブで **[!UICONTROL Use a date field]****、"lastModified** 」フィールドを選択して選択します。ワークフローの次回の実行時に、前回の実行後に変更または作成されたログのみが取得されます。

      ![](assets/export_logs_query_processeddata.png)

      ワークフローの最初の実行後、次の実行時に使用される最後の実行日がこのタブに表示されます。ワークフローが実行されるたびに自動的に更新されます。必要に応じて新しい入力を手動で入力することで、この値を上書きできます。

1. Add an **[!UICONTROL Extract file]** activity that will export the queried data in a file:

   * **[!UICONTROL Extraction]** タブで、ファイルの名前を指定します。この名前は、エクスポート日によって自動的に完了し、抽出されたすべてのファイルが一意になります。

      ファイルでエクスポートする列を選択します。配信またはプロファイル情報などの関連リソースから取得したデータをここから選択できます。最終的なファイルを整理するには、並べ替えを適用します。例えば、次の例のように、ログ日付を指定します。

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >ログリソースの一意の識別子（プライマリキー）を書き出すことはできません。

   * **[!UICONTROL File structure]** タブで、必要に応じて出力ファイルの形式を定義します。

      Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. このオプションを使用すると、IDの代わりに理解しやすい短いラベルを取得できます。

1. **[!UICONTROL Transfer file]** アクティビティを追加し、新しく作成したファイルをAdobe Campaignサーバーからアクセスできる別の場所（SFTPサーバーなど）に転送するよう設定します。

   * **[!UICONTROL General]** タブでは、目的 **[!UICONTROL File upload]** のファイルを選択して、Adobe Campaignから別のサーバーにファイルを送信します。
   * **[!UICONTROL Protocol]** タブで、トランスファーパラメーターを指定し、使用する [外部アカウント](../../administration/using/external-accounts.md#creating-an-external-account) を選択します。

1. **[!UICONTROL End]** アクティビティを追加して、適切に終了してワークフローを保存するようにします。

   ![](assets/export_logs_example_workflow.png)

これで、ワークフローを実行し、外部サーバー上の出力ファイルを取得できます。

**関連トピック:**

[ワークフロー](../../automating/using/discovering-workflows.md)
