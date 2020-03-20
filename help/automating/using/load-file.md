---
title: ファイル読み込み
description: ファイルを読み込みアクティビティを使用すると、1つの構造化されたフォームにデータを読み込んで、Adobe Campaignでこのデータを使用できます。
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# ファイル読み込み {#load-file}

## 説明 {#description}

![](assets/data_loading.png)

アクティビテ **[!UICONTROL Load file]** ィを使用すると、1つの構造化されたフォームにデータをインポートして、このデータをAdobe Campaignで使用できます。 データが一時的にインポートされ、Adobe Campaignデータベースに統合する別のアクティビティが必要です。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティが設定されるときに定義されます。 たとえば、ロードするファイルは連絡先のリストです。

>[!CAUTION]
>
>.txt、.csvなどの「フラットな」構造ファイルのみが考慮されます。

次の操作をおこなうことができます。

* ファイル構造を使用して、別のファイルのデータ（アクティビティを使用して回復）に適用するか、ま **[!UICONTROL Transfer file]** たは、
* ファイルの構造とデータを使用して、Adobe Campaignにインポートします。

## 設定 {#configuration}

アクティビティの設定には、2つの手順があります。 まず、サンプルファイルをアップロードして、必要なファイル構造を定義する必要があります。 これを行ったら、データを読み込むファイルの元を指定できます。

>[!NOTE]
>
>サンプルファイルのデータは、アクティビティの設定に使用されますが、読み込まれません。 データの少ないサンプルファイルを使用することをお勧めします。

1. アクティビティをワークフロー **[!UICONTROL Load file]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 最終的なファイルの読み込み時に期待される構造を定義できるサンプルファイルをアップロードします。

   ![](assets/wkf_file_loading.png)

   データファイルがアップロードされると、アクティビティに2つの新しいタブが表示されます。 **[!UICONTROL File structure]** と **[!UICONTROL Column definition]**

1. タブに移動し、サ **[!UICONTROL File structure]** ンプルファイルから自動的に検出される構造を表示します。

   ファイル構造が正しく検出されなかった場合は、次のいくつかのオプションを使用して、エラーを修正できます。

   * オプションを選択して、別のファイルの構造を使用することがで **[!UICONTROL Detect structure from a new file]** きます。
   * デフォルトの検出パラメータを変更して、ファイルに適合させることができます。 このフ **[!UICONTROL File type]** ィールドでは、読み込むファイルが固定長の列で構成されているかどうかを指定できます。 この場合、タブの各列の最大文字数も指定する必要があり **[!UICONTROL Column definition]** ます。

      ファイルからデータを正しく回復するために必要なすべての検出オプションが、に再グループ化されま **[!UICONTROL File format]**&#x200B;す。 これらの新しい設定を考慮すると、アクティビティに読み込まれた最後のファイルの構造を再検出できます。 これを行うには、ボタンを使用 **[!UICONTROL Apply configuration]** します。 例えば、別の列区切り文字を指定できます。

      >[!NOTE]
      >
      >この操作では、アクティビティに読み込まれた最後のファイルが考慮されます。 検出されたファイルのサイズが大きい場合、データプレビューには最初の30行のみが表示されます。

      ![](assets/wkf_file_loading3.png)

      このセクシ **[!UICONTROL File format]** ョンでは、 **[!UICONTROL Check columns from file against column definitions]** アップロードするファイルの列が列の定義に対応していることを確認できます。

      列の数や名前が列の定義と一致しない場合は、ワークフローの実行時にエラーメッセージが表示されます。 このオプションが有効になっていない場合は、警告がログファイルに表示されます。

      ![](assets/wkf_file_loading_check.png)

