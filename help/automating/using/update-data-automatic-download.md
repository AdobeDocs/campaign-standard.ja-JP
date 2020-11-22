---
solution: Campaign Standard
product: campaign
title: ファイルの自動ダウンロードに基づくデータの更新
description: '次の例は、「ファイル転送」アクティビティから自動的に「ファイル読み込み」アクティビティがダウンロードされ、「データ更新」アクティビティがその後に実行された場合の結果を示しています。 '
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%

---


# ファイルの自動ダウンロードに基づくデータの更新 {#updating-data-automatic-file-download}

「ファイル読み込み」アクティビティは主に、「ファイル転送」アクティビティから取得したデータを構造化し、既存のデータに統合します。

次の例は、「ファイル転送」アクティビティから自動的に「ファイル読み込み」アクティビティがダウンロードされ、「データ更新」アクティビティがその後に実行された場合の結果を示しています。このワークフローでは、Adobe Campaign データベースを新しいプロファイルで拡張したり、インポートしたファイルから回復したデータを使用して既存のプロファイルを更新することを目的としています。

![](assets/load_file_workflow_ex1.png)

ワークフローを構築するには、次の手順に従います。

1. 「[Transfer file](../../automating/using/transfer-file.md)」アクティビティをワークフローにドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アクティビティを設定し、希望のファイルが回復されるようにします。 「**[!UICONTROL Protocol]**」タブで「**SFTP**」を選択します。
1. 「**Use connection parameters defined in an external account**」オプションを選択します。
1. 外部アカウントの名前を入力します。
1. **リモートサーバーのファイルパス**&#x200B;を入力します。

   ![](assets/wkf_file_transfer_07.png)

1. アクティビティを確認します。
1. Drag and drop a [Load file](../../automating/using/load-file.md) activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 「**[!UICONTROL Execution]**」タブの「**[!UICONTROL File to load]**」セクションで、「**[!UICONTROL Use the file specified in the inbound transition]**」オプションをオンにします。

   ![](assets/wkf_file_loading8.png)

1. 前の指定内容に従って、アクティビティを設定します。
1. Drag and drop an [Update data](../../automating/using/update-data.md) activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it.

ワークフローが開始されると、アップロードされたファイルのデータが抽出され、Adobe Campaign データベースの拡張に使用されます。
