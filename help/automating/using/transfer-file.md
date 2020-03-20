---
title: ファイル転送
description: ファイルの転送アクティビティを使用すると、ファイルの受信や送信、Adobe Campaign内のファイルの有無のテスト、ファイルのリスト表示を行うことができます。
page-status-flag: never-activated
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# ファイル転送{#transfer-file}

## 説明 {#description}

![](assets/file_transfer.png)

アクティビティ **[!UICONTROL Transfer file]** を使用すると、ファイルの受信や送信、Adobe Campaign内のファイルの有無のテスト、ファイルのリスト表示を行うことができます。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティが設定されるときに定義されます。 たとえば、ロードするファイルは連絡先のリストです。

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
1. 使用するプロトコルを選択します。
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blobストレージ](#azure-blob-configuration-wf)
   * [Adobe Campaignサーバーに存在するファイル](#files-server-configuration-wf)

1. 選択し **[!UICONTROL Additional options]** たプロトコルに応じて使用できるセクションでは、プロトコルにパラメータを追加できます。 次の操作をおこなうことができます。

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:このオプションは、アクションを選択する際に使用 **[!UICONTROL File listing]** できます。 サーバー上に存在するすべてのファイルのインデックスを **vars.filenames** イベント変数で作成できます。この変数では、ファイル名が「n」文字で区切ら **れています** 。

1. タブの **[!UICONTROL If no files are found]** セクションで **[!UICONTROL Advanced options]** は、アクティビティの開始時にエラーや存在しないファイルが検出された場合に、特定のアクションを設定できます。

   再試行を定義することもできます。 ワークフローの実行ログには、様々な再試行が表示されます。

   ![](assets/wkf_file_transfer_09.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

### HTTPを使用した設定 {#HTTP-configuration-wf}

HTTPプロトコルを使用すると、外部アカウントまたはURLからファイルのダウンロードを開始できます。

このプロトコルを使用して、オプションを選択で **[!UICONTROL Use connection parameters defined in an external account]** きます。 この場合、ダウンロードするアカウントを選択し、ダウンロードするファイルのパスを指定します。
![](assets/wkf_file_transfer_03.png)

このオプションを選択することも **[!UICONTROL Quick configuration]** できます。 URLは「URL」フィールドにのみ入力する必要があります。
![](assets/wkf_file_transfer_04.png)

### SFTPを使用した設定 {#SFTP-configuration-wf}

SFTPプロトコルを使用すると、URLまたは外部アカウントからファイルのダウンロードを開始できます。

このプロトコルを使用すると、オプション **[!UICONTROL Use connection parameters defined in an external account]** を選択し、ダウンロードするアカウントを選択して、ダウンロードするファイルのパスを指定できます。
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>ワイルドカードがサポートされています。

このオプションを選択することも **[!UICONTROL Quick configuration]** できます。 URLは「URL」フィールドにのみ入力する必要があります。

### Amazon S3での設定 {#S3-configuration-wf}

Amazon S3プロトコルを使用すると、URLまたはAmazon Simple Storage Service(S3)を介した外部アカウントからのファイルのダウンロードを開始できます。

1. Amazon S3外部アカウントを選択します。 詳しくは、この[ページ](../../administration/using/external-accounts.md#amazon-s3-external-account)を参照してください。

2. またはを選択しま **[!UICONTROL Define a file path]** す **[!UICONTROL Use a dynamic file path]**。

3. ダウンロードするファイルのパスを指定します。

   ![](assets/wkf_file_transfer_08.png)

4. 転送が完了したときにソースファイルを削除する場合は、をチェックしま **[!UICONTROL Delete the source files after transfer]**&#x200B;す。

### Microsoft Azure BLOBストレージの構成 {#azure-blob-configuration-wf}

Microsoft Azure BLOBプロトコルを使用すると、Microsoft Azure BLOBストレージアカウントにあるBLOBにアクセスできます。

1. 外部アカウント **[!UICONTROL Microsoft Azure Blob]** を選択します。 詳しくは、この[ページ](../../administration/using/external-accounts.md#microsoft-azure-external-account)を参照してください。

1. またはを選択しま **[!UICONTROL Define a file path]** す **[!UICONTROL Use a dynamic file path]**。

   ![](assets/wkf_file_transfer_10.png)

1. ダウンロードするファイルのパスを指定します。複数のBLOBと一致する場合があります。 この場合、アクティビティは、BLOB **[!UICONTROL File transfer]** が見つかるたびに送信遷移をアクティブ化します。 その後、アルファベット順に処理されます。

   >[!CAUTION]
   >
   >複数のファイル名に一致するワイルドカードはサポートされていません。 代わりに、プレフィックスを入力する必要があります。 そのプレフィックスに一致するすべてのBLOB名が有効です。

   次に、ファイルパスの例を示します。

   * **&quot;campaign/&quot;**:は、コンテナのルートにあるCampaignフォルダー内のすべてのBLOBに一致します。
   * **&quot;campaign/new-&quot;**:は、「new — 」で始まり、Campaignフォルダーの下にあるファイル名を持つすべてのBLOBに一致します。
   * **&quot;&quot;**:空のパスを追加すると、コンテナ内で使用可能なすべてのBLOBに一致させることができます。

### Adobe Campaignサーバー上に存在するファイルの設定 {#files-server-configuration-wf}

このプ **[!UICONTROL File(s) present on the Adobe Campaign server]** ロトコルは、リカバリするファイルを含むリポジトリに対応します。
メタ文字、ワイルドカード（*や？など）を使用して、ファイルをフィルタリングできます。

またはオプションを選択し **[!UICONTROL Define a file path]** ます。 **[!UICONTROL Use a dynamic file path]**&#x200B;標準 **[!UICONTROL Use a dynamic file path]** 式とイベント変数を使用して、転送するファイルの名前をパーソナライズできます。 詳しくは、イベント変数を使用したアクティビティ [のカスタマイズの節を参照してください](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 。

パスは、Adobe Campaignサーバーの記憶領域ディレクトリからの相対パスである必要があります。 ファイルは、 **sftp&lt;yourinstancename>/ディレクトリにあり** ます。 また、記憶領域の上のディレクトリを参照することもできません。 例：

    >**user&amp;lt;yourinstancename>/my_recipients.csv**が正しい。
    >
    >**../hello/my_recipients.csv**が正しくありません。
    >
    >**//myserver/hello/myrecipients.csv**が正しくありません。

## 履歴化設定 {#historization-settings}

アクティビティが実行 **[!UICONTROL Transfer file]** されるたびに、アップロードまたはダウンロードされたファイルが専用のフォルダーに保存されます。 ワークフローの各アクティビティに対して1 **[!UICONTROL Transfer file]** つのフォルダーが作成されます。 したがって、サーバー上の物理領域を保持するために、このフォルダーのサイズを制限することが重要です。

これを行うには、アクティビティの **[!UICONTROL Historization settings]** でを定義 **[!UICONTROL Advanced options]** する必要があ **[!UICONTROL Transfer File]** ります。

**[!UICONTROL Historization settings]** アクティビティのフォルダーの最大ファイル数または合計サイズを定義できます。 デフォルトでは、100個のファイルと50 MBのファイルが認証されます。

アクティビティが実行されるたびに、フォルダーは次のようにチェックされます。

* アクティビティの実行が行われる24時間以上前に作成されたファイルのみが考慮されます。
* 考慮に入れるファイルの数がパラメーターの値より大きい場合は、許可さ **[!UICONTROL Maximum number of files]** れている数に達するまで最も古いファイルが **[!UICONTROL Maximum number of files]** 削除されます。
* 考慮するファイルの合計サイズがパラメーターの値より大きい場合は、許可さ **[!UICONTROL Maximum size (in MB)]** れる値に達するまで最も古いファイルが **[!UICONTROL Maximum size (in MB)]** 削除されます。

>[!NOTE]
>
>アクティビティが再び実行されない場合、そのフォルダはチェックも削除もされません。 この点を考慮し、大きなファイルを転送する場合は注意が必要です。

## 例 ：{#example}

次の例は、 **File transfer** （ファイルの読み込み）アクティビティの後に、 **Load file** （ファイルの読み込み）アクティビティと **Update data（データの更新）アクティビティの設定を示しています** 。 このワークフローの目的は、Adobe Campaignデータベースプロファイルを、ワークフローで回復したデータで追加または更新することです。

1. 「ファイルを転送」アクティビティ **をワークフロー** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. タブで、「 **[!UICONTROL Protocol]** SFTP」を選択 **します**。
1. [外部アカウ **ントで定義された接続パラメータを使用する** ]オプションを選択します。
1. 外部アカウントの名前を入力します。
1. リモートサ **ーバーのファイルパスを入力します**。

   ![](assets/wkf_file_transfer_07.png)

1. アクティビティを確認し、ワークフローを保存します。

