---
solution: Campaign Standard
product: campaign
title: データインポートおよびエクスポートについて
description: Adobe Campaignと共にデータを読み込んだり書き出したりする様々な方法について説明します。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---


# データインポートおよびエクスポートについて{#about-data-import-and-export}

ビジネスニーズに応じて、Adobe Campaignと共にデータをインポートおよびエクスポートする方法はいくつかあります。

* **パッケージ**:パッケージは、Adobe Campaignインスタンスから別のインスタンスへの設定やデータセットの書き出しと読み込みを可能にするXMLファイルです。システムの更新は、パッケージの読み込みによっても実行されます。
* **リスト**:すべてのリスト画面を設定し、表示データを別のファイルに書き出すことができます。
* **ワークフロー**:ファイルからデータをインポートし、それを使用してデータベースを更新したり電子メールを送信したりします。ファイル内に書き出すデータを選択することもできます。 ワークフローは、プロファイルの読み込みなど、定期的な更新を自動化する最善の方法です。

   * 「**[!UICONTROL Load file]**」アクティビティを使用すると、1 つの構造化されたフォームにデータをインポートして、Adobe Campaign で使用することができます。データは一時的にインポートされます。このデータを Adobe Campaign データベースに確実に統合するには別のアクティビティが必要です。このアクティビティの使い方の詳細は、[](../../automating/using/load-file.md)を参照してください。
   * 「**[!UICONTROL Transfer file]**」アクティビティを使用すると、ファイルの送受信、ファイルの有無のテスト、Adobe Campaign 内のファイルの一覧表示ができます。外部ソースからファイルを取得する必要がある場合に備えて、**[!UICONTROL Load file]**&#x200B;の前にこのアクティビティを使用できます。 このアクティビティの使い方の詳細は、[](../../automating/using/transfer-file.md)を参照してください。

読み込みプロセスを設計する際は、必要に応じて適応できるワークフローテンプレートを使用することをお勧めします。 データをインポートするワークフローテンプレートの設定方法について詳しくは、[この使用例](../../automating/using/creating-import-workflow-templates.md)を参照してください。

また、Adobe Campaignは、**インポートテンプレート**&#x200B;の設計で構成される、簡単な定期的な読み込みの実行方法をオファーします。 インポートテンプレートは、専用のワークフローテンプレートで、専用の画面から利用できます。 設計が完了すると、読み込みを実行するユーザは、読み込むファイルを簡単な表示でアップロードするだけで済みます。

**関連トピック**：

* [インポートテンプレートを使用したデータのインポート](../../automating/using/importing-data-with-import-templates.md)
* [インポートテンプレートの定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [パッケージの管理](../../automating/using/managing-packages.md)
