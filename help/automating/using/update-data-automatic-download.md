---
title: ファイルの自動ダウンロードに基づくデータの更新
description: 次の例は、ファイル転送アクティビティに続いて「データを更新」アクティビティを使用して、自動的にダウンロードされたファイルを読み込みアクティビティの結果を示しています。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 70%

---

# ファイルの自動ダウンロードに基づくデータの更新 {#updating-data-automatic-file-download}

「ファイル読み込み」アクティビティは主に、「ファイル転送」アクティビティから取得したデータを構造化し、既存のデータに統合します。

次の例は、「ファイル転送」アクティビティから自動的に「ファイル読み込み」アクティビティがダウンロードされ、「データ更新」アクティビティがその後に実行された場合の結果を示しています。このワークフローでは、Adobe Campaign データベースを新しいプロファイルで拡張したり、インポートしたファイルから回復したデータを使用して既存のプロファイルを更新することを目的としています。

![](assets/load_file_workflow_ex1.png)

ワークフローを作成するには、次の手順に従います。

1. 「[Transfer file](../../automating/using/transfer-file.md)」アクティビティをワークフローにドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 目的のファイルを復元するようにアクティビティを設定します。 「**[!UICONTROL Protocol]**」タブで「**SFTP**」を選択します。
1. 「**Use connection parameters defined in an external account**」オプションを選択します。
1. 外部アカウントの名前を入力します。
1. **リモートサーバーのファイルパス**&#x200B;を入力します。

   ![](assets/wkf_file_transfer_07.png)

1. アクティビティを確認します。
1. [&#x200B; ファイルを読み込み &#x200B;](../../automating/using/load-file.md) アクティビティをワークフローにドラッグ&amp;ドロップし、**[!UICONTROL Transfer file]** アクティビティの後に配置します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 「**[!UICONTROL Execution]**」タブの「**[!UICONTROL File to load]**」セクションで、「**[!UICONTROL Use the file specified in the inbound transition]**」オプションをオンにします。

   ![](assets/wkf_file_loading8.png)

1. 前の指定内容に従って、アクティビティを設定します。
1. [&#x200B; データを更新 &#x200B;](../../automating/using/update-data.md) アクティビティをワークフローにドラッグ&amp;ドロップし、**[!UICONTROL Load file]** アクティビティの後に配置してから、設定します。

ワークフローが開始されると、アップロードされたファイルのデータが抽出され、Adobe Campaign データベースの拡張に使用されます。
