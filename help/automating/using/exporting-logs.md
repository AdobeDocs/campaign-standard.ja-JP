---
solution: Campaign Standard
product: campaign
title: ログの書き出し
description: ログデータは、配信と購読のどちらに関連するものであっても、単純なワークフローを通してエクスポートできます。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: ワークフロー
role: Data Architect
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 14%

---


# ログの書き出し{#exporting-logs}

ログデータは、配信と購読のどちらに関連するものであっても、単純なワークフローを通してエクスポートできます。 独自のレポートまたはBIツールでキャンペーンの結果を分析できます。

>[!CAUTION]
>
>**[!UICONTROL Administration]**&#x200B;役割と&#x200B;****&#x200B;へのアクセス権を持つ機能的な[管理者](../../administration/using/users-management.md#functional-administrators)のみが、送信ログ、メッセージログ、トラッキングログ、除外、または購読ログにアクセスできます。 管理者以外のユーザーは、これらのログにターゲットできますが、リンクされたテーブル(プロファイル、配信)から開始できます。

ワークフローが実行されるたびに新しいログを取得する&#x200B;**[!UICONTROL Incremental query]**&#x200B;と、出力列を定義する単純な&#x200B;**[!UICONTROL Extract file]**&#x200B;アクティビティを使用すると、必要な形式とすべてのデータを持つファイルを取得できます。 次に、**[!UICONTROL Transfer file]**&#x200B;アクティビティを使用して最終ファイルを取得します。 各ワークフローの実行は&#x200B;**[!UICONTROL Scheduler]**&#x200B;によって計画されます。

エクスポートログ操作は、標準ユーザーが実行できます。 次のようなプライベートリソース。ブロードログ、トラッキングログ、除外ログの購読ログ、および&#x200B;**プロファイル**&#x200B;の購読履歴ログは、機能管理者のみが管理できます。

1. [このセクション](../../automating/using/building-a-workflow.md#creating-a-workflow)で詳しく説明するように、新しいワークフローを作成します。
1. &lt;追加a0/>アクティビティを作成し、必要に応じて設定します。 **[!UICONTROL Scheduler]**&#x200B;月別の実行例を以下に示します。

   ![](assets/export_logs_scheduler.png)

1. 追加&#x200B;**[!UICONTROL Incremental query]**&#x200B;アクティビティを設定し、必要なログが選択されるようにします。 例えば、新しいブロードログまたは更新されたブロードログをすべて選択するには(プロファイル配信ログ):

   * 「**[!UICONTROL Properties]**」タブで、ターゲットリソースを&#x200B;**配信ログ**(broadLogRcp)に変更します。

      ![](assets/export_logs_query_properties.png)

   * 「**[!UICONTROL Target]**」タブで、2016以降に送信された配信に対応するすべての配信ログを取得する条件を設定します。 詳しくは、「[クエリの編集](../../automating/using/editing-queries.md#creating-queries)」を参照してください。

      ![](assets/export_logs_query_target.png)

   * 「**[!UICONTROL Processed data]**」タブで「**[!UICONTROL Use a date field]**」を選択し、「**lastModified**」フィールドを選択します。 ワークフローの次回の実行時には、最後の実行後に変更または作成されるログのみが取得されます。

      ![](assets/export_logs_query_processeddata.png)

      ワークフローの初回実行後は、このタブに表示される最後の実行日が次回の実行に使用されます。この日付は、ワークフローが実行されるたびに、自動的に更新されます。それでも、必要に応じて手動で別の値を入力すれば、この値を上書きすることはできます。

1. ファイル追加内のクエリーされたデータをエクスポートする&#x200B;**[!UICONTROL Extract file]**&#x200B;アクティビティ:

   * 「**[!UICONTROL Extraction]**」タブで、ファイルの名前を指定します。

      **[!UICONTROL Add date and time to the file name]**&#x200B;オプションを選択すると、この名前はエクスポートの日付と共に自動的に完了し、すべての抽出されたファイルが一意になります。 ファイルに書き出す列を選択します。 配信情報やプロファイル情報などの関連リソースからのデータをここで選択できます。

      >[!NOTE]
      >
      >各ログに一意の識別子を書き出すには、**[!UICONTROL Delivery log ID]**&#x200B;要素を選択します。

      最終的なファイルを整理するために、並べ替えを適用できます。 例えば、次の例に示すように、ログ日に表示されます。

      ![](assets/export_logs_extractfile_extraction.png)

   * **[!UICONTROL File structure]**&#x200B;タブで、必要に応じて出力ファイルの形式を定義します。

      定義済みリストの値を書き出す場合は、「**[!UICONTROL Export labels instead of internal values of enumerations]**」オプションを選択します。このオプションを使用すると、ID の代わりに短くてわかりやすいラベルを取得できます。

1. &lt;追加a0/>アクティビティを設定し、新しく作成したファイルをAdobe Campaignサーバーから、SFTPサーバーなど、アクセス可能な別の場所に転送するように設定します。**[!UICONTROL Transfer file]**

   * 「**[!UICONTROL General]**」タブで、「**[!UICONTROL File upload]**」を選択します。これは、ファイルをAdobe Campaignから別のサーバーに送信するためのものです。
   * 「**[!UICONTROL Protocol]**」タブで、転送パラメーターを指定し、使用する[外部アカウント](../../administration/using/external-accounts.md#creating-an-external-account)を選択します。

1. &lt;a0追加/>アクティビティを追加し、適切に終了してワークフローを保存するようにします。**[!UICONTROL End]**

   ![](assets/export_logs_example_workflow.png)

これで、ワークフローを実行し、外部サーバーで出力ファイルを取得できます。

**関連トピック：**

[ワークフロー](../../automating/using/get-started-workflows.md)
