---
title: ファイル転送
description: '[ファイルの転送]アクティビティを使用すると、ファイルの受信や送信、ファイルの存在のテスト、リストファイルのAdobe Campaign。'
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
source-git-commit: 7f203ff0e635faf802a5577f761dc308dae4ab66

---


# ファイル転送{#transfer-file}

## 説明 {#description}

![](assets/file_transfer.png)

この **[!UICONTROL Transfer file]** アクティビティを使用すると、ファイルの受信や送信、ファイルの有無のテスト、リストファイルのAdobe Campaign。

## 使用状況 {#context-of-use}

データの抽出方法は、データの設定時にアクティビティされます。 ロードするファイルは、たとえば接触のリストである場合があります。

このアクティビティを使用して、データを回復し、そのデータがアクティビティで構造化され **[!UICONTROL Load file]** ます。

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Transfer file]** アクティビティをドロップします。
1. アクティビティを選択し、表示されるクイックアク ![](assets/edit_darkgrey-24px.png) ションのボタンを使用して開きます。
1. フィールドのドロップダウンリストを使用し **[!UICONTROL Action]** て、次のいずれかのアクションをアクティビティします。

   ![](assets/wkf_file_transfer_01.png)

   * **ファイルのダウンロード**:ファイルをダウンロードできます。
   * **ファイルのアップロード**:ファイルをアップロードできます。 ファイルをAdobe Campaignファイルからアップロードすると、メニューにログエントリが生成 **[!UICONTROL Export audits]** されます。 エクスポート監査の詳細については、「エクスポートの監査 [](../../administration/using/auditing-export-logs.md) 」を参照してください。
   * **ファイルが存在するかどうかを確認する**:ファイルが存在するかどうかを確認できます。
   * **ファイル一覧**:タブで定義されたリスト上にあるファイルをサーバーにで **[!UICONTROL Protocol]** きます。 このアクションは主にデバッグ目的で使用され、リモートサーバーからファイルをダウンロードする前に、アクティビティがニーズに合わせて設定されているかどうかを確認します。

