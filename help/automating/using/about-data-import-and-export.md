---
title: データのインポートおよびエクスポートについて
description: Adobe Campaignでデータをインポートおよびエクスポートする様々な方法について説明します。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 12%

---

# データのインポートおよびエクスポートについて{#about-data-import-and-export}

ビジネスニーズに応じて、Adobe Campaignでデータをインポートおよびエクスポートする方法がいくつかあります。

* **パッケージ**：パッケージは、設定やデータセットをAdobe Campaignインスタンスから別のインスタンスに書き出し、読み込むことができる XML ファイルです。 システムの更新は、パッケージの読み込みを通じても実行されます。
* **リスト**：すべてのリスト画面を設定し、別のファイルに書き出した表示データを指定できます。
* **ワークフロー**：ファイルからデータをインポートし、それを使用してデータベースを更新したり、E メールを送信したりします。 また、ファイルに書き出すデータを選択することもできます。 ワークフローは、プロファイルのインポートなど、定期的な更新を自動化する最適な方法です。

   * 「**[!UICONTROL Load file]**」アクティビティを使用すると、1 つの構造化されたフォームにデータをインポートして、Adobe Campaign で使用することができます。データは一時的にインポートされます。このデータをAdobe Campaignデータベースに確実に統合するには、別のアクティビティが必要です。 このアクティビティの使用方法について詳しくは、 [この節](../../automating/using/load-file.md).
   * The **[!UICONTROL Transfer file]** 「 」アクティビティを使用すると、ファイルの送受信、ファイルの有無のテスト、Adobe Campaign内のファイルの一覧表示ができます。 このアクティビティは、 **[!UICONTROL Load file]** 外部ソースからファイルを取得する必要がある場合に備えて、 このアクティビティの使用方法について詳しくは、 [この節](../../automating/using/transfer-file.md).

インポートプロセスを設計する際には、必要に応じて適応可能なワークフローテンプレートを使用することをお勧めします。 データをインポートするためのワークフローテンプレートの設定方法について詳しくは、 [この使用例](../../automating/using/creating-import-workflow-templates.md).

また、Adobe Campaignでは、 **テンプレートをインポート**. インポートテンプレートは、専用の画面から使用できる専用のワークフローテンプレートです。 設計が完了したら、インポートを実行するユーザーはファイルをアップロードするだけで、インポートは簡略表示になります。

**関連トピック**：

* [インポートテンプレートを使用したデータのインポート](../../automating/using/importing-data-with-import-templates.md)
* [インポートテンプレートの定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [パッケージの管理](../../automating/using/managing-packages.md)
