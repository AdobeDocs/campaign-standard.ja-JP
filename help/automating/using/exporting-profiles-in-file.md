---
title: 外部ファイル内のプロファイルの書き出し
description: この使用例は、プロファイルのリストを外部ファイルの形式でエクスポートし、Adobe Campaign外でデータを使用できるようにする方法を示します。
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
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---


# 外部ファイル内のプロファイルの書き出し {#exporting-profiles-external-file}

次の例は、 **[!UICONTROL Extract file]** アクティビティ後に **[!UICONTROL Query]** アクティビティを設定する方法を示しています。

このワークフローの目的は、プロファイルのリストを外部ファイルの形式で書き出し、Adobe Campaign外でデータを使用できるようにすることです。

1. 「 [ファイルの](../../automating/using/extract-file.md) 抽出 [」アクティビティをワークフローにドラッグ&amp;ドロップし、クエリ](../../automating/using/query.md) アクティビティの後に配置します。

   この例では、クエリは18 ～ 30歳のすべてのプロファイルで実行されます。

1. アクティビティを開いて編集します。 **[!UICONTROL Extract file]**
1. 出力ファイルに名前を付けます。
1. 追加出力列

   この例では、プロファイルの電子メール、年齢、生年月日、名、姓が出力列として追加されます。

   ![](assets/wkf_data_export6.png)

1. タブをクリックして次を定義し **[!UICONTROL File structure]** ます。

   * CSV出力形式

      ![](assets/wkf_data_export7.png)

   * 日付フォーマット

      ![](assets/wkf_data_export9.png)

1. アクティビティを確認します。
1. アクティビティの後に[ [転送ファイル](../../automating/using/transfer-file.md)**[!UICONTROL Extract file]** ]アクティビティをドラッグ&amp;ドロップして、抽出ファイルを外部アカウントに回復します。
1. アクティビティを開き、 **[!UICONTROL File upload]** 操作を選択します。

   ![](assets/wkf_data_export11.png)

1. 外部アカウントを選択し、サーバー上のフォルダーのパスを入力します。

   ![](assets/wkf_data_export12.png)

1. アクティビティを確認し、ワークフローを保存します。
1. ワークフローを開始します。

   ワークフローが正しく実行されると、抽出されたファイルが外部アカウントーで利用できるようになります。
