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
ht-degree: 24%

---

# データのインポートおよびエクスポートについて{#about-data-import-and-export}

ビジネスニーズに応じて、Adobe Campaignでのデータのインポートおよびエクスポートには、いくつかの方法があります。

* **パッケージ**:パッケージは、Adobe Campaignインスタンスから別のインスタンスに設定とデータセットを書き出し、読み込むことができるXMLファイルです。システムの更新は、パッケージの読み込みもおこなわれます。
* **リスト**:すべてのリスト画面を設定し、別のファイルに書き出した表示データを指定できます。
* **ワークフロー**:ファイルからデータをインポートし、それを使用してデータベースを更新したり、eメールを送信したりします。また、ファイルに書き出すデータを選択することもできます。 ワークフローは、プロファイルのインポートなど、定期的な更新を自動化する最適な方法です。

   * 「**[!UICONTROL Load file]**」アクティビティを使用すると、1 つの構造化されたフォームにデータをインポートして、Adobe Campaign で使用することができます。データは一時的にインポートされます。このデータを Adobe Campaign データベースに確実に統合するには別のアクティビティが必要です。このアクティビティの使用方法について詳しくは、[この節](../../automating/using/load-file.md)を参照してください。
   * 「**[!UICONTROL Transfer file]**」アクティビティを使用すると、ファイルの送受信、ファイルの有無のテスト、Adobe Campaign 内のファイルの一覧表示ができます。外部ソースからファイルを取得する必要がある場合に備えて、 **[!UICONTROL Load file]**&#x200B;の前にこのアクティビティを使用できます。 このアクティビティの使用方法について詳しくは、[この節](../../automating/using/transfer-file.md)を参照してください。

インポートプロセスを設計する場合は、ニーズに合わせて調整できるワークフローテンプレートを使用することをお勧めします。 データをインポートするためのワークフローテンプレートの設定方法について詳しくは、[この使用例](../../automating/using/creating-import-workflow-templates.md)を参照してください。

Adobe Campaignでは、**インポートテンプレート**&#x200B;の設計で構成される、通常のインポートを簡単に実行する方法も提供しています。 インポートテンプレートは、専用の画面で使用できる専用のワークフローテンプレートです。 設計が完了したら、インポートを実行するユーザーはファイルをアップロードするだけで、インポートを簡略化できます。

**関連トピック**：

* [インポートテンプレートを使用したデータのインポート](../../automating/using/importing-data-with-import-templates.md)
* [インポートテンプレートの定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [パッケージの管理](../../automating/using/managing-packages.md)
