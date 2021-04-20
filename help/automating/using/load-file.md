---
solution: Campaign Standard
product: campaign
title: ファイル読み込み
description: 「ファイル読み込み」アクティビティを使用すると、1 つの構造化されたフォームにデータをインポートして、Adobe Campaign で使用することができます。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1368'
ht-degree: 93%

---


# ファイル読み込み {#load-file}

## 説明 {#description}

>[!CAUTION]
>
>この機能を使用する際は、Adobe Campaign契約に従って、SFTPストレージ、DBストレージ、およびアクティブなプロファイルの制限に留意してください。

![](assets/data_loading.png)

「**[!UICONTROL Load file]**」アクティビティを使用すると、1 つの構造化されたフォームにデータをインポートして、Adobe Campaign で使用することができます。データは一時的にインポートされます。このデータを Adobe Campaign データベースに確実に統合するには別のアクティビティが必要です。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティの設定時に定義されます。読み込むファイルとしては、例えば連絡先のリストなどがあります。

次の操作をおこなうことができます。

* ファイル構造を使用して、別のファイルのデータ（「**[!UICONTROL Transfer file]**」アクティビティを使用して回復したもの）に適用するか、
* ファイルの構造とデータを使用して、Adobe Campaign にインポートします。

>[!IMPORTANT]
>
>.txt、.csv などの「フラット」な構造のファイルのみが対象となります。

**関連トピック：**

