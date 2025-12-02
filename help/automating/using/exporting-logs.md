---
title: ログのエクスポート
description: 配信に関連しているか購読に関連しているかに関わらず、ログデータは簡単なワークフローで書き出すことができます。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 14%

---

# ログのエクスポート{#exporting-logs}

配信に関連しているか購読に関連しているかに関わらず、ログデータは簡単なワークフローで書き出すことができます。 これにより、独自のレポートまたは BI ツールでキャンペーンの結果を分析できます。

>[!CAUTION]
>
>[ の役割と ](../../administration/using/users-management.md#functional-administrators) すべて **[!UICONTROL Administration]** ユニットへのアクセス権を持つ機能 **管理者** のみが、送信ログ、メッセージログ、トラッキングログ、除外またはサブスクリプションログにアクセスできます。 管理者以外のユーザーは、これらのログをターゲットにすることができますが、これはリンクされたテーブル（プロファイル、配信）から開始します。

ワークフローを実行するたびに新しいログのみを取得する **[!UICONTROL Incremental query]** と、出力列を定義するシンプルな **[!UICONTROL Extract file]** アクティビティを使用すると、形式と必要なすべてのデータを含んだファイルを取得できます。 次に、**[!UICONTROL Transfer file]** アクティビティを使用して、最終的なファイルを取得します。 各ワークフローの実行は、**[!UICONTROL Scheduler]** ーザーが計画します。

ログの書き出し操作は、標準ユーザーが実行できます。 broadlog、トラッキングログ、除外ログ、（プロファイル **上のサブスクリプションログやサブスクリプション履歴ログなどのプライベートリソースは** 機能管理者のみが管理できます。

1. [ この節 ](../../automating/using/building-a-workflow.md#creating-a-workflow) の説明に従って、新しいワークフローを作成します。
1. **[!UICONTROL Scheduler]** アクティビティを追加し、必要に応じて設定します。 以下は、月次実行の例です。

   ![](assets/export_logs_scheduler.png)

1. **[!UICONTROL Incremental query]** アクティビティを追加し、必要なログを選択するように設定します。 例えば、新しい broadlog または更新されたすべての broadlog （プロファイル配信ログ）を選択するには、次のようにします。

   * 「**[!UICONTROL Properties]**」タブで、ターゲットリソースを **配信ログ** （broadLogRcp）に変更します。

     ![](assets/export_logs_query_properties.png)

   * 「**[!UICONTROL Target]**」タブで、2016 年以降に送信された配信に対応するすべての配信ログを取得する条件を設定します。 詳しくは、[ クエリの編集 ](../../automating/using/editing-queries.md#creating-queries) の節を参照してください。

     ![](assets/export_logs_query_target.png)

   * 「**[!UICONTROL Processed data]**」タブで「**[!UICONTROL Use a date field]**」を選択し、「**lastModified**」フィールドを選択します。 ワークフローの次回の実行時には、最後の実行後に変更または作成されたログのみが取得されます。

     ![](assets/export_logs_query_processeddata.png)

     ワークフローの初回実行後は、このタブに表示される最後の実行日が次回の実行に使用されます。この日付は、ワークフローが実行されるたびに、自動的に更新されます。それでも、必要に応じて手動で別の値を入力すれば、この値を上書きすることはできます。

1. クエリされたデータをファイルにエクスポートする **[!UICONTROL Extract file]** アクティビティを追加します。

   * 「**[!UICONTROL Extraction]**」タブで、ファイルの名前を指定します。

     **[!UICONTROL Add date and time to the file name]** オプションを選択した場合は、抽出されたすべてのファイルが一意になるように、この名前は書き出しの日付で自動的に補完されます。 ファイルに書き出す列を選択します。 配信やプロファイル情報など、関連リソースから取得したデータを選択できます。

     >[!NOTE]
     >
     >各ログの一意の ID を書き出すには、**[!UICONTROL Delivery log ID]** 要素を選択します。

     最終的なファイルを整理するには、並べ替えを適用します。 以下の例に示すように、ログ日付の例。

     ![](assets/export_logs_extractfile_extraction.png)

   * 「**[!UICONTROL File structure]**」タブで、必要に応じて出力ファイルの形式を定義します。

     定義済みリストの値をエクスポートする場合は、「**[!UICONTROL Export labels instead of internal values of enumerations]**」オプションを選択します。このオプションを使用すると、ID の代わりに短くてわかりやすいラベルを取得できます。

1. **[!UICONTROL Transfer file]** アクティビティを追加し、新しく作成したファイルをAdobe Campaign サーバーから、アクセスできる別の場所（SFTP サーバーなど）に転送するように設定します。

   * Adobe Campaignから別のサーバーにファイルを送信する目的で、「**[!UICONTROL General]**」タブで「**[!UICONTROL File upload]**」を選択します。
   * 「**[!UICONTROL Protocol]**」タブで、転送パラメーターを指定し、使用する [ 外部アカウント ](../../administration/using/external-accounts.md#creating-an-external-account) を選択します。

1. **[!UICONTROL End]** アクティビティを追加し、適切に終了していることを確認して、ワークフローを保存します。

   ![](assets/export_logs_example_workflow.png)

これで、ワークフローを実行して、外部サーバーの出力ファイルを取得できるようになりました。

**関連トピック：**

[ワークフロー](../../automating/using/get-started-workflows.md)
