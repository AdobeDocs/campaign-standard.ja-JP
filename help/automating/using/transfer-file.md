---
title: ファイルの転送
seo-title: ファイルの転送
description: ファイルの転送
seo-description: ファイルの転送アクティビティでは、ファイルの受信または送信、ファイルが存在するかどうかのテスト、Adobe Campaignのファイルのリストを実行できます。
page-status-flag: 常にアクティブ化されていない
uuid: a2f18118- b681-4310- aee0-9e82179d2032
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: data- management- activity
discoiquuid: 752f2aed- f897-485e- b329- f3cc1756ee8e
context-tags: fileTransfer、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# Transfer file{#transfer-file}

## 説明 {#description}

![](assets/file_transfer.png)

**[!UICONTROL Transfer file]** このアクティビティでは、ファイルの受信または送信、ファイルが存在するかどうかのテスト、Adobe Campaignのファイルのリストを実行できます。

## Context of use {#context-of-use}

データの抽出方法は、アクティビティの設定時に定義されます。読み込むファイルは、連絡先のリストです。

You can use this activity to recover data that will then be structured with the **[!UICONTROL Load file]** activity.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Transfer file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. **[!UICONTROL Action]** フィールドのドロップダウンリストを使用して、次のいずれかのアクティビティアクションを選択します。

   ![](assets/wkf_file_transfer_01.png)

   * **ファイルのダウンロード**:を使用すると、ファイルをダウンロードできます。
   * **ファイルのアップロード**:を使用すると、ファイルをアップロードできます。Uploading a file from Adobe Campaign file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.
   * **ファイルが存在**&#x200B;するかどうかをテストします。ファイルがあるかどうかを確認できます。
   * **ファイルリスト**:では、Adobe Campaignに存在するファイルを一覧表示できます。
   選択したアクションに応じて、1つまたは複数のプロトコルを使用できます。

   * **HTTP**:このプロトコルを使用すると、外部アカウントまたはURLからファイルのダウンロードを開始できます。

      * **[!UICONTROL Use connection parameters defined in an external account]** このオプションをクリックして、ダウンロードするファイルのパスを選択し、ダウンロードするファイルのパスを指定します。

         ![](assets/wkf_file_transfer_03.png)

      * **[!UICONTROL Quick configuration]** このオプションをクリックし、表示されるフィールドにURLを入力します。

         ![](assets/wkf_file_transfer_04.png)
   * **S3**:このプロトコルを使用すると、URLまたは外部アカウントからのファイルのダウンロードをAmazon Simple Storage Service（S3）経由で開始できます。

      * 外部アカウントを選択し、ダウンロードするファイルのパスを指定します。

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**:このプロトコルを使用すると、URLまたは外部アカウントからファイルのダウンロードを開始できます。

      * **[!UICONTROL Use connection parameters defined in an external account]** このオプションをクリックして、ダウンロードするファイルのパスを選択し、ダウンロードするファイルのパスを指定します。

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >ワイルドカードがサポートされています。

      * **[!UICONTROL Quick configuration]** このオプションをクリックし、表示されるフィールドにURLを入力します。
      * If you want to sort the imported files, select the **[!UICONTROL Sort alphanumerically]** option from the **[!UICONTROL Additional options]** section. ファイルは順番に処理されます。

         ![](assets/wkf_file_transfer_sort.png)
   * **Adobe Campaignサーバーに存在するファイル**:このプロトコルは、回復するファイルを含むリポジトリに対応しています。

      メタ文字またはワイルドカード（*や?）などを使用してファイルをフィルタリングできます。

      このフィールドに入力し、アクティビティを確認して、このプロトコルを使用します。

      >[!NOTE]
      >
      >パスは、Adobe Campaignサーバーの記憶領域ディレクトリからの相対パスである必要があります。ファイルは** sftp&lt; yourinstancename&gt;/**ディレクトリにあります。ストレージスペースの上にあるディレクトリを参照することもできません。For example: **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** が正しくない。**//myserver/hello/myrecipients.csv** が正しくない。
   プロトコルを選択し、関連するフィールドを入力します。

   **[!UICONTROL Use a dynamic file path]** 各プロトコルで使用できるオプションを使用すると、標準の式とイベント変数を使用して、転送するファイルの名前をパーソナライズできます。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. **[!UICONTROL Additional options]** 選択したプロトコルに応じて使用できるセクションでは、プロトコルにパラメーターを追加できます。次のことができます。

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:このオプションは **[!UICONTROL File listing]** 、アクションを選択するときに使用できます。It allows you to index all the files present on the server in the **vars.filenames** event variable in which the file names are separated by the **'n'** characters.

1. The **[!UICONTROL If no files are found]** section of the **[!UICONTROL Advanced options]** tab allows you to configure specific actions if any errors or inexistent files are detected when the activity is started.

   再試行を定義することもできます。ワークフロー実行ログには、様々な再試行が表示されます。

   ![](assets/wkf_file_transfer_09.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

## Historization settings {#historization-settings}

**[!UICONTROL Transfer file]** アクティビティが実行されるたびに、アップロードされたファイルまたはダウンロードされたファイルが専用フォルダーに保存されます。One folder is created for each **[!UICONTROL Transfer file]** activity of a workflow. したがって、サーバー上の物理的な空間を維持するために、このフォルダーのサイズを制限することが重要です。

To do that, you can define **[!UICONTROL Historization settings]** in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Transfer File]** activity.

**[!UICONTROL Historization settings]** アクティビティのフォルダーの最大数または合計サイズを定義できます。デフォルトでは、100個のファイルと50MBが認証されています。

アクティビティが実行されるたびに、次のようにフォルダーがチェックされます。

* アクティビティの実行が考慮されるまでに24時間以上作成されたファイルのみが考慮されます。
* If the number of files taken into account is greater than the value of the **[!UICONTROL Maximum number of files]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum number of files]** allowed is reached.
* If the total size of files taken into account is greater than the value of the **[!UICONTROL Maximum size (in MB)]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum size (in MB)]** allowed is reached.

>[!NOTE]
アクティビティが再度実行されない場合、そのフォルダーはチェックされず、削除されません。大きなファイルを転送する際は、注意が必要です。

## Example {#example}

The following example shows the configuration of a **File transfer** activity which will then be followed by a **Load file** activity then an **Update data** activity. このワークフローの目的は、ワークフローによって回復されるデータを使用してAdobe Campaignデータベースプロファイルを追加または更新することです。

1. Drag and drop a **Transfer file** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. **[!UICONTROL Protocol]** タブで、「 **SFTP**」を選択します。
1. Select the **Use connection parameters defined in an external account** option.
1. 外部アカウントの名前を入力します。
1. Enter the **File path on the remote server**.

   ![](assets/wkf_file_transfer_07.png)

1. アクティビティを確認し、ワークフローを保存します。

