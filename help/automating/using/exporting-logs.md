---
title: ログのエクスポート
description: ログデータは、配信と購読のどちらに関連しているかに関わらず、シンプルなワークフローを通じてエクスポートできます。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---

# ログのエクスポート{#exporting-logs}

ログデータは、配信と購読のどちらに関連しているかに関わらず、シンプルなワークフローを通じてエクスポートできます。 これにより、独自のレポートまたはBIツールでキャンペーンの結果を分析できます。

>[!CAUTION]
>
>**[!UICONTROL Administration]**&#x200B;の役割と&#x200B;**へのアクセス権を持つ機能[管理者](../../administration/using/users-management.md#functional-administrators)のみが、送信ログ、メッセージログ、トラッキングログ、除外ログ、サブスクリプションログにアクセスできます。**&#x200B;管理者以外のユーザーは、これらのログをターゲットに設定できますが、リンクされたテーブル（プロファイル、配信）から始めることができます。

ワークフローが実行されるたびに新しいログのみを取得する&#x200B;**[!UICONTROL Incremental query]**&#x200B;と、出力列を定義する単純な&#x200B;**[!UICONTROL Extract file]**&#x200B;アクティビティを使用することで、必要な形式とすべてのデータを含むファイルを取得できます。 次に、 **[!UICONTROL Transfer file]**&#x200B;アクティビティを使用して最終ファイルを取得します。 各ワークフローの実行は、**[!UICONTROL Scheduler]**&#x200B;によって計画されます。

ログの書き出し操作は、標準ユーザーが実行できます。 次のようなプライベートリソース&#x200B;**プロファイル**&#x200B;のbroadlog、トラッキングログ、除外ログ、購読履歴ログは、機能管理者のみが管理できます。

1. [この節](../../automating/using/building-a-workflow.md#creating-a-workflow)で説明されているように、新しいワークフローを作成します。
1. **[!UICONTROL Scheduler]**&#x200B;アクティビティを追加し、必要に応じて設定します。 次に、月別の実行例を示します。

   ![](assets/export_logs_scheduler.png)

1. **[!UICONTROL Incremental query]**&#x200B;アクティビティを追加し、必要なログが選択されるように設定します。 例えば、新規または更新されたすべてのbroadlog（プロファイル配信ログ）を選択するには、次のようにします。

   * 「**[!UICONTROL Properties]**」タブで、ターゲットリソースを「**配信ログ**」(broadLogRcp)に変更します。

      ![](assets/export_logs_query_properties.png)

   * 「**[!UICONTROL Target]**」タブで、2016年以降に送信された配信に対応するすべての配信ログを取得する条件を設定します。 詳しくは、[クエリの編集](../../automating/using/editing-queries.md#creating-queries)の節を参照してください。

      ![](assets/export_logs_query_target.png)

   * 「**[!UICONTROL Processed data]**」タブで「**[!UICONTROL Use a date field]**」を選択し、「**lastModified**」フィールドを選択します。 ワークフローの次回の実行時には、最後の実行後に変更または作成されたログのみが取得されます。

      ![](assets/export_logs_query_processeddata.png)

      ワークフローの初回実行後は、このタブに表示される最後の実行日が次回の実行に使用されます。この日付は、ワークフローが実行されるたびに、自動的に更新されます。それでも、必要に応じて手動で別の値を入力すれば、この値を上書きすることはできます。

1. クエリされたデータをファイルにエクスポートする&#x200B;**[!UICONTROL Extract file]**&#x200B;アクティビティを追加します。

   * 「**[!UICONTROL Extraction]**」タブで、ファイルの名前を指定します。

      **[!UICONTROL Add date and time to the file name]**&#x200B;オプションを選択した場合、抽出したすべてのファイルが一意になるように、エクスポート日付と共にこの名前が自動的に入力されます。 ファイルにエクスポートする列を選択します。 配信やプロファイル情報などの関連リソースから得られるデータをここで選択できます。

      >[!NOTE]
      >
      >各ログの一意の識別子を書き出すには、**[!UICONTROL Delivery log ID]**&#x200B;要素を選択します。

      最終的なファイルを整理するには、並べ替えを適用します。 例えば、ログ日に、次の例のように表示されます。

      ![](assets/export_logs_extractfile_extraction.png)

   * 「**[!UICONTROL File structure]**」タブで、必要に応じて出力ファイルの形式を定義します。

      定義済みリストの値を書き出す場合は、「**[!UICONTROL Export labels instead of internal values of enumerations]**」オプションを選択します。このオプションを使用すると、ID の代わりに短くてわかりやすいラベルを取得できます。

1. **[!UICONTROL Transfer file]**&#x200B;アクティビティを追加し、新しく作成したファイルをAdobe Campaignサーバーから、SFTPサーバーなど、新しくアクセスできる別の場所に転送するように設定します。

   * 「**[!UICONTROL General]**」タブで、「**[!UICONTROL File upload]**」を選択します。この目的は、Adobe Campaignから別のサーバーにファイルを送信することです。
   * 「**[!UICONTROL Protocol]**」タブで転送パラメーターを指定し、使用する[外部アカウント](../../administration/using/external-accounts.md#creating-an-external-account)を選択します。

1. **[!UICONTROL End]**&#x200B;アクティビティを追加して、適切に終了するようにし、ワークフローを保存します。

   ![](assets/export_logs_example_workflow.png)

これで、ワークフローを実行し、外部サーバーで出力ファイルを取得できます。

**関連トピック：**

[ワークフロー](../../automating/using/get-started-workflows.md)
