---
title: 転送ファイル
description: ファイルの転送アクティビティでは、ファイルの受信や送信、Adobe Campaign内のファイルの有無のテスト、ファイルのリスト表示を行うことができます。
page-status-flag: 非活性化の
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: データ管理活動
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 転送ファイル{#transfer-file}

## 説明 {#description}

![](assets/file_transfer.png)

このア **[!UICONTROL Transfer file]** クティビティでは、ファイルの受信や送信、Adobe Campaign内のファイルの有無のテスト、ファイルのリスト表示を行うことができます。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティが設定されるときに定義されます。 読み込むファイルは、例えば連絡先のリストです。

このアクティビティを使用して、アクティビティで構造化されるデータを回復で **[!UICONTROL Load file]** きます。

## 設定 {#configuration}

1. アクティビティをワ **[!UICONTROL Transfer file]** ークフローにドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. フィールドのドロップダウンリストを使用し **[!UICONTROL Action]** て、次のアクティビティアクションの1つを選択します。

   ![](assets/wkf_file_transfer_01.png)

   * **ファイルのダウンロード**:ファイルをダウンロードできます。
   * **ファイルのアップロード**:ファイルをアップロードできます。 Adobe Campaignファイルからファイルをアップロードすると、メニューにログエントリが生成さ **[!UICONTROL Export audits]** れます。 エクスポート監査の詳細については、「エクスポートの監査 [](../../administration/using/auditing-export-logs.md) 」を参照してください。
   * **ファイルが存在するかどうかを確認する**:ファイルが存在するかどうかを確認できます。
   * **ファイル一覧**:adobe Campaignに存在するファイルを一覧表示できます。
   選択した操作に応じて、1つまたは複数のプロトコルを使用できます。

   * **HTTP**:このプロトコルを使用すると、外部アカウントまたはURLからファイルのダウンロードを開始できます。

      * オプション **[!UICONTROL Use connection parameters defined in an external account]** をクリックし、ダウンロードするアカウントを選択し、ダウンロードするファイルのパスを指定します。

         ![](assets/wkf_file_transfer_03.png)

      * オプション **[!UICONTROL Quick configuration]** をクリックし、表示されるフィールドにURLを入力します。

         ![](assets/wkf_file_transfer_04.png)
   * **S3**:このプロトコルを使用すると、Amazon Simple Storage Service(S3)を介してURLまたは外部アカウントからファイルのダウンロードを開始できます。

      * 外部アカウントを選択し、ダウンロードするファイルのパスを指定します。

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**:このプロトコルを使用すると、URLまたは外部アカウントからファイルのダウンロードを開始できます。

      * オプション **[!UICONTROL Use connection parameters defined in an external account]** をクリックし、ダウンロードするアカウントを選択し、ダウンロードするファイルのパスを指定します。

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >ワイルドカードがサポートされます。

      * オプション **[!UICONTROL Quick configuration]** をクリックし、表示されるフィールドにURLを入力します。
      * 読み込んだファイルを並べ替える場合は、セクションからオ **[!UICONTROL Sort alphanumerically]** プションを選択 **[!UICONTROL Additional options]** します。 その後、ファイルは順番に処理されます。

         ![](assets/wkf_file_transfer_sort.png)
   * **Adobe Campaignサーバーに存在するファイル**:このプロトコルは、リカバリするファイルを含むリポジトリに対応します。

      メタ文字、ワイルドカード（*や？など）は、ファイルのフィルタリングに使用できます。

      このフィールドに入力し、このプロトコルを使用するアクティビティを確認します。

      >[!NOTE]
      >
      >パスは、Adobe Campaignサーバーの記憶領域ディレクトリを基準とした相対パスで指定する必要があります。 ファイルは、 **sftp&lt;yourinstancename&gt;/ディレクトリにありま** す。 また、ストレージスペースの上のディレクトリを参照することもできません。 例： **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** is incorrect. **//myserver/hello/myrecipients.csv** is incorrect.
   プロトコルを選択し、関連するフィールドに入力します。

   各プロ **[!UICONTROL Use a dynamic file path]** トコルで使用できるこのオプションを使用すると、標準の式とイベント変数を使用して、転送するファイルの名前をパーソナライズできます。 詳しくは、「イベント変数を使用したアクティビティ [のカスタマイズ」の節を参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) い。

1. 選択し **[!UICONTROL Additional options]** たプロトコルに応じて利用できるセクションでは、プロトコルにパラメータを追加できます。 次の操作をおこなうことができます。

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:このオプションは、アクションを選択する際に使用 **[!UICONTROL File listing]** できます。 サーバー上に存在するすべてのファイルのインデックスを **vars.filenames** イベント変数で作成できます。この変数では、ファイル名が「n」文字で区切ら **れていま** す。

1. タブの **[!UICONTROL If no files are found]** セクションでは、ア **[!UICONTROL Advanced options]** クティビティの開始時にエラーや存在しないファイルが検出された場合に、特定のアクションを設定できます。

   再試行を定義することもできます。 ワークフローの実行ログには、様々な再試行が表示されます。

   ![](assets/wkf_file_transfer_09.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

## 履歴化設定 {#historization-settings}

アクティビティが実行さ **[!UICONTROL Transfer file]** れるたびに、アップロードされたファイルまたはダウンロードされたファイルが専用のフォルダーに保存されます。 ワークフローのアクティビティごとに1 **[!UICONTROL Transfer file]** つのフォルダーが作成されます。 したがって、サーバー上の物理領域を保持するために、このフォルダーのサイズを制限できることが重要です。

そのためには、アクティビティの **[!UICONTROL Historization settings]** 内でを定 **[!UICONTROL Advanced options]** 義でき **[!UICONTROL Transfer File]** ます。

**[!UICONTROL Historization settings]** アクティビティのフォルダーの最大ファイル数または合計サイズを定義できます。 デフォルトでは、100個のファイルと50 MBのファイルが許可されます。

アクティビティが実行されるたびに、フォルダーは次のようにチェックされます。

* アクティビティの実行前に24時間以上作成されたファイルのみが考慮されます。
* 考慮に入れるファイルの数がパラメーターの値より大きい場合、許可され **[!UICONTROL Maximum number of files]** ている数に達するまで最も古いファイルが **[!UICONTROL Maximum number of files]** 削除されます。
* 考慮に入れるファイルの合計サイズがパラメーターの値より大きい場合は、許可されているサイズに達す **[!UICONTROL Maximum size (in MB)]** るまで、最も古いファイルが **[!UICONTROL Maximum size (in MB)]** 削除されます。

>[!NOTE]
アクティビティが再び実行されない場合、そのフォルダーはチェックも削除もされません。 この点を考慮して、大きなファイルを転送する場合は注意が必要です。

## 例 ：{#example}

次の例は、 **File転送アクティビティの設定を示しています** 。その後に、 **Load file** （ファイルの読み込み）アクティビティが続き、次に **Update data** （データの更新）アクティビティが続きます。 このワークフローの目的は、Adobe Campaignデータベースプロファイルを、ワークフローで回復したデータで追加または更新することです。

1. 「ファイルを転送」アクティビティ **をワークフロー** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. タブで、「 **[!UICONTROL Protocol]** SFTP」を選択し **ます**。
1. [外部アカウ **ントで定義された接続パラメータを使用する** ]オプションを選択します。
1. 外部アカウントの名前を入力します。
1. リモートサ **ーバーのファイルパスを入力します**。

   ![](assets/wkf_file_transfer_07.png)

1. アクティビティを確認し、ワークフローを保存します。

