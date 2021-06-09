---
solution: Campaign Standard
product: campaign
title: プロセスとデータ管理の概要
description: ワークフローを使用すれば、データおよびオーディエンスの管理やメッセージの送信などのプロセスを自動化できます。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: ワークフロー
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 7808aea42f417994a61fdde84a44299c0954b346
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 41%

---

# プロセスとデータ管理の概要 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">ワークフローアクティビティ</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">ユースケース</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">データのフィルタリング</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">データのインポート/エクスポート</a></p></td></tr>
</table>

Adobe Campaign は、セグメント化、キャンペーン実行、ファイル処理などの複雑なプロセスを設計できる包括的なグラフィカル環境を提供します。 例えば、ワークフローを使用して、サーバーからファイルをダウンロードした後、ファイルを解凍し、ファイル内のレコードを Adobe Campaign データベースに読み込むことができます。

ワークフローには、ユーザーにタスクを割り当てたり、実行されたタスクを承認させることによって、ユーザーの関与を促すこともできます。 つまり、1 人または複数のユーザーにタスクを割り当ててコンテンツで作業したり、ターゲットを指定したり、メッセージを送信する前に証明を承認したりできます。

ワークフローは、次のように異なるコンテキストで使用できます。

* オーディエンスを管理したり、メッセージを送信したりするためのターゲティング。
* データを操作するためのデータ管理（ETL）。
* Campaign データベースへのデータの読み込み。
* データベースのクリーンアップ、トラッキング情報の復元などの技術的プロセス。

## ワークフローアクティビティ {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

ワークフローの設計に役立つ様々なアクティビティを利用できます。

[ターゲテ](../../automating/using/about-targeting-activities.md) ィングアクティビティを使用すると、セットを定義し、積集合、和集合、除外の各操作を使用して分割または組み合わせることで、1つ以上のターゲットを作成できます。

[Campaign Standardアクティビティ](../../automating/using/about-execution-activities.md)では、ワークフローとそのアクティビティを調整し、[チャネルアクティビティ](../../automating/using/about-channel-activities.md)では、実行通信チャネルを組み合わせてクロスチャネルワークフローを作成できます。

最後に、[データ管理アクティビティ](../../automating/using/about-data-management-activities.md)を使用して、データベースのデータを操作できます。

詳しくは、以下を参照してください。

* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [ワークフローの実行](../../automating/using/about-workflow-execution.md)
* [ワークフローのベストプラクティス](../../automating/using/best-practices-workflows.md)

## データのフィルタリング {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

**クエリエディター**&#x200B;を利用して、データベースのデータをフィルターし、母集団を作成して受信者のターゲティングを向上させます。 クエリエディターを使用して、次の複数のアクションをCampaign Standardで実行できます。ワークフローアクティビティで、クエリタイプのオーディエンスを作成、配信ターゲットまたは母集団を定義します。

クエリエディターには、すばやく簡単にフィルタリングできる&#x200B;**定義済みフィルターとルール**&#x200B;が付属しています。 ただし、**高度な式編集**&#x200B;機能を使用することもできます。 これにより、条件を手動で入力し、関数を使用して独自のルールを作成できます。

詳しくは、以下を参照してください。

* [クエリの編集](../../automating/using/editing-queries.md)
* [高度な式の編集](../../automating/using/advanced-expression-editing.md)
* [関数のリスト](../../automating/using/list-of-functions.md)

## データのインポート/エクスポート{#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standardには、データのインポートおよびエクスポートをおこなう&#x200B;**データ管理機能**&#x200B;がいくつか用意されています。

[ワークフローのデータ管](../../automating/using/about-data-management-activities.md) 理アクティビティを使用すると、データのインポート、フィールドに対する一括更新の実行、ファイルの受信または送信、不明なデータの既存のリソースへのリンクをおこなうことができます。

[インポートテンプレート](../../automating/using/importing-data-with-import-templates.md)を使用すると、管理者が定義した特定のタイプのインポートを、シンプルなインポート機能によって管理できます。

[ログをエ](../../automating/using/exporting-logs.md) クスポートすると、シンプルなワークフローでログデータをエクスポートでき、独自のレポートまたはBIツールでマーケティングキャンペーンの結果を分析できます。

[パッケージ](../../automating/using/managing-packages.md)を活用して、異なるキャンペーンインスタンス間でリソースを交換します。例えば、インスタンスの設定をレプリケートしたり、カスタムリソースを含むサーバー間でデータを転送したりします。

最後に、[リスト](../../automating/using/exporting-lists.md)を書き出すことで、Campaign Standardから任意のリストを書き出すことができます（例えば、テストプロファイルのリスト、強制隔離Eメールアドレスのリストなど）。

詳しくは、以下を参照してください。

* [データのインポートおよびエクスポート](../../automating/using/about-data-import-and-export.md)
* [使用例：カスタムリソースのエクスポート／インポート](../../automating/using/exporting-importing-custom-resources.md)

## その他のリソース

* [プロセスとデータ管理のチュートリアルビデオ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=ja)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [Campaign Standard データモデルの概要](../../developing/using/get-started-data-model.md)
