---
title: ロードファイル
seo-title: ロードファイル
description: ロードファイル
seo-description: ロードファイルアクティビティでは、1つの構造化フォームでデータをインポートして、このデータをAdobe Campaignで使用できます。
page-status-flag: 決して活性化されていない
uuid: 69af12cc-6f82-4977-9f53- aa7bc26f5e7e
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: データ管理活動
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: ファイルインポート、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc3c687328c5a460b442b8b2497965ccab3be50b

---


# ロードファイル{#load-file}

## 説明 {#description}

![](assets/data_loading.png)

**[!UICONTROL Load file]** このアクティビティでは、1つの構造化フォームでデータをインポートして、このデータをAdobe Campaignで使用できます。データは一時的にインポートされ、Adobe Campaignデータベースに定義するために別のアクティビティが必要になります。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティの構成時に定義されます。ロードするファイルは、たとえば、連絡先のリストです。

>[!CAUTION]
>
>たとえば、.txt、. csvなどのファイルのように、「フラット」構造ファイルのみが考慮されます。

次のことができます。

* ファイル構造を使用して、別のファイルのデータ（ **[!UICONTROL Transfer file]** アクティビティを使用してリカバリ）に適用するか、
* ファイルの構造とデータを使用して、Adobe Campaignにインポートします。

## 構成 {#configuration}

アクティビティ構成には2つのステップがあります。まず、サンプルファイルをアップロードして、必要なファイル構造を定義する必要があります。これが完了したら、データをインポートするファイルの原点を指定できます。

>[!NOTE]
>
>サンプルファイルのデータは、アクティビティの構成に使用されますが、インポートされません。データの少ないサンプルファイルを使用することをお勧めします。

1. **[!UICONTROL Load file]** アクティビティをワークフローにドラッグアンドドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 最終ファイルのインポート時に予期される構造を定義できるサンプルファイルをアップロードします。

   ![](assets/wkf_file_loading.png)

   データファイルがアップロードされると、2つの新しいタブがアクティビティに表示されます。 **[!UICONTROL File structure]****[!UICONTROL Column definition]**&#x200B;とします。

1. **[!UICONTROL File structure]** タブに移動して、サンプルファイルから自動的に検出される構造を表示します。

   ファイル構造が誤って検出された場合は、次のようなエラーを修正するオプションがいくつかあります。

   * このオプション **[!UICONTROL Detect structure from a new file]** を選択すると、別のファイルの構造を使用することができます。
   * デフォルトの検出パラメータを変更して、ファイルに適合させることができます。このフィールド **[!UICONTROL File type]** では、インポートするファイルを固定長の列で構成するかどうかを指定できます。その場合は **[!UICONTROL Column definition]** 、タブの各列の最大文字数を指定する必要があります。

      ファイルからデータを正しくリカバリするために必要なすべての検出オプションは、に再グループ化 **[!UICONTROL File format]**&#x200B;されます。これらの新しい設定を考慮して、アクティビティにロードされた最後のファイルの構造を再検出することができます。これを行うには、 **[!UICONTROL Apply configuration]** ボタンを使用します。たとえば、別の列区切り記号を指定できます。

      >[!NOTE]
      >
      >この操作は、アクティビティに読み込まれた最後のファイルを考慮します。検出されたファイルが大きい場合、データプレビューには最初の30行のみが表示されます。

      ![](assets/wkf_file_loading3.png)

      **[!UICONTROL File format]** セクションでは、 **[!UICONTROL Check columns from file against column definitions]** アップロードするファイルの列が列定義に対応しているかどうかを確認できます。

      列の番号や名前が列の定義と一致しない場合は、ワークフローの実行時にエラーメッセージが表示されます。このオプションが有効になっていない場合は、ログファイルに警告が表示されます。

      ![](assets/wkf_file_loading_check.png)

