---
title: ログのエクスポート
description: ログデータは、配信に関連するデータか、購読に関連するデータかに関わらず、シンプルなワークフローで書き出すことができます。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 14%

---

# ログのエクスポート{#exporting-logs}

ログデータは、配信に関連するデータか、購読に関連するデータかに関わらず、シンプルなワークフローで書き出すことができます。 これにより、独自のレポートまたは BI ツールでキャンペーンの結果を分析できます。

>[!CAUTION]
>
>機能のみ [管理者](../../administration/using/users-management.md#functional-administrators)、を **[!UICONTROL Administration]** 役割とアクセス権 **すべて** ユニットは、送信ログ、メッセージログ、トラッキングログ、除外ログ、購読ログにアクセスできます。 管理者以外のユーザーは、リンクされたテーブル（プロファイル、配信）から開始しながら、これらのログをターゲットにすることができます。

次を使用： **[!UICONTROL Incremental query]** ワークフローが実行されるたびに新しいログのみを取得し、 **[!UICONTROL Extract file]** 「 」アクティビティを使用して、出力列を定義し、必要な形式とすべてのデータを含んだファイルを取得できます。 その後、 **[!UICONTROL Transfer file]** 「 」アクティビティを使用して、最終ファイルを取得します。 各ワークフローの実行は、 **[!UICONTROL Scheduler]**.

書き出しログの操作は、標準のユーザーが実行できます。 次のプライベートリソース（broadlog、トラッキングログ、除外ログの購読ログ、購読履歴ログなど）。 **プロファイル** は、機能管理者のみが管理できます。

1. 新しいワークフローを作成します。詳しくは、 [この節](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. を追加します。 **[!UICONTROL Scheduler]** アクティビティを作成し、必要に応じて設定します。 次に、月別の実行の例を示します。

   ![](assets/export_logs_scheduler.png)

1. を追加します。 **[!UICONTROL Incremental query]** アクティビティを開き、必要なログが選択されるように設定します。 例えば、新規または更新されたすべての broadlog（プロファイル配信ログ）を選択するには、次のようにします。

   * Adobe Analytics の **[!UICONTROL Properties]** タブで、ターゲットリソースを次に変更します。 **配信ログ** (broadLogRcp) を呼び出します。

     ![](assets/export_logs_query_properties.png)

   * Adobe Analytics の **[!UICONTROL Target]** 「 」タブで、2016 年以降に送信された配信に対応するすべての配信ログを取得する条件を設定します。 詳しくは、 [クエリの編集](../../automating/using/editing-queries.md#creating-queries) 」セクションに入力します。

     ![](assets/export_logs_query_target.png)

   * Adobe Analytics の **[!UICONTROL Processed data]** タブ、選択 **[!UICONTROL Use a date field]** を選択し、 **lastModified** フィールドに入力します。 ワークフローの次回の実行時には、最後の実行後に変更または作成されたログのみが取得されます。

     ![](assets/export_logs_query_processeddata.png)

     ワークフローの初回実行後は、このタブに表示される最後の実行日が次回の実行に使用されます。この日付は、ワークフローが実行されるたびに、自動的に更新されます。それでも、必要に応じて手動で別の値を入力すれば、この値を上書きすることはできます。

1. を追加します。 **[!UICONTROL Extract file]** クエリされたデータをファイルにエクスポートするアクティビティ：

   * Adobe Analytics の **[!UICONTROL Extraction]** 「 」タブで、ファイルの名前を指定します。

     次を選択した場合、 **[!UICONTROL Add date and time to the file name]** 」オプションを選択すると、書き出し日付と共にこの名前が自動的に入力され、抽出されたすべてのファイルが一意になります。 ファイルにエクスポートする列を選択します。 配信やプロファイル情報などの関連リソースから取得したデータをここで選択できます。

     >[!NOTE]
     >
     >各ログの一意の ID を書き出すには、 **[!UICONTROL Delivery log ID]** 要素を選択します。

     最終的なファイルを整理するには、並べ替えを適用します。 例えば、ログ日付は、次の例のようになります。

     ![](assets/export_logs_extractfile_extraction.png)

   * Adobe Analytics の **[!UICONTROL File structure]** 「 」タブで、必要に応じて出力ファイルの形式を定義します。

     定義済みリストの値を書き出す場合は、「**[!UICONTROL Export labels instead of internal values of enumerations]**」オプションを選択します。このオプションを使用すると、ID の代わりに短くてわかりやすいラベルを取得できます。

1. を追加します。 **[!UICONTROL Transfer file]** 「 」アクティビティを開き、新しく作成したファイルをAdobe Campaignサーバーから別の場所（SFTP サーバーなど）に転送するように設定します。

   * Adobe Analytics の **[!UICONTROL General]** タブ、選択 **[!UICONTROL File upload]** は、ファイルをAdobe Campaignから別のサーバーに送信するためのものです。
   * Adobe Analytics の **[!UICONTROL Protocol]** 」タブで、転送パラメーターを指定し、 [外部アカウント](../../administration/using/external-accounts.md#creating-an-external-account) を使用します。

1. を追加します。 **[!UICONTROL End]** 「 」アクティビティを使用して、ワークフローが正しく終了することを確認し、ワークフローを保存します。

   ![](assets/export_logs_example_workflow.png)

これで、ワークフローを実行し、外部サーバーで出力ファイルを取得できるようになりました。

**関連トピック：**

[ワークフロー](../../automating/using/get-started-workflows.md)
