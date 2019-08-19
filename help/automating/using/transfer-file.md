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
source-git-commit: 4fe36a1747aca69e8857cf415593086781947a47

---


# ファイルの転送{#transfer-file}

## 説明 {#description}

![](assets/file_transfer.png)

**[!UICONTROL Transfer file]** このアクティビティでは、ファイルの受信または送信、ファイルが存在するかどうかのテスト、Adobe Campaignのファイルのリストを実行できます。

## 使用コンテキスト {#context-of-use}

データの抽出方法は、アクティビティの設定時に定義されます。読み込むファイルは、連絡先のリストです。

このアクティビティを使用して、 **[!UICONTROL Load file]** アクティビティで構造化されたデータを回復できます。

## 設定 {#configuration}

1. アクティビティを **[!UICONTROL Transfer file]** ワークフローにドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用してそのアクティビティを開きます。
1. **[!UICONTROL Action]** フィールドのドロップダウンリストを使用して、次のいずれかのアクティビティアクションを選択します。

   ![](assets/wkf_file_transfer_01.png)

   * **ファイルのダウンロード**:を使用すると、ファイルをダウンロードできます。
   * **ファイルのアップロード**:を使用すると、ファイルをアップロードできます。Adobe Campaignファイルからファイルをアップロードすると、メニューに **[!UICONTROL Export audits]** ログエントリが生成されます。エクスポート監査について詳しくは [、「監査エクスポート](../../administration/using/auditing-export-logs.md) 」セクションを参照してください。
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
      * 読み込んだファイルを並べ替える場合は、セクションから **[!UICONTROL Sort alphanumerically]** オプションを選択 **[!UICONTROL Additional options]** します。ファイルは順番に処理されます。

         ![](assets/wkf_file_transfer_sort.png)
   * **Adobe Campaignサーバーに存在するファイル**:このプロトコルは、回復するファイルを含むリポジトリに対応しています。

      メタ文字またはワイルドカード（*や?）などを使用してファイルをフィルタリングできます。

      このフィールドに入力し、アクティビティを確認して、このプロトコルを使用します。

      >[!NOTE]
      >
      >パスは、Adobe Campaignサーバーの記憶領域ディレクトリからの相対パスである必要があります。ファイルは **sftp&lt; yourinstancename&gt;/** ディレクトリにあります。ストレージスペースの上にあるディレクトリを参照することもできません。次に例を示します。 **user&lt; yourinstancename&gt;/my_ recipient. csv** が正しい。**../hello/my_recipients.csv** が正しくない。**//myserver/hello/myrecipients.csv** が正しくない。
   プロトコルを選択し、関連するフィールドを入力します。

   **[!UICONTROL Use a dynamic file path]** 各プロトコルで使用できるオプションを使用すると、標準の式とイベント変数を使用して、転送するファイルの名前をパーソナライズできます。これについて詳しくは、「イベント変数を使用したアクティビティ [のカスタマイズ」](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) を参照してください。

1. **[!UICONTROL Additional options]** 選択したプロトコルに応じて使用できるセクションでは、プロトコルにパラメーターを追加できます。次のことができます。

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:このオプションは **[!UICONTROL File listing]** 、アクションを選択するときに使用できます。ファイル名が"n"文字で区切られている **vars. filename** イベント変数内のサーバーに存在するすべてのファイルをインデックス作成 **** できます。

1. タブの **[!UICONTROL If no files are found]** セクション **[!UICONTROL Advanced options]** では、アクティビティの開始時にエラーまたは存在しないファイルが検出された場合に、特定のアクションを設定できます。

   再試行を定義することもできます。ワークフロー実行ログには、様々な再試行が表示されます。

   ![](assets/wkf_file_transfer_09.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

## 履歴化の設定 {#historization-settings}

**[!UICONTROL Transfer file]** アクティビティが実行されるたびに、アップロードされたファイルまたはダウンロードされたファイルが専用フォルダーに保存されます。ワークフローのアクティビティごと **[!UICONTROL Transfer file]** に1つのフォルダーが作成されます。したがって、サーバー上の物理的な空間を維持するために、このフォルダーのサイズを制限することが重要です。

そのためには、アクティビティ **[!UICONTROL Historization settings]** の中で **[!UICONTROL Advanced options]** 定義 **[!UICONTROL Transfer File]** できます。

**[!UICONTROL Historization settings]** アクティビティのフォルダーの最大数または合計サイズを定義できます。デフォルトでは、100個のファイルと50MBが認証されています。

アクティビティが実行されるたびに、次のようにフォルダーがチェックされます。

* アクティビティの実行が考慮されるまでに24時間以上作成されたファイルのみが考慮されます。
* 考慮したファイル数が **[!UICONTROL Maximum number of files]** パラメーターの値よりも大きい場合、最も古いファイルは **[!UICONTROL Maximum number of files]** 許可されるまで削除されます。
* 考慮したファイルの合計サイズが **[!UICONTROL Maximum size (in MB)]** パラメーターの値よりも大きい場合、許可されるまで最も古いファイルは **[!UICONTROL Maximum size (in MB)]** 削除されます。

>[!NOTE]
アクティビティが再度実行されない場合、そのフォルダーはチェックされず、削除されません。大きなファイルを転送する際は、注意が必要です。

## 例 {#example}

次の例で **は、ファイル転送** アクティビティの設定を示しています。この設定に続けて **、"Load"データ** アクティビティが **実行さ** れます。このワークフローの目的は、ワークフローによって回復されるデータを使用してAdobe Campaignデータベースプロファイルを追加または更新することです。

1. ワークフローに **転送ファイル** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用してそのアクティビティを開きます。
1. **[!UICONTROL Protocol]** タブで、「 **SFTP**」を選択します。
1. 外部アカウント **** オプションで定義されている接続パラメーターを使用します。
1. 外部アカウントの名前を入力します。
1. リモートサーバー上の **ファイルパスを入力**&#x200B;します。

   ![](assets/wkf_file_transfer_07.png)

1. アクティビティを確認し、ワークフローを保存します。

