---
title: ファイル転送
description: '[ファイルの転送]アクティビティを使用すると、ファイルの受信や送信、ファイルの存在のテスト、Adobe Campaign内のリストファイルの送信が可能です。'
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
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 2%

---


# ファイル転送{#transfer-file}

## 説明 {#description}

![](assets/file_transfer.png)

この **[!UICONTROL Transfer file]** アクティビティを使用すると、ファイルの受信や送信、ファイルの存在のテスト、Adobe Campaign内のリストファイルの送信が可能です。

>[!CAUTION]
>
>20.3リリース以降、 **[!UICONTROL Transfer File]** アクティビティと共にダウンロードされたファイルはX日後に削除されます。XはWorkflowプロパティの **[!UICONTROL History in days]****[!UICONTROL Execution]** メニューの下のフィールドによって決定されます。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティの設定時に定義されます。 読み込むファイルは、例えば連絡先のリストである場合があります。

このアクティビティを使用すると、 **[!UICONTROL Load file]** アクティビティで構造化されるデータを回復できます。

**関連トピック：**

* [使用例： ファイルの自動ダウンロードに基づくデータの更新](../../automating/using/update-data-automatic-download.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Transfer file]** アクティビティをドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. フィールドのドロップダウンリストを使用して、次のアクティビティ操作のいずれかを選択します。 **[!UICONTROL Action]**

   ![](assets/wkf_file_transfer_01.png)

   * **ファイルのダウンロード**: ファイルをダウンロードできます。
   * **ファイルのアップロード**: ファイルをアップロードできます。 Adobe Campaignファイルからファイルをアップロードすると、 **[!UICONTROL Export audits]** メニューにログエントリが生成されます。 エクスポート監査の詳細については、「 [監査エクスポート](../../administration/using/auditing-export-logs.md) 」の項を参照してください。
   * **ファイルが存在するかどうかをテストします**: ファイルが存在するかどうかを確認できます。
   * **ファイルの一覧**: タブで定義されたサーバーに存在するファイルをリストでき **[!UICONTROL Protocol]** ます。 この操作は主にデバッグ目的で使用され、リモートサーバーからファイルをダウンロードする前に、必要に応じてアクティビティが構成されているかどうかを確認します。

