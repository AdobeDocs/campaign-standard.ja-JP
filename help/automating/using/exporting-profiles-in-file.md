---
title: 外部ファイルへのプロファイルのエクスポート
description: この使用例では、データをAdobe Campaign外で使用できるように、プロファイルのリストを外部ファイルの形式で書き出す方法を示します。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---

# 外部ファイルへのプロファイルのエクスポート {#exporting-profiles-external-file}

次の例は、「**[!UICONTROL Query]**」アクティビティの後に「**[!UICONTROL Extract file]**」アクティビティを設定する方法を示しています。

このワークフローの目的は、プロファイルのリストを外部ファイルの形式で書き出し、Adobe Campaign 外でデータを使用できるようにすることです。

1. ドラッグ&amp;ドロップ [ファイルを抽出](../../automating/using/extract-file.md) アクティビティをワークフロー内に追加し、その後に配置します。 [クエリ](../../automating/using/query.md) アクティビティ。

   この例では、クエリは 18～30 歳のすべてのプロファイルで実行されます。

1. を開きます。 **[!UICONTROL Extract file]** アクティビティを編集します。
1. 出力ファイルに名前を付けます。
1. 出力列を追加します。

   この例では、プロファイルの E メール、年齢、生年月日、名、姓が出力列として追加されます。

   ![](assets/wkf_data_export6.png)

1. 「**[!UICONTROL File structure]**」タブをクリックして次を定義します。

   * CSV 出力形式

      ![](assets/wkf_data_export7.png)

   * 日付フォーマット

      ![](assets/wkf_data_export9.png)

1. アクティビティを確認します。
1. ドラッグ&amp;ドロップ [ファイル転送](../../automating/using/transfer-file.md) アクティビティ **[!UICONTROL Extract file]** 「 」アクティビティを使用して、抽出したファイルを外部アカウントで復元します。
1. アクティビティを開き、**[!UICONTROL File upload]** アクションを選択します。

   ![](assets/wkf_data_export11.png)

1. 外部アカウントを選択し、サーバー上のフォルダーのパスを入力します。

   ![](assets/wkf_data_export12.png)

1. アクティビティを確認し、ワークフローを保存します。
1. ワークフローを開始します。

   ワークフローが正しく実行されると、抽出したファイルが外部アカウントで利用できるようになります。
