---
title: 外部ファイルへのプロファイルのエクスポート
description: このユースケースでは、Adobe Campaign以外でデータを使用できるように、プロファイルのリストを外部ファイル形式で書き出す方法を示します。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
TQID: https://experienceleague.adobe.com/wVo-oDNJNFmaNcb7p6fACNIfrPG-2Y-VbXxXG0P8XTQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 68%

---

# 外部ファイルへのプロファイルのエクスポート {#exporting-profiles-external-file}

次の例は、「**[!UICONTROL Query]**」アクティビティの後に「**[!UICONTROL Extract file]**」アクティビティを設定する方法を示しています。

このワークフローの目的は、プロファイルのリストを外部ファイルの形式でエクスポート、Adobe Campaign 外でデータを使用できるようにすることです。

1. [ ファイルを抽出](../../automating/using/extract-file.md) アクティビティをワークフローにドラッグ&amp;ドロップし、[ クエリ ](../../automating/using/query.md) アクティビティの後に配置します。

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
1. **[!UICONTROL Extract file]** アクティビティの後に[ ファイル転送](../../automating/using/transfer-file.md) アクティビティをドラッグ&amp;ドロップして、外部アカウントの抽出ファイルを回復します。
1. アクティビティを開き、**[!UICONTROL File upload]** アクションを選択します。

   ![](assets/wkf_data_export11.png)

1. 外部アカウントを選択し、サーバー上のフォルダーのパスを入力します。

   ![](assets/wkf_data_export12.png)

1. アクティビティを確認し、ワークフローを保存します。
1. ワークフローを開始します。

   ワークフローが正しく実行されると、抽出したファイルが外部アカウントで利用できるようになります。