1. 各列のデータ形 **[!UICONTROL Column definition]** 式を確認し、必要に応じてパラメータを調整するには、タブに移動します。

   このタ **[!UICONTROL Column definition]** ブでは、エラーを含まないデータをインポート（例えば、null管理を使用）し、今後の操作のためにAdobe Campaignデータベースに既に存在するタイプと一致させるために、各列のデータ構造を正確に指定できます。

   例えば、列のラベルを変更し、そのタイプ（文字列、整数、日付など）を選択できます。またはエラー処理を指定することもできます。

   For more information, refer to the [Column format](#column-format) section.

   ![](assets/wkf_file_loading4.png)

1. タブで、 **[!UICONTROL Execution]** データの読み込み用にファイルを処理するかどうかを指定します。

   * ワークフロー内の受信トランジションから取得されます。
   * は、前の手順でアップロードしたものです。
   * ローカルマシンからアップロードする新しいファイルです。 最初のフ **[!UICONTROL Upload a new file from local machine]** ァイルが既にワークフローで定義されている場合は、このオプションが表示されます。 これにより、現在のファイルがニーズに合わない場合に、別のファイルをアップロードして処理できます。

      ![](assets/wkf_file_loading1.png)

1. データの読み込み元のファイルが圧縮されてGZIPファイル(.gz)になっている場合は、フィールドでオ **[!UICONTROL Decompression]** プションを選択し **[!UICONTROL Add a pre-processing step]** ます。 これにより、データを読み込む前にファイルを解凍できます。 このオプションは、ファイルがアクティビティの受信移行から来た場合にのみ使用できます。
1. このオ **[!UICONTROL Keep the rejects in a file]** プションを使用すると、読み込み中に発生したエラーを含むファイルをダウンロードし、後処理段階でそのファイルに適用できます。 このオプションを有効にすると、外部遷移の名前が「拒否」に変更されます。

   >[!NOTE]
   >
   >このオ **[!UICONTROL Add date and time to the file name]** プションを使用すると、リジェクトを含むファイルの名前にタイムスタンプを追加できます。

   ![](assets/wkf_file_loading_keeprejects.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

ワークフローの実行後にアクティビティでエラーが発生した場合は、ログを参照して、ファイル内の誤った値の詳細を取得します。 For more on workflows logs, refer to [this section](../../automating/using/executing-a-workflow.md#monitoring).

## 列のフォーマット {#column-format}

サンプルファイルを読み込むと、列の形式が各データ型のデフォルトのパラメーターで自動的に検出されます。 このデフォルトのパラメーターを編集して（特に誤りや空の値がある場合）、特定の処理を指定してデータに適用することができます。

これを行うには、列の **[!UICONTROL Edit properties]** 形式を定義するクイックアクションから選択します。 列形式の詳細ウィンドウが開きます。

![](assets/wkf_file_loading4.png)

その後、各列の形式設定を変更できます。

列のフォーマットでは、以下の設定で各列の値の処理方法を定義できます。

* **[!UICONTROL Ignore column]**:は、データの読み込み中にこの列を処理しません。
* **[!UICONTROL Data type]**:各列に必要なデータのタイプを指定します。
* **[!UICONTROL Format and separators]**、プロ **パティ**:テキスト、時間、日付、数値の形式のプロパティ、および列コンテキストで指定された区切り文字を指定します。

   * **[!UICONTROL Maximum number of characters]**:文字列型の列の最大文字数を指定します。

      固定長の列で構成されるファイルを読み込む場合は、このフィールドに入力する必要があります。

   * **[!UICONTROL Letter case management]**:テキストデータに文字の大文字と小文字の処理を適用する必要があるかどうかを **定義します** 。
   * **[!UICONTROL White space management]**:は、テキストデータの文字列内で特定のスペースを無視する必要があるかどうかを **指定します** 。
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**:日付、時間、日 **時デー**&#x200B;タ **** の形式を指定します **** 。
   * **[!UICONTROL Format]**:整数データと浮動小数点数データの数値の形式を **定義で** きます **** 。
   * **[!UICONTROL Separator]**:列コンテキストで指定される区切り文字を定義します（数値の千単位区切り文字、日付と時刻の区切り文字） **。** Date **,** Time **Dateと** Time **,** IntegerInteger **,** IntegerFloatingData, Floating

* **[!UICONTROL Remapping of values]**:このフィールドは、列の詳細設定でのみ使用できます。 読み込み時に特定の値を変換できます。 例えば、「three」を「3」に変換できます。
* **[!UICONTROL Error processing]**:エラーが発生した場合の動作を定義します。

   * **[!UICONTROL Ignore the value]**:値は無視されます。 ワークフローの実行ログに警告が生成されます。
   * **[!UICONTROL Reject the line]**:行全体が処理されません。
   * **[!UICONTROL Use a default value]**:エラーの原因となる値を、フィールドに定義されているデフォルト値に置き換 **[!UICONTROL Default value]** えます。
   * **[!UICONTROL Use a default value in case the value is not remapped]**:エラーの原因となる値を、エラーのある値に対してマッピングが定義されていない限り、フィールドで定義されているデフォルト値に置き換えます(上 **[!UICONTROL Default value]** 記のオプションを **[!UICONTROL Remapping of values]** 参照)。
   * **[!UICONTROL Reject the line when there is no remapping value]**:マッピングが誤った値に対して定義されていない限り、行全体が処理され **[!UICONTROL Remapping of values]** ません（上記のオプションを参照）。
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** 読み込まれたファイルの値に関するエラーに関する問題です。 例えば、データタイプの不良（「整数」列の「4」文字すべて）、許可された最大文字数を超える文字を含む文字列、区切り文字の不良のある日付など。 ただし、このオプションは、空の値の管理によって生成されるエラーには関係しません。

* **[!UICONTROL Default value]**:は、選択したエラー処理に従ってデフォルト値を指定します。
* **[!UICONTROL Empty value management]**:データの読み込み中に空の値を管理する方法を指定します。

   * **[!UICONTROL Generate an error for numerical fields]**:数値フィールドのみに対してエラーを生成し、それ以外の場合はNULL値を挿入します。
   * **[!UICONTROL Insert NULL in the corresponding field]**:は空の値を許可します。 したがって、null 値が挿入されます。
   * **[!UICONTROL Generate an error]**:値が空の場合にエラーを生成します。

## 例1:データベースの更新 {#example-1-update-the-database}

ロード・ファイル・アクティビティは、既存のデータに統合するために、転送ファイル・アクティビティからのデータを主に構成する。

次の例は、ファイル転送アクティビティを介して自動的にダウンロードされたファイル読み込みアクティビティの結果と、データ更新アクティビティの結果を示しています。 このワークフローは、Adobe Campaignデータベースに新しいプロファイルを追加したり、インポートしたファイルから回復したデータを使用して既存のプロファイルを更新したりする目的です。

![](assets/load_file_workflow_ex1.png)

1. アクティビティをワ **[!UICONTROL Transfer file]** ークフローにドラッグ&amp;ドロップし、希望のファイルが回復されるように設定します。
1. アクティビティをワークフ **[!UICONTROL Load file]** ローにドラッグ&amp;ドロップし、アクティビティの後に配置 **[!UICONTROL Transfer file]** します。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. タブのセク **[!UICONTROL File to load]** ションで、オ **[!UICONTROL Execution]** プションをオンに **[!UICONTROL Use the file specified in the inbound transition]** します。

   ![](assets/wkf_file_loading8.png)

1. 前述の手順に従って、アクティビティを設定します。
1. アクティビティをワークフ **[!UICONTROL Update data]** ローにドラッグ&amp;ドロップし、アクティビティの後 **[!UICONTROL Load file]** に配置して、設定を行います。 「データの更 [新」を参照](../../automating/using/update-data.md)。

ワークフローが開始されると、アップロードされたファイルのデータが抽出され、Adobe Campaignデータベースの拡張に使用されます。

## 例2:強化されたフィールドを含む電子メールの送信 {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

また、ファイルの読み込みアクティビティを使用すると、同じワークフロー内の外部ファイルから追加のデータを含む電子メールを送信できます。

次の例は、ファイルの読み込みアクティビティを通じて外部ファイルから取得した追加のデータを使用して電子メールを送信する方法を示しています。 この例では、外部ファイルに、関連するアカウント番号と共にプロファイルのリストが含まれています。 このデータをインポートして、各プロファイルにアカウント番号と共に電子メールを送信します。

![](assets/load_file_workflow_ex2.png)

1. アクティビティをワークフ **[!UICONTROL Query]** ローにドラッグ&amp;ドロップし、開いてメインターゲットを定義します。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. アクティビティをドラッグ&amp;ド **[!UICONTROL Load file]** ロップして、一部のデータをプロファイルに割り当てます。 この例では、データベースの一部のプロファイルに対応するアカウント番号を含むファイルを読み込みます。

   ![](assets/load_file_activity.png)

1. アクティビティをワークフローにド **[!UICONTROL Enrichment]** ラッグ&amp;ドロップし、ロードファイルとクエリーアクティビティをそのワークフローにリンクします。

1. 強化アクテ **[!UICONTROL Advanced relations]** ィビティのタブで、調整に使用す **[!UICONTROL 0 or 1 cardinality simple link]** るフィールドを選択し、定義します。 ここでは、姓を使用して、データをデータベースプロファイルと調整します。

   ![](assets/load_file_enrichment_relation.png)

1. タブで **[!UICONTROL Additional data]** 、電子メールに使用する要素を選択します。 ここで、「アカウント番号」（ファイルの読み込みアクティビティで取得したファイルの列）を選択します。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   詳しくは、「エンリッチメント」の節を参照し [てくださ](../../automating/using/enrichment.md) い。

1. アクティビティをワークフ **[!UICONTROL Segmentation]** ローにドラッグ&amp;ドロップして開き、メインのターゲットを絞り込みます。

   ![](assets/load_file_segmentation.png)

   詳しくは、「セグメント化」の節を参照し [てください](../../automating/using/segmentation.md) 。

1. アクティビティをワークフ **[!UICONTROL Email delivery]** ローにドラッグ&amp;ドロップして開きます。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. パーソナライゼーションフィールドを追加し、ノードからエンリッチメントアクティビティ（ここでは「アカウント番号」）で定義された追加のデータを選択 **[!UICONTROL Additional data (targetData)]** します。 これにより、電子メールコンテンツ内の各プロファイルのアカウント番号を動的に取得できます。

   ![](assets/load_file_perso_field.png)

1. 電子メールを保存し、ワークフローを開始します。

電子メールがターゲットに送信されます。 各プロファイルは、対応するアカウント番号を持つ電子メールを受信します。

![](assets/load_file_email.png)
