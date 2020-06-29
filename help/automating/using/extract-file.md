---
title: ファイル抽出
description: 「ファイルの抽出」アクティビティを使用すると、Adobe Campaignから外部ファイルの形式でデータを書き出すことができます。
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 1%

---


# ファイル抽出{#extract-file}

## 説明 {#description}

![](assets/export.png)

この **[!UICONTROL Extract file]** アクティビティを使用すると、外部ファイルの形式でAdobe Campaignからデータを書き出すことができます。

## 使用状況 {#context-of-use}

データの抽出方法は、アクティビティの設定時に定義されます。

>[!CAUTION]
>
>この **[!UICONTROL Extract file]** アクティビティを使用するには、 **[!UICONTROL Query]** アクティビティの後に配置する必要があります。

**関連トピック：**

* [使用例： 外部ファイル内のプロファイルの書き出し](../../automating/using/exporting-profiles-in-file.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Extract file]** アクティビティをドラッグ&amp;ドロップします。

   ![](assets/wkf_data_export1.png)

1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. **出力ファイルのラベルを入力します**。 ファイルのラベルは、一意になるように作成された日時と共に自動的に完成します。 次に例を示します。 ファイルの受信者_20150815_081532.txtは、2015年8月15日の08:15:32に生成されました。

   >[!NOTE]
   >
   >このフィールドの **[!UICONTROL formatDate]** 関数を使用して、ファイル名を指定できます。

1. 必要に応じて、フィールドのを選択して、出力ファイル **[!UICONTROL Compression]** をzip形式で圧縮でき **[!UICONTROL Add a pre-processing step]** ます。 出力ファイルは圧縮されてGZIPファイル(.gz)になります。

   また、この **[!UICONTROL Add a pre-processing step]** フィールドを使用すると、ファイルを抽出する前にファイルを暗号化できます。 暗号化されたファイルを使用する方法について詳しくは、 [この節を参照してください](../../automating/using/managing-encrypted-data.md)

1. 出力列を追加するには、 ![](assets/add_darkgrey-24px.png) または **[!UICONTROL Add an element]** ボタンをクリックします。

   ![](assets/wkf_data_export2.png)

   新しいウィンドウが開きます。

   ![](assets/wkf_data_export3.png)

1. 式を入力します。 これを行うには、既存の式を選択するか、 **式エディタを使用して新しいを作成します**。
1. 式を確認します。

   式が出力列に追加されます。

1. 必要な数の列を作成します。 列の式とラベルをクリックして、列を編集できます。

   プロファイルを書き出しており、外部ツールで使用する場合は、一意の識別子を書き出す必要があります。 デフォルトでは、すべてのプロファイルがデータベースに追加される方法に応じて、固有の識別子を持つわけではありません。 詳しくは、「プロファイルに一意のIDを [生成する](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) 」を参照してください。

1. タブをクリックして、書き出すファイルの出力、日付、数値の形式を設定します。 **[!UICONTROL File structure]**

   定義済みリストの値を書き出す場合は、この **[!UICONTROL Export labels instead of internal values of enumerations]** オプションを選択します。 このオプションを使用すると、短いラベルを取得して、IDの代わりにわかりやすくすることができます。

1. 「 **[!UICONTROL Properties]** 」タブで、受信トランジションが空の場合に空のファイルをSFTPサーバーで作成してアップロードしないようにする **[!UICONTROL Do not generate a file if the inbound transition is empty]** オプションを選択します。
1. アクティビティの設定を確認し、ワークフローを保存します。
