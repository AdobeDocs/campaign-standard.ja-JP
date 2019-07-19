---
title: ファイルの抽出
seo-title: ファイルの抽出
description: ファイルの抽出
seo-description: ファイルアクティビティを抽出すると、Adobe Campaignから外部ファイルの形式でデータを書き出すことができます。
page-status-flag: 常にアクティブ化されていない
uuid: 631f0fbd-9e8d-4f77- a338- fcb7f4fc1774
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: data- management- activity
discoiquuid: a06509f9-4731-4187- b43d-3bfa361284d3
context-tags: fileExport、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Extract file{#extract-file}

## 説明 {#description}

![](assets/export.png)

**[!UICONTROL Extract file]** アクティビティでは、Adobe Campaignから外部ファイルの形式でデータを書き出すことができます。

## Context of use {#context-of-use}

データの抽出方法は、アクティビティの設定時に定義されます。

>[!CAUTION]
>
>**[!UICONTROL Extract file]** アクティビティを使用するには **[!UICONTROL Query]** 、アクティビティの後にアクティビティを配置する必要があります。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow.

   ![](assets/wkf_data_export1.png)

1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. **出力ファイルのラベルを入力**&#x200B;します。ファイルのラベルは、一意になるように作成された日時で自動的に完了します。次に例を示します。recipients_20150815_081532.txtファイルの場合、2015年8月15日15時15:32になります。

   >[!NOTE]
   >
   >It is possible to use the **[!UICONTROL formatDate]** function in this field to specify the file name.

1. If you like, you can zip the output file by selecting **[!UICONTROL Compression]** in the **[!UICONTROL Add a pre-processing step]** field. 出力ファイルはGZIPファイル（.gz）に圧縮されます。
1. Click the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button to add an output column.

   ![](assets/wkf_data_export2.png)

   新しいウィンドウが開きます。

   ![](assets/wkf_data_export3.png)

1. 式を入力します。To do this, you can select an existing expression or create a new one using the **expression editor**.
1. 式を確認します。

   式が出力列に追加されます。

1. 必要な数の列を作成します。式とラベルをクリックして、列を編集できます。

   プロファイルをエクスポートし、外部ツールで使用する場合は、一意の識別子を書き出してください。デフォルトでは、データベースに追加される方法に応じて、すべてのプロファイルに一意の識別子があります。For more information, refer to the [Generating a unique ID for profiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) section.

1. Click the **[!UICONTROL File structure]** tab to configure the output, date, and number formats for the file that will be exported.

   Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. このオプションを使用すると、IDの代わりに理解しやすい短いラベルを取得できます。

1. In the **[!UICONTROL Properties]** tab, select the **[!UICONTROL Do not generate a file if the inbound transition is empty]** option to avoid creating and uploading empty files on SFTP servers if the inbound transition is empty.
1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

The following example illustrates how to configure an **[!UICONTROL Extract file]** activity after a **[!UICONTROL Query]** activity.

このワークフローの目的は、プロファイルのリストを外部ファイル形式でエクスポートし、Adobe Campaign以外でデータを使用できるようにすることです。

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow and place it after the **[!UICONTROL Query]** activity.

   この例では、18~30歳のすべてのプロファイルでクエリーが実行されています。

1. ファイルアクティビティを抽出して編集します。
1. 出力ファイルに名前を付けます。
1. 出力列を追加します。

   この例では、電子メール、年齢、生年月日、プロファイルの姓と姓が出力列として追加されています。

   ![](assets/wkf_data_export6.png)

1. Click the **[!UICONTROL File structure]** tab to define:

   * CSV出力形式

      ![](assets/wkf_data_export7.png)

   * 日付形式

      ![](assets/wkf_data_export9.png)

1. アクティビティを確認します。
1. Drag and drop a **[!UICONTROL Transfer file]** activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Open the activity and choose the **[!UICONTROL File upload]** action.

   ![](assets/wkf_data_export11.png)

1. 外部アカウントを選択し、サーバー上のフォルダのパスを入力します。

   ![](assets/wkf_data_export12.png)

1. アクティビティを確認し、ワークフローを保存します。
1. ワークフローを開始します。

   ワークフローが正しく実行されると、抽出されたファイルが外部アカウントで使用できるようになります。