* [使用例：外部データを使用したデータベースの更新](../../automating/using/update-database-file.md)
* [使用例：ファイルの自動ダウンロードに基づくデータの更新](../../automating/using/update-data-automatic-download.md)
* [使用例：強化されたフィールドを含む電子メールの送信](../../automating/using/sending-email-enriched-fields.md)
* [使用例：ファイルオーディエンスとデータベースとの調整](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

アクティビティの設定には、2 つの手順があります。まず、サンプルファイルをアップロードして、目的のファイル構造を定義する必要があります。この処理が完了したら、データをインポートするファイルのインポート元を指定します。

>[!NOTE]
>
>サンプルファイルのデータはアクティビティの設定に使用されますが、インポートされません。データの少ないサンプルファイルを使用することをお勧めします。

1. ワークフローに「**[!UICONTROL Load file]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 最終的なファイルのインポート時に、目的の構造を定義するためのサンプルファイルをアップロードします。

   ![](assets/wkf_file_loading.png)

   データファイルがアップロードされると、「**[!UICONTROL File structure]**」と「**[!UICONTROL Column definition]**」の 2 つの新しいタブがアクティビティに表示されます。

1. 「**[!UICONTROL File structure]**」タブに移動して、サンプルファイルから自動的に検出される構造を表示します。

   ファイル構造が正しく検出されなかった場合は、次のいくつかの方法でエラーを修正できます。

   * 別のファイルの構造を使用する場合は、「**[!UICONTROL Detect structure from a new file]**」オプションを選択します。
   * ファイルに合うように、デフォルトの検出パラメータを変更することができます。「**[!UICONTROL File type]**」フィールドでは、インポートするファイルが固定長の列で構成されているかどうかを指定します。その場合は、「**[!UICONTROL Column definition]**」タブで各列の最大文字数も指定する必要があります。

      ファイルからデータを正しく回復するために必要なすべての検出オプションは、「**[!UICONTROL File format]**」に再グループ化されています。これらのオプションを変更してから、新しい設定を適用すると、アクティビティに最後に読み込まれたファイルの構造が再検出されます。これをおこなうには、「**[!UICONTROL Apply configuration]**」ボタンを使用します。例えば、別の列区切り文字を指定できます。

      >[!NOTE]
      >
      >この操作では、アクティビティに最後に読み込まれたファイルが適用されます。検出されたファイルのサイズが大きい場合、データプレビューには最初の 30 行だけが表示されます。

      ![](assets/wkf_file_loading3.png)

      「**[!UICONTROL File format]**」セクションの「**[!UICONTROL Check columns from file against column definitions]**」オプションを使用すると、アップロードするファイルの列が列定義に対応していることを確認できます。

      列の数や名前が列の定義と一致しない場合は、ワークフローの実行時にエラーメッセージが表示されます。このオプションが有効になっていない場合は、ログファイルに警告が表示されます。

      ![](assets/wkf_file_loading_check.png)

1. 「**[!UICONTROL Column definition]**」タブに移動して各列のデータ形式をチェックし、必要に応じてパラメータを調整します。

   「**[!UICONTROL Column definition]**」タブでは、各列のデータ構造を正確に指定することにより、エラーがないデータを（null 管理を使用するなどの方法で）インポートし、将来使用できるように Adobe Campaign データベースに既に存在するタイプと一致していることを確認します。

   例えば、列のラベルを変更し、そのタイプ（文字列、整数、日付など）を選択したり、エラー処理を指定することもできます。

   詳しくは、[列のフォーマット](#column-format)の節を参照してください。

   ![](assets/wkf_file_loading4.png)

1. 「**[!UICONTROL Execution]**」タブで、ファイルをデータの読み込み用に処理するかどうかを指定します。

   * ワークフローの受信トランジションから取得されます。
   * 前の手順でアップロードしたものです。
   * ローカルマシンからアップロードする新しいファイルです。「**[!UICONTROL Upload a new file from local machine]**」オプションは、最初のファイルアップロードが既にワークフローで定義されている場合に表示されます。これにより、現在のファイルがニーズに合わない場合は、別のファイルをアップロードして処理できます。

      ![](assets/wkf_file_loading1.png)

1. データの読み込み元のファイルが圧縮されて GZIP ファイル（.gz）になっている場合は、「**[!UICONTROL Add a pre-processing stage]**」フィールドで「**[!UICONTROL Decompression]**」オプションを選択します。これにより、データを読み込む前にファイルを解凍できます。このオプションは、ファイルがアクティビティの受信トランジションから送信されている場合にのみ使用できます。

   **[!UICONTROL Add a pre-processing stage]**&#x200B;フィールドでは、ファイルをデータベースにインポートする前に、ファイルを復号化することもできます。 暗号化されたファイルの使い方について詳しくは、[この](../../automating/using/managing-encrypted-data.md)を参照してください。

1. 「**[!UICONTROL Keep the rejects in a file]**」オプションを使用すると、インポート中に発生したエラーが含まれるファイルをダウンロードし、後処理段階でそのファイルに適用することができます。このオプションを有効にすると、送信トランジションの名前が「却下」に変更されます。

   >[!NOTE]
   >
   >「**[!UICONTROL Add date and time to the file name]**」オプションを使用すると、タイムスタンプを、却下の情報が含まれるファイルの名前に追加できます。

   ![](assets/wkf_file_loading_keeprejects.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

ワークフローの実行後にアクティビティでエラーが発生した場合は、ログを参照して、ファイル内の誤った値の詳細を確認します。ワークフローのログについて詳しくは、[この節](../../automating/using/monitoring-workflow-execution.md)を参照してください。

## 列の形式 {#column-format}

サンプルファイルを読み込む際に、各データタイプのデフォルトのパラメーターを使用して列の形式が自動的に検出されます。このデフォルトのパラメーターを編集して（特に誤りや空の値がある場合）、特定の処理を指定してデータに適用することができます。

これをおこなうには、形式を定義する列のクイックアクションから「**[!UICONTROL Edit properties]**」オプションを選択します。列形式の詳細ウィンドウが表示されます。

![](assets/wkf_file_loading4.png)

その後、各列の形式設定を変更できます。

列の形式設定では、各列の値の処理方法を定義できます。

* **[!UICONTROL Ignore column]**：データの読み込み時の処理で、この列をスキップします。
* **[!UICONTROL Data type]**：各列に適用されるデータタイプを指定します。
* **[!UICONTROL Format and separators]**、**プロパティ**：テキスト、時間、日付、数値の形式のプロパティ、および列コンテキストで指定される区切り文字を指定します。

   * **[!UICONTROL Maximum number of characters]**：文字列タイプの列の最大文字数を指定します。

      固定長の列で構成されるファイルを読み込む場合は、このフィールドを入力する必要があります。

   * **[!UICONTROL Letter case management]**：**テキスト**&#x200B;データに文字ケース処理を適用する必要があるかどうかを定義します。
   * **[!UICONTROL White space management]**：**テキスト**&#x200B;データの文字列で特定のスペースを無視する必要があるかどうかを指定します。
   * **[!UICONTROL Time format]**、**[!UICONTROL Date format]**：**日付**、**時間**、**日時**&#x200B;の各データの形式を指定します。
   * **[!UICONTROL Format]**：**整数**&#x200B;および&#x200B;**浮動小数点数**&#x200B;データの数値の形式を定義します。
   * **[!UICONTROL Separator]**：**日付**、**時間**、**日時**、**整数**、**浮動小数点**&#x200B;の各データについて、列コンテキストで指定される区切り文字（数値の場合は桁区切り文字や小数点、日付と時間の場合は区切り文字）を定義します。

* **[!UICONTROL Remapping of values]**：このフィールドは、列の詳細設定でのみ使用できます。この設定により、特定の値をインポート時に変換できます。例えば、「three」を「3」に変換できます。
* **[!UICONTROL Error processing]**：エラーが発生した場合の処理を定義します。

   * **[!UICONTROL Ignore the value]**：値は無視されます。ワークフローの実行ログに警告が生成されます。
   * **[!UICONTROL Reject the line]**：行全体が処理されなくなります。
   * **[!UICONTROL Use a default value]**：エラーの原因となる値を、「**[!UICONTROL Default value]**」フィールドで定義されているデフォルト値に置き換えます。
   * **[!UICONTROL Use a default value in case the value is not remapped]**：エラーの原因となる値を、「**[!UICONTROL Default value]**」フィールドで定義されているデフォルト値に置き換えます。ただし、エラー値についてマッピングが定義されている場合は除きます（前述の「**[!UICONTROL Remapping of values]**」オプションを参照）。
   * **[!UICONTROL Reject the line when there is no remapping value]**：行全体が処理されなくなります。ただし、エラー値についてマッピングが定義されている場合は除きます（前述の「**[!UICONTROL Remapping of values]**」オプションを参照）。

   >[!NOTE]
   >
   >「**[!UICONTROL Error processing]**」で対象となるのは、インポートしたファイルの値に関するエラーです。例えば、異常なデータタイプ（「整数」タイプの列で英字の「four」が入力されている）、許可された最大文字数より多い文字を含む文字列、区切り文字の不具合のある日付などです。一方、このオプションでは、空の値の管理によって生成されるエラーは対象となりません。

* **[!UICONTROL Default value]**：選択したエラーの処理方法に応じてデフォルトの値を選択します。
* **[!UICONTROL Empty value management]**：データの読み込み中に空の値を管理する方法を指定します。

   * **[!UICONTROL Generate an error for numerical fields]**：数値フィールドのみエラーを生成します。それ以外は、null 値を挿入します。
   * **[!UICONTROL Insert NULL in the corresponding field]**: 空の値を許可します。したがって、null 値が挿入されます。
   * **[!UICONTROL Generate an error]**：値が空の場合に、エラーを生成します。