1. 使用するプロトコルを選択します。
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blobストレージ](#azure-blob-configuration-wf)
   * [Adobe Campaignサーバーに存在するファイル](#files-server-configuration-wf)

1. 選択し **[!UICONTROL Additional options]** たプロトコルに応じて使用できるセクションでは、プロトコルにパラメータを追加できます。 次の操作をおこなうことができます。

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:このオプションは、タブでアクションを選 **[!UICONTROL File listing]** 択する際に使用で **[!UICONTROL General]** きます。 サーバ上に存在するすべてのファイルのインデックスを **vars.filenames** イベント変数内で作成できます。この変数内では、ファイル名が「n」文字で区切ら **れています** 。

1. タブの **[!UICONTROL If no files are found]** セクションで **[!UICONTROL Advanced options]** は、アクティビティの起動時にエラーや存在しないファイルが検出された場合に、特定のアクションを設定できます。

   また、定義も可能です。再試行 異なる再試行がワークフローの実行ログに表示されます。

   ![](assets/wkf_file_transfer_09.png)

1. ワークフローの設定を確認し、アクティビティを保存します。

### HTTPを使用した設定 {#HTTP-configuration-wf}

HTTPプロトコルを使用すると、開始から、またはURLからのファイルのダウンロードを外部アカウントできます。

このプロトコルを使用して、オプションを選択で **[!UICONTROL Use connection parameters defined in an external account]** きます。 この場合、ダウンロードするアカウントを選択し、ダウンロードするファイルのパスを指定します。
![](assets/wkf_file_transfer_03.png)

このオプションを選択することも **[!UICONTROL Quick configuration]** できます。 URLは「URL」フィールドにのみ入力する必要があります。
![](assets/wkf_file_transfer_04.png)

### SFTPを使用した設定 {#SFTP-configuration-wf}

SFTPプロトコルを使用すると、URLまたは開始からファイルをダウンロードする際に外部アカウントが可能です。

このプロトコルを使用すると、オプション **[!UICONTROL Use connection parameters defined in an external account]** を選択し、ダウンロードするアカウントを選択して、ダウンロードするファイルのパスを指定できます。
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>ワイルドカードがサポートされています。

このオプションを選択することも **[!UICONTROL Quick configuration]** できます。 URLは「URL」フィールドにのみ入力する必要があります。

### Amazon S3での設定 {#S3-configuration-wf}

Amazon S3プロトコルを使用すると、URLまたは外部アカウントから、Amazon Simpleストレージサービス(S3)を介してファイルを開始ダウンロードできます。

1. 「Amazon S3」オプションを外部アカウントします。 詳しくは、この[ページ](../../administration/using/external-accounts.md#amazon-s3-external-account)を参照してください。

2. またはを選択しま **[!UICONTROL Define a file path]** す **[!UICONTROL Use a dynamic file path]**。

3. ダウンロードするファイルのパスを指定します。

   ![](assets/wkf_file_transfer_08.png)

4. 転送が完了したときにソースファイルを削除する場合は、をチェックしま **[!UICONTROL Delete the source files after transfer]**&#x200B;す。

### Microsoft Azure BLOBの構成ストレージ {#azure-blob-configuration-wf}

Microsoft Azure Blobプロトコルを使用すると、Microsoft Azure Blobプロトコルアカウント上のBLOBにアクセスできます。ストレージ

1. オプションを **[!UICONTROL Microsoft Azure Blob]** 外部アカウントします。 詳しくは、この[ページ](../../administration/using/external-accounts.md#microsoft-azure-external-account)を参照してください。

1. またはを選択しま **[!UICONTROL Define a file path]** す **[!UICONTROL Use a dynamic file path]**。

   ![](assets/wkf_file_transfer_10.png)

1. ダウンロードするファイルのパスを指定します。複数のBLOBと一致する場合があります。 この場合、アクティビティはBLOBが見つか **[!UICONTROL File transfer]** ったたびに送信トランジションをアクティブ化します。 その後、アルファベット順に処理されます。

   >[!CAUTION]
   >
   >複数のファイル名に一致するワイルドカードはサポートされていません。 代わりに、プレフィックスを入力する必要があります。 そのプレフィックスに一致するすべてのBLOB名が有効です。

   ファイルパスのリストの例を次に示します。

   * **&quot;キャンペーン/&quot;**:は、フォルダーのルートにあるキャンペーンフォルダー内のすべてのBLOBに一致します。コンテナーのルートにあるBLOBに一致します。
   * **&quot;キャンペーン/新規 —&quot;**:は、「new — 」で始まり、フォルダーの下にあるファイル名を持つすべてのBLOBに一致します。キャンペーンー
   * **&quot;&quot;**:空のパスを追加すると、そのパスで使用可能なすべてのBLOBに一致するコンテナです。

### ファイルがサーバーに存在するAdobe Campaign設定 {#files-server-configuration-wf}

このプ **[!UICONTROL File(s) present on the Adobe Campaign server]** ロトコルは、リカバリするファイルを含むリポジトリに対応します。
メタ文字、ワイルドカード（*や？など）を使用して、ファイルをフィルタリングできます。

またはオプションを選択し **[!UICONTROL Define a file path]** ます。 **[!UICONTROL Use a dynamic file path]**&#x200B;標準 **[!UICONTROL Use a dynamic file path]** の式変数とイベント変数を使用して、転送するファイルの名前をパーソナライズできます。 詳しくは、「変数を使用したアクティビティのカスタマ [イズ」の節を参照して](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 、

パスは、サーバーのストレージ領域ディレクトリからの相対パスである必要があります。 ファイルは、 **sftp&lt;yourinstancename>/ディレクトリにあり** ます。 また、ディレクトリスペースの上のディレクトリを参照することはストレージできません。 次に例を示します。

    >**user&amp;lt;yourinstancename>/my_recipients.csv**が正しい。
    >
    >**../hello/my_recipients.csv**が正しくありません。
    >
    >**//myserver/hello/myrecipients.csv**が正しくありません。

## 履歴化設定 {#historization-settings}

アクティビティが実行されるた **[!UICONTROL Transfer file]** びに、アップロードまたはダウンロードされたファイルが専用のフォルダーに保存されます。 ワークフローの各アクティビティに対して1つのフ **[!UICONTROL Transfer file]** ォルダが作成されます。 したがって、サーバー上の物理領域を保持するために、このフォルダーのサイズを制限することが重要です。

そのためには、のを定 **[!UICONTROL Historization settings]** 義で **[!UICONTROL Advanced options]** きま **[!UICONTROL Transfer File]** す。

**[!UICONTROL Historization settings]** を使用して、アクティビティのフォルダーの最大ファイル数または合計サイズを定義できます。 デフォルトでは、100個のファイルと50 MBのファイルが認証されます。

フォルダーが実行されるたびに、アクティビティは次のようにチェックされます。

* 24時間以上前に作成されたファイルのみが考慮され、アクティビティの実行が行われます。
* 考慮に入れるファイルの数がパラメーターの値より大きい場合は、許可さ **[!UICONTROL Maximum number of files]** れている数に達するまで最も古いファイルが **[!UICONTROL Maximum number of files]** 削除されます。
* 考慮するファイルの合計サイズがパラメーターの値より大きい場合は、許可さ **[!UICONTROL Maximum size (in MB)]** れる値に達するまで最も古いファイルが **[!UICONTROL Maximum size (in MB)]** 削除されます。

>[!NOTE]
>
>このアクティビティが再び実行されない場合、フォルダはチェックも削除もされません。 この点を考慮し、大きなファイルを転送する場合は注意が必要です。

## 例 ：{#example}

次の例は、ファイル転送 **アクティビティの設定を示しています** 。その後にファイルの読み込みアクティビティ、次に更新データ ******** アクティビティが続きます。 このワークフローの目的は、ワークフローで回復したデータを使用してAdobe Campaignデータベースプロファイルを追加または更新することです。

1. 「ファイルを転送」 **アクティビティを** 、ワークフローにドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアク ![](assets/edit_darkgrey-24px.png) ションのボタンを使用して開きます。
1. タブで、「 **[!UICONTROL Protocol]** SFTP」を選択 **します**。
1. [接続パラメ **ータの定義を使用する]オプションを外部アカウント** 。
1. 外部アカウント名
1. リモートサ **ーバーのファイルパスを入力します**。

   ![](assets/wkf_file_transfer_07.png)

1. ワークフローをアクティビティし、保存します。