1. **[!UICONTROL Column definition]** タブに移動して各列のデータ形式を確認し、必要に応じてパラメータを調整します。

   **[!UICONTROL Column definition]** このタブでは、エラーを含まないデータをインポートするために各列のデータ構造を正確に指定できます。たとえば、NULL管理を使用して、今後の操作のためにAdobe Campaignデータベースに既に存在する型と一致させることができます。

   たとえば、列のラベルを変更し、その型（文字列、整数、日付など）を選択できます。またはエラー処理を指定します。

   詳細については [、「列のフォーマット」](../../automating/using/load-file.md#column-format) セクションを参照してください。

   ![](assets/wkf_file_loading4.png)

1. **[!UICONTROL Execution]** タブで、データをロードするためにファイルを処理するかどうかを指定します。

   * ワークフローのインバウンド遷移から取得します。
   * 前の手順でアップロードしたものです。
   * ローカルマシンからアップロードする新しいファイルです。最初のファイルをワークフローで既に定義している場合は **[!UICONTROL Upload a new file from local machine]** 、このオプションが表示されます。これにより、現在のファイルが必要に応じていない場合に、処理する別のファイルをアップロードできます。

      ![](assets/wkf_file_loading1.png)

1. データを読み込むファイルがGZIPファイル（.gz）に圧縮されている場合は、フィールドのオプション **[!UICONTROL Decompression]** を選択 **[!UICONTROL Add a pre-processing step]** します。これにより、データを読み込む前にファイルを解凍できます。このオプションは、ファイルがアクティビティの着信遷移から来た場合にのみ使用できます。
1. **[!UICONTROL Keep the rejects in a file]** このオプションを使用すると、インポート中に発生したエラーを含むファイルをダウンロードし、処理後の段階に適用できます。

   >[!NOTE]
   >
   >**[!UICONTROL Add date and time to the file name]** このオプションを使用すると、拒否を含むファイル名のタイムスタンプを追加できます。

   ![](assets/wkf_file_loading_keeprejects.png)

1. アクティビティの構成を確認し、ワークフローを保存します。

## 列の形式 {#column-format}

サンプルファイルを読み込むと、各データ型の既定のパラメーターで列の形式が自動的に検出されます。これらの既定のパラメーターを変更すると、データに適用する特定のプロセスを指定できます。特に、エラーや空の値がある場合に使用します。

これを行うには、定義する形式の列のクイックアクション **[!UICONTROL Edit properties]** から選択します。列の形式詳細ウィンドウが開きます。

![](assets/wkf_file_loading4.png)

その後、各列の書式設定を変更できます。

列の書式設定では、各列の値処理を定義できます。

* **[!UICONTROL Ignore column]**:は、データの読み込み中にこの列を処理しません。
* **[!UICONTROL Data type]**:各列に必要なデータのタイプを指定します。
* **[!UICONTROL Format and separators]**、 **プロパティ**:テキストのプロパティ、時刻、日付、数値の形式、および列コンテキストで指定された区切り記号を指定します。

   * **[!UICONTROL Maximum number of characters]**:文字列型の列の最大文字数を指定します。

      このフィールドは、固定長の列で構成されるファイルを読み込むときに入力する必要があります。

   * **[!UICONTROL Letter case management]**:文字のケースプロセスを **テキスト** データに適用する必要があるかどうかを定義します。
   * **[!UICONTROL White space management]**: **テキスト** データの文字列で特定のスペースを無視する必要があるかどうかを指定します。
   * **[!UICONTROL Time format]****[!UICONTROL Date format]**: **日付**&#x200B;データ、 **時刻データ、** 日時 **** データの形式を指定します。
   * **[!UICONTROL Format]**: **整数** と **浮動小数点** データの数値の形式を定義できます。
   * **[!UICONTROL Separator]**: **は、日付**、 **時刻**、 **日付および時刻**、 **整数**、 **浮動小数点数** のデータの列コンテキストで指定された区切り記号（数値の区切り記号、桁区切り記号、日付と時刻の区切り記号）を定義します。

* **[!UICONTROL Remapping of values]**:このフィールドは、列詳細構成でのみ使用できます。これにより、インポート時に特定の値を変換できます。たとえば、"3"を"3"に変換できます。
* **[!UICONTROL Error processing]**:エラーが発生した場合の動作を定義します。

   * **[!UICONTROL Ignore the value]**:値は無視されます。ワークフロー実行ログに警告が生成されます。
   * **[!UICONTROL Reject the line]**:行全体は処理されません。
   * **[!UICONTROL Use a default value]**:エラーの原因となった値が、フィールド **[!UICONTROL Default value]** で定義されたデフォルト値に置き換えられます。
   * **[!UICONTROL Use a default value in case the value is not remapped]**:エラーの原因となった値を、誤った値に対してマッピングが定義されていない限り、デフォルト **[!UICONTROL Default value]** 値で置き換えられます（上記 **[!UICONTROL Remapping of values]** のオプションを参照）。
   * **[!UICONTROL Reject the line when there is no remapping value]**:間違った値にマッピングが定義されていない限り、行全体は処理されません（上記 **[!UICONTROL Remapping of values]** のオプションを参照）。
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** インポートされたファイルの値に関するエラーに関連します。たとえば、障害のあるデータ型（"Integer"列の場合は"4"すべての文字）、許可された最大数よりも多くの文字を含む文字列、障害が発生した日付などがあります。ただし、このオプションは空の値管理によって生成されるエラーには関係ありません。

* **[!UICONTROL Default value]**:選択したエラー処理に従って既定値を指定します。
* **[!UICONTROL Empty value management]**:データの読み込み中に空の値を管理する方法を指定します。

   * **[!UICONTROL Generate an error for numerical fields]**:は数値フィールドに対してのみエラーを生成し、それ以外の場合はNULL値を挿入します。
   * **[!UICONTROL Insert NULL in the corresponding field]**:空の値を承認します。そのため、NULL値が挿入されます。
   * **[!UICONTROL Generate an error]**:値が空の場合は、エラーが発生します。

## 例1:データベースの更新 {#example-1-update-the-database}

ロードファイルアクティビティは、主に転送ファイルアクティビティのデータを構造化して、既存のデータに統合します。

次の例は、転送ファイルアクティビティを介して自動的にダウンロードされたロードファイルアクティビティの結果と、更新データアクティビティを示しています。このワークフローでは、Adobe Campaignデータベースを新しいプロファイルで充実させるか、インポートされたファイルからリカバリされたデータを使用して既存のプロファイルを更新することを目的としています。

![](assets/load_file_workflow_ex1.png)

1. ワークフローに **[!UICONTROL Transfer file]** アクティビティをドラッグアンドドロップし、目的のファイルを復旧させるように構成します。
1. **[!UICONTROL Load file]** アクティビティをワークフローにドラッグアンドドロップし、 **[!UICONTROL Transfer file]** アクティビティの後に配置します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. タブの **[!UICONTROL File to load]** セクションで、 **[!UICONTROL Execution]****[!UICONTROL Use the file specified in the inbound transition]** オプションを確認します。

   ![](assets/wkf_file_loading8.png)

1. 前に指定したアクティビティを構成します。
1. アクティビティ **[!UICONTROL Update data]** をワークフローにドラッグアンドドロップし、 **[!UICONTROL Load file]** アクティビティの後に配置してから構成します。["Update data](../../automating/using/update-data.md)」を参照してください。

ワークフローが開始されると、アップロードされたファイルのデータが抽出され、Adobe Campaignデータベースの充実に使用されます。

## 例2:豊富なフィールドを持つ電子メールの送信 {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](../../automating/using/load-file.md#example-2-email-with-enriched-fields)-->

ロードファイルアクティビティでは、同じワークフロー内の外部ファイルから追加データを含む電子メールを送信することもできます。

次の例では、ロードファイルアクティビティを介して外部ファイルから取得した追加データを使用して電子メールを送信する方法を示します。この例では、外部ファイルには、関連付けられたアカウント番号を持つプロファイルのリストが含まれています。このデータをインポートして、アカウント番号を使用して各プロファイルに電子メールを送信します。

![](assets/load_file_workflow_ex2.png)

1. ワークフローに **[!UICONTROL Query]** アクティビティをドラッグアンドドロップして開き、メインターゲットを定義します。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. **[!UICONTROL Load file]** アクティビティをドラッグアンドドロップして、一部のデータをプロファイルに割り当てます。この例では、データベースの一部のプロファイルに対応するアカウント番号を含むファイルをロードします。

   ![](assets/load_file_activity.png)

1. **[!UICONTROL Enrichment]** アクティビティをワークフローにドラッグアンドドロップし、ロードファイルとクエリアクティビティをリンクします。

1. 濃縮活動の **[!UICONTROL Advanced relations]** タブで、調整に使用するフィールドを選択 **[!UICONTROL 0 or 1 cardinality simple link]** して定義します。ここでは、姓を使用してデータベースプロファイルとデータを調整します。

   ![](assets/load_file_enrichment_relation.png)

1. **[!UICONTROL Additional data]** タブで、電子メールで使用する要素を選択します。ここで、「アカウント番号」（ロードファイルアクティビティを通じて取得したファイルの列）を選択します。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   詳細については [、「濃縮」](../../automating/using/enrichment.md) セクションを参照してください。

1. ワークフローに **[!UICONTROL Segmentation]** アクティビティをドラッグアンドドロップして開き、メインターゲットを調整します。

   ![](assets/load_file_segmentation.png)

   詳細については [、Segmentation](../../automating/using/segmentation.md) セクションを参照してください。

1. **[!UICONTROL Email delivery]** アクティビティをワークフローにドラッグアンドドロップして開きます。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. パーソナライズ・フィールドを追加し、ノード **[!UICONTROL Additional data (targetData)]** からエンハンスメント・アクティビティ（「アカウント番号」）で定義された追加データを選択します。これにより、電子メールコンテンツ内の各プロファイルのアカウント番号を動的に取得できます。

   ![](assets/load_file_perso_field.png)

1. 電子メールを保存してワークフローを開始します。

電子メールはターゲットに送信されます。各プロファイルは、対応するアカウント番号で電子メールを受信します。

![](assets/load_file_email.png)