1. 使用するプロトコルを選択します。
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blobストレージ](#azure-blob-configuration-wf)
   * [Adobe Campaignサーバーに存在するファイル](#files-server-configuration-wf)

1. 選択したプロトコルに応じて使用できる **[!UICONTROL Additional options]** セクションでは、プロトコルにパラメータを追加できます。 次の操作をおこなうことができます。

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: このオプションは、「 **[!UICONTROL File listing]** action」を選択するときに使用できます。この **[!UICONTROL General]** タブで使用できます。 サーバー上に存在するすべてのファイルのインデックスを **vars.filenames** イベント変数に作成できます。この変数では、ファイル名がn **** 文字で区切られています。

1. 「 **[!UICONTROL If no files are found]** 」 **[!UICONTROL Advanced options]** タブのセクションでは、アクティビティの起動時にエラーや存在しないファイルが検出された場合に、特定のアクションを設定できます。

   また、再試行を定義することもできます。 ワークフローの実行ログに様々な再試行が表示されます。

   ![](assets/wkf_file_transfer_09.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

### HTTPを使用した設定 {#HTTP-configuration-wf}

HTTPプロトコルを使用すると、外部アカウントーまたはURLからのファイルのダウンロードに開始を発生させることができます。

このプロトコルを使用して、オプションを選択でき **[!UICONTROL Use connection parameters defined in an external account]** ます。 この場合、ダウンロードするアカウントを選択し、ダウンロードするファイルのパスを指定します。
![](assets/wkf_file_transfer_03.png)

また、この **[!UICONTROL Quick configuration]** オプションを選択することもできます。 URLは「URL」フィールドに入力する必要があるだけです。
![](assets/wkf_file_transfer_04.png)

### SFTPを使用した設定 {#SFTP-configuration-wf}

SFTPプロトコルを使用すると、URLまたは外部アカウントからのファイルのダウンロードに開始を発生させることができます。

このプロトコルでは、「選択」 **[!UICONTROL Use connection parameters defined in an external account]** オプションを選択してから、ダウンロードするアカウントを選択し、ダウンロードするファイルのパスを指定できます。
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>ワイルドカードがサポートされます。

また、この **[!UICONTROL Quick configuration]** オプションを選択することもできます。 URLは「URL」フィールドに入力する必要があるだけです。

### Amazon S3での設定 {#S3-configuration-wf}

Amazon S3プロトコルを使用すると、URLまたは外部アカウントからAmazon Simpleストレージサービス(S3)を介してファイルを開始ダウンロードできます。

1. Amazon S3外部アカウントを選択します。 詳しくは、この[ページ](../../administration/using/external-accounts.md#amazon-s3-external-account)を参照してください。

2. またはを選択し **[!UICONTROL Define a file path]** ま **[!UICONTROL Use a dynamic file path]**&#x200B;す。

3. ダウンロードするファイルのパスを指定します。

   ![](assets/wkf_file_transfer_08.png)

4. 転送の完了時にソースファイルを削除する場合は、[ ]をオンにし **[!UICONTROL Delete the source files after transfer]**&#x200B;ます。

### Microsoft Azure Blobストレージとの構成 {#azure-blob-configuration-wf}

Microsoft Azure Blobプロトコルを使用すると、Microsoft Azure BlobストレージアカウントにあるBLOBにアクセスできます。

1. 外部アカウントを選択し **[!UICONTROL Microsoft Azure Blob]** ます。 詳しくは、この[ページ](../../administration/using/external-accounts.md#microsoft-azure-external-account)を参照してください。

1. またはを選択し **[!UICONTROL Define a file path]** ま **[!UICONTROL Use a dynamic file path]**&#x200B;す。

   ![](assets/wkf_file_transfer_10.png)

1. ダウンロードするファイルのパスを指定します。複数のBLOBと一致する場合があります。 この場合、 **[!UICONTROL File transfer]** アクティビティは、BLOBが見つかったごとに送信トランジションをアクティブ化します。 その後、アルファベット順に処理されます。

   >[!CAUTION]
   >
   >複数のファイル名に一致するワイルドカードはサポートされていません。 代わりに、プレフィックスを入力する必要があります。 そのプレフィックスに一致するすべてのBLOB名が有効です。

   ファイルパスの例を次のリストに示します。

   * **&quot;キャンペーン/&quot;**: は、コンテナのルートにあるキャンペーンフォルダー内のすべてのblobに一致します。
   * **&quot;キャンペーン/新規 —&quot;**: は、「new — 」で始まり、キャンペーンーフォルダーの下にあるファイル名を持つすべてのblobに一致します。
   * **&quot;&quot;**: 空のパスを追加すると、コンテナで使用可能なすべてのBLOBを一致させることができます。

### Adobe Campaignサーバー上に存在するファイルの設定 {#files-server-configuration-wf}

この **[!UICONTROL File(s) present on the Adobe Campaign server]** プロトコルは、リカバリするファイルを含むリポジトリに対応します。
メタ文字、ワイルドカード（*や？など） を使用して、ファイルをフィルターできます。

必要に応じて選択するか、 **[!UICONTROL Define a file path]** または **[!UICONTROL Use a dynamic file path]**&#x200B;この **[!UICONTROL Use a dynamic file path]** オプションを選択します。標準の式変数とイベント変数を使用して、転送するファイルの名前をパーソナライズできます。 詳しくは、「イベント変数を使用したアクティビティの [カスタマイズ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 」を参照してください。

パスは、Adobe Campaignサーバーのストレージ領域ディレクトリを基準とした相対パスである必要があります。 ファイルは、 **sftp&lt;yourinstancename>/** ディレクトリにあります。 また、ストレージ領域の上のディレクトリを参照することもできません。 次に例を示します。

    >**user&amp;lt;yourinstancename>/my_recipients.csv**が正しい。
    >
    >**../hello/my_recipients.csv**が正しくありません。
    >
    >**//myserver/hello/myrecipients.csv**が正しくありません。

## 履歴化設定 {#historization-settings}

アクティビティが実行されるたびに、アップロードされたファイルまたはダウンロードされたファイルが専用のフォルダーに保存されます。 **[!UICONTROL Transfer file]** ワークフローの **[!UICONTROL Transfer file]** アクティビティごとに1つのフォルダーが作成されます。 したがって、サーバー上の物理領域を保持するために、このフォルダーのサイズを制限できることが重要です。

そのためには、 **[!UICONTROL Historization settings]** アクティビティのでを定義し **[!UICONTROL Advanced options]****[!UICONTROL Transfer File]** ます。

**[!UICONTROL Historization settings]** アクティビティのフォルダーの最大数または合計サイズを定義できます。 デフォルトでは、100個のファイルと50 MBのファイルが許可されます。

アクティビティを実行するたびに、次のようにフォルダがチェックされます。

* アクティビティの実行が考慮されるのは、24時間以上前に作成されたファイルのみです。
* 考慮に入れるファイルの数が **[!UICONTROL Maximum number of files]** パラメーターの値より大きい場合、最も古いファイルは、 **[!UICONTROL Maximum number of files]** 許容される数に達するまで削除されます。
* 考慮に入れるファイルの合計サイズが **[!UICONTROL Maximum size (in MB)]** パラメーターの値より大きい場合、最も古いファイルは、 **[!UICONTROL Maximum size (in MB)]** 許可される値に達するまで削除されます。

>[!NOTE]
>
>アクティビティが再び実行されない場合、そのフォルダはチェックされず、削除されません。 この点に留意し、大きなファイルを転送する場合は注意が必要です。
