---
title: データインポートおよびエクスポートについて
description: Adobe Campaignと共にデータを読み込んだり書き出したりする様々な方法について説明します。
page-status-flag: never-activated
uuid: f6810364-555c-4b72-8a9c-4ae2fcb2ba63
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 31215773-6c0c-48f1-9101-da0ea2a366da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0deabe17442b679a340a4497945837b83b4c9207
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 6%

---


# データインポートおよびエクスポートについて{#about-data-import-and-export}

ビジネスニーズに応じて、Adobe Campaignと共にデータをインポートおよびエクスポートする方法はいくつかあります。

* **パッケージ**: パッケージは、Adobe Campaignインスタンスから別のインスタンスへの設定やデータセットの書き出しと読み込みを可能にするXMLファイルです。 システムの更新は、パッケージの読み込みによっても実行されます。
* **リスト**: すべてのリスト画面を設定し、表示データを別のファイルに書き出すことができます。
* **ワークフロー**: ファイルからデータをインポートし、それを使用してデータベースを更新したり電子メールを送信したりします。 ファイル内に書き出すデータを選択することもできます。 ワークフローは、プロファイルの読み込みなど、定期的な更新を自動化する最善の方法です。

   * この **[!UICONTROL Load file]** アクティビティを使用すると、1つの構造化されたフォームにデータを読み込んで、このデータをAdobe Campaignで使用できます。 データは一時的にインポートされ、Adobe Campaignデータベースに確実に統合するには別のアクティビティが必要です。 For more on how to use this activity, refer to [this section](../../automating/using/load-file.md).
   * この **[!UICONTROL Transfer file]** アクティビティを使用すると、ファイルの受信や送信、ファイルの存在のテスト、Adobe Campaign内のリストファイルの送信が可能です。 外部ソースからファイルを取得する必要がある場合 **[!UICONTROL Load file]** に備えて、このアクティビティを外部ソースの前に使用できます。 For more on how to use this activity, refer to [this section](../../automating/using/transfer-file.md).

読み込みプロセスを設計する際は、必要に応じて適応できるワークフローテンプレートを使用することをお勧めします。 データをインポートするワークフローテンプレートの設定方法について詳しくは、 [この使用例を参照してください](../../automating/using/creating-import-workflow-templates.md)。

また、Adobe Campaignは、 **インポートテンプレートの設計で構成される、簡単な定期的な読み込みの実行方法をオファーします**。 インポートテンプレートは、専用のワークフローテンプレートで、専用の画面から利用できます。 設計が完了すると、読み込みを実行するユーザは、読み込むファイルを簡単な表示でアップロードするだけで済みます。

**関連トピック**：

* [インポートテンプレートを使用したデータのインポート](../../automating/using/importing-data-with-import-templates.md)
* [インポートテンプレートの定義](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [パッケージの管理](../../automating/using/managing-packages.md)
