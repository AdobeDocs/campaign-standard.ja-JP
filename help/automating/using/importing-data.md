---
title: データの読み込み
seo-title: データの読み込み
description: データの読み込み
seo-description: ワークフローでデータをインポートする方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: d909d26a- cf50-46af- ae09- f0fd7258ca27
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow- general- operation
discoiquuid: 75b83165- dcbd-4bb7- b703- ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Importing data{#importing-data}

## Collecting data {#collecting-data}

ファイルからデータを収集して処理したり、Adobe Campaignデータベースに読み込むことができます。

* **[!UICONTROL Load file]** このアクティビティにより、Adobe Campaignでこのデータを使用するために、構造化された1つのフォームにデータを読み込むことができます。データは一時的にインポートされ、別のアクティビティがAdobe Campaignデータベースに定義するために必要になります。
* **[!UICONTROL Transfer file]** このアクティビティでは、ファイルの受信または送信、ファイルが存在するかどうかのテスト、Adobe Campaignのファイルのリストを実行できます。

   You can use this activity before a **[!UICONTROL Load file]** in case you need to retrieve the file from an external source.

## Import best practices {#import-best-practices}

以下に説明するいくつかの簡単なルールに従って、データベース内でデータの一貫性を確保し、データベースの更新またはデータのエクスポート中に一般的なエラーを回避するために、多くの簡単なルールを使用できます。

### Using import templates {#using-import-templates}

Most import workflows should contain the following activities: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

インポートテンプレートを使用すると、類似のインポートを準備し、データベース内のデータの整合性を確実に保つことができます。

In many projects, imports are built without **[!UICONTROL Deduplication]** activity because the files used in the project do not have duplicates. 異なるファイルの読み込み時に重複が生じることがあります。重複の排除は困難です。したがって、すべてのインポートワークフローで重複排除手順を実行することをお勧めします。

受信データが一貫しており、正確であること、またはIT部門またはAdobe Campaign担当者がこのデータを処理しないことを前提としています。プロジェクト中に、データのクレンジングを念頭に置きます。データの読み込み時に一貫性を排除、調整および維持します。

An example of a generic workflow template designed for importing data is available in the [Example: Import workflow template](../../automating/using/importing-data.md#example--import-workflow-template) section.

>[!NOTE]
>
>[インポートテンプレート](../../automating/using/importing-data-with-import-templates.md)を使用することもできます。これらは管理者が定義したワークフローテンプレートであり、アクティブ化すると、インポートするデータを含むファイルを指定できるようになります。

### Using flat file formats {#using-flat-file-formats}

読み込みの最も効率的な形式は、フラットファイルです。フラットファイルは、一括モードで一括モードで読み込むことができます。

次に例を示します。

* 区切り文字:タブまたはセミコロン
* ヘッダー付きの先頭行
* 文字列区切り文字なし
* 日付形式:YYYY/MM/DD HH:mm:SS

読み込むファイルの例:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### Using compression {#using-compression}

可能であれば、zipファイルをインポートおよびエクスポート用に使用します。GZIPはデフォルトでサポートされています。You can add pre-processing when importing files or post-processing when extracting data, respectively in the **[!UICONTROL Load file]** and **[!UICONTROL Extract file]** workflow activities.

### Importing in Delta mode {#importing-in-delta-mode}

通常のインポートは、差分モードで行う必要があります。つまり、変更されたデータまたは新しいデータのみが、毎回表全体ではなく、Adobe Campaignに送信されます。

フルインポートは、初回読み込みのみで使用します。

### Maintaining consistency {#maintaining-consistency}

Adobe Campaignデータベースでデータの一貫性を維持するには、以下の原則に従います。

* インポートしたデータがAdobe Campaignの参照テーブルと一致する場合は、ワークフローのテーブルと調整する必要があります。一致しないレコードは拒否されます。
* Ensure that the imported data is always **"normalized"** (email, phone number, direct mail address) and that this normalization is reliable and will not change over the years. 大文字と小文字が区別されない場合は、一部の複製がデータベースに表示される可能性があり、Adobe Campaignでは「あいまい」に一致するツールを提供しないので、管理や削除が非常に難しくなります。
* トランザクションデータは、重複を作成しないように、紐付けキーを持つ必要があり、既存のデータと調和させる必要があります。
* **関連ファイルを順番**&#x200B;に読み込みます。インポートが相互に依存する複数のファイルから構成されている場合、ワークフローではファイルが正しい順序で読み込まれることを確認する必要があります。ファイルが失敗すると、その他のファイルは読み込まれません。
* **データの読み込み時に一貫性を排除**、調整および維持します。

## Example: Import workflow template {#example--import-workflow-template}

同じ構造を持つファイルを定期的に読み込む必要がある場合は、インポートテンプレートを使用することをお勧めします。

この例は、Adobe Campaignデータベース内のCRMからのプロファイルをインポートするために再利用できるワークフローを事前設定する方法を示しています。

1. Create a new workflow template from **[!UICONTROL Resources > Templates > Workflow templates]**.
1. 次のアクティビティを追加します。

   * **[!UICONTROL Load file]**:読み込むデータを含むファイルの構造を定義します。

      >[!NOTE]
      >
      >データは、1つのファイルからのみインポートできます。If the workflow has multiple **[!UICONTROL Load file]** activities, the same file will be used each time.

   * **[!UICONTROL Reconciliation]**:インポートしたデータをデータベースデータに調整します。
   * **[!UICONTROL Segmentation]**:フィルターを処理するかどうかによって、レコードの処理方法が異なります。
   * **[!UICONTROL Deduplication]**:受信ファイルのデータをデータベースに挿入する前に重複排除します。
   * **[!UICONTROL Update data]**:読み込んだプロファイルを使用してデータベースを更新します。
   ![](assets/import_template_example0.png)

1. **[!UICONTROL Load file]** アクティビティの設定:

   * サンプルファイルをアップロードして、構造を定義してください。サンプルファイルには、インポートに必要な数行のみが含まれている必要があります。各列のタイプが正しく設定されていることを確認するには、ファイル形式をチェックして編集します。テキスト、日付、整数など次に例を示します。

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * **[!UICONTROL File to load]** セクションで、フィールドを空白 **[!UICONTROL Upload a new file from the local machine]** のままにしておきます。このテンプレートから新しいワークフローが作成されるたびに、定義した構造に対応するファイルをここで指定できます。

      任意のオプションを使用できますが、それに応じてテンプレートを変更する必要があります。For example, if you select **[!UICONTROL Use the file specified in the inbound transition]**, you can add a **[!UICONTROL Transfer file]** activity before to retrieve the file to import from a FTP/SFTP server.

      If you want users to be able to download a file containing errors that occurred during an import, check the **[!UICONTROL Keep the rejects in a file]** option and specify the **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. **[!UICONTROL Reconciliation]** アクティビティを設定します。このコンテキストの目的は、受信データを特定することです。

   * **[!UICONTROL Relations]** タブで、インポートしたデータと受信者のターゲティングディメンションの間のリンクを選択 **[!UICONTROL Create element]** して定義します（ディメンションとリソース [](../../automating/using/query.md#targeting-dimensions-and-resources)のターゲット設定を参照）。In this example, the **CRM ID** custom field is used to create the join condition. 一意のレコードを識別できる限り、フィールドのフィールドまたは組み合わせを使用します。
   * **[!UICONTROL Identification]** タブで **[!UICONTROL Identify the document from the working data]** 、オプションの選択を解除したままにします。
   ![](assets/import_template_example2.png)

1. Configure the **[!UICONTROL Segmentation]** activity to retrieve reconciled recipients in one transition and recipients that could not be reconciled but who have enough data in a second transition.

   その後、調整された受信者を含む移行を使用してデータベースを更新できます。その後、不明な受信者を持つ移行を使用して、最小限の情報セットがファイル内にある場合に、データベースに新しい受信者エントリを作成できます。

   データを調整できず、補足的な送信トランジションで十分なデータが選択されていない場合、または個別のファイルにエクスポートすることも、単純に無視することもできます。

   * In the **[!UICONTROL General]** tab of the activity, set the **[!UICONTROL Resource type]** to **[!UICONTROL Temporary resource]** and select **[!UICONTROL Reconciliation]** as the targeted set.
   * **[!UICONTROL Advanced options]** タブで **[!UICONTROL Generate complement]** 、レコードがデータベースに挿入できないかどうかを確認できるオプションを選択します。必要に応じて、補足データにさらに処理を適用できます。ファイルのエクスポート、リストの更新など
   * **[!UICONTROL Segments]** タブの最初のセグメントで、受信母集団にフィルター条件を追加して、プロファイルのCRM IDが0と等しくないレコードのみを選択します。この方法で、そのサブセット内のデータベースからのプロファイルと調和するデータのデータが選択されます。

      ![](assets/import_template_example3.png)

   * データベースに挿入する十分なデータを持つ、紐付けされていないレコードを選択する2つ目のセグメントを追加します。次に例を示します。電子メールアドレス、名、姓。紐付けされていないレコードのプロファイルのCRM ID値は0に等しくなります。

      ![](assets/import_template_example3_2.png)

   * All records that are not selected in the first two subsets are selected in the **[!UICONTROL Complement]**.

1. Configure the **[!UICONTROL Update data]** activity located after the first outbound transition of the **[!UICONTROL Segmentation]** activity configured previously.

   * Select **[!UICONTROL Update]** as **[!UICONTROL Operation type]** since the inbound transition only contains recipients already present in the database.
   * **[!UICONTROL Identification]** タブで **[!UICONTROL Using reconciliation criteria]****[!UICONTROL Dimension to update]** 、"-プロファイル」の"-プロファイル」と **[!UICONTROL Reconciliation]** 、アクティビティで作成されたリンクの間のキーを選択して定義します。In this example, the **CRM ID** custom field is used.

      ![](assets/import_template_example6.png)

   * **[!UICONTROL Fields to update]** タブで、ファイルから対応する列の値で更新するプロファイルディメンションのフィールドを示します。ファイル列の名前が、受信者ディメンションフィールドの名前と同じまたはほぼ同一である場合は、自動的に異なるフィールドに一致するように自動的に選択できます。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >これらのプロファイルにダイレクトメールを送信する場合は、ダイレクトメールプロバイダーにとって重要な情報として住所を含めてください。Also make sure that the **[!UICONTROL Address specified]** box in your profiles' information is checked. To update this option from a workflow, simply add an element to the fields to update, and specify **1** as **[!UICONTROL Source]** and select the **[postalAddress/@addrDefined]** field as **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. Configure the **[!UICONTROL Deduplication]** activity located after the transition containing unreconciled profiles:

   * **[!UICONTROL Properties]** タブで、ワークフロー **[!UICONTROL Resource type]** の **[!UICONTROL Reconciliation]** アクティビティから生成された一時リソースを設定します。

      ![](assets/import_template_example4.png)

   * この例では、電子メールフィールドを使用して一意のプロファイルを見つけます。入力されているフィールドと一意の組み合わせの一部を使用できます。
   * Choose a **[!UICONTROL Deduplication method]**. この場合、アプリケーションは重複の場合に記録されるレコードを自動的に決定します。
   ![](assets/import_template_example7.png)

1. Configure the **[!UICONTROL Update data]** activity located after the **[!UICONTROL Deduplication]** activity configured previously.

   * Select **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** since the inbound transition only contains profiles not present in the database.
   * **[!UICONTROL Identification]** タブで **[!UICONTROL Using reconciliation criteria]****[!UICONTROL Dimension to update]** 、"-プロファイル」の"-プロファイル」と **[!UICONTROL Reconciliation]** 、アクティビティで作成されたリンクの間のキーを選択して定義します。In this example, the **CRM ID** custom field is used.

      ![](assets/import_template_example6.png)

   * **[!UICONTROL Fields to update]** タブで、ファイルから対応する列の値で更新するプロファイルディメンションのフィールドを示します。ファイル列の名前が、受信者ディメンションフィールドの名前と同じまたはほぼ同一である場合は、自動的に異なるフィールドに一致するように自動的に選択できます。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >これらのプロファイルにダイレクトメールを送信する場合は、ダイレクトメールプロバイダーにとって重要な情報として住所を含めてください。Also make sure that the **[!UICONTROL Address specified]** box in your profiles' information is checked. To update this option from a workflow, simply add an element to the fields to update, and specify **1** as **[!UICONTROL Source]** and select the **[postalAddress/@addrDefined]** field as **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. **[!UICONTROL Segmentation]** アクティビティの3番目のトランジションの後、データベースに挿入されていないデータを追跡したい場合は **[!UICONTROL Extract file]** 、アクティビティと **[!UICONTROL Transfer file]** アクティビティを追加します。必要な列をエクスポートするように設定し、ファイルを取得できるFTPまたはSFTPサーバーに転送します。
1. Add an **[!UICONTROL End]** activity and save the workflow template.

テンプレートを使用できるようになり、新しいワークフローごとに使用できるようになりました。All is needed is then to specify the file containing the data to import in the **[!UICONTROL Load file]** activity.

![](assets/import_template_example9.png)

