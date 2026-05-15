---
title: データのインポートおよびエクスポートについて
description: Adobe Campaignを使用してデータを読み込みおよび書き出すさまざまな方法について説明します。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
TQID: https://experienceleague.adobe.com/WP1mlY9lQQu5qWqIx5L89VE6MxnOhxoYewTWAYwfFTI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 24%

---

# データのインポートおよびエクスポートについて{#about-data-import-and-export}

ビジネスニーズに応じて、Adobe Campaignでデータをインポートおよびエクスポートするには、いくつかの方法があります。

* **パッケージ**: パッケージは、Adobe Campaign インスタンスから別のインスタンスに設定とデータのセットを書き出して読み込むことができるXML ファイルです。 システムの更新は、パッケージのインポートを通じて実行されます。
* **リスト**：すべてのリスト画面を設定し、表示データを別のファイルに書き出すことができます。
* **ワークフロー**: ファイルからデータを読み込み、データベースの更新またはメール送信に使用します。 ファイルに書き出すデータを選択することもできます。 ワークフローは、プロファイルの読み込みなど、定期的な更新を自動化する最適な方法です。

   * 「**[!UICONTROL Load file]**」アクティビティを使用すると、1 つの構造化されたフォームにデータをインポートして、Adobe Campaign で使用することができます。 データは一時的にインポートされます。このデータを Adobe Campaign データベースに確実に統合するには別のアクティビティが必要です。 このアクティビティの使用方法について詳しくは、[このセクション &#x200B;](../../automating/using/load-file.md)を参照してください。
   * 「**[!UICONTROL Transfer file]**」アクティビティを使用すると、ファイルの送受信、ファイルの有無のテスト、Adobe Campaign 内のファイルの一覧表示ができます。 外部ソースからファイルを取得する必要がある場合は、**[!UICONTROL Load file]**&#x200B;の前にこのアクティビティを使用できます。 このアクティビティの使用方法について詳しくは、[このセクション &#x200B;](../../automating/using/transfer-file.md)を参照してください。

インポートプロセスを設計する場合は、ニーズに合わせてワークフローテンプレートを調整することをお勧めします。 データをインポートするためのワークフローテンプレートの設定方法について詳しくは、[このユースケース &#x200B;](../../automating/using/creating-import-workflow-templates.md)を参照してください。

Adobe Campaignでは、定期的なインポートを簡単に実行できます。これには、**インポートテンプレート**&#x200B;の設計が含まれます。 インポートテンプレートは、専用の画面から利用できる専用のワークフローテンプレートです。 設計が完了すると、読み込みを実行するユーザーは、読み込むファイルを簡単なビューにアップロードするだけで済みます。

**関連トピック**：

* [インポートテンプレートを使用したデータのインポート](../../automating/using/importing-data-with-import-templates.md)
* [インポートテンプレートの定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [パッケージの管理](../../automating/using/managing-packages.md)
