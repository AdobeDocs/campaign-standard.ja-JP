---
solution: Campaign Standard
product: campaign
title: プロセスとデータ管理の概要
description: ワークフローを使用すれば、データおよびオーディエンスの管理やメッセージの送信などのプロセスを自動化できます。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 14%

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

## ワークフローアクティビティ{#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

ワークフローのデザインに役立つ様々なアクティビティが用意されています。

[ターゲット](../../automating/using/about-targeting-activities.md) アクティビティを使用すると、セットを定義し、交差、和集合または除外操作を使用してセットを分割または組み合わせることで、1つ以上のターゲットを作成できます。

[実行アクティビティ](../../automating/using/about-execution-activities.md)を使用して、ワークフローとそのアクティビティを調整します。一方、[チャネルアクティビティ](../../automating/using/about-channel-activities.md)を使用すると、Campaign Standard通信チャネルを組み合わせて、チャネル間のワークフローを作成できます。

最後に、[データ管理アクティビティ](../../automating/using/about-data-management-activities.md)を使用して、データベースのデータを操作できます。

詳しくは、以下を参照してください。

* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [ワークフローの実行](../../automating/using/about-workflow-execution.md)
* [ワークフローのベストプラクティス](../../automating/using/best-practices-workflows.md)

## データをフィルター {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

**クエリエディター**&#x200B;を使用して、データベースのデータをフィルターし、受信者のターゲットを高めるために母集団を構築します。 クエリエディターでは、Campaign Standardで次のいくつかの操作を実行できます。クエリタイプオーディエンスを作成し、配信ターゲットまたはワークフローアクティビティ内の母集団を定義します。

クエリエディターには、すばやく簡単にフィルタリングできる&#x200B;**定義済みフィルターとルール**&#x200B;が付属しています。 ただし、**高度な式編集**&#x200B;機能を使用することもできます。 これにより、手動で条件を入力し、関数を使用して独自のルールを作成できます。

詳しくは、以下を参照してください。

* [クエリの編集](../../automating/using/editing-queries.md)
* [高度な式の編集](../../automating/using/advanced-expression-editing.md)
* [関数のリスト](../../automating/using/list-of-functions.md)

## データのインポート/エクスポート{#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standardには、データのインポートとエクスポートを行う&#x200B;**データ管理機能**&#x200B;がいくつか用意されています。

[ワークフローデータ管理](../../automating/using/about-data-management-activities.md) アクティビティでは、データの読み込み、フィールドに対する一括更新、ファイルの受信と送信、または未識別のデータの既存のリソースへのリンクを行うことができます。

[インポートテンプレート](../../automating/using/importing-data-with-import-templates.md)を使って、管理者が定義した特定の種類のインポートを、シンプル化されたインポート機能で管理します。

[ログをエクス](../../automating/using/exporting-logs.md) ポートすると、簡単なワークフローでログデータをエクスポートでき、独自のレポートまたはBIツールでマーケティングキャンペーンの結果を分析できます。

[パッケージ](../../automating/using/managing-packages.md)を活用して、異なるキャンペーンインスタンス間でリソースを交換します。例えば、インスタンスの構成を複製したり、カスタムリソースを含む別のサーバーにデータを転送したりします。

最後に、[リストのエクスポート](../../automating/using/exporting-lists.md)では、テストプロファイルのリスト、強制隔離の電子メールアドレスのリストなど、Campaign Standardから任意のリストをエクスポートできます。

詳しくは、以下を参照してください。

* [データのインポートおよびエクスポート](../../automating/using/about-data-import-and-export.md)
* [使用例：カスタムリソースのエクスポート／インポート](../../automating/using/exporting-importing-custom-resources.md)

## その他のリソース

* [プロセスとデータ管理のチュートリアルビデオ](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [Campaign Standard データモデルの概要](../../developing/using/get-started-data-model.md)
