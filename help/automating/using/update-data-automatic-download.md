---
title: ファイルの自動ダウンロードに基づくデータの更新
description: 次の例は、「ファイル転送」アクティビティから自動的に「ファイル読み込み」アクティビティがダウンロードされ、「データ更新」アクティビティがその後に実行された場合の結果を示しています。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
TQID: 'https://experienceleague.adobe.com/q-u5dH48a4wea1yStaF-QekcD9VaS2NjDhWnSQc6QGU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%
---
# ファイルの自動ダウンロードに基づくデータの更新 {#updating-data-automatic-file-download}

「ファイル読み込み」アクティビティは主に、「ファイル転送」アクティビティから取得したデータを構造化し、既存のデータに統合します。

次の例は、「ファイル転送」アクティビティから自動的に「ファイル読み込み」アクティビティがダウンロードされ、「データ更新」アクティビティがその後に実行された場合の結果を示しています。 このワークフローでは、Adobe Campaign データベースを新しいプロファイルで拡張したり、インポートしたファイルから回復したデータを使用して既存のプロファイルを更新することを目的としています。

![](assets/load_file_workflow_ex1.png)

ワークフローを構築するには、次の手順に従います。

1. 「[Transfer file](../../automating/using/transfer-file.md)」アクティビティをワークフローにドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 必要なファイルを復元できるように、アクティビティを設定します。 「**[!UICONTROL Protocol]**」タブで「**SFTP**」を選択します。
1. 「**Use connection parameters defined in an external account**」オプションを選択します。
1. 外部アカウントの名前を入力します。
1. **リモートサーバーのファイルパス**&#x200B;を入力します。

   ![](assets/wkf_file_transfer_07.png)

1. アクティビティを確認します。
1. [ ファイルを読み込み](../../automating/using/load-file.md) アクティビティをワークフローにドラッグ&amp;ドロップし、**[!UICONTROL Transfer file]** アクティビティの後に配置します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 「**[!UICONTROL Execution]**」タブの「**[!UICONTROL File to load]**」セクションで、「**[!UICONTROL Use the file specified in the inbound transition]**」オプションをオンにします。

   ![](assets/wkf_file_loading8.png)

1. 前の指定内容に従って、アクティビティを設定します。
1. [ データの更新](../../automating/using/update-data.md) アクティビティをワークフローにドラッグ&amp;ドロップし、**[!UICONTROL Load file]** アクティビティの後に配置してから設定します。

ワークフローが開始されると、アップロードされたファイルのデータが抽出され、Adobe Campaign データベースの拡張に使用されます。
