---
title: データのインポートおよびエクスポートについて
description: Adobe Campaignでデータをインポートおよびエクスポートする様々な方法について説明します。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 12%

---

# データのインポートおよびエクスポートについて{#about-data-import-and-export}

ビジネスニーズに応じて、Adobe Campaignでデータをインポートおよびエクスポートする方法はいくつかあります。

* **パッケージ**：パッケージは、Adobe Campaign インスタンスから別のインスタンスに設定とデータセットを書き出したり読み込んだりできる XML ファイルです。 システムの更新は、パッケージの読み込みからも実行されます。
* **リスト**：すべてのリスト画面を設定し、表示データを別のファイルに書き出すことができます。
* **ワークフロー**：ファイルからデータをインポートし、それを使用してデータベースを更新したりメールを送信したりします。 ファイルに書き出すデータを選択することもできます。 ワークフローは、プロファイルの読み込みなど、定期的な更新を自動化する最適な方法です。

   * 「**[!UICONTROL Load file]**」アクティビティを使用すると、1 つの構造化されたフォームにデータをインポートして、Adobe Campaign で使用することができます。データは一時的にインポートされるので、データをAdobe Campaign データベースに確実に統合するには、別のアクティビティが必要です。 このアクティビティの使用方法について詳しくは、[ この節 ](../../automating/using/load-file.md) を参照してください。
   * **[!UICONTROL Transfer file]** アクティビティでは、ファイルの送受信、ファイルの有無のテスト、Adobe Campaignでのファイルのリストアップが可能です。 外部ソースからファイルを取得する必要がある場合は、**[!UICONTROL Load file]** の前にこのアクティビティを使用できます。 このアクティビティの使用方法について詳しくは、[ この節 ](../../automating/using/transfer-file.md) を参照してください。

インポートプロセスを設計するときは、ニーズに合わせて調整できるワークフローテンプレートを使用することをお勧めします。 データをインポートするためのワークフローテンプレートの設定方法について詳しくは、[ このユースケース ](../../automating/using/creating-import-workflow-templates.md) を参照してください。

Adobe Campaignには、通常のインポートを実行するためのシンプルな方法も用意されています。この方法では、**インポートテンプレート** のデザインを行います。 インポートテンプレートは、専用の画面から使用できる専用のワークフローテンプレートです。 設計後、読み込みを実行するユーザーは、読み込むファイルを簡略化されたビューでアップロードするだけで済みます。

**関連トピック**：

* [インポートテンプレートを使用したデータのインポート](../../automating/using/importing-data-with-import-templates.md)
* [インポートテンプレートの定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [パッケージの管理](../../automating/using/managing-packages.md)
