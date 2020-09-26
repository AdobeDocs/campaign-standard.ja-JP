---
title: プロセスとデータ管理の概要
description: ワークフローを使用してプロセスを自動化し、データとオーディエンスを管理し、メッセージを送信するなど、様々な機能を備えています。
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5636b2ab5a673b0a52158b1a5411e090e4b45ca7
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 9%

---


# プロセスとデータ管理の概要 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">ワークフローアクティビティ</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">使用例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">データをフィルター</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">データの読み込み/書き出し</a></p></td></tr>
</table>

Adobe Campaignオファーは、セグメント化、キャンペーン実行、ファイル処理などの複雑なプロセスを設計できる包括的なグラフィカル環境です。 例えば、ワークフローを使用して、サーバーからファイルをダウンロードし、圧縮を解除してから、そのレコードをAdobe Campaignデータベースにインポートできます。

ワークフローには、ユーザーを割り当てたり、実行されたタスクをタスクに承認させたりすることで、ユーザーを関与させることもできます。 つまり、1人または複数のタスクに対して、コンテンツの操作やターゲットの指定を行ったり、配達確認を承認した後でメッセージを送信したりできます。

ワークフローは、次のように異なるコンテキストで使用できます。

* オーディエンスの管理やメッセージの送信のターゲット設定です。
* データ管理(ETL)を使用してデータを操作します。
* キャンペーンデータベースにデータをインポートしています。
* データベースのクリーンアップ、追跡情報の回復などの技術的なプロセス

## ワークフローアクティビティ {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

ワークフローのデザインに役立つ様々なアクティビティが用意されています。

[ターゲット設定のアクティビティ](../../automating/using/about-targeting-activities.md) を使用すると、セットを定義し、交差、和集合または除外の演算を使用してセットを分割または組み合わせることで、1つ以上のターゲットを作成できます。

実 [行アクティビティを使用して、ワークフローとそのアクティビティを調整します](../../automating/using/about-execution-activities.md)。一方、 [](../../automating/using/about-channel-activities.md) チャネルアクティビティを使用すると、Campaign Standard通信チャネルを組み合わせて、チャネル間のワークフローを作成できます。

最後に、 [データ管理アクティビティ](../../automating/using/about-data-management-activities.md) (Database Data Management)を使用して、データベースのデータを操作できます。

詳しくは、以下を参照してください。

* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [ワークフローの実行](../../automating/using/about-workflow-execution.md)
* [ワークフローのベストプラクティス](../../automating/using/best-practices-workflows.md)

## データをフィルター {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

データベースからデータをフィルターし、 **クエリのターゲットを高めるための母集団を作成するには、受信者エディターを使用します** 。 クエリエディターでは、Campaign Standardで次のいくつかの操作を実行できます。クエリタイプオーディエンスを作成し、配信ターゲットまたはワークフローアクティビティ内の母集団を定義します。

クエリエディターには、すばやく簡単にフィルタリングできる **定義済みフィルターとルールが付属しています** 。 ただし、 **高度な式編集** 機能を使用することもできます。 これにより、手動で条件を入力し、関数を使用して独自のルールを作成できます。

詳しくは、以下を参照してください。

* [クエリの編集](../../automating/using/editing-queries.md)
* [高度な式の編集](../../automating/using/advanced-expression-editing.md)
* [関数のリスト](../../automating/using/list-of-functions.md)

## データの読み込み/書き出し {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standardには、データの読み込みと書き出しを行う **データ管理機能がいくつか用意されています** 。

[ワークフローデータ管理アクティビティ](../../automating/using/about-data-management-activities.md) ：データの読み込み、フィールドの一括更新、ファイルの受信と送信、または未識別のデータを既存のリソースにリンクすることができます。

[インポートテンプレートを使用して](../../automating/using/importing-data-with-import-templates.md)、管理者が定義した特定のタイプのインポートを、シンプル化されたインポート機能を使用して管理します。

[ログのエクスポートを使用すると](../../automating/using/exporting-logs.md) 、簡単なワークフローでログデータをエクスポートでき、独自のレポートまたはBIツールでマーケティングキャンペーンの結果を分析できます。

「 [パッケージ](../../automating/using/managing-packages.md) 」を使用して、異なるキャンペーンインスタンス間でリソースを交換します。例えば、インスタンスの設定を複製したり、カスタムリソースを含むサーバー間でデータを転送したりします。

最後に、 [リストを](../../automating/using/exporting-lists.md) エクスポートすると、Campaign Standardから任意のリスト(テストプロファイルのリスト、強制隔離の電子メールアドレスのリストなど)をエクスポートできます。

詳しくは、以下を参照してください。

* [データのインポートおよびエクスポート](../../automating/using/about-data-import-and-export.md)
* [使用例：カスタムリソースのエクスポート／インポート](../../automating/using/exporting-importing-custom-resources.md)

## その他のリソース

* [プロセスとデータ管理のチュートリアルビデオ](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [Campaign Standard データモデルの概要](../../developing/using/get-started-data-model.md)
