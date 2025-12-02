---
title: 外部ファイルへのプロファイルのエクスポート
description: このユースケースは、プロファイルのリストを外部ファイルの形式で書き出し、Adobe Campaignの外部でデータを使用できるようにする方法を示しています。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 68%

---

# 外部ファイルへのプロファイルのエクスポート {#exporting-profiles-external-file}

次の例は、「**[!UICONTROL Query]**」アクティビティの後に「**[!UICONTROL Extract file]**」アクティビティを設定する方法を示しています。

このワークフローの目的は、プロファイルのリストを外部ファイルの形式でエクスポート、Adobe Campaign 外でデータを使用できるようにすることです。

1. [&#x200B; ファイルを抽出 &#x200B;](../../automating/using/extract-file.md) アクティビティをワークフローにドラッグ&amp;ドロップし、[&#x200B; クエリ &#x200B;](../../automating/using/query.md) アクティビティの後に配置します。

   この例では、クエリは 18～30 歳のすべてのプロファイルで実行されます。

1. **[!UICONTROL Extract file]** アクティビティを開いて編集します。
1. 出力ファイルに名前を付けます。
1. 出力列を追加します。

   この例では、プロファイルのメール、年齢、生年月日、名、姓が出力列として追加されます。

   ![](assets/wkf_data_export6.png)

1. 「**[!UICONTROL File structure]**」タブをクリックして次を定義します。

   * CSV 出力形式

     ![](assets/wkf_data_export7.png)

   * 日付フォーマット

     ![](assets/wkf_data_export9.png)

1. アクティビティを確認します。
1. [&#x200B; ファイルを転送 &#x200B;](../../automating/using/transfer-file.md) アクティビティを **[!UICONTROL Extract file]** アクティビティの後にドラッグ&amp;ドロップして、抽出ファイルを外部アカウントに復元します。
1. アクティビティを開き、**[!UICONTROL File upload]** アクションを選択します。

   ![](assets/wkf_data_export11.png)

1. 外部アカウントを選択し、サーバー上のフォルダーのパスを入力します。

   ![](assets/wkf_data_export12.png)

1. アクティビティを確認し、ワークフローを保存します。
1. ワークフローを開始します。

   ワークフローが正しく実行されると、抽出したファイルが外部アカウントで利用できるようになります。
