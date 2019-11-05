---
title: ファイルの抽出
description: 「ファイルの抽出」アクティビティを使用すると、外部ファイルの形式でAdobe Campaignからデータをエクスポートできます。
page-status-flag: 非活性化の
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: データ管理活動
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ファイルの抽出{#extract-file}

## 説明 {#description}

![](assets/export.png)

このア **[!UICONTROL Extract file]** クティビティでは、外部ファイルの形式でAdobe Campaignからデータをエクスポートできます。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティを設定する際に定義します。

>[!CAUTION]
>
>アクティビティ **[!UICONTROL Extract file]** を使用するには、アクティビティの後 **[!UICONTROL Query]** にアクティビティを配置する必要があります。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Extract file]** にドラッグ&amp;ドロップします。

   ![](assets/wkf_data_export1.png)

1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 出力ファイルのラベルを **入力します**。 ファイルのラベルは、一意になるように作成された日時と共に自動的に完成します。 例：ファイルのrecipients_20150815_081532.txtでは、2015年8月15日08:15:32に生成されました。

   >[!NOTE]
   >
   >このフィールドの関数を使 **[!UICONTROL formatDate]** 用して、ファイル名を指定できます。

1. 必要に応じて、フィールド内のを選択して、出力ファイルのzip **[!UICONTROL Compression]** 圧縮を行い **[!UICONTROL Add a pre-processing step]** ます。 出力ファイルは圧縮されてGZIPファイル(.gz)になります。
1. 出力列を追加す ![](assets/add_darkgrey-24px.png) るには、ま **[!UICONTROL Add an element]** たはボタンをクリックします。

   ![](assets/wkf_data_export2.png)

   新しいウィンドウが開きます。

   ![](assets/wkf_data_export3.png)

1. 式を入力します。 これを行うには、既存の式を選択するか、式エディターを使用して新しい式を作 **成します**。
1. 式を確認します。

   出力列に式が追加されます。

1. 必要な数の列を作成します。 列の式とラベルをクリックして、列を編集できます。

   プロファイルを書き出して、外部ツールで使用する場合は、一意の識別子を書き出す必要があります。 デフォルトでは、すべてのプロファイルがデータベースに追加される方法に応じて一意の識別子を持つわけではありません。 詳しくは、「プロファイルの一意のID [の生成」の節を参照してください](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) 。

1. タブをク **[!UICONTROL File structure]** リックして、書き出すファイルの出力形式、日付形式、数値形式を設定します。

   列挙値をエクス **[!UICONTROL Export labels instead of internal values of enumerations]** ポートする場合は、このオプションを選択します。 このオプションを使用すると、IDの代わりに理解しやすい短いラベルを取得できます。

1. 受信トランジ **[!UICONTROL Properties]** ションが空の場合にSFTPサ **[!UICONTROL Do not generate a file if the inbound transition is empty]** ーバー上で空のファイルを作成してアップロードしないようにするには、タブでこのオプションを選択します。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、アクティビティの後にアクティビティを設 **[!UICONTROL Extract file]** 定する方法を示し **[!UICONTROL Query]** ています。

このワークフローの目的は、データをAdobe Campaignの外部で使用できるように、プロファイルのリストを外部ファイルの形式でエクスポートすることです。

1. アクティビティをワークフ **[!UICONTROL Extract file]** ローにドラッグ&amp;ドロップし、アクティビティの後に配置 **[!UICONTROL Query]** します。

   この例では、18 ～ 30才のすべてのプロファイルに対してクエリが実行されます。

1. ファイルの抽出アクティビティを開いて編集します。
1. 出力ファイルに名前を付けます。
1. 出力列を追加します。

   この例では、プロファイルの電子メール、年齢、生年月日、名、姓が出力列として追加されます。

   ![](assets/wkf_data_export6.png)

1. タブをクリッ **[!UICONTROL File structure]** クして次を定義します。

   * CSV出力形式

      ![](assets/wkf_data_export7.png)

   * 日付フォーマット

      ![](assets/wkf_data_export9.png)

1. アクティビティを確認します。
1. アクティビティの後にアクテ **[!UICONTROL Transfer file]** ィビティをドラッグ&amp;ド **[!UICONTROL Extract file]** ロップし、外部アカウントの抽出ファイルを回復します。
1. アクティビティを開き、アクションを選 **[!UICONTROL File upload]** 択します。

   ![](assets/wkf_data_export11.png)

1. 外部アカウントを選択し、サーバー上のフォルダーのパスを入力します。

   ![](assets/wkf_data_export12.png)

1. アクティビティを確認し、ワークフローを保存します。
1. ワークフローを開始します。

   ワークフローが正しく実行されると、抽出されたファイルは外部アカウントで使用できます。

